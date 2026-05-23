---
title: Machine Unlearning in Small Language Models
date: 2024-12-25
links:
  - type: code 
    url: https://github.com/dhruvmadhwal/machine-unlearning-slms
tags:
  - PyTorch 
  - Hugging Face
  - Machine Unlearning 
  - LoRA
  - PEFT 
---

Large language models can memorize facts during training, but removing a specific piece of knowledge after training is not straightforward. Retraining a model from scratch is expensive, and deleting the original data does not guarantee that the model will stop producing what it learned.

<!--more-->

## Why Unlearning Matters

Machine unlearning studies how to make a model intentionally forget targeted information while preserving its general abilities. This matters because models may need to forget private data, copyrighted material, outdated facts, or unsafe responses.

Prior work such as [Who's Harry Potter? Approximate Unlearning in LLMs](https://arxiv.org/abs/2310.02238) showed that approximate unlearning can reduce a model’s ability to recall specific content while keeping much of its general performance intact. Other recent work, such as [Machine Unlearning of Pre-trained Large Language Models](https://arxiv.org/abs/2402.15159), has explored unlearning as a way to remove harmful behavior, copyrighted content, and memorized knowledge from language models.

## What I Explored

In this project, I explored machine unlearning for small language models in the 3B-4B parameter range. I focused on two techniques: random labeling and gradient ascent.

- With random labeling, the model is fine-tuned on incorrect or randomized answers for the fact it should forget.
- With gradient ascent, the training objective is reversed so the model becomes worse at recalling the targeted information.

## Efficiency Through Lightweight Adaptation

To keep the process efficient, I used PEFT and LoRA adapters with quantization. This allowed me to change the model’s behavior without fully retraining it.

## Evaluation

A major challenge was making the model forget the target fact without damaging its broader question-answering ability. To evaluate this, I tested whether the model stopped producing the targeted answer while also measuring general performance using BLEU, ROUGE-L, BERTScore, and [TruthfulQA](https://arxiv.org/abs/2109.07958), a benchmark designed to measure whether models produce truthful answers rather than imitating common falsehoods.

