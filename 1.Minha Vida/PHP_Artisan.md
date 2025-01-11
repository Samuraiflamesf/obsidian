---
title: PHP_Artisan
created: 2024-09-30
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - git
---
| [Voltar](index) | [[Git Flow]] | [[Aprendendo Git]] |
**Rodar filas/Queue
```bash
php artisan queue:listen --tries=1
```
**Rodar filas de Upload de fotos para store**
```bash
php artisan storage:link
```
Abrindo Server
```bash
php artisan serve
```
Você pode rodar todas as migrations e seeders juntos com o comando:
```
php artisan migrate --seed
```
Isso irá rodar as migrations e, em seguida, executar os seeders configurados.
Para um controller simples, criar um controller com metodo  `__invoke`:
```bash
php artisan make:controller ProvisionServer --invokable
```
