# title
[Understand MVC Architecture in 5 mins](https://www.crio.do/blog/understand-mvc-architecture/)

# author
Joidev Singh Bhui

# summary
Model, View, Controller
- ビジネスロジックはModelに書く
レストランの例え
- Model：シェフ、冷蔵庫
- View：メニュー、食事（User）
- Controller：ウェイター
注文アプリの例え
- Model: ユーザーやメニュー、食事に関する全てのデータを扱う
- View: 商品一覧、食事の情報、ショッピングカートなど全てのUI
- Controller: Viewの動作を起点にModelにデータを問い合わせて、Viewに返す
特徴
- それぞれの層で開発を分けることができる、Viewはフロントエンドなど
- 言語が違っても同じ似たパターンで設計されている
メリット（参考：https://qiita.com/suema0331/items/673fb9f342d802d0d13a）
1. Loosely coupled: 疎結合 → お互いに依存していない
2. Highly cohesive: 高凝集性 → 責任範囲が明確
3. Rapid Development: 1,2の特徴により複数のチームで同時に開発できる
4. Easier to test and debug: 1,2の特徴によりテストとデバッグがしやすい
MVCの限界
- 複雑になるケースもある

# words
- appropriate: 適切な
- refrigerator: 冷蔵庫
- residential: 居住の
- overarching: 包括的な
- hense: 従って、それゆえ
- interdependence: 相互依存

# impression
普段書いているLaravelもMVCモデルのためイメージしやすい

チームに経験が浅い人もアサインしてくるので説明用に使いたい