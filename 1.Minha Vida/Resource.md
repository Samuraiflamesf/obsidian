---
Title: Criando a Resource no Filament
created: 2024-11-11
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
| [Voltar](index) |
### **Criando a Resource no Filament**
Após configurar a model e a migration, crie a resource do Filament. No terminal:
```bash
php artisan make:filament-resource Product
```
Este comando cria um conjunto de arquivos no diretório `App/Filament/Resources/ProductResource`. 
No `ProductResource.php`, você configurará os layouts de listagem, criação e edição para o painel administrativo.
## **Listagem** (`Table`)
Configure a listagem de forma clara e adicione filtros ou ações para facilitar a administração. Exemplo:
```php
protected function getTableColumns(): array
{
    return [
        TextColumn::make('name')->sortable()->searchable(),
        TextColumn::make('price')->sortable(),
        TextColumn::make('stock')->sortable(),
        BooleanColumn::make('is_active'),
        TextColumn::make('created_at')->dateTime(),
    ];
}
```
## **Formulário** (`Form`)
Defina o layout do formulário de criação e edição com componentes adequados, como `TextInput`, `Textarea`, `Select`, etc.
```php
protected function getFormSchema(): array
{
    return [
        TextInput::make('name')->required(),
        TextInput::make('price')->numeric()->required(),
        Textarea::make('description')->nullable(),
        TextInput::make('stock')->numeric()->required(),
    ];
}
```