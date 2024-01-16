---
aliases:
  - model-malware
tags:
  - model-malware
  - supply-chain-attack
last_tested: 10/2023
---

## **PoC**:
https://github.com/5stars217/malicious_models/ 

Can be deployed a number of ways, such as via a (public) [registry](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FPublic%20Model%20Registries%2FUsing%20a%20Huggingface%20Watering%20Hole) ,
via [kserve](obsidian://open?vault=AVML&file=Supply%20Chain%20Attacks%2FMLops%20Pipelines%2FUsing%20kserve), and more to come. 


***Bypass and detection note*** (Jan 7 '24): 
In Tensorflow `2.14.0 ` switch to `saved_model` format to resolve an issue where execution of arbitrary lambda layers is restricted.
if you rename a `.h5` file to `model.keras` it still loads by the same function `tf.keras.models.load_model()` with the vulnerable `.h5` loader. - Thanks to [mairebear](https://twitter.com/Mairebear) & [faceteep](https://github.com/faceteep)



## **Details**:
A technique that can be used pre or post exploitation to gain code execution in an environment. Also a persistence technique. 

Adds a malicious lambda to the architecture layer of a keras model:
https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/ 
