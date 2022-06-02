# title
[5 Tips For Writing Cleaner Code](https://domtech.hashnode.dev/5-tips-for-writing-cleaner-code)

# author
Dominic Duke

# summary
1. 不必要なネストを避ける
- `Return Early`デザインパターン
- if文をガード条項として使用し、エラーをチェックし、それ以上のコードを実行する前にリターンする
- if/elseの使用や不必要なネストを避けることができる
- 「早く返す」アプローチはコードをより直線的に、綺麗に、読みやすくする
```javascript
function saveItem(item) {
  if (item == null) return;

  console.log("Validating");
  if (!item.isValid) return;

  console.log("Saving item")
  item.save();
}
```
2. 関数のパラメータにオブジェクトの再構築を使用
- `Object Destructuring`
```javascript
function getFullName({ firstName, lastName }) {
    return `${firstName} ${lastName}`;
}
```
3. Pure Functions で副作用を避ける
- 関数の中で外部変数を使わない
- 新しい値を返すようにする
```javascript
function addThree(number) {
    return number + 3;
}
```
4. 関数をシンプルに保つ
- 関数は一つのことだけに責任を持つようにする
```javascript
function signUp() {
}
function validate() {
}
```
5. 意味のある変数名を使う
- 関数名には動詞を使う、`validatePassword()`
- boolean型、`isValidPassword`
- 配列は複数形、`const animals = ["cat", "dog"];`
- コールバック関数を使う際、イテレート時には意味のある名前にする
```javascript
animals.forEach((animal) => {
    console.log(animal);
});
```

# words
- inherently: 本質的に
- negate: 否定する
- assume: 仮定する、思い込む、決めてかかる

# impression
Return Early については他の記事も読んだが賛否両論ある感じ

プロダクトの中で一貫性を持たせることは大事

例外処理など早めに返す方が良いケースもあるためその場合は採用ありか（知見が少ないので学習必要）