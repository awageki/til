# title
[How to setup and scale the perfect websocket server for your Laravel project](https://aboutyou.tech/blog/setup-and-scale-a-websocket-server-with-laravel/)

# author
Simon Ellensohn

# summary
- どの方法が目的に合っているか概要を知っておくべき
Laravel Echo Server
- LMSにで初めに推奨された方法
- NodeJSで書かれている
- ボランティアでメンテされており、レガシーになりつつある（最後のバージョンが2020）

Soketi
- 新しい手法
- NodeJSとCで書かれている
- Pusherのプロトコルを使用
- Dockerコンテナで管理、スケーリングが可能

Laravel Websockets
- 最も人気のある方法
- PHPのネイティブで使用可能（他にサーバーを用意する必要がない）
- PHP React ライブラリをベースに作成されている
- リリース時期未定だがベータ版のver2では並列的にスケール可能（Redisを使うなど？）

# words
- incorporate: 組み込む
- atypically: 例外的に
- integrate: 統合
- pros and cons: 長所と短所
- implementation: 実装

# impression
日本語の記事で比較している記事がなかったので需要あるかも