---
tags:
  - model-malware
  - supply-chain-attack
aliases:
  - lobotoMI
last_tested:
---

**PoC:**
https://github.com/alkaet/LobotoMl/tree/main/ONNX_runtime_hacks

Can be deployed a number of ways, such as via a (public) [registry](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FPublic%20Model%20Registries%2FUsing%20a%20Huggingface%20Watering%20Hole) ,
via [kserve](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FMLops%20Pipelines%2FUsing%20kserve), and more to come.  Recommend deploying via container.

**Details**
A proof of concept custom operation in ONNX runtime that has side effects and creates files on the target machine. This should be extended to run shellcode from ONNX.
Difficult to deploy remotely, could be chained with a [kserve based attack](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FMLops%20Pipelines%2FUsing%20kserve)  to make shared library this relies on portable. 

