# Videio
[VSCodeでPHPをデバッグする方法](https://www.youtube.com/watch?v=Rnos6bMnTGo)

# 事前準備
- XdebugをPCに入れておく
    - `phpinfo();`でインストール済みか確認
    - `xdebug-client-port`でポート番号を確認
    - VSCodeの拡張機能を入れる(PHP Debug)
- launch.json ファイルを作成する
    - portを確認したものに変更
    - 左：Docker、右：ローカル

```json
【pathMappingsの設定例】
"pathMappings": {
    "/var/www/html":"D:/test_project/web"
}
```

# デバッグの実行
- スタート
- ブレークポイントを設置
- ステップイン or F11で一行ずつ進めていく →　関数の中に入る
- ステップオーバー →　関数の中に入らない
- ステップアウト：関数の処理を飛ばす