---
title: Iniciando_projeto_laravel
created: 2024-09-24
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - php
---
| [Voltar](index) |
**Passos para iniciar o projeto Laravel usando o CMD:**

1. **Criar a pasta do projeto:**
   - Abra o Prompt de Comando (CMD).
   - Navegue até o diretório onde deseja criar o projeto.
   - Digite o seguinte comando:
     ```
     mkdir example-app
     ```
2. **Acessar a pasta do projeto:**
   - Digite o seguinte comando para acessar a pasta do projeto:
     ```
     cd example-app
     ```
3. **Criar o projeto Laravel:**
   - Digite o seguinte comando para criar o projeto Laravel:
     ```
     composer create-project laravel/laravel .
     ```
4. **Mover para o diretório público:**
   - Digite o seguinte comando para navegar até o diretório público do projeto:
     ```
     cd public
     ```
5. **Iniciar o servidor:**
   - Digite o seguinte comando para iniciar o servidor web local:
 ```
 php -S localhost:8000
 ```
6. Instalando git flow:
    ```
     git flow init
    ```

Agora, o servidor web deve estar em execução e você pode acessar o seu projeto Laravel em:
http://localhost:8000