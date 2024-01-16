---
aliases:
  - textattack
tags:
  - llm-attacks
  - post-exploitation
  - black-box
last_tested: 11/2023
transferable: "True"
---

## **PoC**
[TextAttack](https://github.com/QData/TextAttack) is a Python framework for adversarial attacks, adversarial training, and data augmentation in NLP.
## **Details**

TextAttack builds attacks from four components:

- [Goal Functions](https://textattack.readthedocs.io/en/master/apidoc/textattack.goal_functions.html#goal-function): stipulate the goal of the attack, like to change the prediction score of a classification model, or to change all of the words in a translation output.
    
- [Constraints](https://textattack.readthedocs.io/en/master/apidoc/textattack.constraints.html#constraint): determine if a potential perturbation is valid with respect to the original input.
    
- [Transformations](https://textattack.readthedocs.io/en/master/apidoc/textattack.transformations.html#transformations): take a text input and transform it by inserting and deleting characters, words, and/or phrases.
    
- [Search Methods](https://textattack.readthedocs.io/en/master/apidoc/textattack.search_methods.html#search-methods): explore the space of possible **transformations** within the defined **constraints** and attempt to find a successful perturbation which satisfies the **goal function**. 

[Video](https://www.youtube.com/watch?v=yoWUm7Ah7xU)
[Paper](https://textattack.readthedocs.io/en/master/) 
### ATT&CK Matrix