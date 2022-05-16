# title
[Session vs JWTs - A Complete Guide to Authentication](https://blog.dhruva.is-a.dev/sessions-vs-jwts-a-complete-guide-to-authentication)

# author
Dhruva Srinivas

# summary
authを実現する2つの方法
1. Sessions
2. JSON Web Tokens(JWTs)

- Session Store(Redis)
- Redisはスピードが速いのでよく使われるセッションストアである
- 柔軟にコントロールしやすい
- 埋め込みやすい
- セッションストアは公開されずサーバーに保存されるため、傍受される可能性がない

- JWTs
- Bearer Tokenをヘッダーに入れる
- cookieに保存、localStorageには保存しない→XSS攻撃に対して脆弱
- ブラックリスト方式
- JWTは安全ではないため機密性の高いユーザーデータは保存してはいけない、userIdのようなサーバーがユーザーを知るために必要な最低限の認証情報のみ保存する


# words
- allocate: 割り当てる
- vulnerable: 脆弱
- hence: 従って、それゆえに

# impression
実装が簡単で、より安全なためSessionsを進めている

聞いたことはあるが十分に理解できていない単語もあったため深掘りしてみたい
