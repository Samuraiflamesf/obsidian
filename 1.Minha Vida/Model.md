---
Title: Model
created: 2024-11-12
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
| [Voltar](index) |
## Exemplo de Relacionamento `One to Many` (Um para Muitos):
#### **Modelo `User`:**
O modelo `User` representa o "lado pai" do relacionamento.
```php
class User extends Model
{
    use HasFactory;

    // Relacionamento: Um usuário tem muitos posts
    public function posts()
    {
        return $this->hasMany(Post::class);
    }
}
```
#### **Modelo `Post`:**
O modelo `Post` representa o "lado filho" do relacionamento.
```php
class Post extends Model
{
    use HasFactory;

    // Relacionamento: Um post pertence a um usuário
    public function user()
    {
        return $this->belongsTo(User::class);
    }
}

```