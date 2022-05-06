# title
[Laravel Jetstream:Add CRUD with Spatie Permission](https://laravel-news.com/jetstream-spatie-permission)

# author
PocilasKorop

# summary
Jetstream でロール/パーミッションを使った簡単な CRUD 機能を実装する

```shell
php artisan make:model Task -mcrR

-m: マイグレーションクラス作成
-cr: index, create, store... が予め作成済みのコントローラーを作成
-R: リクエストクラスを2つ作成（StoreTaskRequest, UpdateTaskRequest）
```

`auth:sanctum` は Jetstream 独自の書き方

書き方を確認しておく
>If you are not familiar with the syntax like x-app-layout or x-slot, read about layouts using Blade components.If you are not familiar with the __() method, read about translations in Laravel.

`Laravel Permission`

# words
- proceed：発生する、由来する
- scaffolding：（建築現場などの）足場
- irrelevant：不適切な、見当違いの
- correspond：一致する

# impression
Jetstream を使っても色々カスタマイズ可能

実際にコード書いてみる