# title
[Restructuring a Laravel Controller using Services, Events, Jobs, Actions, and more](https://laravel-news.com/controller-refactor)

# author
PovilasKorop

# summary
- 構造をどうするか、について明確な答えはない
- ロジックはControllerに書くべきではない、ではどこに書くべきか
- 将来そのコードをメンテナンスするチームが選ぶ必要がある

Controllerの3つの役割
1. ルートや他の入力からパラメータを受け取る
2. ロジッククラスやメソッドを呼び出し、パラメータを渡す
3. 結果を返す：ビュー、リダイレクト、JSONリターンなど
つまり、Controllerはメソッドを呼び出すのであって、Controller自身の中でロジックを実装するわけではない

チップス
1. バリデーションは`Request`クラスで行う
2. ユーザーの作成は`Service`クラスで行う
- Controllr内で`new UserService()`を行う必要はない

Service Class の責務
- Service はパラメータを受け取るだけで、それがどこから来たか分からない「ブラックボックス」のように振る舞うべき

Action クラス
- ユーザーに関する処理をUserServiceクラスにまとめて書くのではなく、Actionクラスに分割して書く
- Single Reposibility Principle の観点からは理にかなっているが、クラスを分けるのがどうか、という意見もある

# words
- fancy: 派手な

# impression