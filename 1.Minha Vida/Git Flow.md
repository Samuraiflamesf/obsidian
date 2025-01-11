---
title: Git Flow
created: 2024-09-28
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - git
---
| [Voltar](index) | [[Aprendendo Git]] | [[PHP_Artisan]] |
# Git Flow

O **Git Flow** é um modelo de ramificação do Git que organiza o desenvolvimento de software em várias etapas, facilitando o controle de versões e o gerenciamento de lançamentos. Ele é baseado em cinco tipos principais de branches: `main`, `develop`, `feature`, `release` e `hotfix`.
## Estrutura Principal
- **main**: contém o código em produção (estável).
- **develop**: serve como o branch de desenvolvimento, onde novas funcionalidades são integradas.
- **feature**: utilizado para desenvolver novas funcionalidades.
- **release**: usado para preparar um novo lançamento.
- **hotfix**: para correção de bugs críticos em produção.
## Passos do Git Flow
### 1. Iniciar Git Flow
Primeiramente, inicializa-se o Git Flow no repositório, o que configura automaticamente os branches.
```bash
git flow init
```
Ao executar o comando, o Git Flow solicitará os nomes dos branches principais (geralmente `main` e `develop`).
### 2. Criar uma Feature
As funcionalidades são desenvolvidas em branches `feature` derivados de `develop`.
```bash
git flow feature start minha-feature
```
Quando a funcionalidade está pronta, a `feature` é mesclada de volta no `develop`:
```bash
git flow feature finish minha-feature
```
Isso vai mesclar a feature no branch `develop` local. Após isso, envie o `develop` para o GitHub:
```bash
git push origin develop
```
Ao iniciar o editor de texto, documente o propósito do recurso criado. Em seguida, pressione a tecla de escape (ESC) e digite `:wq`. Pressione Enter para salvar e sair do editor.

### 3. Criar um Release
Para preparar uma nova versão, um branch `release` é criado a partir do `develop`.
```bash
git flow release start v1.0.0
```
Vamos publicar o release para o repositório remoto:
```bash
git flow release publish v1.0.0
```
Após testes e ajustes, ele é mesclado no `main` e `develop`. Um **tag** pode ser adicionado:
```bash
git flow release finish v1.0.0
```
## Comandos Auxiliares
**Listar features** em desenvolvimento:
``` bash
git flow feature list
```
**Cancelar uma feature**:
``` bash
git flow feature delete minha-feature
```
**Deletando uma branch**:
``` bash
git branch -d nome-da-branch
```
**Fatal: Working tree contains unstaged changes. Aborting.**
``` bash
git add .
git commit -m "TAG"  
git push --all  
git flow init -d
```
**Resetar para a versão remota**
```bash
git fetch origin
git reset --hard origin/nome-da-branch
```
