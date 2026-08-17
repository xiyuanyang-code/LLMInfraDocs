+++
title = 'LLM Training Algo'
description = 'LLM training algorithms from scratch: SFT, RL (GRPO / PPO), and OPD.'
date = '2026-08-16'
tags = ['llm-training-algo']
weight = -95 # 置顶, 优先级在 intro (-100) 和 slime (-90) 之间
pin = 'algo' # 首页卡片用橙色
+++

在 Slime 中，我们在代码中学习若干核心的 LLM 训练算法如何被执行调用。抛开事件的观点，算法理论的严谨和直觉，本身也需要被培养。

因此，在本专题中，我们将聚焦**若干核心的 LLM 训练算法**，在 Data First 的 LLM 时代下，看看这些算法如何承载高效的数据和参数 Scaling 特征，将外部数据**内化**到模型参数中。

我们会从基础训练算法开始(包含预训练/中训练的训练算法)，一步步推演扩展到后训练中纷繁复杂、百花齐放的训练算法(SFT, PEFT, RL, Agentic RL, OPD)

## Outlines

- `Pretrain & Midtrain`: basic llm pre-training/mid-training algo
- `SFT`: Full SFT/Lora
- `RL`: PPO, DPO, GRPO and Agentic RL
- `OPD`: Onpolicy Distillation, MOPD

