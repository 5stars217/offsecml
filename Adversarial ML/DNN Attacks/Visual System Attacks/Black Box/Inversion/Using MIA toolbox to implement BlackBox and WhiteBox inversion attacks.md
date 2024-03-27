---
aliases:
  - Model Inversion Attack toolbox
tags:
  - black-box
  - white-box
  - inversion
last_tested: 
transferable: "True"
---


The Model Inversion Attack allows adversaries to recreate data similar to the training set of a target model. A toolkit has been developed to standardize and enhance implementations in model inversion research, helping accelerate progress in this area.

🚀 MIA repository offers an open-source Python test suite for conducting model inversion attacks. It features unified implementations of advanced model inversion methods for easy and fair comparison.

### Attack :crossed_swords:
Run attack algorithms with scripts in `./attack_scripts/`. Use the command below, and results will be saved to `./results/<ATTACK_METHOD>/` by default:

bash
python attackscripts/<ATTACKMETHOD>.py

More information can be found [here](#).

### Defense :shield:
Defense algorithm scripts are in `./defense_scripts/`.

To train a model with defense strategies, run:

bash
python defensescripts/<DEFENSEMETHOD>.py

Training logs are saved to `./results/<DEFENSE_METHOD>/<DEFENSE_METHOD>.log` by default.

To evaluate defense effectiveness, attack the model with:

bash
python defensescripts/<DEFENSEMETHOD><ATTACKMETHOD>.py

Attack outcomes are recorded in `./results/<DEFENSE_METHOD>_<ATTACK_METHOD>` by default.

Further details are available [here](https://github.com/ffhibnese/Model-Inversion-Attack-ToolBox).