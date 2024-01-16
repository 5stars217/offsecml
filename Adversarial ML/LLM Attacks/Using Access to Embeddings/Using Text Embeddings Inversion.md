---
aliases:
  - rec2text
tags:
  - llm-attacks
last_tested: 11/2023
transferable: "True"
---


## **PoC**

Reconstruct text sequences from embeddings as well as run pre-trained models.
The library can be used to embed text and then invert it, or invert directly from embeddings.
**Most of the code in this repository facilitates training inversion models**
https://github.com/jxmorris12/vec2text 

## **Details**
It has been previously assumed that embeddings could not be reconstructed to reveal the sensitive data within, that should never be the assumption. 
[video](https://www.youtube.com/watch?v=lguThumFUl4) 
[Code demo](https://colab.research.google.com/drive/14RQFRF2It2Kb8gG3_YDhP_6qE0780L8h?usp=sharing )
[Paper](https://arxiv.org/abs/2310.06816) 
### ATT&CK Matrix