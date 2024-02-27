---
aliases:
  - llm_ctf
tags:
  - black-box
  - offensiveML
  - GenAI
last_tested: 2/2024
transferable: "True"
---
## **PoC**
[the code](https://github.com/NickNameInvalid/LLM_CTF/tree/main)

## **Details**
Bench-marked study of LLMs  against human participants found that LLMs achieve higher success rate than an average human participant (from a student cohort). The primary cause of failure on non-completion was 'not returning solution or gives up and interrupts itself (36.67% w/ GPT4)'.

Most of the solves were not particularly interesting, but a couple of the solves showed some real efficacy. [E.g stealing the weights of a linear model from a server using black-box input/output queries in bash.](https://moyix.net/~moyix/secret/llm_ctf_transcripts/misc/linear_aggressor/conversation.gpt-4-1106-preview.8.html)
[Video]()
[Paper](https://arxiv.org/pdf/2402.11814.pdf) 
### ATT&CK Matrix