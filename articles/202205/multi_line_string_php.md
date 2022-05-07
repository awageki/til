# title
[How to Create a Multi-line String in PHP-3 Methods](https://code.tutsplus.com/tutorials/how-to-create-a-multi-line-string-in-php-3-methods--cms-39425)

# author
Monty Shokeen

# summary
PHPで改行する3つの方法
1. \n, \r, \r\n
ダブルクォーテーションの中でしか利用できない（シングル×）
```php
$string = "Hello World\nGood By";
```
- プラットフォームによって動作が異なる（Windows: \r\n, Linux or MacOS: \n）
2. PHP_EOL
```php
$string = "Hello World". PHP_EOL. "Good By";
```
3. Heredoc & Nowdoc
Heredoc: ダブルクォーテーションで囲った形
Noedoc: シングルクォーテーションで囲った形
```php
$string = <<<HEREA
    Hello World
    Good By
HEREA;
```
Heredocは定義済みの変数が使用できる


# words
- concatenate: 連結
- involve: 関与する

# impression
短めなら`PHP_EOL`、長めなら`HEREA`か。