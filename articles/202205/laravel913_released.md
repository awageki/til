# title
[Laravel 9.13 Released](https://laravel-news.com/laravel-9-13-0)

# author
Paul Redmond

# summary
Laravel9.13のリリースに伴う新機能の紹介

1. Collectionのメソッドに`value()`が追加
keyを指定して最初にマッチした値を返す
```php
$c = new $collection([
    ['id' => 1, 'name' => 'Hello'],
    ['id' => 2, 'name' => 'World']
]);

$this->assertEquals('Hello', $c->value('name'));
$this->assertEquals('World', $c->where('id', 2)->value('name'));
```
2. テストメソッドに`assertJsonMissingPath`が追加
```php
$this->getJson('/users/1')
    ->assertOK()
    ->assertJsonMissingPath('email'); // Never return the user email
```
3. テストメソッドに`assertCount`が追加
```php
Notification::fake();

// Assert four notifications were sent
Notification::assertCount(4);
```
4. テストメソッドに`collect()`が追加
json_decoded した状態で値を返してれる
```php
$response->collect();
$response->collect('foo');
```
5. `Arr:map()`メソッドが追加
```php
$data = ['first' => 'taylor', 'last' => 'otwell'];
$mapped = Arr::map($data, function ($value, $key) {
    return $key . '_' . strrev($value);
});
```
PHPの`arary_map`とは少し書き方が違う
```php
function cube($n) {
    return ($n * $n * $n);
}

$a = [1, 2, 3, 4, 5];
$b = array_map('cube', $a);
print_r($b)
// [1, 8, 27, 64, 125]
```

# words

# impression
テスト系のメソッド追加が多い印象、やっぱりテストは大事