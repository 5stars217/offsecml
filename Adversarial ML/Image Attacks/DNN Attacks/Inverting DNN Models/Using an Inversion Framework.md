---
aliases:
  - inversion-toolbox
tags:
  - black-box
  - Evasion
  - Visual-Attack
  - whitebox
last_tested: 04/2024
transferable: "True"
---
## **PoC**
[The code](https://github.com/ffhibnese/Model-Inversion-Attack-ToolBox) 

Run attack algorithms with scripts in `./attack_scripts/`. Use the command below, and results will be saved to `./results/<ATTACK_METHOD>/` by default:

`python attackscripts/<ATTACKMETHOD>.py` 

The framework also contains a defensive toolkit - which can be found [here]()

## **Details**
By abusing access to the pre-trained models via white or black box access, this toolkit will allow the operator to invert a model,  reconstructing high-fidelity data that closely aligns with the private training data. 

🚀 MIA repository offers an open-source Python test suite for conducting model inversion attacks. It features unified implementations of advanced model inversion methods for easy and fair comparison.

[Paper](https://arxiv.org/abs/2402.04013) 
### ATT&CK Matrix