# 機械学習 第4回 python演習 (Numpy & Matolitlib)
# 4-0
### ML_classディレクトリにml04ディレクトリを作成せよ．
```bash
$ cd ~/ML_class # ML_class ディレクトリに移動する．「~」の部分は適宜変更．home直下にML_classディレクトリがある人は「~」のままでOK.
$ mkdir ./ml04
$ cd ./ml04
```

# 4-1
### 以下の３つのndarrayを作成し表示する，スクリプト「ml0401.py」を作成せよ．

実行結果：
```
$ python3 ml0401.py
[1 2 3 4]

[[1 2]
 [3 4]]

[[1. 2.]
 [3. 4.]]
```

<details> <summary>ヒント</summary>
① numpyをimportする<br>
<b>import numpy as np</b><br><br>
② ndarrayを作成する<br>
<b>n_array = np.array([1, 2, 3, 4])</b><br><br>
③ ndarrayの各要素の型を指定する<br>
<b>n_array = np.array([1, 2, 3, 4], np.float32)</b><br><br>
</details>

<details> <summary>解答</summary>
    <img src="./img/4-1.png" width="400">
</details>

# 4-2
### 以下のような0~11を保持する1次元のndarrayをarange()を用いて作成し表示する．その後，作成した1次元のndarrayを"2×6"と"4×3"のndarrayに形状を変換し表示するスクリプトを「ml0402.py」として作成せよ．

```
[0 1 2 3 4 5 6 7 8 9 10 11]
```

実行結果：
```
[[ 0  1  2  3  4  5]
 [ 6  7  8  9 10 11]]

[[ 0  1  2]
 [ 3  4  5]
 [ 6  7  8]
 [ 9 10 11]]
```

<details> <summary>ヒント</summary>
① arange()はrange()と同じ様に使用可能<br>
ragne()の使い方は先週の資料参照( )<br>
② ndarrayの形状の変更は<br>
<b>reshape()</b><br>
を使用する．<br>
</details>

<details> <summary>解答</summary>
    <img src="./img/4-2.png" width="300">
</details>

# 4-3 
### 以下のような0~99を保持する2次元のndarrayを作成し，スライスを用いて実行結果の様に表示するスクリプトを「ml0403.py」として作成せよ．

<b>ndarray</b>
```
[[ 0  1  2  3  4  5  6  7  8  9]
 [10 11 12 13 14 15 16 17 18 19]
 [20 21 22 23 24 25 26 27 28 29]
 [30 31 32 33 34 35 36 37 38 39]
 [40 41 42 43 44 45 46 47 48 49]
 [50 51 52 53 54 55 56 57 58 59]
 [60 61 62 63 64 65 66 67 68 69]
 [70 71 72 73 74 75 76 77 78 79]
 [80 81 82 83 84 85 86 87 88 89]
 [90 91 92 93 94 95 96 97 98 99]]
```

実行結果：
```
$ python3 ml0403.py
結果1
[[43 44 45 46]
 [53 54 55 56]]
結果2
[[15 16 17]
 [25 26 27]
 [35 36 37]
 [45 46 47]
 [55 56 57]
 [65 66 67]
 [75 76 77]]
```

<b>スライスについては講義資料を参照</b>

<details> <summary>解答</summary>
    <img src="./img/4-3.png" width="400">
</details>

# 4-4
### 4-3の2次元のndarrayから6で割り切れる要素を抜き出し，リストに格納し，対象の要素を全て抽出後表示するスクリプトを「ml0404.py」として作成せよ．for文を必ず使うこと．

実行結果：
```
[0, 6, 12, 18, 24, 30, 36, 42, 48, 54, 60, 66, 72, 78, 84, 90, 96]
```
<details> <summary>ヒント</summary>
    ① for文を用いてndarrayから要素を１つずつ抽出し，6で割り切れるかif文を用いて判定すれば良い．<br>
    ② 抽出した値はappend()でリストに追加する．<br>
</details>

<details> <summary>解答</summary>
    <img src="./img/4-4.png" width="400">
</details>

# 4-5
### 4-4の課題をfor文を使わないで実装せよ．スクリプト名は 「ml0405.py」とせよ．

実行結果：
```
[ 0  6 12 18 24 30 36 42 48 54 60 66 72 78 84 90 96]
```

<details> <summary>ヒント</summary>
    ① 第４回講義資料のスライド25-26を参照．<br>
    <b>
        n_array = np.array([1, -2, 3, -4])<br>
        print(n_array[n_array>0])<br>
    </b>
    ↓<br>
    ↓<br>
    <b>出力：[1 3]<br></b>
</details>

<details> <summary>解答</summary>
    <img src="./img/4-5.png" width="400">
</details>


# 4-6
### 以下のndarrayのna1とna2の四則演算の結果を表示するスクリプトを「ml0406.py」として作成せよ．
```
na1
[[3 5]
 [9 4]]

na2
[[4 3]
 [7 1]]
```

実行結果：
```
$ python3 ml0406.py
足し算：
[[ 7  8]
 [16  5]]
引き算：
[[-1  2]
 [ 2  3]]
掛け算(アダマール積)：
[[12 15]
 [63  4]]
割り算：
[[0.75       1.66666667]
 [1.28571429 4.        ]]
```
<details> <summary>解答</summary>
    <img src="./img/4-6.png" width="300">
</details>

# 4-7
### 以下の2つのndarrayの行列積を求めるスクリプト「ml0407.py」を作成せよ．
```
na1
[[-6 5]
 [-3 4]]

na2
[[4 -4]
 [1 1]]
```

実行結果：
```
$ python3 ml0407.py
[[-19  29]
 [ -8  16]]
```

<details> <summary>ヒント</summary>
    行列積の計算は<br>
    <b>np.dot()</b><br>
    を使用する．
</details>

<details> <summary>解答</summary>
    <img src="./img/4-7.png" width="300">
</details>

# 4-8
### 以下の4つのndarrayについて次の行列積を((na1×na2)×na3)×na4の順で計算するスクリプト「ml0408.py」を作成せよ．この順序で掛け合わせるのエラーとなるので，適宜「転置」を用いることで計算すること．
```
na1:
[[-2  5]
 [-3  4]]
na2:
[[ 4 -4  1]
 [ 1 -1  3]]
na3:
[[-6  5  4]
 [-4 -7  1]
 [-1 -2  4]
 [ 1  2  3]]
na4:
[[ 2 -2  1 -1]
 [ 1  1 -1  2]]
```

実行結果：
```
$ python3 ml0408.py
[[169 124]
 [271 151]]
```

<details> <summary>ヒント</summary>
    ①行列の転置は<br>
    <b>ndarray.T</b><br>
    を使用する．<br>
    ②<b>ndarray.shape</b>を使用すると行列の形状の確認をすることができる．<br>
</details>

<details> <summary>解答</summary>
    <img src="./img/4-8.png" width="500">
</details>

# 4-9
### 先週の演習3-17,3-18,3-19で作成した「MyAddMatrices.py」「MySubMatrices.py」「MyMulMatrices.py」をml04ディレクトリにコピー後，numpyを使用し書き換えよ．3ファイルを読み込み実行する「ml0409.py」を作成せよ．「ml0409.py」と「MyAddMatrices.py」は以下にある例をコピー＆ペーストして良い．
3ファイルのコピー：
```bash
$ cp ../ml03/MyAddMatrices.py .
$ cp ../ml03/MySubMatrices.py .
$ cp ../ml03/MyMulMatrices.py .
```

<b>MyAddMatrices.pyをnumpyを使って実装した例．
これを参考にMySubMatrices.pyとMyMulMatrices.pyを書き換えよ．</b>
```python
import numpy as np

class AddMatrices:
    def __init__(self, Mat1, Mat2):
        self.mat1 = np.array(Mat1)
        self.mat2 = np.array(Mat2)
    
    def calculate(self):
        result = self.mat1 + self.mat2
        return result
```

<b>ml0409.pyの例</b>
```python
import sys
sys.path.append("~/ML_class/ml04")
from MyAddMatrices import AddMatrices
from MyMulMatrices import MulMatrices
from MySubMatrices import SubMatrices

Mat1 = [[1,2,3],[4,5,6],[7,8,9]]
Mat2 = [[1,4,7],[2,5,8],[3,6,9]]

MyClasses = [AddMatrices, MulMatrices, SubMatrices]

for Class in MyClasses:
    each_class = Class(Mat1, Mat2)
    result = each_class.calculate()
    print(result)
    print()
```

<details> <summary>解答(MySubMatrices.py)</summary>
    <img src="./img/4-9-1.png" width="300">
</details>

<details> <summary>解答(MyMulMatrices.py)</summary>
    <img src="./img/4-9-2.png" width="400">
</details>

# 4-10
### 以下のソースコードをコピー＆ペーストし実行させよ．スクリプト名は「ml0410.py」とせよ．
```python
import numpy as np
import matplotlib.pyplot as plt #① matplotlibのimport
x = np.arange(0, 6, 0.1) #② x軸の値の生成
y1 = np.sin(x) #③ y軸の値の生成
y2 = np.cos(x) #③ y軸の値の生成
plt.plot(x, y1, label="sin") #④ xとy1をプロット
plt.plot(x, y2, linestyle="--", label="cos") #④ xとy2をプロット
plt.xlabel("x")
plt.ylabel("y")
plt.title("sin&cos")
plt.legend()
# plt.show() #⑤ 図の描画
plt.savefig("./sin_cos.png") #⑤ 図の保存
```
