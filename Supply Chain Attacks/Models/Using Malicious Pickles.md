---
tags:
  - model-malware
  - supply-chain-attack
last_tested: 1/2024
---
## **PoC:**
PyTorch malicious model by [the code](https://github.com/stealth/tensor-pwn/tree/master/pytorch)  from [stealth](https://twitter.com/steaith) tested on PyTorch `2.1.2`


Can be deployed a number of ways, such as via a (public) [registry](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FPublic%20Model%20Registries%2FUsing%20a%20Huggingface%20Watering%20Hole) ,
via [kserve](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FMLops%20Pipelines%2FUsing%20kserve), and more to come. 

## **Details**:
A technique that can be used pre or post exploitation to gain code execution in an environment. Also a persistence technique. 