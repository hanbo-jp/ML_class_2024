# 機械学習 第4回 python演習 (Numpy & Matolitlib)

# 4-1
### 以下の３つのndarrayを作成し表示する，スクリプト「ml0401.py」を作成せよ．

```
1つ目
[1 2 3 4]

2つ目
[
    [1 2]
    [3 4]
]
３つ目
[
    [1. 2.]
    [3. 4.]
]
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
### 以下の0~11を保持する1次元のndarrayをarange()を用いて作成し表示する．その後，作成した1次元のndarrayを"2×6"と"4×3"のndarrayに形状を変換し表示するスクリプトを「ml0402.py」として作成せよ．

<details> <summary>ヒント</summary>
① arange()はrange()と同じ様に使用可能<br>
ragne()の使い方は先週の資料参照()<br>
② ndarrayの形状の変更は<br>
<b>reshape()</b><br>
を使用する．<br>
</details>

<details> <summary>解答</summary>
    <img src="./img/4-2.png" width="400">
</details>



