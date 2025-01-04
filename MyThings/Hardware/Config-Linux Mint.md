
## Tutorial para Instalação e Conexão com a VPN da Empresa

#### 1. *Criar o Arquivo de Configuração my-ssl.conf*
1. Abra o terminal e vá para o diretório pessoal (~/).
2. Crie um arquivo chamado my-ssl.conf com o seguinte conteúdo:
   
   ```bash
   nano ~/my-ssl.conf
   ```
   
3. Copie e cole as linhas abaixo no arquivo:

   
   openssl_conf = openssl_init

   [openssl_init]
   ssl_conf = ssl_sect

   [ssl_sect]
   system_default = system_default_sect

   [system_default_sect]
   Options = UnsafeLegacyRenegotiation
   

4. Salve e feche o editor (Ctrl + X, depois Y e Enter).

#### 2. *Instalar o pipx para Gerenciar Pacotes Python*
1. No terminal, execute:

   ```bash
   sudo apt update
   sudo apt install -y pipx
   ```

#### 3. *Instalar o openconnect-sso*
1. Instale o openconnect-sso usando o pipx:

   ```bash
   pipx install openconnect-sso
   ```

#### 4. *Modificar a Variável de Ambiente PATH*
1. No terminal, adicione o caminho ~/.local/bin ao início da variável PATH:

   ```bash
   export PATH="$HOME/.local/bin:$PATH"
   ```

2. Para tornar essa modificação permanente, adicione a linha acima ao final do arquivo ~/.bashrc:

   ```bash
   nano ~/.bashrc
   ```

   - Adicione a linha abaixo no final do arquivo:

     ```bash
     export PATH="$HOME/.local/bin:$PATH"
     ```

   - Salve e feche o editor (Ctrl + X, depois Y e Enter).

3. Recarregue o bash para aplicar as alterações:

   ```bash
   source ~/.bashrc
   ```

#### 5. *Instalar Dependências do Qt*
1. Instale as bibliotecas necessárias para o openconnect-sso:

   ```bash
   sudo apt update
   sudo apt install -y libxcb-xinerama0 libxcb-cursor0 libxkbcommon-x11-0 libqt5gui5
   ```

2. Se o problema persistir, instale também o plugin adicional do Qt:

   ```bash
   sudo apt install -y qt5-qpa-platformplugin
   ```

#### 6. *Conectar-se à VPN*
1. Defina a variável de ambiente para o arquivo my-ssl.conf:

   ```bash
   export OPENSSL_CONF="$HOME/my-ssl.conf"
   ```

2. Execute o openconnect-sso para iniciar a conexão com a VPN:

   ```bash
   openconnect-sso -s oi-corp.vpn.seg.br
   ```

Após seguir esses passos, o openconnect-sso deve iniciar a interface de autenticação SSO para que você possa se conectar à VPN da empresa.




url para liberar navegação após conexão com a VPN:

https://isepx12.oi.net.br:8443/portal/PortalSetup.action?portal=aa72bfd7-24e5-4ba1-84ab-203e03c0bc01&sessionId=0a3d320e4199a00066fdd2fe&action=cpp


#### Para desconectar da VPN:

Ctrl + C no terminal

reiniciar o wifi ou a rede.

### AUTOMATIZAÇÃO:

#### Conexão da VPN
Crie um arquivo startVPN.sh na Pasta Pessoal, com o seguinte conteúdo:


export OPENSSL_CONF="./my-ssl.conf"
openconnect-sso -s oi-corp.vpn.seg.br


#### Desconectar da VPN
Crie um arquivo stopVPN.sh na Pasta Pessoal, com o seguinte conteúdo:


nmcli device disconnect wlp4s0
sleep 6
nmcli device connect wlp4s0

#### para descobrir o nome da placa de wifi ou rede cabeada
```
 ip -c -br a
 ```


___
## Configurações para a clonagem do repositório Azure


### Criar chave SSH para conexão com Git Azure

```bash
ssh-keygen -t rsa -C "jady.godoi@oi.net.br" -f /home/jady/.ssh/id_rsa_jady_oi
cat id_rsa_jady_oi.pub
```


#### Atualizar o ssh para permitir métodos antigos (temporário)

Configure manualmente o método de troca de chave para permitir diffie-hellman-group14-sha1 adicionando a opção diretamente no comando:

```bash

GIT_SSH_COMMAND='ssh -oKexAlgorithms=+diffie-hellman-group14-sha1' git clone ssh://azure.oi.intranet:22/devops/Oi%20Solu%C3%A7%C3%B5es%20Grandes%20Empresas/_git/Oi_Grandes_Empresas
```

#### Editar a configuração do SSH

Adicione as seguintes linhas no arquivo de configuração SSH (~/.ssh/config) para o host específico:

Host azure.oi.intranet
    KexAlgorithms +diffie-hellman-group14-sha1
Host azure.oi.intranet
    HostKeyAlgorithms +ssh-rsa
    PubkeyAcceptedAlgorithms +ssh-rsa


Essas configurações dizem ao cliente SSH para aceitar o tipo de chave ssh-rsa que está sendo oferecido pelo servidor, que foi desativado por padrão em versões mais novas do OpenSSH devido a preocupações de segurança.

Agora vc deve conseguir clonar o repositorio do Azure.

_____

## Para starter do Docker-Lumis_Ubuntu

Antes de iniciar o docker abra a pasta ./Documentos/Docker-Lumis-Ubuntu e abra o arquivo **README.md**

Nesse arquivo tem a etapa 3 (3.1 e 3.2): execute-a:

> #### 3. Faça build das imagens na primeira utilização
> ##### 3.1 Build lumis
> 
>     docker build -f Dockerfile_lumis_nonroot -t lumis_image_centos8_nr .
>     docker build -f Dockerfile_lumis_nonroot_java -t lumis_image_java .
> 
> #### 3.2 Build elasticsearch
> 
>     docker build -f Dockerfile_elastic -t elastic_image .

Antes da etapa 4, execute o comando de reset do Lumis: ./ComandosUteis/resetLumis.sh

Então pode executar o comando de start do Lumis: ./ComandosUteis/startLumis.sh

Abra o VSCode na pasta ./Documentos/source_lumis para visualizar o projeto e os dockers bem como o log do tomcat para ver se deu tudo certo.

Após a montagem completa dos Dockers e o ambiente montado, você poderá ver o Lumis rodando na porta localhost:9080

Faça o deploy do br.com.oi.portais.oauthautenticador.zip depois do módulo versionado:
- se já tiver o módulo na pasta source_lumis é só fazer o deploy a partir dessa pasta
- se não tiver é só fazer o clone do repositório develop. Siga o tutorial de reset de ambiente.
