---
aliases:
  - toxic-chat
  - xs-test
tags:
  - black-box
last_tested: 02/2024
transferable: "True"
---
## **PoC**
[benign](https://huggingface.co/datasets/natolambert/xstest-v2-copy)
[toxic](https://huggingface.co/datasets/lmsys/toxic-chat)
## **Details**
Striking the balance between safe and unsafe LLM prompts and responses is difficult.
Datasets such as this one can be used to evaluate the effectiveness of AI Red Teaming in meeting safety requirements whilst not rendering the LLM useless. 

It can also be used to benchmark prompt injection and safety tools, though keep in mind that these open source datasets are often used in testing cycles by the same. 

[Paper](https://arxiv.org/abs/2308.01263) 
### ATT&CK Matrix