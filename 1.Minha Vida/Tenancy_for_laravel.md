---
title: Tenancy_for_laravel
created: 2024-10-10
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - php
---
| [Voltar](index) |
**Para rodar migrations:**
```
php artisan tenants:migrate
```
**Para rodar seed:**
```
php artisan tenants:seed
```
**Para rodar tudo novamente:**
```
php artisan migrate:fresh
```
**Para rodar migrações e seed em um tenant específico:**
```
php artisan tenants:migrate-fresh --tenants=8075a580-1cb8-11e9-8822-49c5d8f8ff23
```
**Comando lista todos os inquilinos existentes:**
```
php artisan tenants:list
```
