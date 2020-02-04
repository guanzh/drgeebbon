---
title: 'Score simulation and analysis'
subtitle: 'Simulation scores and analysis, try pca'
summary:
authors:
- admin
tags:
- Academic
categories:
- Demo
date: "2019-04-01T00:00:00Z"
lastmod: "2019-04-01T00:00:00Z"
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
image:
  placement: 2
  caption: ''
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---


一次考试成绩能够反应多少东西，分数是否可以反应平时的用功程度，此外还能够反应出什么，采用一个模拟案例分析。

## 问题1，同学间的成绩差异到底有多大？

综合汇总同学各科成绩计算总分，总体上属正态分布，最高分与最低分相差超过100分，大部分同学集中于500到560之间，优秀学生占少数，按照80%原则，560以上10人。

![成绩排序的直方图](./1817671-a597b409a7c621e5.png)

## 问题2，是否存在在成绩上表现极优秀同学？
从分数上看，没有出现个别极优秀同学，即各门功课均显著突出的。

## 问题3，同学们的综合成绩表现如何?
综合选择解释力最强的2个主成分分析，能够解释52.2%的成绩差异。如果我主观武断按照7人1组的分群，这5个群体可以在横轴（即主成分1）上区分开来。从图形上看，前1、2、3群个体形成较为密集的分布，而4、5群个体分布较为离散。

![按照成绩进行聚类](./featured.png)

## 问题4，哪些课程影响了同学们的综合成绩？
观察各门功课对于同学在综合表现上（即对主成分1和2的载荷值）的影响，其中影响最大的3门课是，数学影响最大、其次是化学、然后是英语，这3门课将同学在横轴上拉开。在纵轴上影响最大的3门课，拉开距离的是体育、职业生涯规划、思想道德。虽然相关性分析也反映了总分受到数学、化学和英语影响显著，但实际上这3门课对于总成绩差异的解释很有限，PC1为30.1%。

## 问题5，这个班级有什么特点？
1 大多数同学的成绩分数较为集中，成绩最优异的几个同学相对于大部分同学的分数有差距，但并没有非常大的差距，同时没有非常偏科的同学；
2 这个班级大多数同学主要在横轴上有所区分，即数学、化学和英语对于这个班级同学的成绩差异具有显著影响；
3 成绩靠后的同学在纵轴上差异较大；
4 成绩和同学在其他方面上的表现并不明显，在所有同学中，从最左边到最右边，均有个体同学在其他方面的优秀表现没有反映到成绩上；
5 我们无法评价具体分数能够反应出多少同学的能力差异，例如无法评价相差10分能够反映出多少用功程度，但是确定的是相差100分肯定和平时付出的努力相关的，好在该班级在巨大的分数差异上仅有个别同学。

## 数据虽为模拟，但依然可以表现出PCA的能力，至少一半的个体差异能够表现出来，并能够进行解释；同时，本案例分析受到了一些限制，例如模拟时期较短，科目成绩不全面，且没有考虑到个体本身的能力差异，廖为一窥而已。
