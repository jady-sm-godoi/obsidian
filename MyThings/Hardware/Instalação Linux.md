
- Baixar a Iso do Linux desejado
- Gravar a iso em pendrive
	- usar programa para gravar como o **Popsicle**
- Com o pendrive com a iso espetado no pc, reiniciar o pc e apertar a tecla F10 (ou outra conforme a máquina - testar) até entrar na Bios
- Escolher por onde vai ser feito o boot: pendrive
- Após a inicialização, escolher o Linux
- Conectar à internet
- Neste momento você pode testar a seu novo Linux, que está rodando a partir do pendrive


pwd
copia o enderco da pasta home
ls para ver se tem a pasta do usuario
sudo -i para entrar como root
cd enderecodapastaquevccopiou
mv jady jady2


- Clicar em instalar
- Escolher o teclado:
	- teclado internacional: escolha English(US) (US, intl, with dead keys)
- Escolher entre fazer uma partição do zero ou modo avançado
- Modo avançado:
	- Escolher as repartições:

|---Boot---|------( / )------|--------------( /home )-----------|-----Swap-----|

Boot: efi - 1G (1024M)

( / ): ext4 - onde fica o Linux - +/- 50G

( /home ): btrfs ou ext4 - onde ficam os arquivos de usuários - tamanho: tudo que sobrar, a maior partição

Swap: +/- 8G

_____

# Para pegar documentos de uma máquina para a outra dentro da mesma rede

#### TERMINAL MAQUINA CONSULTADA

Para visualizar o ip da maquina a ser consultada
```bash
ip -c -br a 
```

#### TERMINAL ABA DA MAQUINA CONSULTADA
Para conectar com a máquina a ser consultada:
```bash
ssh usuario@ip.da.maquina
```
Exemplo:
```bash
ssh jady@192.168.15.30 
```


#### TERMINAL ABA MINHA MÁQUINA

Para ter certeza que estou na minha máquina:
```bash
pwd 
```

Comando para pegar o arquivo ou diretório da maquina consultada e copiar para a maquina de destino:
```bash
sudo rsync -av --progress usuari@ip.da.maquina.consultada:arquivo/ /diretorio/destino 
```
**Obs:**
_arquivo/_ 
A barra faz você copiar o conteúdo do diretório

Exemplo:
```bash
sudo rsync -av --progress jady@192.168.15.30:.ssh/ /home/jady/.ssh 
```

Para visualizar o conteúdo do diretorio
```bash
ls -lisa
```

Para visualizar o conteúdo do diretório. Veja o novo conteúdo copiado da máquina consultada
```bash
ls -lisa
```