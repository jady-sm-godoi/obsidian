

---

### **1. Componentes do Bootstrap**

- **Carrossel**: Apresentação de slides com navegação intuitiva (indicadores e botões de controle).
- **Cards**: Contêineres flexíveis para exibir informações com título, texto, links e imagens.
- **Modal**: Janela flutuante para exibir notificações ou informações adicionais.

---

### **2. Boas Práticas**

- **Design Responsivo**: Adicione a meta tag `<meta name="viewport" content="width=device-width, initial-scale=1.0">` para garantir que a página se adapte a diferentes dispositivos.
- **Consistência Visual**: Use imagens de tamanhos iguais em Carrosséis e Cards para manter harmonia no layout.

---

### **3. Aplicação Prática**

- **Inicie um Projeto**:
    
    1. Configure seu arquivo HTML com o doctype HTML5.
    2. Inclua os arquivos CSS e JS do Bootstrap:
        
        ```html
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
        ```
        
    3. Estruture seu layout com um Carrossel no header, Cards no corpo e um Modal acionado por um botão.
- **Código de Exemplo - Layout Básico**:
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
        <title>Exemplo Bootstrap</title>
    </head>
    <body>
        <!-- Carrossel -->
        <div id="demo" class="carousel slide" data-bs-ride="carousel">
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <img src="img1.jpg" class="d-block w-100" alt="Imagem 1">
                </div>
                <div class="carousel-item">
                    <img src="img2.jpg" class="d-block w-100" alt="Imagem 2">
                </div>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#demo" data-bs-slide="prev">
                <span class="carousel-control-prev-icon"></span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#demo" data-bs-slide="next">
                <span class="carousel-control-next-icon"></span>
            </button>
        </div>
    
        <!-- Card -->
        <div class="card" style="width: 18rem;">
            <img src="img-card.jpg" class="card-img-top" alt="Imagem Card">
            <div class="card-body">
                <h5 class="card-title">Título do Card</h5>
                <p class="card-text">Texto descritivo.</p>
                <a href="#" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#myModal">Saiba Mais</a>
            </div>
        </div>
    
        <!-- Modal -->
        <div class="modal" id="myModal">
            <div class="modal-dialog">
                <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title">Título da Modal</h5>
                        <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                    </div>
                    <div class="modal-body">Conteúdo da Modal</div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fechar</button>
                    </div>
                </div>
            </div>
        </div>
    
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    </body>
    </html>
    ```
    

---

### **4. Recursos Adicionais**

- Explore exemplos prontos no site oficial do Bootstrap: [Bootstrap Examples](https://getbootstrap.com/docs/5.3/examples/).
- Use o repositório mencionado para práticas avançadas: [GitHub FrontEnd](https://github.com/FaculdadeDescomplica/Practitioner_FrontEnd.git).

Se precisar de ajustes ou exemplos mais específicos, é só avisar!