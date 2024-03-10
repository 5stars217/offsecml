---
aliases: 
tags:
  - llm-defense
last_tested: 10/2023
transferable: "True"
---
## **PoC**
[The code](https://github.com/protectai/rebuff )  - note that LLM based detections can be considered to be vulnerable themselves to prompt injection, and often benchmark as a high latency solution when deployed as an in-line defense. 

## **Details**
Rebuff offers 4 layers of defense:

- Heuristics: Filter out potentially malicious input before it reaches the LLM.
- LLM-based detection: Use a dedicated LLM to analyze incoming prompts and identify potential attacks.
- VectorDB: Store embeddings of previous attacks in a vector database to recognize and prevent similar attacks in the future.
- Canary tokens: Add canary tokens to prompts to detect leakages, allowing the framework to store embeddings about the incoming prompt in the vector database and prevent future attacks.

[Paper](https://github.com/protectai/rebuff?tab=readme-ov-file) 
