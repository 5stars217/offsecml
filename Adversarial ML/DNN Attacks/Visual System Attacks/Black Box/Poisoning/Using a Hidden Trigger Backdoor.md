---
aliases:
  - Sleeper Agent
tags:
  - black-box
  - Visual-Attack
last_tested: 
transferable: "True"
---


## **PoC**
https://github.com/hsouri/Sleeper-Agent 

`python sleeper_agent.py --patch_size 30 --budget 0.0005 --pbatch 128 --epochs 80 --sources 50 --dataset ImageNet --pretrained_model --data_path /your/path/to/ImageNet --pbatch 128 --source_gradient_batch 300


## **Details**
Backdoor attackers tamper with training data to embed a vulnerability in models that are trained on that data. This vulnerability is then activated at inference time by placing a "trigger" into the model's input. Typical backdoor attacks insert the trigger directly into the training data, although the presence of such an attack may be visible upon inspection. In contrast, the Hidden Trigger Backdoor Attack achieves poisoning without placing a trigger into the training data at all. However, this hidden trigger attack is ineffective at poisoning neural networks trained from scratch. We develop a new hidden trigger attack, Sleeper Agent, which employs gradient matching, data selection, and target model re-training during the crafting process. Sleeper Agent is the first hidden trigger backdoor attack to be effective against neural networks trained from scratch.
[Video]()
[Paper](https://arxiv.org/abs/2106.08970) 
### ATT&CK Matrix