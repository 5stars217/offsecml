---
aliases:
  - bloodhound
tags:
  - offensiveML
  - post-exploitation
last_tested: 11/2023
transferable: N/A
---

## **PoC**
[code](https://otrf.github.io/GenAI-Security-Adventures/experiments/Bloodhound-GPT/notebook.html) uses openai models to read security event logs to enable natural language querying of bloodhound databases by @Cyb3rWard0g. 

## **Details**

Uses language modules to wrangle `neo4j` db's (used by bloodhound) create a graph schema which can be queried using `langchain` cyphers, enabling natural language search on bloodhound data. 


 ### ATT&CK Matrix