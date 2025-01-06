
# Manipulando Dados JSON com Angular e TypeScript

## Introdução

JSON (JavaScript Object Notation) é uma das formas mais populares de serializar e transferir dados em aplicações front-end e back-end. No Angular, trabalhar com JSON envolve a manipulação de dados estruturados em forma de objetos, listas, strings e números para exibição ou processamento.

Nesta aula, exploraremos como:

- Manipular dados JSON.
- Utilizar services para gerenciar comunicações com APIs.
- Criar uma FAKE API com o JSON Server.
- Trabalhar com uma REST API para implementar um CRUD simples.

Vamos iniciar com um exemplo básico e, em seguida, aprofundar o tema com aplicações práticas.

---

## Configuração Inicial

Crie uma nova aplicação Angular ou utilize uma existente. Certifique-se de que o Angular CLI esteja instalado:

```bash
npm install -g @angular/cli
ng new manipulando-json
cd manipulando-json
```

### Adicionando o JSON para Manipulação

Na pasta `src/app`, crie um arquivo chamado `students.json` com o seguinte conteúdo:

```json
[
  { "id": 1, "name": "Maria Silva", "age": 22 },
  { "id": 2, "name": "João Souza", "age": 24 },
  { "id": 3, "name": "Ana Costa", "age": 21 }
]
```

Altere o arquivo `angular.json` para permitir o acesso ao arquivo JSON local:

```json
"assets": [
  "src/assets",
  "src/app/students.json"
]
```

---

## Criando o Componente

Gere um componente chamado `manipulando-json`:

```bash
ng g component manipulando-json
```

No arquivo `manipulando-json.component.ts`, adicione a interface e importe o JSON:

```typescript
import { Component, OnInit } from '@angular/core';
import studentsData from '../students.json';

interface Student {
  id: number;
  name: string;
  age: number;
}

@Component({
  selector: 'app-manipulando-json',
  templateUrl: './manipulando-json.component.html',
  styleUrls: ['./manipulando-json.component.css']
})
export class ManipulandoJsonComponent implements OnInit {
  students: Student[] = [];

  ngOnInit(): void {
    this.students = studentsData;
    console.log(this.students);
  }
}
```

No arquivo HTML do componente, use a diretiva `*ngFor` para exibir os dados:

```html
<div *ngFor="let student of students">
  <p>ID: {{ student.id }} - Nome: {{ student.name }} - Idade: {{ student.age }}</p>
</div>
```

---

## Trabalhando com JSON Server

O JSON Server é uma ferramenta simples para simular uma REST API com base em um arquivo JSON.

### Instalação

```bash
npm install -g json-server
```

### Configuração do JSON Server

Crie um arquivo `db.json` na raiz do projeto com o seguinte conteúdo:

```json
{
  "students": [
    { "id": 1, "name": "Maria Silva", "age": 22 },
    { "id": 2, "name": "João Souza", "age": 24 },
    { "id": 3, "name": "Ana Costa", "age": 21 }
  ]
}
```

Inicie o servidor:

```bash
json-server --watch db.json
```

A REST API estará acessível em: `http://localhost:3000/students`.

---

## Criando um Service Angular

Gere um service chamado `students`:

```bash
ng g service services/students
```

No arquivo `students.service.ts`, adicione as funções para consumir a API:

```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

interface Student {
  id: number;
  name: string;
  age: number;
}

@Injectable({
  providedIn: 'root'
})
export class StudentsService {
  private apiUrl = 'http://localhost:3000/students';

  constructor(private http: HttpClient) {}

  getStudents(): Observable<Student[]> {
    return this.http.get<Student[]>(this.apiUrl);
  }

  addStudent(student: Student): Observable<Student> {
    return this.http.post<Student>(this.apiUrl, student);
  }

  deleteStudent(id: number): Observable<void> {
    return this.http.delete<void>(`${this.apiUrl}/${id}`);
  }
}
```

No componente, use o service para consumir os dados:

```typescript
import { Component, OnInit } from '@angular/core';
import { StudentsService } from '../services/students.service';

@Component({
  selector: 'app-manipulando-json',
  templateUrl: './manipulando-json.component.html',
  styleUrls: ['./manipulando-json.component.css']
})
export class ManipulandoJsonComponent implements OnInit {
  students: any[] = [];

  constructor(private studentsService: StudentsService) {}

  ngOnInit(): void {
    this.studentsService.getStudents().subscribe(data => {
      this.students = data;
    });
  }

  addStudent(): void {
    const newStudent = { id: 4, name: 'Novo Aluno', age: 20 };
    this.studentsService.addStudent(newStudent).subscribe(student => {
      this.students.push(student);
    });
  }
}
```

No HTML, adicione um botão para criar novos estudantes:

```html
<button (click)="addStudent()">Adicionar Estudante</button>
<div *ngFor="let student of students">
  <p>ID: {{ student.id }} - Nome: {{ student.name }} - Idade: {{ student.age }}</p>
</div>
```

---

## Tópicos Avançados

### Autenticação e Autorização

Estude sobre JWT (JSON Web Tokens) para proteger suas APIs.

### GraphQL

Explore como o GraphQL oferece uma abordagem mais flexível em comparação ao REST.

### Firebase

Use o Firebase como uma solução de backend-as-a-service para armazenar dados JSON.

---

Com essa base, você já consegue criar aplicações robustas e dinâmicas com Angular e JSON!


_______________
___________________


A funcionalidade principal do arquivo **service** no Angular é **manipular dados de forma global para todos os componentes de um determinado módulo**, geralmente sendo utilizado para acessar uma API, compartilhar lógica de negócios ou realizar operações assíncronas, como chamadas HTTP.

Exemplo de serviço que acessa uma API:

```typescript
@Injectable({
  providedIn: 'root',
})
export class DataService {
  constructor(private http: HttpClient) {}

  getData() {
    return this.http.get('https://api.exemplo.com/dados');
  }
}
```

Esse serviço pode ser injetado em qualquer componente ou outro serviço do módulo.
