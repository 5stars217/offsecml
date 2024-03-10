---
aliases:
  - representation-engineering
tags:
  - llm-defense
last_tested: 03/2024
transferable: "True"
---
## **PoC**
[The code](https://github.com/andyzoujm/representation-engineering) 
It can be used to focus the LLM in a variety of ways, including to prevent jailbreaks, but the control vector will be present on every token. PoCs show it being particularly effective on LLMs that are given a particular job as say, a 'car dealership assistant'.  By [andyzoujm & team](https://github.com/andyzoujm) 

## **Details**
A control vector is a vector (technically a list of vectors, one per layer) that you can apply to model activations during inference to control the model's behavior without additional prompting

[Paper](https://vgel.me/posts/representation-engineering/) 
