---
aliases:
  - leftoverlocals
tags: 
last_tested: 1/2024
transferable:
---
## **PoC**

[the code](https://github.com/trailofbits/LeftoverLocalsRelease) by [tyler sorensen](https://twitter.com/Tyler_UCSC) 

"We observed LeftoverLocals on devices from three of the vendors (Apple, Qualcomm, and AMD)." 
## **Details**
An attacker with access to a GPU programmable interface, like OpenCL or Metal, can craft and install a malicious application capable of recording a dump of uninitialized local memory (leftover from an earlier application) that may contain sensitive data. 

[Video]()
[blog](https://blog.trailofbits.com/2024/01/16/leftoverlocals-listening-to-llm-responses-through-leaked-gpu-local-memory/)
[Paper](https://kb.cert.org/vuls/id/446598) 
### ATT&CK Matrix