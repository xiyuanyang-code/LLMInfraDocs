+++
title = 'Pretraining and Midtraining'
description = 'Basic Training Algorithms in Pretraining and Midtraining'
date = '2026-08-16'
tags = ['llm-training-algo']
weight = 30 # Hugo 会把未设 weight(=0) 的页面排在最后, 因此显式给值
+++

在本文中，我们详细讲解一般的 Dense 模型和 MoE 模型在 Pretraining 和 Midtraining 使用的训练范式。关于详细的数据配比，模型架构等策略，我们会在后续章节详细展开。

## Pretraining

我们从若干技术报告出发:

- [DeepSeek V2](https://arxiv.org/abs/2405.04434)
- [DeepSeek V3](https://arxiv.org/pdf/2412.19437)
- [DeepSeek V4](https://arxiv.org/pdf/2606.19348)

### DeepSeek V2: MoE & MHA

我们首先迅速了解一下 DeepSeek 系列模型一贯的 MoE 架构:

