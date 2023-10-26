---
aliases:
  - model-malware
tags:
  - model-malware
  - supply-chain-attack
last_tested: 10/2023
---


**PoC**:
https://github.com/5stars217/malicious_models/ 

Can be deployed a number of ways, such as via a (public) [registry](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FPublic%20Model%20Registries%2FUsing%20a%20Huggingface%20Watering%20Hole) ,
via [kserve](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FMLops%20Pipelines%2FUsing%20kserve), and more to come. 

**Details**:
A technique that can be used pre or post exploitation to gain code execution in an environment. Also a persistence technique. 

Adds a malicious lambda to the architecture layer of a keras model:
https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/ 
