# 開発に取り入れたいもの

## リーダブルコードより

### フォーマット規約
「JavaScript：The Good Parts」はコンストラクタを使って呼び出される関数は大文字で始め。
通常の関数は小文字で始めているように著者が提唱。
```
// これがBetter

var x = new DatePicker();
var y = pageHight();
```
<p>jqueryのライブラリ関数を呼び出した時には、変数名の頭に`$をつける`という慣習がある。</p>

```
var $all_images = $("img");
var height = 250;
```
<p>HTMLとCSSの書き方</p>
<p>idやclassの区切り文字にはアンダースコアを、classにの区切り文字にはハイフンを使うの規約が有力</p>

```
<div id="middle_column" class="main-content">...</div>
```
<hr>

## 意味のある並び

case1: 引数が明示的になる。

```
CheckFullName("Doug Adams" , "Mr.Dougles Adams" , "");
CheckFullName("Jake Brown" , "Mr.Jake Brown III", "");
CheckFullName("No Such Guy", ""                 , "no match found");
CheckFullName("John"       , ""                 , "more than one result")
```

case2: タイプミスにも気づくことができる。

```
#POSTのパラメータをローカル変数に割り当てる

details  = request.POST.get('details');
location = request.POST.get('location');
phone    = equest.POST.get('phone');
email    = request.POST.get('email');
url      = request.POST.get('url');
```

また以上のようなものであれば、意味のある並びをしていくのが良いのかもしれない。

<li>対応するHTMLの`inputタグ`順に並べるとか</li>
<li>最重要のものから重要順に並べていくとか</li>
<li>アルファベット順に並べていくとか</li>
<hr>

## コードの欠陥にコメントをつける
<table>
    <tr>
        <th>記法</th>
        <th>典型的な意味</th>
    </tr>
        <tr>
            <td>TODO:</td>
            <td>あとで手をつける</td>
        </tr>
        <tr>
            <td>FIXME:</td>
            <td>既知の不具合があるコード</td>
        </tr>
        <tr>
            <td>HACK:</td>
            <td>あまり綺麗じゃない解決策</td>
        </tr>
        <tr>
            <td>XXX:</td>
            <td>危険！大きな問題がある</td>
        </tr>
</table>

<hr>

## スーパー学び

case：Ajaxエラーが生じたときように書いて置いて良いかもしれない。

```
.fail(function(data, textStatus, jqXHR){
    console.log("fail");
    // errorの場所を特定する
    console.log("XMLHttpRequest : " + XMLHttpRequest.status);
    console.log("textStatus     : " + textStatus);
    console.log("errorThrown    : " + errorThrown.message);
});
```
<hr>

## ES2015
・ES2015の使用を自分で調べて書いておく必要性があるのかもしれない
<br>

### 変数・定数の概念
varは次のデメリットが存在する
エラーの温床となってしまうので、変数や定数を使うことが推奨されている。
<li>再宣言できて使い回しができる</li>
<li>上書きができてしまう</li>
<br>

<p>let：上書き可・再宣言不可</p>

```
let val2 = "let変数";
console.log(val2);

val2 = "let変数を上書き";
console.log(val2);

//　これはエラーになってしまう
let val2 = "let変数を再宣言";
```

<p>const：上書きも再宣言も不可</p>

```
const val3 = "変数1";

// 上書きエラー
val3 = "変数2";

// 再宣言エラー
const val3 = "変数3";

```

<hr>

### テンプレート文字列

<br>
<p>文字列結合の記述が簡潔になり見やすくなった</p>

<p>変更前</p>

```
const name = "田中";

hello() {
    return '私の名前は'+name+'です。';
}
```

<p>変更後</p>

```
const name = "田中";

hello() {
    return `私の名前は${name}です。`
}
```

<hr>

### アロー関数

<p>functionよりも短い記入の仕方でできてしまう</p>

<p>変更前</p>

```
function func1(value){
    return value;
}

// execute

console.log(func1("func1です"));

```

<p>変更後</p>

```
const func1 = (value) => {
    return value;
}

// execute

console.log(func1("func1です"));

```

<hr>

### デフォルト値

<br>
<p>変更前：引数を渡さなかった場合</p>

```
const sayHello = (name) => {
    console.log(`こんにちは！${name}さん！`);
}

// execute
// こんにちは！undefinedさん!になってしまう。

sayHello();

```

<p>変更後</p>

```
const sayHello = (name = "ゲスト") => {
    console.log(`こんにちは！${name}さん！`);
}

// execute
// デフォルトでもこんにちは！ゲストさん!となる

sayHello();

```

### モジュールimportの整理
https://jsprimer.net/basic/module/