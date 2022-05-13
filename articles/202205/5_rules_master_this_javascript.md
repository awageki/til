# title
[5 Rules to master 'this' in Javascript](https://blog.tusharcodes.tech/5-rules-to-master-this-in-javascript)

# author
Tushar Tiwari

# summary
1. 関数がnewでインスタンス化された場合、関数内のthisは空のオブジェクトになる
```javascript
function print() {
    congole.log(this)
}
new print();
// {}
```
2. 関数内で使用され、call, apply, bindによって呼び出された場合、引数をとる
```javascript
function print() {
    console.log(this);
}
const developer = {
    love: "JavaScript"
}
const bindeFn = print.bind(developer);
bindFn(); // { love: "JavaScript" }
print.call(developer); // { love: "JavaScript" }
print.apply(developer);  // { love: "JavaScript" }
```
参考記事：[JavaScriptのbindって何？？を理解する](https://reffect.co.jp/html/javascript-bind)
3. 関数がオブジェクトの内部に存在している場合、関数はオブジェクトのプロパティとなる
```javascript
const calculate = {
    a: 2,
    b: 3,
    sum: function() {
        console.log(this);
        return this.a + this.b;
    }
}
const ans = calculate.sum(); // { a: 2, b: 3, sum: f }
console.log(ans); //5
```
4. 呼び出し時に`new`を使わない場合、グローバルオブジェクトとなる（strictモードだと未定義）
```javascript
function print() {
    console.log(this);
}
print() // Window {stop: f, open: f, alert: f, ...}
```
5. アロー関数内で使用されるとき、引数となる
```javascript
function outer() {
    console.log(this); // { x : 5 }
    this.x = 10;
    const inner = () => {
        console.log(this); // { x : 10 }
    }
    inner();
}
outer.call({x: 5});
```

# words
invocation: 呼び出し

# impression
JavaScriptの`this`の挙動については完全に理解できていないため一度まとめてみる。

実務ではあまり使用することはないが、PHPやGoと比較しても良いかも。