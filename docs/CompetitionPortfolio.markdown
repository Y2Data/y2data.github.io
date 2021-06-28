---
layout: default
date: 2021-06-28 14:16:15 +0900
Title: Competition Portfolio
categories: Essay
author:  Yuhao Dai
---

1. [SETI](https://www.kaggle.com/c/seti-breakthrough-listen)
  Finish date: 29th July, 2021
  Approach I took:
    1. I started late in the competition, and there was already public notebooks that takes the AUC score to 0.970. I copied one of them and started to tune the hyper-parameter.
    2. The model wasn't even overfitting on the training data too well, so I spent 2 days on looking at the data.
    3. I found that data that was labeled "true" was hard to understand the reason behind. I tried to artificially add a line in between images to imitate the signal (for 30 true labels) and it did not improve the performance. At this point the attempt to artificially generate some training data becomes impossible, leaving the only option to augmentations.
    4. After some simple augmentations, the model started to overfit to 0.991 AUC on best epoch, and 0.988 on CV. I used ResNet34d instead of originally proposed ResNet18d, and increased the batch size, this got me on the leaderboard at around 100 place, with an AUC of 0.978.
    5. The double data leakage happened, the leaderboard was taken over by cheating 1.000 AUC Kagglers, so I turned my eyes to another competition. (Not Fixed at time of writing, 29th of June).

2. [Google Smartphone Decimeter](https://www.kaggle.com/c/google-smartphone-decimeter-challenge)
  Finish date: 5th August, 2021
  Approach I took:
    1. This is a competition that required highly in both domain knowledge and pre-processing, so I spent two days on researching all the things I should know about GNSS.
    2. Imitating the SETI notebook, I wrote a baseline notebook that would read, one-hot encode and combine all the data, and run a simple lightgbm model. This was scored poorly at around 1100.
    3. 
