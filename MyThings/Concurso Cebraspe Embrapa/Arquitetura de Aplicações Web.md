

---

### **MVC (Model-View-Controller)**

#### **O que é?**

O MVC é um padrão de arquitetura de software usado para organizar e estruturar aplicações. Ele separa a lógica da aplicação em três componentes principais:

1. **Model (Modelo):**
    - Representa os dados e as regras de negócio.
    - Lida com a manipulação e consulta dos dados, geralmente interagindo com um banco de dados.
    - Exemplo:
        
        ```javascript
        class UserModel {
            constructor(name, email) {
                this.name = name;
                this.email = email;
            }
        
            save() {
                // Simulação de salvar no banco
                console.log(`${this.name} foi salvo no banco!`);
            }
        }
        ```
        
2. **View (Visão):**
    - Responsável pela apresentação da interface ao usuário.
    - Exibe dados vindos do `Model` e recebe interações do usuário.
    - Exemplo:
        
        ```html
        <div id="user">
            <h1>Nome do Usuário: {{name}}</h1>
            <p>Email: {{email}}</p>
        </div>
        ```
        
3. **Controller (Controlador):**
    - Intermediário entre o `Model` e a `View`.
    - Recebe inputs do usuário via `View`, processa (ou delega ao `Model`) e retorna a resposta para a `View`.
    - Exemplo:
        
        ```javascript
        const userController = {
            createUser(req, res) {
                const user = new UserModel(req.body.name, req.body.email);
                user.save();
                res.send('Usuário criado com sucesso!');
            }
        }
        ```
        

#### **Fluxo de Dados no MVC**

1. A **View** recebe uma interação do usuário.
2. A interação é processada pelo **Controller**.
3. O **Controller** comunica-se com o **Model** para manipular os dados.
4. Os dados atualizados são enviados de volta à **View** para exibição.

---

### **Monólitos vs. Microservices**

#### **Monólito**

- **Definição**: Um sistema monolítico é uma aplicação única e indivisível. Todos os componentes (front-end, back-end, lógica de negócio, banco de dados) estão integrados em um único projeto.
- **Características**:
    - Foco em simplicidade.
    - Código centralizado.
    - Boa para projetos menores ou equipes pequenas.
- **Exemplo**:
    - Uma aplicação e-commerce onde o gerenciamento de produtos, carrinho e pedidos está em um único código-base.
- **Vantagens**:
    - Simples de desenvolver e implantar.
    - Ideal para projetos iniciais.
- **Desvantagens**:
    - Dificuldade em escalar partes individuais.
    - Problemas em manutenção e atualizações (qualquer mudança exige deploy do sistema inteiro).

#### **Microservices**

- **Definição**: Abordagem onde a aplicação é dividida em vários serviços pequenos e independentes, cada um com uma funcionalidade específica.
    
- **Características**:
    
    - Cada serviço tem seu próprio banco de dados e lógica.
    - Comunicação entre serviços via APIs (REST, GraphQL, etc.).
- **Exemplo**:
    
    - O mesmo e-commerce, mas agora o gerenciamento de produtos, carrinho e pedidos são serviços separados.
- **Vantagens**:
    
    - Escalabilidade independente para cada serviço.
    - Menor impacto de falhas.
- **Desvantagens**:
    
    - Maior complexidade na comunicação e gerenciamento.
    - Requer maior esforço de desenvolvimento inicial.

---

### **Comunicação entre serviços: REST e GraphQL**

#### **REST (Representational State Transfer)**

- **Definição**: Arquitetura de comunicação entre sistemas baseada em recursos (ex.: usuários, produtos).
- **Características**:
    - Cada recurso é identificado por uma URL.
    - Usa métodos HTTP (GET, POST, PUT, DELETE) para realizar operações.
- **Exemplo**:
    - **GET `/products`**: Retorna todos os produtos.
    - **POST `/products`**: Cria um novo produto.
- **Vantagens**:
    - Simplicidade e padronização.
    - Largamente adotado.
- **Desvantagens**:
    - Overfetching: Retorna mais dados do que o necessário.
    - Underfetching: Pode exigir múltiplas requisições para obter todos os dados.

#### **GraphQL**

- **Definição**: Linguagem de consulta para APIs que permite ao cliente especificar exatamente quais dados deseja.
- **Características**:
    - Em vez de múltiplas URLs, tudo é acessado por um único endpoint.
    - Consultas são personalizadas.
- **Exemplo**:
    
    ```graphql
    {
        product(id: "1") {
            name
            price
            category {
                name
            }
        }
    }
    ```
    
    - Retorna exatamente os campos solicitados.
- **Vantagens**:
    - Evita overfetching e underfetching.
    - Ideal para aplicações com dados complexos.
- **Desvantagens**:
    - Complexidade maior para configurar e gerenciar.
    - Sobrecarga em consultas mal otimizadas.

---

Com esses conceitos, você pode entender a arquitetura de sistemas e como os serviços se comunicam, além de escolher abordagens ideais para diferentes cenários no desenvolvimento de aplicações.

____________________
____________________

```javascript

// Estrutura da API seguindo o padrão MVC

// ===================
// Modelo (Model)
// ===================
const mongoose = require('mongoose');

const tarefaSchema = new mongoose.Schema({
    titulo: { type: String, required: true },
    concluida: { type: Boolean, default: false }
});

const Tarefa = mongoose.model('Tarefa', tarefaSchema);

module.exports = Tarefa;

// ===================
// Controlador (Controller)
// ===================
const Tarefa = require('../models/Tarefa');

const tarefaController = {
    listar: async (req, res) => {
        try {
            const tarefas = await Tarefa.find();
            res.status(200).json(tarefas);
        } catch (err) {
            res.status(500).json({ erro: 'Erro ao listar tarefas' });
        }
    },

    criar: async (req, res) => {
        try {
            const { titulo } = req.body;
            const novaTarefa = new Tarefa({ titulo });
            await novaTarefa.save();
            res.status(201).json(novaTarefa);
        } catch (err) {
            res.status(500).json({ erro: 'Erro ao criar tarefa' });
        }
    },

    atualizar: async (req, res) => {
        try {
            const { id } = req.params;
            const { titulo, concluida } = req.body;
            const tarefaAtualizada = await Tarefa.findByIdAndUpdate(
                id,
                { titulo, concluida },
                { new: true }
            );
            if (!tarefaAtualizada) {
                return res.status(404).json({ erro: 'Tarefa não encontrada' });
            }
            res.status(200).json(tarefaAtualizada);
        } catch (err) {
            res.status(500).json({ erro: 'Erro ao atualizar tarefa' });
        }
    },

    deletar: async (req, res) => {
        try {
            const { id } = req.params;
            const tarefaDeletada = await Tarefa.findByIdAndDelete(id);
            if (!tarefaDeletada) {
                return res.status(404).json({ erro: 'Tarefa não encontrada' });
            }
            res.status(200).json({ mensagem: 'Tarefa deletada com sucesso' });
        } catch (err) {
            res.status(500).json({ erro: 'Erro ao deletar tarefa' });
        }
    }
};

module.exports = tarefaController;

// ===================
// Rotas (View)
// ===================
const express = require('express');
const tarefaController = require('../controllers/tarefaController');
const router = express.Router();

router.get('/tarefas', tarefaController.listar);
router.post('/tarefas', tarefaController.criar);
router.put('/tarefas/:id', tarefaController.atualizar);
router.delete('/tarefas/:id', tarefaController.deletar);

module.exports = router;

// ===================
// App Principal
// ===================
const express = require('express');
const mongoose = require('mongoose');
const tarefaRoutes = require('./routes/tarefaRoutes');

const app = express();
app.use(express.json());
app.use('/api', tarefaRoutes);

const PORT = 3000;
const MONGO_URI = 'mongodb://localhost:27017/tarefasDB';

mongoose.connect(MONGO_URI, { useNewUrlParser: true, useUnifiedTopology: true })
    .then(() => {
        console.log('Conectado ao MongoDB');
        app.listen(PORT, () => console.log(`Servidor rodando na porta ${PORT}`));
    })
    .catch(err => console.error('Erro ao conectar ao MongoDB:', err));


```



A API foi reorganizada para seguir o padrão MVC:

1. **Model (Modelo)**: Define a estrutura e a lógica do banco de dados para as tarefas. Aqui utilizamos o MongoDB com Mongoose.
2. **Controller (Controlador)**: Centraliza a lógica da aplicação, manipulando os dados recebidos do Model e enviando as respostas apropriadas para as rotas.
3. **View (Rotas)**: Fornece os pontos de entrada da API, definindo como as requisições HTTP interagem com o controlador.

### Como testar:

1. **Iniciar o MongoDB**: Certifique-se de que o serviço MongoDB está rodando.
2. **Instalar dependências**:
    
    ```bash
    npm install express mongoose
    ```
    
3. **Executar a aplicação**:
    
    ```bash
    node app.js
    ```
    
4. **Testar com ferramentas como Postman ou curl**:
    - Listar tarefas: `GET http://localhost:3000/api/tarefas`
    - Criar tarefa: `POST http://localhost:3000/api/tarefas` com JSON `{ "titulo": "Nova Tarefa" }`
    - Atualizar tarefa: `PUT http://localhost:3000/api/tarefas/:id` com JSON `{ "titulo": "Atualizado", "concluida": true }`
    - Deletar tarefa: `DELETE http://localhost:3000/api/tarefas/:id`