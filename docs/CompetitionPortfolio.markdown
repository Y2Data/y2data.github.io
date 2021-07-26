---
layout: default
date: 2021-06-28 14:16:15 +0900
Title: Competition Portfolio
categories: Essay
author:  Yuhao Dai
---

## [Kaggle](https://www.kaggle.com/tim2dai):

1. [SETI](https://www.kaggle.com/c/seti-breakthrough-listen)
  Finish date: 29th July, 2021
  Approach I took:
    1. I started late in the competition, and there was already public notebooks that takes the AUC score to 0.970. I copied one of them and started to tune the hyper-parameter.
    2. The model wasn't even overfitting on the training data too well which indicates a need for bigger model, but before that I spent 2 days on looking at the data.
    3. I found that data that was labeled "true" was hard to understand the reason behind. I tried to artificially add a line in between images to imitate the signal (for 30 true labels) and it did not improve the performance. At this point the attempt to artificially generate some training data becomes impossible, leaving the only option to augmentations.
    4. After some simple augmentations, the model started to overfit to 0.991 AUC on best epoch, and 0.988 on CV. I used ResNet34d instead of originally proposed ResNet18d, and increased the batch size, this got me on the leaderboard at around 100 place, with an AUC of 0.978.
    5. The double data leakage happened, the leaderboard was taken over by cheating 1.000 AUC Kagglers, so I turned my eyes to another competition. (Not Fixed at time of writing, 29th of June).

1. [SETI](https://www.kaggle.com/c/seti-breakthrough-listen)
  終了日：2021年7月29日\n
  取ったアプローチ：
    1. コンペへは参加し遅れたため、既に高得点のパブリックノートブックがありました（AUC0.970)。一つコピーしてからハイパーパラメーターのチューニングをしていました
    2. トレーニングデータでさえ過剰適合が起きないため、より強力なモデルが必要と思ったが、その前に二日間、データをひたすら見つめていました。
    3. 「True」とラベル付けられたデータでさえ、何の根拠を持ってTrueと言っているのかがわかりませんでしたが、人工的に複数画像に渡る線の入った画像を作り、Trueとラベル付けてSignalを模倣していたが、モデルのパフォーマンスが上がりませんでした。この時点で人工的にデータを合成するのが不可能だと判断し、画像増強に目を向けました。
    4. いくつか簡単な増強後、移転学習のモデルをResNet18dからより大きいResNet34dに換え、BatchSizeを増やした結果、Epochで最高0.991と、CVで最高0.988のAUCが出たが、LBでは0.978に足止まりで100位前後しか上がりませんでした。
    5. この時点でコンペのテストデータから二重のリークが発生し、LBがリークを使用したAUC1.000の人に占められていたため、一度別のコンペに目を向けることにしました。（まだ修復されていません。6月29日）

----------

2. [Google Smartphone Decimeter](https://www.kaggle.com/c/google-smartphone-decimeter-challenge)
  Finish date: 5th August, 2021
  Approach I took:
    1. This is a competition that required highly in both domain knowledge and pre-processing, so I spent two days on researching all the things I should know about GNSS.
    2. Imitating the SETI notebook, I wrote a baseline notebook that would read, one-hot encode and combine all the data, and run a simple lightgbm model. This was scored poorly at around 1100.
    3. Something was fundamentally wrong about the approach, so I rewrote the notebook in Keras, which can utilize the TPU.


2. [Google Smartphone Decimeter](https://www.kaggle.com/c/google-smartphone-decimeter-challenge)
  終了日：2021年8月5日\n
  取ったアプローチ:
    1. このコンペが高度なドメイン知識とデータの前処理を要求するため、二日間データをみてGNSSについて調べてみました。
    2. SETIのノートブックに真似て、lightgbmによるBaselineモデルを書きました。データを読み、ワンホットエンコーディング、シフト操作などができるが、スコアが1100から全く下がらずにいる。
    3. アプローチ自体に問題があると思い、Gradient Boostをやめ、TPUを使用できるKerasによるDLモデルを書きました。


----------

3. [AI Quest Hotel Price Prediction](https://signate.jp/courses/kYNRLg60ZbWZj3vo)
Finish Date: 9th August, 2021
Approach I took:
    1. This is obviously a feature-engineering heavy competition, so I started just there. Domain specific approaches include:
      * Encode latitude and longitude into
        `x = cos(lat) * cos(lon)`
        `y = cos(lat) * sin(lon)`
        `z = sin(lat) `
      * Encode cancellation policy into numerical based on the level of strictness.
      * Encode first_review, last_review, host_since into timedelta between the record and today, so that they can reflect if said hotel's popularity and their age.
      * Encode mentioned amenities (which is a json formatted string) into just a counter of them. The idea is the more amenities it mentions (let alone the kind), more likely they charge a premium for the room (the psychology of anticipation reflected on the item count).

3. [AI Quest Hotel Price Prediction](https://signate.jp/courses/kYNRLg60ZbWZj3vo)
  終了日：2021年8月9日\n
  取ったアプローチ:
    1. 特徴量エンジニアリングが（ほぼ）全てを決めるコンペだったので、そこからはじめました。ドメイン的にユニークな調整が以下の通り:
      * 緯度経度の正規化:
        `x = cos(lat) * cos(lon)`
        `y = cos(lat) * sin(lon)`
        `z = sin(lat) `
      * キャンセルポリシーを厳しさの順で0~5にエンコード
      * first_review, last_review, host_sinceという日付特徴を、本日との差という数値特徴へ変換し、数字が大きければ大きいほど古いことを差す（そして、古いほど値段が低いという仮設
      * アメニティというJsonフォーマットの特徴量をcounterという数値へ変換。アイディアとしてはアメニティが多い所（または多くあると見せようとするところ）の方が、価格が上がりやすいという仮設
