---
title: "「ニューラルネットワークにおける数式と計算の概要」読んでみた"
date: 2023-06-26
draft: false
description: "How to install the Blowfish theme."
# slug: ""
tags: ["学んだこと「英語」", "Speaking", "読んでみた"]
# series: ["GitHub"]
# series_order: 1
# authors:
#  - "nunocoracao"
# showAuthorsBadges : false 
---







### ニューラルネットワークにおける数式と計算の概要

ニューラルネットワークの各層における計算は、主に行列とベクトルの足し算・掛け算によって行われます。以下はその具体的な数式と計算方法です。

---

#### 数式の概要

1. **隠れ層の計算**:
   \[
   h = f(W_1 x + b_1)
   \]
   - \(W_1\) : 重み行列（入力層から隠れ層への接続）
   - \(x\) : 入力ベクトル
   - \(b_1\) : バイアスベクトル（隠れ層用）
   - \(f\) : 活性化関数
   - \(h\) : 隠れ層の出力ベクトル

2. **出力層の計算**:
   \[
   y = g(W_2 h + b_2)
   \]
   - \(W_2\) : 重み行列（隠れ層から出力層への接続）
   - \(h\) : 隠れ層の出力ベクトル
   - \(b_2\) : バイアスベクトル（出力層用）
   - \(g\) : 活性化関数
   - \(y\) : 出力ベクトル

---

#### 行列とベクトルの計算

- **行列とベクトルの掛け算**:
  - 入力 \(x\) と重み行列 \(W_1\) の掛け算 \(W_1 x\) は、各入力要素が対応する重みによってスケーリングされ、線形結合されることを意味します。
  - 同様に、隠れ層の出力 \(h\) と重み行列 \(W_2\) の掛け算 \(W_2 h\) も同様の計算を行います。

- **バイアスの加算**:
  - バイアスベクトル \(b_1\) と \(b_2\) は、それぞれの層の線形結合後の出力に加算されます。このバイアスは、ニューロンの出力をシフトさせる役割を果たします。

- **活性化関数の適用**:
  - 活性化関数 \(f\) と \(g\) は、各層の出力に対して要素ごとに適用されます。これにより、非線形性が導入され、ネットワークが複雑なパターンを学習できるようになります。

---

### 具体的な例

#### 隠れ層の計算

1. **行列とベクトルの掛け算**:
{{< katex >}}
   \[
   W_1 = \begin{pmatrix}
   w_{11} & w_{12} \\
   w_{21} & w_{22} \\
   w_{31} & w_{32}
   \end{pmatrix}, \quad
   x = \begin{pmatrix}
   x_1 \\
   x_2
   \end{pmatrix}
   \]
   \[
   W_1 x = \begin{pmatrix}
   w_{11} x_1 + w_{12} x_2 \\
   w_{21} x_1 + w_{22} x_2 \\
   w_{31} x_1 + w_{32} x_2
   \end{pmatrix}
   \]

2. **バイアスの加算**:
   \[
   b_1 = \begin{pmatrix}
   b_{1} \\
   b_{2} \\
   b_{3}
   \end{pmatrix}
   \]
   \[
   W_1 x + b_1 = \begin{pmatrix}
   w_{11} x_1 + w_{12} x_2 + b_{1} \\
   w_{21} x_1 + w_{22} x_2 + b_{2} \\
   w_{31} x_1 + w_{32} x_2 + b_{3}
   \end{pmatrix}
   \]

3. **活性化関数の適用**:
   \[
   h = f(W_1 x + b_1)
   \]
   各要素に対して活性化関数 \(f\) を適用します。

#### 出力層の計算

1. **行列とベクトルの掛け算**:
   \[
   W_2 = \begin{pmatrix}
   w_{11} & w_{12} & w_{13} \\
   w_{21} & w_{22} & w_{23}
   \end{pmatrix}, \quad
   h = \begin{pmatrix}
   h_1 \\
   h_2 \\
   h_3
   \end{pmatrix}
   \]
   \[
   W_2 h = \begin{pmatrix}
   w_{11} h_1 + w_{12} h_2 + w_{13} h_3 \\
   w_{21} h_1 + w_{22} h_2 + w_{23} h_3
   \end{pmatrix}
   \]

2. **バイアスの加算**:
   \[
   b_2 = \begin{pmatrix}
   b_{1} \\
   b_{2}
   \end{pmatrix}
   \]
   \[
   W_2 h + b_2 = \begin{pmatrix}
   w_{11} h_1 + w_{12} h_2 + w_{13} h_3 + b_{1} \\
   w_{21} h_1 + w_{22} h_2 + w_{23} h_3 + b_{2}
   \end{pmatrix}
   \]

3. **活性化関数の適用**:
   \[
   y = g(W_2 h + b_2)
   \]
   各要素に対して活性化関数 \(g\) を適用します。

---

### まとめ

- **入力層から隠れ層、隠れ層から出力層への計算は、行列とベクトルの掛け算、バイアスの加算、および活性化関数の適用によって行われます**。
- **活性化関数は全てのノード（ニューロン）に対して要素ごとに適用され、非線形性を導入します**。

これにより、ニューラルネットワークは複雑なパターンや関係性を学習できるようになります。

