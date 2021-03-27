---
layout: post
date: 2021-03-27 11:59:21 +0900
title: Information Theory
categories: Essay
author:  Yuhao Dai
---


1. 情報量(Quantity of Information)＝事象がどれくらい起こりにくいのかを表す尺度  
$$ QoI \ = -log_2P $$
* サイコロで5が出た：確率が1／6のため、  P＝1/6 $$ -log_2 1/6 = -log_{2}6^{-1} \approx 2.58 bits $$
* コインで1が出た：確率が1／2のため、  P=1/2 $$ -log_2 1/2 = -log_{2}2^{-1} = 1 bit $$  


2. 平均情報量(Entropy) = 全ての事象の平均を取ったもの  
$$ Entropy = \sum^{n}_{k=1} \{P(A_k) * QoI(A_k)\} $$
* 例えば、平均的に、東京では晴れ／曇り／雨の確率がそれぞれ50%/25%/25%としよう
  それぞれのQoI: 1/2/2 bits  
  $$ Entropy = (0.5 * 1) + (0.25 * 2) + (0.25 * 2) = 1.5 bits $$
