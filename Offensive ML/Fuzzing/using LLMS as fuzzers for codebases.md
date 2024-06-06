---
aliases:
  - syzGPT
tags:
  - offensiveML
  - vulnerability-scanner
last_tested: 2/2024
transferable: N/A
---
---


## **PoC** - fuzzing a kernel module
Step-by-Step guide is [here](https://albocoder.github.io/fuzzing/exploitation/linux%20kernel/hacking/ai/gpt/llm/2023/11/27/GPT-syzkaller.html?utm_source=tldrsec.com&utm_medium=referral&utm_campaign=tl-dr-sec-211-llms-fuzzing-navigating-the-incident-response-maze-product-security-hashicorp) for fuzzing a kernel module using LLM generated content on system calls. 

## **Details**
By [albocoder](twitter.com/albocoder)
[Video]()
[Paper](https://albocoder.github.io/fuzzing/exploitation/linux%20kernel/hacking/ai/gpt/llm/2023/11/27/GPT-syzkaller.html?utm_source=tldrsec.com&utm_medium=referral&utm_campaign=tl-dr-sec-211-llms-fuzzing-navigating-the-incident-response-maze-product-security-hashicorp) 

**3/10/24 update:** A great thread [here](https://twitter.com/moyix/status/1765967602982027550)on  using Claude Opus for this task, and the incredible performance it obtained. 

## **PoC** - Fuzzing c/c++ libs

[The code](https://github.com/google/oss-fuzz-gen) 

## Details
This framework generates fuzz targets for real-world `C`/`C++` projects with various Large Language Models (LLM) and benchmarks them via the [`OSS-Fuzz` platform](https://github.com/google/oss-fuzz).
This work has really great prompt engineering which is [worth a look](https://storage.googleapis.com/oss-fuzz-llm-targets-public/jsoncpp-json-value-removeindex/prompts.txt). 

[paper](https://security.googleblog.com/2023/08/ai-powered-fuzzing-breaking-bug-hunting.html)


## **PoC** - Fuzzing network protocols

[The code](https://github.com/ChatAFLndss/ChatAFL) 

## Details
Network protocol fuzzer based on benchmark for protocol fuzzing [ProFuzzBench](https://github.com/profuzzbench/profuzzbench) and [AFLNet](https://github.com/aflnet/aflnet). The LLM generates a grammar for the protocol and follows the state machine to send messages after mutating them. The LLM is also used to increase randomness of mutation and coverage.

[paper](https://mengrj.github.io/files/chatafl.pdf)

## **Survey** - Large Language Models Based Fuzzing Techniques

Comprehensive survey for LLM applications in fuzzing. Notable bullet points:

- promt engineering based LLM fuzzers
	- ParaFuzz
		- synonym mutations
	- Fuzz4All
	- CHATAFL
	- Fuzz Driver Generation 
	- BertRLFuzzer
- seed mutation LLM fuzzers
	- [Titanfuzz](https://github.com/ise-uiuc/TitanFuzz)
		- CodeX generates data
		- Part of data is masked
		- Use fill in models to fill in the blanks
	- Fuzzing parsers
	- [Fuzz4all](https://zenodo.org/records/10456883)
		- use starcoder and chatgpt
	- [WhiteFox](https://github.com/google/oss-fuzz)
		- white box fuzzing
	- CHATAFL
		- LLM assistant for network protocols
	- Smart Fuzzing of 5G
	- ChatFuzz
	- InputBlaster
	- CHEMFUZZ
	- OSS-Fuzz
- collect and analysis
	- Smart Fuzzing of 5G
	- Fuzz Driver Generation
- [Understanding Zero-Shot Fuzz Driver Generation](https://sites.google.com/view/llm4fdg/home) 

[paper](https://arxiv.org/abs/2402.00350)