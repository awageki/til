# title
[Laravel Route Grouping: 6 Techniques to Organize Routes](https://laravel-news.com/laravel-route-organization-tips)

# author
PoviasKorop

# summary
課題
- プロジェクトが大きくなるにつれてルートを探すのが難しくなる
1. Route::resource
[resource controller](https://laravel.com/docs/9.x/controllers#resource-controllers) の場合
- index(), create(), store(), show(), edit(), update(), destroy()
```php
// 上記の7つ全てが一行で書ける
Route::resource('books', BookController::class);

// APIプロジェクトなどcereate、edit以外の5つを使用する場合
Route::apiResource('books', BookController::class);

// 2~4個のメソッドであっても resource controller を使うのがおすすめ → メソッド、ルート名について標準的な命名規則が維持できるから
Route::resource('books', BookController::class)->only(['create', 'store']);
```

2. Group の中で Group を使う
```php
Route::middleware('auth')->group(function() {
    Route::middleware('is_admin')->prefix('admin')->group(fucntion() {
        Route::get(...) // administrator routes
    })

    Route::middleware('is_user')->prefix('user')->group(function() {
        Route::get(...) // user routes
    })
})
```

3. Group の中で Middleware が複数使われる場合
`app/Http/Kernel.php`に書くことでまとめて書ける
```php
// Kernel.php
protected $middlewareGroups = [

    // new middleware group
    'check_user` => [
        'auth',
        'check.role',
        'check.user.status',
        'locale'
    ],
];

// web.php
Route::prefix('managers')->middleware(['check_user'])->group(function() {

})
```

4. 同じ名前の Controller が複数の namespaces で使用されている場合
トップで別名を指定するのではなく、サブフォルダに namespace() を追加する
```php
use App\Http\Controllers\Admin\HomeController; // as AdminHomeController; とはしない
use App\Http\Controllers\User\HomeController;


Route::prefix('admin')->namespace('App\Http\Controllers\Admin')->middleware('is_admin')->group(function () {
    Route::get('home', [HomeController::class, 'index']);
    // ... other controllers from Admin namespace
});
 
Route::prefix('user')->namespace('App\Http\Controllers\User')->middleware('is_user')->group(function () {
    Route::get('home', [HomeController::class, 'index']);
    // ... other controllers from User namespace
});
```

5. route ファイルを分ける
- web.php, api.php がデフォルトだが、`app/Providers/RouteServiceProvider.php`に追加すれば別のファイルにもルートを設定できる
- service provider を触りたくない場合は、デフォルトのルートファイルに直接読み込むことでも対応可
```php
// 筆者のおすすめはこっち
Route::get('/', function () {
    return view('welcome');
});
 
Route::get('/dashboard', function () {
    return view('dashboard');
})->middleware(['auth'])->name('dashboard');
 
require __DIR__.'/auth.php';
```

6. Route::controller()
- Laravel9と8の最新バージョンでのみ使用可
- 標準的なメソッドでなくてもメソッドごとに Controller 名を繰り返さずにグループ化することができる
```php
Route::controller(ProfileController::class)->group(function() {
    Route::get('profile', 'getProfile');
    Route::put('profile', 'updateProfile');
    Route::delete('profile', 'deleteProfile');
});
```

# words
- corresponds: 対応する、準ずる
- quite: とても
- confusing: 紛らわしい

# impression
普段使用していない書き方があり勉強になった

大きいプロジェクトだとルートファイルが肥大化するので、積極的に採用したい