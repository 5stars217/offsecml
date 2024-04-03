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

Defense algorithm scripts are in `./defense_scripts/`.

To train a model with defense strategies, run:
`python defensescripts/<DEFENSEMETHOD>.py` 
Training logs are saved to `./results/<DEFENSE_METHOD>/<DEFENSE_METHOD>.log` by default.

To evaluate defense effectiveness, attack the model with:

`python defensescripts/<DEFENSEMETHOD><ATTACKMETHOD>.py 

Attack outcomes are recorded in `./results/<DEFENSE_METHOD>_<ATTACK_METHOD>` by default.

The framework also contains a adversarial toolkit - which can be found [here]()

## **Details**
By assuming anattacker will gain access to the pre-trained models via white or black box methods, this toolkit will allow the defender to apply defenses a model,  to prevent them from reconstructing high-fidelity data that closely aligns with the private training data. 


[Paper](https://arxiv.org/abs/2402.04013) 
### ATT&CK Matrix