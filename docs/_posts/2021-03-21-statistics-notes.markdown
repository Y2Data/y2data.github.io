---
layout: post
date: 2021-03-21 21:44:53 +0900
title: 統計ノート
categories: Statistic
author:  Yuhao Dai
---


21st Mar. 2021

* ヒストグラム(Histogram): 度数と長方形の面積が比例するように長方形の高さを設定する
* 変動係数(Coefficient of Variation): 標準偏差を平均値で割った　$$ cv = s / \overline x $$ もの
* 偏差: $$ \sum^n_{i=1}(x_i - \overline x) = \sum^n_{i=1}x_i - n\overline x = n\overline x - n\overline x = 0 $$，一般的には $$ s^2 $$と書きます．その平方根 $$ \sigma $$が標準偏差stdである
* 平均偏差(Deviation): $$ \frac{1}{n}\sum^n_{i=1}\vert x_i - \overline x \vert $$
* 分散(Variance): $$ \frac{1}{n}\sum_{i=1}^{n}(x_i - \overline x)^2 $$
> 分散，標準偏差，平均偏差，範囲，四分位範囲と同様にデータの散らばりを表している

* 四分位範囲(Interquartile Range, IQR): $$ Q_3 - Q_1 $$　比較的外れ値の影響を受けない
* 相関関数(Correlation Coefficient): xとyを標準化したu,vの共分散であることから，x/yを正の定数倍を加えたり引いたりしても変化しない
* 国勢調査(Census): 1920年10月1日から5年ごとに実施し，日本在住の全員を対象に行われる全数調査，Internet，郵送や直接提出で参加できる
* 母集団(Statistical Population): 特徴や傾向などを知りたい集団全体を母集団という
* 標本(Sample): 実際に調査を実施する母集団の一部のこと
* 幾何平均： $$ \left(\textstyle \prod \limits _{i=1}^{n}a_{i}\right)^{\frac {1}{n}}={\sqrt[{n}]{a_{1}a_{2}\dotsb a_{n}}} $$

統計検定を合格したいということであればまだ，どのように偏差や分散が計算されるかを知らなければなりませんが，実際ではPythonを使用して分析を行うため，あまり役に立たないとも思いました．

ここで（自分へのノートも兼ねて）Pythonコードをちょっとだけまとめよう

データの指標まとめ（count, mean, std, min, 1qr, median, 3qr, max, datatype)
~~~ python
import pandas as pd

data = pd.read_csv("ch1.csv")

data.握力.describe()

"""
count    10.000000
mean     38.880000
std       8.337306
min      26.000000
25%      34.775000
50%      37.800000
75%      45.600000
max      50.900000
Name: 握力, dtype: float64
"""
~~~
これだけで，個数，平均値，標準偏差，最小最大値などが見れて，IQRも分かります

次では標準化などを記載する予定です
