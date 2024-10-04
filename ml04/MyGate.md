# 機械学習 第4回 python演習 (パーセプトロンで論理回路を表現する)

# 4-P1
### 以下の「_____」を適切に埋めて,「MyGate.py」を作成せよ．難しく見えるかもしれないが，4-9で作成したMyAddMatrices.pyやMyMulMatrices.pyと構造はほぼ変わらない．

```python
import numpy as np

class Gate:
    def __init__(self, w1, w2, b):
        self.w = _____ # w1とw2を要素に持つ1次元のndarrayを作成
        ____.b = b # bをどこからでも参照可能にする

    def calculate(self, x1, x2):
        x = _____ # x1とx2を要素に持つ1次元のndarrayを作成
        mul = ____ # xとself.wのアダマール積
        aff = np.sum(mul) + self.b # np.sum(mul)→mul内の全要素の総和
        if aff <= 0:
            return ____ # affineの結果が0以下の時
        else:
            return ____ # affineの結果が1より大きい時
```
### Point
### ①__init__(self, w1, w2, b)のw1, w2, bはfloat型の変数である．
### ②np.sum(mul)とすると1次元ndarrayであるmul内の全ての要素を足した合わせることができる．
### ③np.sum(mul) + self.bでは，np.sum(mul)の結果はnp.int64型であるが，通常のint型とみなしてOK．よってこの計算は "int型 + float型" である．

<details> <summary>解答</summary>
    <img src="./img/4-P1.png" width="300">
</details>

# 4-P2
### ANDゲートのx1とx2の値とyの値を格納した以下のXsとYsというリストをfor文を1個だけ用いて出力するスクリプトを「ml04P02.py」として作成せよ．

```python
Xs = [[0, 0], [0, 1], [1, 0], [1, 1]]
Ys = [0, 0, 0, 1]
```

実行結果：
```bash
$ python3 ./ml04P02.py
0 0 0
0 1 0
1 0 0
1 1 1
```
<details> <summary>ヒント</summary>
    ①zip()を使うとXsとYsから同時に要素を1個ずつ取り出すことができる．<br>
    <b>for X, Y in zip(Xs, Ys):</b><br><br>
    ②上記for文の変数であるXはサイズ2のリストである．リストからの値の取り出したは，<br>
    <b>A = [0, 0]<br>a1, a2 = A</b><br>
    とすると一気に2つの値を取り出すことが可能である．<br>
</details>

<details> <summary>解答</summary>
    <img src="./img/4-P2.png" width="300">
</details>

# 4-P3
### ANDゲートのパラメータw1, w2, bを以下の値として，MyGate.pyからGateクラスを呼び出し，ANDゲートを表現する(計算する)スクリプトを「ml04P03.py」として作成せよ．「_____」を埋めれば良い．

```python
w1, w2, b = 0.5, 0.5, -0.7
```

実行結果：
```bash
$ python3 ./ml04P3.py
0 0 0 pred_y: 0
0 1 0 pred_y: 0
1 0 0 pred_y: 0
1 1 1 pred_y: 1
```

<b>ml04P03.py</b>
```python
import sys
sys.path.append("~/ML_class/ch04")
from MyGate import _____
import numpy as np

Xs = [[0, 0], [0, 1], [1, 0], [1, 1]]
Ys = [0, 0, 0, 1]

w1, w2, b = 0.5, 0.5, -0.7

AND = Gate(_____, _____, _____)
for X, y in zip(Xs, Ys):
    x1, x2 = X
    pred_y = AND._____(x1, x2)
    print(x1, x2, y, "pred_y:", pred_y)
```

<details> <summary>解答</summary>
    <img src="./img/4-P3.png" width="300">
</details>