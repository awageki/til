# title
[Modern tools for PHP developers](https://blog.logrocket.com/modern-tools-php-developers/)

# author
Maruo Chojrin

# summary
- この記事では modern PHP とはv7以降のものを指している
- PHP7は2015/12/3リリースで多くの新機能が追加された
    - 型
    - アロー関数
- デバッガー
    - var_dump, echo, print_r を使ったデバッグはセキュリティ面からも良くない
    - Xdebug, ZendDebugger, phpdbg
- 依存関係
    - PEAR→Composer
    - composerでは全てのプロジェクトに独自の composer.json と vendor があり、設定を保存している
    - あとバージョン管理も
- MVCフレームワーク
    -  Symfony, Laravel
- テスト自動化
    - phpUnit
- 静的解析ツール
    - phpstan, psalm, exakat
    - CIやGit Hooksの一部として行うとコードの品質が担保される
- Deployツール
    - Deployer
    - 自動で本番やSTG環境にデプロイするツール
    - GitHub Actionsの自動デプロイと同じ？
    - [GitHub Actionsだけではデプロイできない](https://zenn.dev/tokku5552/articles/laravel-github-actions)
- 非同期実行
    - Fibers
    - v8からPHPでも非同期処理ができるようになった
    - あまり実用的ではない？
    - [PHPで書いて覚える非同期処理](https://speakerdeck.com/hanhan1978/php-async-programming?slide=136)

# words
- reputation: 評判
- suck: 吸う、舐める、ひどい
    - Suck on a straw
    - That resturant has a nice vibe, but the food sucks
- execution: 実行
- prominent: 目立つ、主要な
- precise: 正確、精密、的確

# impression
知っているツールが多いが実際にできていないことも多い。
全てを一度に導入するのは難しいのでまずは一つずつ自分で試してみることが大事か
versionがアップした際の新機能も人と通り試してみる
「PHPで書いて覚える非同期処理」で書かれていた echo サーバーの写経をしてみたくなった