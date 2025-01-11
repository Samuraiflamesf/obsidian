---
Title: Migrates
created: 2024-11-12
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
| [Voltar](index) |

### **Criar a tabela relacionada (com chave estrangeira):**

Na tabela relacionada, você deve incluir a chave estrangeira referenciando a tabela principal. Por exemplo, para uma tabela de "posts" relacionada a "users":

```php
Schema::create('posts', function (Blueprint $table) {
    $table->id();
    $table->string('title');
    $table->text('content');
    $table->foreignId('user_id') 
    // Cria a coluna `user_id` com a referência automática
          ->constrained('users') 
          // Refere-se à tabela `users` pela coluna `id`
          ->onDelete('cascade'); 
          // Configura para deletar posts se o usuário for excluído
    $table->timestamps();
});

```
![[Model]]