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
<p>jqueryのライブラリ関数を呼び出した時には、変数名の頭に`$をつける`というものがある。</p>

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


## ES2015
・ES2015の使用を自分で調べて書いておく必要性があるのかもしれない