---
title: 'OneNet论文阅读'
date: 2023-10-20
permalink: /posts/OneNet论文阅读/
tags:
  - 论文阅读
  - 时间序列
---

今天读到一篇时序文章 [OneNet: Enhancing Time Series Forecasting Models under Concept Drift by Online Ensembling ](https://arxiv.org/abs/2309.12659v1)，文章发表在了NeurIPS 2023，这篇文章和我之前follow的文章特别像，都是利用Cross-time和Cross-variable并融合得到预测结果，这篇文章在融合的时候运用了强化学习的方法，而且理论推导充足，实验充分，并且运用到了很多凸优化相关知识，正好这学期有门课《最优化方法》有学习到凸优化，于是打算好好阅读这篇文章，体会顶刊的写作水平和实验思路的同时学习最优化方法的应用。

## 简要 :

- 本研究提出了一种名为OneNet的在线集成方法，通过动态更新和组合两个模型，以增强时间序列预测模型在概念漂移下的性能。该方法结合了时间维度的依赖性和跨变量的依赖性，并利用强化学习方法动态调整模型权重。实验结果表明，与现有方法相比，OneNet将在线预测误差降低了50%以上。

## 背景信息:

- 论文背景: 近年来，将深度学习应用于时间序列预测的研究不断增加。然而，现有的研究主要集中在批量学习设置下，无法处理概念漂移等实际应用中的问题。因此，需要一种在线学习方法来动态更新预测模型以适应环境中的变化。
- 过去方案: 过去的研究中，一些方法尝试通过设计高级的更新结构或学习目标来解决在线时间序列预测中的问题。然而，这些方法往往依赖于特定的模型结构，无法充分利用更先进的网络结构。此外，现有方法在适应概念漂移方面存在一定的局限性。
- Motivation: 鉴于现有方法的局限性，本研究提出了一种在线集成方法OneNet，通过组合不同的模型来提高预测性能。该方法结合了时间维度的依赖性和跨变量的依赖性，并利用强化学习方法动态调整模型权重。实验结果表明，OneNet在减小预测误差方面具有显著优势。

## 方法:

- a. 理论背景:
  - 本文介绍了现有时间序列预测模型在处理概念漂移时的局限性，即输入和输出变量之间的关系随时间变化。强调了在线更新预测模型以捕捉环境中不断变化的动态的必要性。还提到了在线预测面临的挑战，如噪声梯度和连续分布变化。
- b. 技术路线:
  - 本文提出了一种名为OneNet的在线时间序列预测方法。它利用集成学习框架，并引入变量独立性的概念，以提高模型在概念漂移下的鲁棒性。该方法涉及训练两个独立的分支来捕捉时间和交叉变量之间的依赖关系。引入了在线凸规划（OCP）块来动态调整集成学习中使用的组合权重。

