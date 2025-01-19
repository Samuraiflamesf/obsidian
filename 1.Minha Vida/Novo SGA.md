---
Title: Como Implementar o Novo SGA (Sistema de Gerenciamento de Senhas)
created: 2024-12-11
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
| [Voltar](index) |
Este tutorial fornece um passo a passo para a implementação do Novo SGA, um sistema de gerenciamento de senhas eficiente e amplamente utilizado em ambientes públicos e privados.
## Requisitos Mínimos
- **1 Computador**: Para o serviço SGA.
- **1 Computador**: Para o chamamento.
- **1 TV**: Para exibição das senhas.
- **Conectividade**: Todos os dispositivos devem estar conectados à mesma rede (cabo ou Wi-Fi).
---
## Etapas de Implementação

### 1. Preparação do Ambiente
Instalando Terminal do Windows:
[Windows Terminal | Microsoft Store](https://apps.microsoft.com/detail/9n0dx20hk701?hl=pt-BR&gl=BR)
#### Configuração do Ambiente WSL
**Ativação do WSL:**
1. Acesse o **Painel de Controle**.
2. Selecione **Programas**.
3. Clique em **Ativar ou Desativar Recursos do Windows**.
	1. ![[Novo SGA-20250106144627611.webp]]
4. Habilite a opção **Subsistema Windows para Linux (WSL)**.
5. Confirme com **OK**.
#### Instalação do WSL:
* Abra o **PowerShell** como administrador.
* Execute o comando: 
```bash
wsl --install -d Ubuntu-24.04
```
* Reinicie o computador.
- Após a reinicialização, digite um nome de usuário e uma senha para a distribuição do Linux recém-instalada.
### Método 1: Instalando Docker, Docker Compose e Portainer
#### **1. Atualizando o Sistema**
Antes de qualquer instalação, atualize seu sistema para garantir que os pacotes estão na última versão:

```
sudo apt update && sudo apt upgrade -y
```
#### **2. Instalando o Docker**
1. **Pré-requisitos**: Instale pacotes que permitem o uso de HTTPS para downloads seguros:
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
2. **Adicionando a chave GPG e o repositório oficial do Docker**:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
3. **Instalando o Docker**:
```
sudo apt update && sudo apt install docker-ce
```
1. **Verificando a instalação**:
```
docker --version
```
Para usar o Docker sem `sudo`, adicione seu usuário ao grupo apropriado:
```
sudo usermod -aG docker ${MASTECDASF-509685}
su - ${MASTECDASF-509685}
```
#### **3. Instalando o Docker Compose**
1. **Criando o diretório para plugins**:
```
mkdir -p ~/.docker/cli-plugins/
```
2. **Baixando e configurando o Docker Compose**:
```
curl -SL https://github.com/docker/compose/releases/download/v2.27.1/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose
chmod +x ~/.docker/cli-plugins/docker-compose
```
3. **Verificando a instalação**:
```
docker compose version
```
#### **4. Gerenciamento de Containers**
Criando novo volume:
```
docker volume create portainer_data
```
Download e instalação do Portainel:
```
docker run -d -p 8000:8000 -p 9000:9000 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.21.5
```
Link para testar:
http://localhost:9000/
### Método 2: Instalando Docker no [Windows | Docker Docs](https://docs.docker.com/desktop/setup/install/windows-install/)
- Baixar e instalar o Docker Desktop
### 3. Docker Compose
Arquivo `docker-composer.yml`:
```yaml
services:
  novosga:
    image: novosga/novosga:2.1
    restart: always
    depends_on:
      - mysqldb
    ports:
      - "80:80"
    environment:
      APP_ENV: 'prod'
      # database connection
      DATABASE_URL: 'mysql://novosga:MySQL_App_P4ssW0rd@mysqldb:3306/novosga2?charset=utf8mb4&serverVersion=5.7'
      # default admin user
      NOVOSGA_ADMIN_USERNAME: 'admin'
      NOVOSGA_ADMIN_PASSWORD: '123456'
      NOVOSGA_ADMIN_FIRSTNAME: 'Administrador'
      NOVOSGA_ADMIN_LASTNAME: 'Global'
      # default unity
      NOVOSGA_UNITY_NAME: 'Minha unidade'
      NOVOSGA_UNITY_CODE: 'U01'
      # default no-priority
      NOVOSGA_NOPRIORITY_NAME: 'Normal'
      NOVOSGA_NOPRIORITY_DESCRIPTION: 'Atendimento normal'
      # default priority
      NOVOSGA_PRIORITY_NAME: 'Prioridade'
      NOVOSGA_PRIORITY_DESCRIPTION: 'Atendimento prioritário'
      # default place
      NOVOSGA_PLACE_NAME: 'Guichê'
      # Set TimeZone and locale
      TZ: 'America/Sao_Paulo'
      APP_LANGUAGE: 'pt_BR'
      # Endereço Mercure para publicar mensagem (onde "mercure" é o nome do host)
      # esse endereço será chamado internamente via o PHP
      MERCURE_PUBLISH_URL: http://mercure:3000/.well-known/mercure
      # Endereço Mercure para consumir mensagem
      # esse endereço será chamado via o navegador web
      MERCURE_CONSUMER_URL: http://127.0.0.1:3000/.well-known/mercure
      # the default token is signed with the secret key: !ChangeMe!
      MERCURE_JWT_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZXJjdXJlIjp7InB1Ymxpc2giOltdfX0.Oo0yg7y4yMa1vr_bziltxuTCqb8JVHKxp-f_FwwOim0"
  mercure:
    image: novosga/mercure:v0.11
    restart: always
    ports:
      - "3000:3000"
    environment:
      # same value from ports
      SERVER_NAME: ":3000"
      # default publish key, must be changed
      MERCURE_PUBLISHER_JWT_KEY: "!ChangeMe!"
      MERCURE_EXTRA_DIRECTIVES:  "anonymous 1; cors_origins *"
  mysqldb:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_USER: 'novosga'
      MYSQL_DATABASE: 'novosga2'
      MYSQL_ROOT_PASSWORD: 'MySQL_r00t_P4ssW0rd'
      MYSQL_PASSWORD: 'MySQL_App_P4ssW0rd'
      # Set TimeZone
      TZ: 'America/Sao_Paulo'
```
Executando docker-compose:
```
docker-compose up -d
```
Acessar o banco de dados MySQL como `root`:
```
docker-compose exec mysqldb sh -c  'mysql -uroot -p'
```
Dar permissão de acesso para o usuário da aplicação:
```
GRANT ALL ON novosga2.* TO 'novosga'@'%' IDENTIFIED BY 'MySQL_App_P4ssW0rd';
quit
```
### 4. Acesso ao Sistema
1. **Acesse o Novo SGA pelo navegador**:
   - Utilize o IP ou domínio configurado (ex.: `http://seusite.com`).
2. **Configuração Inicial**:
   - Siga o assistente de configuração inicial fornecido pelo sistema.
---
## Referências
[GitHub - Novo SGA](https://github.com/novosga/novosga)
[Documentação | Novo SGA](http://novosga.org/docs/#/)
[Tutorial instalação do Novo SGA 2.0.8 + Painel no Debian server 11 · GitHub](https://gist.github.com/rhuandevops/fe72dc889ca5f8d9b67daf1d2d627be2)
## Conclusão
Caso tenha dúvidas, consulte a [documentação oficial](https://novosga.github.io/) ou entre em contato com a comunidade do Novo SGA.
