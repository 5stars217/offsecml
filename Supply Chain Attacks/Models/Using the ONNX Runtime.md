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

Can be deployed a number of ways, such as via a (public) registry: [[Using a Huggingface Watering Hole]]
via [[Using kserve]], and more to come.  Recommend deploying via container.


***Bypass and detections note 8 Jan '24:*** a file ending in the `.onnx` file format can still be loaded as a pickle data blob if the loading code uses `torch.load()` instead of  `onnx.load().`[by stealth](https://github.com/stealth/tensor-pwn) 

**Details**
A proof of concept custom operation in ONNX runtime that has side effects and creates files on the target machine. This should be extended to run shellcode from ONNX.
Difficult to deploy remotely, could be chained with a [[Using kserve]] style attack to make shared library this relies on portable. 
Using the ONNX runtime for hacks is from the awesome work of [alkaet](https://github.com/alkaet). 

