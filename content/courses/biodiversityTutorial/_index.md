---
# Course title, summary, and position.
linktitle: Biodiversity calculation
summary: Learn how to use simple indexes calculate biodiversity.
weight: 1

# Page metadata.
title: biodiversity_index
date: "2020-02-05T00:00:00Z"
lastmod: "2020-02-05T00:00:00Z"
draft: false  # Is this a draft? true/false
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.

# Add menu entry to sidebar.
# - name: Declare this menu item as a parent with ID `name`.
# - weight: Position of link in menu.
menu:
  biodiversityTutorial:
    name: biodiversity_index
    weight: 1
---

## 物种丰富度（Richness）

最简单的描述多样性的指数就是物种丰富度指数（Species richness），即为群落中丰度大于0的物种数之和，值越大表明群落中物种种类越丰富。下式中，S，物种丰富度指数；n，个体数（丰度）大于0的物种类型总数。

$$
    S = n
$$

该指数只描述物种数量，不考虑物种的个体数量。即当总个体数为100时，4个物种，每个25个个体和，4个物种，个体数量分别是97，1，1，1的情况是一样的。考虑到不同物种的数量不同，且可能有很大差异，我们必须采用香农指数。

## 香农指数（Shannon index）

香农指数（Shannon index）或称香农熵指数（Shannon entropy index）、香农-威纳指数（Shannon-Wiener index），同时考虑了物种丰富度以及均匀度（Shannon，1948a，b）。来源于信息论（information theory），同时考虑物种数量和物种的个体数量，反映了群落中物种存在的无序性，也可以理解为在群落中随机选择的个体属于哪些物种的不确定性。如果有x个物种，每次抽样抽到任意一个物种的概率一样，那就是具有最大的不确定性，香农指数也最高；如果群落仅由单一物种组成（种群），只有抽样就肯定抽到某个物种，那不确定性就为0。

Shannon指数（H）的计算公式如下。式中，S，群落物种丰富度指数，即物种类型总数；pi，物种i的相对丰度；x，通常使用2、e等作为底数。

$$
H = - \sum_{i=1}^{S} p_i log_x p_i
$$


由以上可知，不同物种的不同数量反映了物种丰富度的均匀程度，假设有2个物种，每个物种数为25个，则连续两次抽样个体为相同物种的概率为：$25/50 * 25/50 + 25/50 * 25/50 = 1/2$，若2个物种数量分别为40和10，则连续两次抽样个体为相同物种的概率为：$40/50 * 40/50 + 10/50 * 10/50= 17/25$，由此引入辛普森指数。

## 辛普森指数（Simpson）

辛普森指数（Simpson index）同样考虑了物种丰富度以及均匀度，但与Shannon指数相比，它更受均匀度的影响（Simpson，1949）。该指数反映的是在同一个样本中随机的抽取2个个体，这两个个体来自同一个类的概率。公式如下。式中，S，群落物种丰富度指数，即物种类型总数；pi，物种i的相对丰度。

$$
    D = 1 - \sum_{i=1}^{S}p_{i}^2
$$
Simpson指数的取值范围0-1。当群落物种丰富度较高时，Simpson指数的值主要受均匀度的影响。当群落完全均匀，即群落中所有物种丰度完全一致时（即上式pi = 1/S），Simpson指数可以直接由物种丰富度直接得到。
