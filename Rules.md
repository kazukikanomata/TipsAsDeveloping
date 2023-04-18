# Rules for Developer
## ブランチ
mainブランチを本番のブランチとして定義し、それを元にブランチを切っていく

### 切り方
<li>自分の名前 / 作業内容の名前</li>

```
// 今いるブランチを確認する。

$ git branch
```

```
// ブランチを作成する　ex:　$ git branch waltdisney/bugfix 

$ git branch 名前/作業内容
```
```
// 上でつけた名前のブランチに変更

$ git checkout 名前/作業内容
```
<hr>

## push後の流れ
<br>

<ol>
    <li>プルリクエストを作って（issueがあるならタグをふる）。みてもらいたい箇所なぜその実装をしたのかを書くのがbetter</li>
    <li>依頼された人はレビューをする。</li>
    <li>問題ないならmainブランチにマージする。</li>
    <li>手元の開発環境に戻り、mainブランチに変更する</li>
    <li>pullして取り込む</li>
</ol>
<br>

### ブランチを変更し、mainの変更を取り込む
```
$ git checkout main

$ git pull
```

<hr>

## CSSインデントのルール
波括弧の位置はこれで統一する

```
body {
    font-family: Arial, sans-serif;
}
```
<hr>

```
<!-- この下からは今後こうしていければいいなと思いました。 -->
```

## コメント

### case:　欠陥を見つけた時
<br>

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
<br>
<hr>

## フォーマット規約 『リーダブルコード』より
<br>

### JavaScript
<br>
「JavaScript：The Good Parts」はコンストラクタを使って呼び出される関数は大文字で始め。
通常の関数は小文字で始めているように著者が提唱。
<br>

```
var x = new DatePicker();
var y = pageHight();
```

### jquery
<br>
<p>jqueryのライブラリ関数を呼び出した時には、変数名の頭に`$をつける`という慣習がある。</p>

```
var $all_images = $("img");
var height = 250;
```
### HTMLとCSSの書き方
<br>
<p>idやclassの区切り文字にはアンダースコアを、classにの区切り文字にはハイフンを使うの規約が有力</p>

```
<div id="middle_column" class="main-content">...</div>
```
<hr>