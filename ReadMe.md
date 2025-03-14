

### 参考ページ
https://www.ibnet.ne.jp/column/web/201008/

http://inkscapedesign.web.fc2.com/basic/move.html

https://liginc.co.jp/312143
https://qiita.com/m_shinada/items/b18f41972120c3caeb69
https://qiita.com/chitomo12/items/10e251c8ac470dad8541


https://developer.mozilla.org/ja/docs/Web/SVG/Attribute/d

### SVG要素の意味

※xは縦軸、yは横軸を表す。<br>
`m x,y`のように指定する。
※各コマンドの大文字・小文字の違いは以下の通り
大文字：絶対座標を表す
小文字：直前座標からの相対座標を表す


#### MoveToパスコマンド
##### M/m
カレント座標の移動を意味する。
つまり、最初の指定ではスタート座標を表す。以降は、前の座標からの相対座標を表す。

#### LineToパスコマンド
直線を引くコマンド。

##### L/l
x,yの両方を座標指定し、その場所までの直線を引く。

##### H/h
xを座標指定し、その場所までの直線を引く。

##### V/v
yを座標指定し、その場所までの直線を引く。

#### 3次ペジェ曲線
4点で定義される滑らかな曲線を引くコマンド。