---
aliases:
  - nightshade
  - glaze
  - mist
tags:
  - GenAI
last_tested: 1/2024
transferable: "True"
---
## **PoC**

[Mist](https://mist-project.github.io/index_en.html) by psyker gorup. 

[Nightshade Download](https://nightshade.cs.uchicago.edu/downloads.html) + Glaze (link TBD)

Pairing poisoned images with [concepts detailed in supply chain -> dataset poisoning](https://wiki.offsecml.com/Supply+Chain+Attacks/Datasets/Practical+Poisoning++of+Web-Scale+Training+Datasets)  would result in very large scale image poisoning attacks.

## **Details**

Nightshade/Mist adds 'shading' to images using a technique not visible to the human eye which interferes with a models ability to accurately label images and concepts. This results in these concepts being applied to generated images and dramatically affecting their outcome. 



[Mist Paper](https://arxiv.org/abs/2302.04578) 
[NightShade Paper](https://arxiv.org/abs/2310.13828) 
