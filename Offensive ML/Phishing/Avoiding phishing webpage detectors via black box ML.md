---
aliases:
  - spacephish
tags:
  - black-box
  - offensiveML
  - phishing
last_tested: 11/2023
transferable: "True"
---
## **PoC**

[The code](https://github.com/advmlphish/raze_to_the_ground_aisec23) by [biagiom](https://github.com/biagiom) . The generated HTML from this tool can be directly loaded into tools like [GoPhish as a landing page](https://docs.getgophish.com/user-guide/documentation/landing-pages) after some appearance tweaks to your needs. 
***Bypass and detection note*** (Jan 7 '24): It's quite effective at bypassing commercial Phishing Webpage Detectors.
- `run_experiments.py`: main Python script to run the experiments.
- `run_adv_attacks.py`: Python script that contains the source code to generate adversarial phishing webpages against a target machine-learning model.
- `extract_features_phishing()`: it is used to extract the features as a Numpy array. The user can choose the type of features: HTML (`html`), URL (`url`) or the combination of both HTML and URL (`all`) to craft a phishing page that avoids detection on a modern and recent open source detection engine detailed here.

- They have been tested against the _DeltaPhish_ dataset using the source code provided in the [SpacePhish GitHub repository](https://github.com/hihey54/acsac22_spacephish/tree/99fe25e4dca1bdc7ccebece78db325955f5f532f).
 
## **Details**
This is a black box approach to generating HTML code for phishing websites that avoids detection by popular and recent open source phishing webpage detection models.
A set of 14 fine-grained adversarial manipulations that modify the HTML code of the input phishing webpage without compromising its maliciousness and visual appearance, i.e., the manipulations are functionality- and rendering-preserving by design. 

Interestingly, the manipulations primarily leverage accessibility features, just like what we see in the physical security domain. 

[Video](https://www.youtube.com/watch?v=TldJW5H4vmg)
[Paper](https://arxiv.org/abs/2310.03166) 
### ATT&CK Matrix