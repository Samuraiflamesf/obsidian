---
Title: SAFTEC_CMS
created: 2024-11-27
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
| [Voltar](index) |
# Optimizing images
### Usage:
```php
use Filament\Forms\Components\FileUpload;
 
FileUpload::make('attachment')
    ->image()
    ->optimize('webp'),
```


# [ApexCharts](https://github.com/leandrocfe/filament-demo/tree/apex-charts-plugin-v3) 
### Usage:
```bash
php artisan make:filament-apex-charts BlogPostsChart
```
# [Excel Export by Dennis Koch - Filament](https://filamentphp.com/plugins/pxlrbt-excel) 
### Usage:
```php
<?php
 
namespace App\Filament\Resources;
 
use pxlrbt\FilamentExcel\Actions\Tables\ExportBulkAction;
 
class UserResource extends Resource
{
    public static function table(Table $table): Table
    {
        return $table
            ->columns([
                //
            ])
            ->bulkActions([
                ExportBulkAction::make()
            ]);
    }
}
```
# 
### Usage:
```bash

```
# 
### Usage:
```bash

```