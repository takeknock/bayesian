# 第6章
## 推論のモデル
計測データxが観測される
この世界の状態wを推論する

### 例
画像2枚から
画像から人物を特定

### 推論の種類
- 連続の場合：regressionと呼ばれる
- 離散の場合：clasificationと呼ばれる

### 推論の具体的な目標
取りうるすべてのwの分布に対して、xが得られたときのwの条件付き確率を得る。
P(w|x)を得る。

### 具体的な手順
- modelを決める：xとwを結びつける関係式の族。パラメータΘを持つ。
- 学習：モデルのパラメータΘを学習。
- 推論：得られたΘを用いて、P(w|x)を返す

### Types of model
- discriminative model
計測data xに対して、wを推測。Pr(w|x)を出力
- generative model
どういうwのときにxが得られやすいか。観測データxの確率分布Pr(x|w)を出力。得られた確率分布を使うことで新たなデータを生み出すことができるのでgenerative modelと言われる。

## Discriminative model
### モデル化方法
1. wの確率分布(Pr(w))を選ぶ
1. wの確率分布のparametersをxの関数にする
1. 得られた関数はparameters　Θを受け取る。
（wはΘにも間接的に依存）

Learning algorithm: 訓練データx, wからparameters Θを学習
Inference algorithm: Pr(w|x)を評価


## Generaive model
### モデル化方法
1. xの確率分布(Pr(x))を選ぶ
1. 上記確率分布のパラメータをwの関数にする
1. wの関数はパラメータΘを取る

Learning algorithm: 訓練データx, wからparameters Θを学習
Inference algorithm: Pr(w)を定義してベイズの公式からwの事後確率（Pr(w|x)）を得る

### Pros.
- データの欠損に強い。(xの分布を求めるので、欠損値をその分布に従って生成できる)

### Cons.
- 推論にベイズの公式を用いた計算が必要
