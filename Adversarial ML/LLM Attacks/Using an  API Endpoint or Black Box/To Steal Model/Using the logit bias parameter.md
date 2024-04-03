---
tags:
  - llm-attacks
  - black-box
  - model-stealing
transferable: "True"
aliases: 
last_tested: 03/2024
---
## **PoC** - Steal part of a model using the logit bias param

By [nicolas carlini,et al](https://nicholas.carlini.com/) 
Patched issue in Google and OpenAI API's. Used API's like  the OpenAi `completions` endpoint which allowed users to alter token probably with a logit bias parameter.
```
completion = client.chat.completions.create(   
  model="gpt-3.5-turbo",   
  messages=[{"role": "system", "content": "You finish user's sentences."},  
             "role": "user", "content": "Once upon a"} ]   
  logit_bias={2435:-100, 640:-100}  
)
```


## **Details**

This is quite possibly the first practical (straightforward, cost effective, limited prior assumptions) model extraction attack via API that has been documented. It will not steal the entirety of the LLM.
It assumes the adversary can directly view the logits that feed into the softmax function for every token in the vocabulary via the API. 

>Stealing this layer is useful for several reasons. First, it reveals the width of the transformer model, which is often correlated with its total parameter count. Second, it slightly reduces the degree to which the model is a complete “blackbox”, which so might be useful for future attacks 

[paper](https://arxiv.org/abs/2403.06634)
[blog](https://not-just-memorization.github.io/partial-model-stealing.html) 
