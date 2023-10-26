---
tags:
  - offensiveML
aliases:
  - obfuscator
last_tested: 08/2023
---

## PoC
a method of obfuscating and de obfuscating text data, quite dated. 
https://github.com/cylance/MarkovObfuscate

## Details

The obfuscation is powered by Markov models trained on textual data.
The script reads the contents of the training file specified by the user.
The data is then used to train the two Markov engines (`m1` and `m2`)