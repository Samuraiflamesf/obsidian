---
{"Title":"Deploy Laravel com Coolify","created":"2025-01-02","dg-publish":true,"tags":["pessoal/estudos","pessoal/quaseumdev"],"permalink":"/3-caixa-de-entrada/deploy-laravel-com-coolify/","dgPassFrontmatter":true}
---

| [Voltar](index) |
# Projeto Laravel
## Configuração
Usar esse pacote para filas do php:
```bash
composer require predis/predis
```
## Alterações no código
app\Providers\AppServiceProvider.php:
```php
public function boot(): void {
	// Coolify
	if ($this->app->environment('production')) {
		URL::forceRootUrl(config('app.url'));
	}
}
```
bootstrap\app.php:
```php
->withMiddleware(function (Middleware $middleware) {
        // Coolify
        $middleware->trustProxies(at: "*");
    })
```
## Criando um `nixpacks.toml`
[Laravel | Coolify's Docs](https://coolify.io/docs/applications/laravel)
# Coolify
1. Criar um projeto em:![Pasted image 20241209140203.webp](0.Settings/img/Pasted%20image%2020241209140203.webp)![Pasted image 20241209140235.webp](0.Settings/img/Pasted%20image%2020241209140235.webp)
2. Acesse a produção, e adicione os recurso:![Pasted image 20241209140326.webp](0.Settings/img/Pasted%20image%2020241209140326.webp)
	1. Criando Instacia do `postgress`
	2. Criando Instancia do `redis`
3. Criando app no `GitHub`.
4. Criando resource da Aplicação. ![Pasted image 20241209142910.webp](0.Settings/img/Pasted%20image%2020241209142910.webp)
5.  Colocar porta 80 ![[Pasted image 20250121230750.webp]]
6. Configurando `env`:
```env
APP_NAME="SAFTEC"
APP_ENV=production
APP_KEY=
APP_LOCALE=pt_BR
APP_TIMEZONE=America/Sao_Paulo
APP_URL=
ASSET_URL=

LOG_CHANNEL=error_log

DB_CONNECTION=pgsql
DB_HOST=
DB_PORT=3306
DB_DATABASE=
DB_USERNAME=
DB_PASSWORD=

REDIS_URL=
REDIS_CLIENT=predis

CACHE_DRIVER=redis
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis
```
6. Configurando as migrations e cache:![Pasted image 20241209144730.webp](0.Settings/img/Pasted%20image%2020241209144730.webp)
   ```bash
   php artisan migrate --force && php artisan optimize
```
7. Deploy

# Referências:
[Laravel: Como Fazer Deploy Em Produção Com O Coolify (Tutorial Passo a Passo) - YouTube](https://www.youtube.com/watch?v=m3CSZmSD-wg)
