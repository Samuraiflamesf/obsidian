---
Title: Criando a Model e a Migration
created: 2024-11-11
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
| [Voltar](index) |
### **Criando a Model e a Migration**
No terminal, execute:
```bash
php artisan make:model Product -m
```
Este comando cria a model `Product` e a migration `create_products_table`. Em seguida, defina os atributos e relacionamentos na model e configure as colunas desejadas na migration.

>**Dica**: Inclua sempre as propriedades `$fillable` na model para segurança de atribuição em massa.
``` php
class Product extends Model
{
    protected $fillable = ['name', 'price', 'description', 'stock'];
}
```
Na migration, configure as colunas com os tipos de dados adequados:
```php
Schema::create('products', function (Blueprint $table) {
    $table->id();
    $table->string('name');
    $table->decimal('price', 8, 2);
    $table->text('description')->nullable();
    $table->integer('stock')->default(0);
    $table->timestamps();
});
```
![[Migrates]]
