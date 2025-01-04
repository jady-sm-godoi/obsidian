## 1 - Instalação de Pacotes Iniciais e Configuração de **OpenConnect**

```bash
openconnect-sso -s oi-corp.vpn.seg.br

sudo apt install python3-pip
pip install --user pipx
ln -s /usr/bin/python3 /usr/bin/python
ln -s /usr/bin/pip3 /usr/bin/pip

pipx install "openconnect-sso[full]"
pipx ensurepath
	
export OPENSSL_CONF="./my-ssl.conf"
sudo apt install openconnect
openconnect-sso -s oi-corp.vpn.seg.br
```
ref.: https://pypi.org/project/openconnect-sso/

## 2 - Ajuste do arquivo hosts

```bash
	sudo nano /etc/hosts
```

Dentro do editor de texto, adicione as seguintes linhas:

10.32.150.149 interativa
10.32.209.172 workspace
10.58.94.9 apimhmllocal.intranet
201.15.126.44 apimhml.oi.net.br

### 3 - OPEN SSL -> Fazer Downgrade para openssl-1.1.1l 
Primeiro, remova a versão atual do OpenSSL:

```bash
sudo apt-get remove openssl
sudo apt-get update
sudo apt-get install build-essential
```

Baixe o OpenSSL 1.1.1l do site oficial (https://www.openssl.org/source/openssl-1.1.1l.tar.gzhttps://www.openssl.org/source/openssl-1.1.1l.tar.gz) e faça o link simbólico do libcrypto.so.1.0.0:

```bash
sudo ln -s /home/jady/.local/libcrypto.so.1.0.0 /usr/lib/libcrypto.so.1.0.0
```

Descompactar o arquivo openssl-1.1.1l.tar.gz

```bash
tar -xzf openssl-1.1.1l.tar.gz
cd openssl-1.1.1l/
```

Realizar a compilação deste openssl baixado:

```bash
./config
make
sudo make install
sudo ldconfig
```


> [!NOTE]
> ./config: Este comando é usado para executar o script de configuração do OpenSSL. Esse script é responsável por detectar as configurações do sistema e 				preparar o ambiente para a compilação. Ele geralmente verifica as dependências e define opções de compilação.

> [!NOTE] 
> make: Este comando inicia o processo de compilação. Ele lê as instruções de compilação contidas nos arquivos Makefile e compila o código-fonte do OpenSSL para produzir os binários executáveis.

> [!NOTE]
> make install: Após a compilação, este comando instala os binários, bibliotecas e outros arquivos necessários do OpenSSL no sistema. Isso permite que você use o OpenSSL em suas aplicações.

> [!NOTE]
> ldconfig: Este comando atualiza a tabela de links dinâmicos do sistema. É necessário para garantir que o sistema saiba onde encontrar as bibliotecas recém-instaladas do OpenSSL. Isso é importante para que os programas que dependem do OpenSSL possam encontrá-lo e usá-lo corretamente.


Após a instalação, pode ser necessário reinstalar o ca-certificates. Se houver problemas de dependências, use o seguinte:

```bash
apt --fix-broken install
apt autoremove
apt install ca-certificates
```

## 4 - Configuração do OpenSSH 7.6p1_port

OPEN SSH -> Usar o openssh-7.6p1_port Configurar variavel para ssh antigo
Adicionar a variavel abaixo no seu sourve vi ~/.zshrc ou no ~/.bashrc

```bash
export GIT_SSH_COMMAND="/mnt/centos/devops/Downloads/openssh-7.6p1_port/openssh-7.6p1/ssh"

source ~/.bashrc
source ~/.zshrc
```

## 5 - Criar chave SSH para conexão com Git Azure

```bash
ssh-keygen -t rsa -C "jady.godoi@oi.net.br" -f /home/jady/.ssh/id_rsa_jady_oi
cat id_rsa_jady_oi.pub
```


## 6 - Criar um arquivo executável para conectar à VPN:

criar um arquivo "startVPN.txt" com os seguintes comandos nele:

```bash
export OPENSSL_CONF="./my-ssl.conf" 
openconnect-sso -s oi-corp.vpn.seg.br
```

Em configurações do arquivo, marcar que ele pode ser executado como um programa.


## 7 - PROGRAMAS PARA INSTALAR

- VSCode
- DBeaber
  https://dbeaver.io/download/?start&os=linux&arch=x86_64&dist=deb
- Java
  ```
  sudo apt install openjdk-17-jre-headless
  ```
- Maven
```
sudo apt-get update
sudo apt-get -y install maven
```
- Docker

## 8 - INSTALAÇÃO DO DOCKER NO UBUNTU:

Remova versões antigas do Docker (se existirem):
`sudo apt-get remove docker docker-engine docker.io containerd runc`

Atualize o índice de pacotes do apt e instale pacotes para permitir o apt usar repositórios via HTTPS:
```
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```

Adicione a chave GPG oficial do Docker:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

Adicione o repositório Docker ao apt:
```
echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Instale o Docker Engine:
```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Adicione seu usuário ao grupo docker para evitar a necessidade de usar sudo ao executar comandos Docker:
```
sudo usermod -aG docker $USER
```

Baixe a versão mais recente do Docker Compose:
```
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

Dê permissão de execução ao Docker Compose:
```
sudo chmod +x /usr/local/bin/docker-compose
```

Verifique se a instalação foi bem-sucedida:
```
docker-compose --version
```

ajustar as permissões usando o seguinte comando:
```
sudo chmod 666 /var/run/docker.sock
```

Reinicie o serviço Docker:
```
sudo service docker restart
sudo systemctl status docker //para saber o status do serviço
			   (stop)
			   (start)
			   (restart)
			   (enable) //para colocar na inicialização do sistema
			   (disable) //para tirar da inicialização do sistema
```

### Abrir o Docker-Lumis no VSCode e seguir os passos do README.md

Talvez seja necessário dar permissões às pastas do docker:	
```
sudo chmod 777 -R .
```

Fazer um backupo do lumisportal e mysql limpos para reestartar ambiente.
```
cp -r mysql_data mysql_data_LumisLimpo
cp -r lumisportal lumisportal_LumisLimpo
```

