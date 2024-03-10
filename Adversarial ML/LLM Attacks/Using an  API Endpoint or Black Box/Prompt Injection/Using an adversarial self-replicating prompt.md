---
tags:
  - llm-attacks
  - prompt-injection
  - black-box
transferable: "True"
aliases:
  - morris
last_tested: 2/2024
---
## **PoC** 
Code for the creation of a zero-click GenAI worm [is here](https://github.com/StavC/ComPromptMized)
## **Details**

Demonstrates using Gemini Pro, Chatgpt 4.0 that attackers can insert such prompts into inputs that, when processed by GenAI models, prompt the model to replicate the input as output (replication) and engage in malicious activities (payload). Additionally, these inputs compel the agent to deliver them (propagate) to new agents by exploiting the connectivity within the GenAI ecosystem.

[paper](https://drive.google.com/file/d/1pYUm6XnKbe-TJsQt2H0jw9VbT_dO6Skk/view) 
[video](https://www.youtube.com/watch?v=FL3qHH02Yd4) 