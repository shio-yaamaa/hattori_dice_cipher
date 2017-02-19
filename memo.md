# 次やること

解読機能も付けることになったので、さすがにjsフォルダを暗号化用と解読用と共通に分けた方が良い気がする。

# TODO

saveのaが広がりすぎ

テーブルにするのかキャンバスにするのか。テーブルだとウィンドウサイズを調整したときに自動で追従するし、先に描画しておくので後でキャンバスで書くときにもそのままフォント使える。
キャンバスだと、作った画像をそのまま共有したりできる。

# 残念なところ

きれいな暗号にまとめられない場合が多い。
暗号の画像保存がいくつかのブラウザでサポートされていない（safariでされてないのが一番つらい）。
暗号をコピーしたタイミングでsnackbarか何かで通知した方が親切だと思うが、面倒なのでやってない。
小さいウィンドウでcanvasを表示してからウィンドウを拡大しても、canvasは大きくならない。怠慢。

# ランダムな組み合わせを作る

https://eyalsch.wordpress.com/2010/04/01/random-sample/
nCmのやり方集。

# 正規分布の中でランダムを求める

- δ: デルタ。微小な差を表す

- 正規分布(標準ガウス分布): 平均値付近にデータが集積するような確率分布。σと
- ボックス=ミュラー法: 一様分布に従う確率変数を正規分布に従う確率変数に変換する方法
- 極座標変換: x, yで表される座標を極座標(πとrを用いた座標の表し方)に変換する

ボックス=ミュラー法
極座標変換を考えることで、標準正規分布に独立に従う乱数を二つ同時に作り出してしまおうという考え方。
標準正規分布をいきなり作るのは難しそうなので、極座標変換を使うことで指数分布と[0, 2π]上の一様分布に目的をすり替える。

- 指数分布: 

# Twitter Card

Twitter Cardでimageが表示されない問題。
もしかしたら、cloud9のrobots的にダメなのかも。
https://twittercommunity.com/t/images-not-showing-up-on-summary-cards/15965/20

最低短縮数(J, R): 定数, 目安でしかない
短縮可能数(J, R): 変数
合計短縮数: 変数

短縮可能数が小さすぎる場合
- Jの短縮可能数 < Jの最低短縮数, Rの短縮可能数 < Rの最低短縮数: 無視でOK
- Jの短縮可能数 + Rの短縮可能数 < 合計短縮数: 7*7は諦める

必要短縮数が小さすぎる場合
- 合計短縮数 < Jの最低短縮数 + Rの最低短縮数: パーセンテージで割り振る
	Jの短縮数 = round(合計短縮数 * Jの最低短縮数 / (Jの最低短縮数 + Rの最低短縮数))
	Rの短縮数 = 合計短縮数 - Jの短縮数