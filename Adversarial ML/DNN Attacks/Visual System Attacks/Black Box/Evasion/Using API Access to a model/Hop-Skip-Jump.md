---
aliases: 
tags:
  - black-box
  - Evasion
  - Visual-Attack
last_tested: 10/2023
transferable: "True"
---
## **PoC**
This attack is [implemented in Countefit.](https://github.com/Azure/counterfit/blob/9aee1ea6958fe48edbe289aaef895a902aeccc80/counterfit/frameworks/art/attacks/hop_skip_jump.yml#L2) 

```
set_params --sample_index 5 --norm 2 --max_iter 10 --max_eval 5000 --verbose true
``` 


## **Details**
Can be performed with API access to a model. 

[Paper](https://arxiv.org/abs/1904.02144) 
### ATT&CK Matrix