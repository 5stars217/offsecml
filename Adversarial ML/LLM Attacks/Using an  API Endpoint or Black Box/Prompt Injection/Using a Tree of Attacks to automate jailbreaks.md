---
aliases:
  - TAP
tags:
  - black-box
  - prompt-injection
last_tested: 12/2023
transferable: "True"
---


## **PoC**
[the code](https://github.com/RICommunity/TAP)
A fully transferable attack on LLMs to jailbreak them. 
There's also a minimal implementation of the [code here](https://github.com/dreadnode/parley) by the team at Dreadnode

TAP utilizes an LLM to iteratively refine candidate (attack) prompts using tree-of-thoughts reasoning until one of the generated prompts jailbreaks the target. 

## **Details**
TAP is an automatic query-efficient black-box method for jailbreaking LLMs using interpretable prompts. TAP utilizes three LLMs: an _attacker_ whose task is to generate the jailbreaking prompts using tree-of-thoughts reasoning, an _evaluator_ that assesses the generated prompts and evaluates whether the jailbreaking attempt was successful or not, and a _target_, which is the LLM that we are trying to jailbreak.

[Paper](https://arxiv.org/abs/2312.02119) 
by [Anay](https://github.com/AnayMehrotra) and [drhyrum](https://github.com/drhyrum) et. al 
### ATT&CK Matrix