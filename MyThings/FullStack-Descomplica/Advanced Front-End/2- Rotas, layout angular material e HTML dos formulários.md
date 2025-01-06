
# Guia de Estudos: Configuração de Rotas e Layout com Angular Material

## Objetivos da Aula

- Aprender o básico sobre configuração de rotas no Angular.
- Explorar o uso do Angular Material para construir layouts responsivos.
- Conhecer componentes prontos fornecidos pelo Angular Material.

---

## Introdução ao Angular Material

O Angular Material é uma biblioteca baseada no Material Design do Google, projetada para facilitar a criação de aplicações responsivas e com foco em dispositivos mobile. Ela oferece uma série de componentes estilizados que ajudam a acelerar o desenvolvimento de sistemas.

### Principais Características:

- **Mobile First**: Projetado para funcionar bem em dispositivos móveis.
- **Componentes Reutilizáveis**: Uma ampla gama de elementos, como botões, tabelas, sliders, é fornecida para utilização.
- **Baseado no Material Design**: Alinha-se às diretrizes de design do Google, garantindo um visual moderno e consistente.

### Referência:

Mais informações estão disponíveis na documentação oficial: [Angular Material Components](https://material.angular.io/components/categories)

---

## Configuração de Rotas

No Angular, as rotas são configuradas utilizando o módulo `RouterModule`. Abaixo, segue um exemplo simples de como configurar rotas na aplicação:

```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { ProductFormComponent } from './product-form/product-form.component';

const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'product', component: ProductFormComponent },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule {}
```

- **HomeComponent**: Página inicial para listagem de produtos.
- **ProductFormComponent**: Formulário de cadastro de produtos.

Essa configuração inicial permite navegar entre diferentes partes da aplicação.

---

## Construção de Layouts com Angular Material

### Instalação do Angular Material

Para adicionar o Angular Material ao seu projeto, use o comando abaixo:

```bash
ng add @angular/material
```

Esse comando também configura o tema padrão e adiciona o pacote de animações necessário.

### Exemplo de Layout Básico

Abaixo está um exemplo de layout utilizando o `MatToolbar` e o `MatSidenav`:

```html
<mat-sidenav-container>
  <mat-sidenav mode="side" opened>
    <mat-nav-list>
      <a mat-list-item routerLink="/">Home</a>
      <a mat-list-item routerLink="/product">Cadastro de Produtos</a>
    </mat-nav-list>
  </mat-sidenav>

  <mat-sidenav-content>
    <mat-toolbar color="primary">
      <span>Minha Aplicação</span>
    </mat-toolbar>
    <div class="content">
      <router-outlet></router-outlet>
    </div>
  </mat-sidenav-content>
</mat-sidenav-container>
```

### Formulário com Angular Material

O exemplo abaixo demonstra um formulário básico para cadastro de produtos:

```html
<form class="product-form" [formGroup]="productForm">
  <mat-form-field appearance="fill">
    <mat-label>Nome do Produto</mat-label>
    <input matInput formControlName="name">
  </mat-form-field>

  <mat-form-field appearance="fill">
    <mat-label>Descrição</mat-label>
    <textarea matInput formControlName="description"></textarea>
  </mat-form-field>

  <mat-form-field appearance="fill">
    <mat-label>Preço</mat-label>
    <input matInput type="number" formControlName="price">
  </mat-form-field>

  <button mat-raised-button color="primary" type="submit">Salvar</button>
</form>
```

### Estilização com SCSS

```scss
.product-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 400px;
  margin: auto;
}
```

---

## Frameworks Alternativos

### NG Bootstrap

O NG Bootstrap oferece componentes baseados no Bootstrap para Angular. Ele é uma boa opção para quem já está familiarizado com o Bootstrap.

Link oficial: [NG Bootstrap](https://ng-bootstrap.github.io/#/home)

### IONIC

O Ionic permite criar aplicações multiplataforma (Web, Android e iOS) utilizando Angular. É amplamente utilizado para aplicações mobile-first.

Link oficial: [IONIC Framework](https://ionicframework.com/)

---

## Exercícios Práticos

1. Crie uma aplicação Angular com as seguintes rotas:
    
    - Página inicial (listagem de produtos).
    - Formulário de cadastro de produtos.
2. Utilize componentes do Angular Material como:
    
    - `MatTable` para listagem de produtos.
    - `MatDialog` para modais de confirmação.
3. Experimente usar o tema escuro fornecido pelo Angular Material e personalize as cores principais.
    

---

## Conteúdo Bônus

Explore as diferenças entre os frameworks apresentados:

- **Angular Material**: Melhor para aplicações Angular com foco no Material Design.
- **NG Bootstrap**: Ideal para projetos que migraram do Bootstrap para Angular.
- **Ionic**: Recomendado para projetos mobile-first com suporte multiplataforma.

---

## Referências

- [Angular IO](https://angular.io/)
- [Angular Material](https://material.angular.io/)
- [IONIC Framework](https://ionicframework.com/)
- [NG Bootstrap](https://ng-bootstrap.github.io/#/home)

Com esses conceitos, você está pronto para começar a construir aplicações robustas utilizando Angular, Angular Material e boas práticas de desenvolvimento!