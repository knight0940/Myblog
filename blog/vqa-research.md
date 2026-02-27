---
title: 知识增强型视觉问答系统研究
date: 2025-12-20
tag: Research
---

探讨如何将外部知识库与视觉语言模型结合，提升 VQA 系统的性能。

## 研究背景

视觉问答 (Visual Question Answering, VQA) 需要模型同时理解图像和问题，但现有模型往往缺乏外部知识支持，导致需要外部知识的问答表现不佳。

## Caption as A Bridge 方法

我们的研究成果发表在 *Scientific Reports* 上，核心思想：

### 核心创新

使用图像描述作为桥梁，连接视觉特征和外部知识：

1. 图像 → 描述生成
2. 描述 + 问题 → 知识检索
3. 视觉特征 + 知识 → 答案生成

### 实验结果

在 OK-VQA 和 A-OKVQA 数据集上显著提升：

- OK-VQA: +5.2% accuracy
- A-OKVQA: +3.8% accuracy

## 技术细节

### 知识库

- Wikipedia 快照
- ConceptNet 知识图谱
- 领域知识库

### 模型架构

- 视觉编码器: ViT-L/14
- 语言模型: FlanT5-XXL
- 知识检索: Dense Passage Retrieval

## 未来工作

- 多模态知识图谱
- 实时知识更新
- 可解释性增强
