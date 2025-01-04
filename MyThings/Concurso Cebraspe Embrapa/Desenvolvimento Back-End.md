
Abaixo está o guia detalhado para criar uma API REST que gerencie uma lista de tarefas usando **Node.js**, **Express**, e **SQLite** para o armazenamento. O exemplo será didático, abordando cada etapa com explicações.

---

## **1. Preparação do Ambiente**

### **Instale as ferramentas necessárias:**

1. **Node.js e npm**: Certifique-se de que estão instalados. Verifique com:
    
    ```bash
    node -v
    npm -v
    ```
    
2. **Editor de Código**: Use o VS Code ou outro de sua preferência.

---

## **2. Configurando o Projeto**

1. **Crie o diretório do projeto:**
    
    ```bash
    mkdir task-manager-api
    cd task-manager-api
    ```
    
2. **Inicialize o projeto com npm:**
    
    ```bash
    npm init -y
    ```
    
    Isso criará um arquivo `package.json` básico.
    
3. **Instale as dependências:**
    
    ```bash
    npm install express sqlite3 sequelize body-parser
    ```
    
    - **Express**: Framework para gerenciar rotas e requisições HTTP.
    - **SQLite3**: Banco de dados leve e integrado.
    - **Sequelize**: ORM para simplificar o acesso ao banco.
    - **Body-parser**: Processa requisições JSON.

---

## **3. Estrutura do Projeto**

Organize os arquivos assim:

```
task-manager-api/
├── node_modules/
├── config/
│   └── database.js
├── models/
│   └── Task.js
├── routes/
│   └── tasks.js
├── app.js
├── package.json
```

---

## **4. Configuração do Banco de Dados (SQLite)**

1. **Crie o arquivo `config/database.js`:**
    
    ```javascript
    const { Sequelize } = require('sequelize');
    
    const sequelize = new Sequelize({
        dialect: 'sqlite',
        storage: './tasks.sqlite' // Banco será armazenado aqui
    });
    
    module.exports = sequelize;
    ```
    
2. **Defina o modelo de tarefas em `models/Task.js`:**
    
    ```javascript
    const { DataTypes } = require('sequelize');
    const sequelize = require('../config/database');
    
    const Task = sequelize.define('Task', {
        title: {
            type: DataTypes.STRING,
            allowNull: false,
        },
        completed: {
            type: DataTypes.BOOLEAN,
            defaultValue: false,
        },
    });
    
    module.exports = Task;
    ```
    
    - **`title`**: Nome da tarefa.
    - **`completed`**: Status (padrão: `false`).
3. **Sincronize o banco em `app.js`:**
    
    ```javascript
    const sequelize = require('./config/database');
    const Task = require('./models/Task');
    
    sequelize.sync({ force: true }) // Apaga e recria tabelas (somente para desenvolvimento)
        .then(() => console.log('Database synced'))
        .catch(err => console.error(err));
    ```
    

---

## **5. Criando a API REST**

1. **Configuração principal (`app.js`):**
    
    ```javascript
    const express = require('express');
    const bodyParser = require('body-parser');
    const taskRoutes = require('./routes/tasks');
    
    const app = express();
    const PORT = 3000;
    
    // Middleware para JSON
    app.use(bodyParser.json());
    
    // Rotas
    app.use('/tasks', taskRoutes);
    
    // Inicia o servidor
    app.listen(PORT, () => {
        console.log(`Server running on http://localhost:${PORT}`);
    });
    ```
    

---

2. **Rotas para Tarefas (`routes/tasks.js`):**
    
    ```javascript
    const express = require('express');
    const Task = require('../models/Task');
    const router = express.Router();
    
    // Listar todas as tarefas
    router.get('/', async (req, res) => {
        const tasks = await Task.findAll();
        res.json(tasks);
    });
    
    // Criar uma nova tarefa
    router.post('/', async (req, res) => {
        const { title } = req.body;
        const newTask = await Task.create({ title });
        res.status(201).json(newTask);
    });
    
    // Atualizar uma tarefa
    router.put('/:id', async (req, res) => {
        const { id } = req.params;
        const { title, completed } = req.body;
    
        const task = await Task.findByPk(id);
        if (!task) return res.status(404).json({ error: 'Task not found' });
    
        task.title = title !== undefined ? title : task.title;
        task.completed = completed !== undefined ? completed : task.completed;
        await task.save();
    
        res.json(task);
    });
    
    // Excluir uma tarefa
    router.delete('/:id', async (req, res) => {
        const { id } = req.params;
    
        const task = await Task.findByPk(id);
        if (!task) return res.status(404).json({ error: 'Task not found' });
    
        await task.destroy();
        res.status(204).send();
    });
    
    module.exports = router;
    ```
    

---

## **6. Testando a API**

1. **Inicie o servidor:**
    
    ```bash
    node app.js
    ```
    
2. **Endpoints disponíveis:**
    
    - **GET `/tasks`**: Lista todas as tarefas.
    - **POST `/tasks`**: Cria uma nova tarefa.
        
        ```json
        { "title": "Estudar Node.js" }
        ```
        
    - **PUT `/tasks/:id`**: Atualiza uma tarefa.
        
        ```json
        { "title": "Estudar Node.js e Express", "completed": true }
        ```
        
    - **DELETE `/tasks/:id`**: Exclui uma tarefa.
3. **Testes**: Use ferramentas como **Postman**, **Insomnia**, ou **curl**.
    

---

## **7. Explicação do Fluxo**

1. **Rotas e Métodos HTTP**:
    
    - Cada rota usa um método HTTP (GET, POST, PUT, DELETE).
    - Essas rotas chamam métodos no modelo `Task` para interagir com o banco de dados.
2. **Banco de Dados**:
    
    - O Sequelize simplifica consultas SQL com métodos como `findAll`, `create`, `findByPk`, etc.
3. **Middleware**:
    
    - O **Body-parser** permite ler o corpo das requisições no formato JSON.
4. **Separação de Responsabilidades**:
    
    - **Rotas** lidam com a lógica de requisição.
    - **Modelos** gerenciam os dados.

---

Com isso, você tem uma API REST funcional e modular, cobrindo conceitos fundamentais do backend. Se precisar de ajuda com algum ponto específico, posso detalhar mais!