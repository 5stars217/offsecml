---
aliases:
  - syzGPT
tags:
  - offensiveML
  - vulnerability-scanner
last_tested: 2/2024
transferable: N/A
---

## **PoC** - fuzzing a kernel module
Step-by-Step guide is [here](https://albocoder.github.io/fuzzing/exploitation/linux%20kernel/hacking/ai/gpt/llm/2023/11/27/GPT-syzkaller.html?utm_source=tldrsec.com&utm_medium=referral&utm_campaign=tl-dr-sec-211-llms-fuzzing-navigating-the-incident-response-maze-product-security-hashicorp) for fuzzing a kernel module using LLM generated content on system calls. 

## **Details**
By [albocoder](twitter.com/albocoder)
[Video]()
[Paper](https://albocoder.github.io/fuzzing/exploitation/linux%20kernel/hacking/ai/gpt/llm/2023/11/27/GPT-syzkaller.html?utm_source=tldrsec.com&utm_medium=referral&utm_campaign=tl-dr-sec-211-llms-fuzzing-navigating-the-incident-response-maze-product-security-hashicorp) 

## **PoC** - Fuzzing c/c++ libs

[The code](https://github.com/google/oss-fuzz-gen) 

## Details
This framework generates fuzz targets for real-world `C`/`C++` projects with various Large Language Models (LLM) and benchmarks them via the [`OSS-Fuzz` platform](https://github.com/google/oss-fuzz).
This work has really great prompt engineering which is [worth a look](https://storage.googleapis.com/oss-fuzz-llm-targets-public/jsoncpp-json-value-removeindex/prompts.txt). 

[paper](https://security.googleblog.com/2023/08/ai-powered-fuzzing-breaking-bug-hunting.html)

### ATT&CK Matrix