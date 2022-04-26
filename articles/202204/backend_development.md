# title
[Backend Development Is Not Hard](https://mudit.hashnode.dev/backend-development-is-not-hard)

# author
Mudit Mishra

# summary
- バックエンド開発は皆が思っているほど難しくはない
- ただし、バックエンド開発が簡単、といっている訳ではない
- Node.js、Expressを使ってHTTPサーバーの構築をハンズオンで行う
- たったの6ステップ、たったの7行でローカルでHTTPサーバーが構築できる
- バックエンドエンジニアになって欲しい訳ではなく、興味を持ってもらうことがこの記事の目的

# code
```javascript
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (request, response) => {
     response.send('<h1>Hey👋</h1>');
})
app.listen(port, () => {
     console.log(`Server is running at port ${port}`);
})
```

# words
- assumed：想定
- intimidating：威圧的
- intermediate：中級
- via：経由
- intimidate：脅す

But as soon as you'll clear your basics this will be a **cakewalk** for you.


