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

物种丰富度指数（Species richness）为群落中丰度大于0的物种数之和，值越大表明群落中物种种类越丰富。下式中，S，物种丰富度指数；n，个体数（丰度）大于0的物种类型总数。

$$
    S = n
$$

物种丰富度指数在计算中对所有存在的物种（无论优势物种或稀有物种）等权重看待，只关注物种存在与否，与它们的相对丰度无关。此外，丰富度指数对抽样深度所造成的差异也是非常敏感的。例如，在群落中观测500个个体和1000个个体时，基于1000个个体所观测到的物种类型数量通常会更多，这种差异主要体现在低丰度物种水平。


## 香农指数（Shannon）

香农指数（Shannon index）或称香农熵指数（Shannon entropy index）、香农-威纳指数（Shannon-Wiener index），同时考虑了物种丰富度以及均匀度（Shannon，1948a，b）。它由信息论（information theory）延伸而来，反映了我们能够预测在群落中随机选择的个体属于哪些物种的不确定性。如果群落仅由单一物种组成（种群），那么我们确信随机选择的个体必定为那个唯一的物种，此时不确定性就为零；否则，我们将无法得知随机被选择的个体究竟属于什么物种，并且不确定性也会随着群落物种种类数的增多而增加。但是，如果群落中存在一种或少数几种物种占据了优势地位（与其它物种相比，它们在丰度上具有明显的优势），那么不确定性就不会那么高，因为我们随机选择的个体很有可能就是这些优势物种。

Shannon指数（H）的计算公式如下。式中，S，群落物种丰富度指数，即物种类型总数；pi，物种i的相对丰度；x，通常使用2、e等作为底数。

$$
H = - \sum_{i=1}^{S} p_i log_x p_i
$$

## 辛普森指数（Simpson）


辛普森指数（Simpson index）同样考虑了物种丰富度以及均匀度，但与Shannon指数相比，它更受均匀度的影响（Simpson，1949)）。经典Simpson指数代表了在群落中两个随机选择的个体属于同一物种的概率，当群落物种丰富度增加时，这种概率降低，即Simpson指数随着物种丰富度的增加而降低。由于经典Simpson指数与物种丰富度相反的趋势不直观，如今常用演变而来的Gini-Simpson指数表示Simpson指数，即用1减去经典Simpson指数数值后得到，此时Simpson指数随着丰富度的增加而增加（二者保持一致的趋势）。

经典Simpson指数（D）和Gini-Simpson指数（GS）的公式如下。式中，S，群落物种丰富度指数，即物种类型总数；pi，物种i的相对丰度。

$$
    D = \sum_{i=1}^{S}p_{i}^2
$$
Simpson指数的取值范围0~1，单位是一个概率。当群落物种丰富度较高时，Simpson指数的值主要受均匀度的影响。当群落完全均匀，即群落中所有物种丰度完全一致时（即上式pi = 1/S），Simpson指数可以直接由物种丰富度直接得到。
