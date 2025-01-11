---
Title: Boas Praticas Laravel
created: 2024-11-11
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
| [Voltar](index) |
### Nomeando Models e Migrations
- **Models**: Devem ser nomeadas no singular e em PascalCase. Exemplo: 
  `User`, `Product`, `Order`.
- **Migrations**: Devem ser nomeadas de forma descritiva, no plural e sempre em inglês para facilitar a compatibilidade com pacotes externos. Por exemplo:
  `create_products_table`, `add_status_to_orders_table`.
- **Convenção de Nomenclatura**: As colunas também devem seguir o padrão em inglês e o snake_case, como: 
  `created_at`, `updated_at`, `is_active`.
### Ordem Recomendada de Criação dos Componentes
Abaixo, segue uma ordem recomendada para criação dos elementos que compõem uma resource no Filament:
- **[Model](Model%20e%20a%20Migration.md)**: Comece criando a model, pois ela serve como a representação dos dados da aplicação.
- **[Migration](Model%20e%20a%20Migration.md)**: Após a model, crie a migration para definir a estrutura da tabela no banco de dados.
- **[[Factory]]** (Opcional): Caso vá utilizar dados fake para testes, crie uma factory.
- **[[Seeder]]** (Opcional): Crie o seeder para popular o banco com dados iniciais, se necessário.
- **[[Resource]]**: Por fim, crie a resource no Filament para a model, onde serão configuradas as interfaces de listagem, criação, edição e visualização de dados.
### Configuração dos Relacionamentos
Inclua os relacionamentos entre models diretamente no código da model para permitir o uso simplificado no painel do Filament. Exemplo:
```php
class Product extends Model
{
    public function category()
    {
        return $this->belongsTo(Category::class);
    }
}
```
Em seguida, utilize colunas ou campos calculados no `ProductResource` para facilitar a visualização de dados derivados ou relacionados.