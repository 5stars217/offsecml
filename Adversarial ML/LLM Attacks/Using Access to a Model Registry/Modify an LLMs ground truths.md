---
tags:
  - llm-attacks
  - black-box
  - poisoning
  - post-exploitation
aliases:
  - easyedit
  - rome
last_tested: 08/2023
transferable: "True"
---
**PoC:**
The easiest way to modify an LLM's ground truths is with the EasyEdit Framework:
https://github.com/zjunlp/EasyEdit

Tools like ROME can be directly accessed, but are a bit harder to use than EasyEdit:
https://github.com/kmeng01/rome 

Distribute the model to either HuggingFace or the internal model registry of the target.
https://huggingface.co/docs/hub/models-uploading 


**Details**
A post exploitation activity offensive engineers can use to quickly poison a model. 

An Easy-to-use Knowledge Editing Framework for LLMs. Lets you poison an LLM that is compiled and stored in a model registry. 


EasyEdit is a Python package for edit Large Language Models (LLM) like `GPT-J`, `Llama`, `GPT-NEO`, `GPT2`, `T5`(support models from **1B** to **65B**), the objective of which is to alter the behavior of LLMs efficiently within a specific domain without negatively impacting performance across other inputs. It is designed to be easy to use and easy to extend.
https://github.com/zjunlp/EasyEdit/blob/main/figs/demo.gif 

**paper**: https://arxiv.org/abs/2310.08475 