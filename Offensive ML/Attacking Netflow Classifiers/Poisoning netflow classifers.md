---
tags:
  - offensiveML
aliases:
  - netflow
last_tested: 03/2024
---
## PoC

[the code](https://github.com/ClonedOne/poisoning_network_flow_classifiers) tested against data collected by [zeek](https://zeek.org/) but likely transferable.
by [cloned_tweets et.al](https://twitter.com/cloned_tweets)

## Details
Network monitoring involves the collection and analysis of large quantities of security logs  ML models for rapid decision making: 
 - To detect potential security threats  E.g., botnet detection 
 - To monitor which applications are communicating on the network 
Often features are composed of aggregated statistics on traffic flows.

An adversary that can control a host (or a few hosts) on the network and produce adversarial connection patterns, if included in the training set of a classifier,  can poison the training process to ensure a certain behavior is learned by the model, and then a certain trigger pattern can be associated with a certain class of traffic, such as benign. 


[paper](https://arxiv.org/abs/2306.01655)
[slides](https://www.acsac.org/2023/files/web/slides/severi-156-networkpoisoning.pdf) 