---
aliases:
  - gradsafe
tags:
  - black-box
  - llm-defense
last_tested: 02/2024
transferable: "True"
---

## **PoC**
[The code](https://github.com/xyq7/gradsafe)
## **Details**

 The gradients of an LLM's loss for unsafe prompts paired with compliance response exhibit similar patterns on certain safety-critical parameters. In contrast, safe prompts lead to markedly different gradient patterns which can be used to defend an LLM in a fast, efficient manner.

[Paper](https://arxiv.org/abs/2402.13494) 
