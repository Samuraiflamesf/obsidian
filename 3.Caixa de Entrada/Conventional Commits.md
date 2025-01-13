---
Title: Estrutura de Mensagens de Commit
created: 2025-01-07
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - php
  - laravel
  - git
---
| [Voltar](index) |
# 1. Criando um branch
## Implementação de Novas Funcionalidades:
* Feat: Descrição da funcionalidade adicionada
```
git checkout -b feature/api-gerar-contratos
```
## Correções de Bugs ou Lacunas:
* Fix: Descrição da correção ou adição feita
```
git checkout -b fix/api-gerar-contratos
```
## Testes Unitários:
* Test: Descrição do teste implementado
```
git checkout -b test/api-gerar-contratos
```
## Refatoração de Código:
* Refactor: Descrição das melhorias na estrutura ou clareza do código
```
git checkout -b refactory/api-gerar-contratos
```
## Mudanças na documentação:
* Docs: Descrição das melhorias na documentação ou clareza do código
```
git checkout -b docs/api-gerar-contratos
```
# 2. Faça o commit das mudanças
Escreva mensagens de commit claras e concisas. Use o seguinte padrão para mensagens de commit:
- `feat:` Para novas funcionalidades
- `fix:` Para correção de bugs
- `docs:` Para mudanças na documentação
- `style:` Ajustes de formatação e estilo
- `refactor:` Refatoração de código
- `test:` Adição ou modificação de testes

```
git commit -m "fix: corrigido bug na autenticação de usuários"
```
# 3. Crie um Pull Request
Descreva claramente a mudança e inclua referências a quaisquer issues relacionadas.
> Exemplo de descrição: "Este PR resolve o problema #123 e implementa a funcionalidade de login via autenticação OAuth.
# 4. Pós Pull Request
Apague a branch localmente:
```
git branch -D nome-da-branch
```
Apagando a branch remota:
```
git push origin —delete nome-branch
```
# Refêrencia:
- Lucas Lion