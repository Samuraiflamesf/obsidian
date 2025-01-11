---
title: Aprendendo Git
created: 2024-09-28
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - git
---
| [Voltar](index) | [[Git Flow]] | [[PHP_Artisan]] |
### **Inicialização do Projeto:**
**Criar um novo repositório Git.**
```bash
git init
```
**Para adicionar todos arquivos e criar um commit**
```bash
git commit -am 'Feat: Enviando email, sobre contatos'
```
**Subindo para nuvem**
```bash
git push origin name_branch
```
****
### **Puxando um Projeto:**
**Clonando o repositorio:**
```bash
git clone https://github.com/usuario/repositorio.git
```
**Comece a editar os arquivos**:
```bash
cd repositorio
code .
```
**Sincronização Pré-Edições:**
```bash
git pull origin main
```
_Substitua "main" pelo nome da sua branch principal, se necessário._
**Criação de Branch:**
```bash
git checkout -b minha-branch
```
****
### Sobre Branch
**Para listar todas as branches locais**, utilize o comando:
```bash
git branch
```
**Para remover uma branch local**, use o seguinte comando:
```bash
git branch -d nome-da-branch
```
Para listar as branches remotas, você pode usar:
```bash
git branch -r
```
Para remover uma branch remota, utilize o comando:
```bash
git push origin --delete nome-da-branch
```
**Criação de uma Nova Branch:**
```bash
git checkout -b "nome"
```
**Comando para atualizar as branch do projeto:**
```bash
git fetch
```
**Selecionar branch e atualizar:**
```bash
git pull origin nome_da_branch
```
**Comando para atualizar as branch do projeto:**
```bash
git push origin feature/mailtrap-contact
```
#### Baixar versão mais recente da branch
Resolva os conflitos pendentes, conforme descrito anteriormente:
```bash
git status
```
Após resolver qualquer conflito ou problema pendente, **descarte as alterações locais** se você não precisar mantê-las:
```bash
git reset --hard
```
Certifique-se de estar na branch onde deseja baixar as atualizações:
```bash
git checkout feature/mailtrap-contact
```
Agora, faça o **pull** para baixar a versão mais recente da branch remota:
```bash
git pull origin feature/mailtrap-contact
```
***
### Setup inicial de projeto Laravel
**Clonando projeto**
```bash
git clone Samuraiflamesf/StudyCMS.git
```
**Copie o arquivo .env.example**
```bash
cp .env.example .env
```
**Instale as dependências e o framework**
```bash
composer install
```
**Crie uma nova chave para a aplicação**
```bash
php artisan key:generate
```
**Rodando migrates**
```bash
php artisan migrate
```
***
![[Git Tricks, Bug and Fix]]
