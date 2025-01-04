
### Download Postman

`$ wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz`

### Extract archive

`$ sudo tar -xzf postman.tar.gz -C /opt`

### Make symlink

`$ sudo ln -s /opt/Postman/Postman /usr/bin/postman`

### Optional: Remove downloaded file

`$ rm postman.tar.gz`

### Make Desktop icon**

`$ sudo vim /usr/share/applications/postman.desktop`

```
[Desktop Entry]
Type=Application
Name=Postman
Icon=/opt/Postman/app/resources/app/assets/icon.png
Exec="/opt/Postman/Postman"
Comment=Postman Desktop App
Categories=Development;Code;
```

**
**Para usar o editor vim** e criar ou editar arquivos, siga este passo a passo:

### 1. Abrir o Vim

No terminal, digite:

bash

Copiar código

`sudo vim /usr/share/applications/postman.desktop`

### 2. Navegar no Vim

- Ao abrir, o Vim estará em **modo normal** (onde você pode navegar no texto).

### 3. Entrar no modo de edição

Pressione `i` para entrar no **modo de inserção** e poder editar o conteúdo.

### 4. Editar o Arquivo

Adicione ou modifique o conteúdo para ficar assim:

makefile

Copiar código

`[Desktop Entry] Type=Application Name=Postman Icon=/opt/Postman/app/resources/app/assets/icon.png Exec="/opt/Postman/Postman" Comment=Postman Desktop App Categories=Development;Code;`

### 5. Sair e Salvar as Alterações

- Para salvar e sair, faça o seguinte:
    1. Pressione **`ESC`** para voltar ao **modo normal**.
    2. Digite `:wq` e pressione **Enter**:
        - `w` = write (salvar)
        - `q` = quit (sair)

### 6. Verificar se o Ícone Aparece

- Depois de criar o arquivo `.desktop`, você pode rodar o seguinte para garantir que o ícone seja reconhecido:

bash

Copiar código

`sudo chmod +x /usr/share/applications/postman.desktop`

Agora, o ícone do Postman deve aparecer na interface gráfica no menu de aplicativos.