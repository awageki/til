# title
[Vue vs React: What to choose in 2021]](https://dev.to/digitalyaops/vue-vs-react-what-to-choose-in-2021-3bc)

# author
Digitalya

# summary
Performance
- メモリの割り当てや起動時間は`Vue`の方が少し優れている
- 実行時には`React`に軍配が上がる
- `Vue`はコンポーネント変更時に再レンダリングしない（`React`はする）
- `Vue`の方がフレームレートが高い
Popularity
- Githubスター数、`Vue`:196k、`React`:189k
- 採用市場では`React`の方が多い
State Management
- Redux、Vuex
- state（全てのUIコンポーネント間で共有されるデータのこと）の管理方法が違う
- `Vue`では local state の管理は不要だが、大きなプロジェクトになると管理用のライブラリが必要となる
Key Differences

SEO
- SPA でもインデックスできるようになったと Google は言っているが困難では
- Server-Side-Rendering を使用することでサーバー上で対応は可能
Which is better
- Vue is better if
    - 早く解決したい
    - 複雑なアプリではない
    - リソースと時間に限りがある
    - 経験の浅い開発者が多い
    - クリーンなコードを好む
- React is better if
    - 複雑なアプリケーションやSPAを開発したい場合
    - 将来的にアプリケーションの機能を大幅に拡張する予定がある場合
    - モバイルアプリが必要な場合
    - HTMLよりもJavaScriptを好むチームである
    - チーム内に経験豊富なReact開発者がいる場合
- Reactはテンプレートがないので高度なHTMLの知識が必要
- Vueの方が少し高速だが、Reactの方がAPIオプションが豊富
- どちらが良いか
    - 何を開発するかによる
    - 両方のフレームワークで小さく試してみて選択するのが良い

# words
- intuitive: 直感的な
- optimization: 最適化
- appropriate: 適切な
- 

# impression
Vue を再学習するために、読んでみた

以前両方触った際はReactのJSXの方が直感的だったが、以降バージョンも変わっているため再度触ってみる