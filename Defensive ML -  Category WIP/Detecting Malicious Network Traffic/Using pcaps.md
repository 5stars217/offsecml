---
aliases:
  - pcap
  - pandas
tags:
  - defense
  - network
last_tested: 06/2024
transferable: "True"
---

## **PoC**

https://github.com/mundruid/cyberdata-mlai by [Dr X ](
https://github.com/mundruid)

## **Details**

This project does some great benchmarking between LLMs and visual/statistical methods. 


**Goal**: detect malicious activity using packet capture traffic

- Pcaps need to be converted to Pandas dataframes for ML processing. The unit to or
  - flows
  - packets
- Exploration with visual and statistical methods
- Creative feature engineering
  - Categorical to numerical features
  - Numerical to categorical. This is unusual, but useful for this use case
    - Ex. ports to services
  - Embeddings for words (payload, protocols)
    - Exploration for the best embedding that conveys the meaning of words
  - Convert features to strings, train an LLM for classification
- Train models with labeled data
  - Some algorithms better for cybersecurity applications
    - semi-supervised for very few labeled data
- Fine tune language models
  - works pretty well if the architecture of the model applies to the application.
    - Ex. BERT for classification

[Video]()
[Slides](https://docs.google.com/presentation/d/1wPkWEvS-3Rn-RFp3CumPJQbYaOGXL88FCjV6uCCHaww/edit?usp=sharing)