# DevSecOps：初日

### 課題：nameserver
<p>Publicだから、nameserverは使える。</p>
<p>結論：Googleのキャッシュサーバーを適用させた。</p>

<br>

### 課題：ブルートフォースの攻撃を防ぐ
<ol>
    <li>ポートの解放をする</li>
    <li>使用しているポートの確認</li>
    <li>ssh 接続拒否</li>
</ol>

<p>⭐️　すでにバンされているものを解除して、そこからばんの設定をする。再起動をする。</p>
<br>

<hr>

## パフォーマンス
### 課題： WordPressチューニング

<p>開発環境</p>

<ul>
    <li>Nginx</li>
    <li>WordPress</li>
</ul>
<br>

<h2>keyポイント</h2><br>
<p>Webサーバ上で動くプログラムを一度起動したらしばらく待機させることによって、プログラムの開始と終了にかかる手間を減らし、動きを速くしたりWebサーバの負荷を軽減することができる仕組み</p>
<br>

### CGIの仕組みにおいて、Webサーバ上にいるプログラムさんは普段は寝ています。
<br>
<p>FastCGIが決め手</p>
<p>URL:https://wa3.i-3-i.info/word12806.html</p>

<ol>
    <li> ホームページのファイルをちょうだい</li>
    <li> 起きる</li>
    <li> 仕事をする</li>
    <li> 終わる</li>
    <li> 寝る</li>
</ol>
