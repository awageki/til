# title
[Standard JSON API response format](https://medium.com/@bojanmajed/standard-json-api-response-format-c6c1aabcaa6d)

# author
MaJeD BoJaN

# summary
- JSONのスタンダードなんてものはない
- APIには Success と Error の2種類ある

4つの主なレスポンス
1. error_code
2. Success → true or false
3. Message
4. data

```json
{
  "success": true,
  "messsage": "User logged in successfully",
  "data": {}
}
```

# words

# impression
バックエンドでAPIのみ作成することも多いので、JSONのフォーマットを決めておくのはメリットがある

本記事以外にも探してJSONフォーマットのベストプラクティスを決めたい