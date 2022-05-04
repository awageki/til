# title
[How to design better APIs](https://r.bluethl.net/how-to-design-better-apis)

# author
Ronald Bluthl

# summary
API作成時のチップス集
1. 一貫性を持たせる
- スネークケースで統一
- 単数系でも複数形でも良い
- 全てのエンドポイントに同じ認証方法を使う
- ヘッダーやステータスコード、メソッドは同じものを使う
2. 日時を扱う際は「ISO 8601」を使う
- 2022-03-03T21:59:08Z
3. パブリックなエンドポイントを避け、認証を標準で入れるようにする
- オープンなAPIは別？
4. 動作監視用のエンドポイントを提供する
- GET /health など
- サービス停止時などにロードバランサーから呼び出される
5. APIのバージョン
- ヘッダーかパラメータにバージョンの情報を入れる
```
https://api.averagecompany.com/v1/health
https://api.averagecompany.com/health?api_version=1.0
```
6. APIキーによる認証を受け入れる
- サードパーティのAPIを実行するときに、APIキーを経由して認証を行う
- 認証キーは漏れた場合に備えて削除できるようにしておく
- APIキーはコードに直接書かない、環境変数を用いる（.envに記載する）
    - [参照](https://qiita.com/JrPageboy/items/bba469a19353540c6231)
7. 適正なHTTPステータスコードを使う
- 200, 201, 400など
8. 適正なHTTPメソッドを使う
- POST, GET, PATCH, PUT, DELETE
9. エンドポイントはには簡潔な名前を使う
- Good
    - GET /users →　Rtrieve users
- BAD
    - GET /getUser
10. 標準化されたエラーレスポンスを使う
- エラーのレンスポンスには詳細を記す
11. POSTでは作成された情報を返す
12. PUTよりPATCHを優先する
- PATCH: 部分的に更新
- PUT: 全てをまるっと更新
13. できるだけ具体的に
- リクエストとレスポンスで何を渡すか決めておく
14. ページネーションを使う
- page_number, page_size
15. リソースの拡張を許可しておく
- デフォルトで取得できない情報をexpandで指定して取得できるようにしておく
```
Request => GET /users/T9hoBuuTL4?expand=orders&expand=orders.items
```

# words
- via
- compress: 圧縮する、zipファイル
- language-agnostic: 言語に依存しない
- predictable: 予測可能な、predict
- specific: 具体的な、明確な

# impression
Laravelを使っているとあまり意識していないが、更新の処理にやっているのはほぼ PATCH だった

PUTのように丸ごと新しいものに置き換えるようなことはまずしていない

[参照](https://biz.addisteria.com/laravel_put_patch/)