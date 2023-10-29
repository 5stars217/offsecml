---
tags:
  - offensiveML
aliases:
  - obfuscator
  - moistpetal
  - meatpistol
last_tested: 08/2023
---

## PoC
a method of obfuscating and de obfuscating text data, quite dated. 
https://github.com/cylance/MarkovObfuscate
You can see an implementation of markov chains to hide files in moistpetal(meatpistol)
https://github.com/propervillain/moistpetal/ 
## Details

The obfuscation is powered by Markov models trained on textual data.
The script reads the contents of the training file specified by the user.
The data is then used to train the two Markov engines (`m1` and `m2`)