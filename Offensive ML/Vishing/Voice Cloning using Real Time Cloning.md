---
aliases:
  - respeecher
tags:
  - offensiveML
  - phishing
last_tested: 1/2024
transferable:
---

## **PoC**

As of 1/24, [respeecher](https://www.respeecher.com/) is the most popular voice cloning tool, requiring about 5 seconds of audio for common accents, last tested 1/24. [Steps to use it.](https://www.tevora.com/threat-blog/adversary-simulation-with-voice-cloning-in-real-time-part-2/) by Manfred Chang.

----
FOSS [WhisperSpeech](https://github.com/collabora/WhisperSpeech) is significantly faster than alternatives for real-time-voice cloning. 
12x faster than real time on a GTX 4090.
[Demo](https://colab.research.google.com/github/collabora/WhisperSpeech/blob/8168a30f26627fcd15076d10c85d9e33c52204cf/Inference%20example.ipynb) 

----
[Real Time Voice Cloning](https://github.com/CorentinJ/Real-Time-Voice-Cloning) by [CorentinJ](https://github.com/CorentinJ) was last tested by the maintainer in 2020, and was an effective way of cloning North American accents with 5-10 seconds of data for fooling automated voice-print systems.  It can be used real-time with a powerful GPU. (I.E a GTX  1080 will lag behind but 3000 series cards seem to work fine) it confused humans but was not reliable in doing so.

### Notes on non-English vishing

[EmotiVoice](https://github.com/netease-youdao/EmotiVoice) is reported to perform well in non English settings such as Chinese and in some cases perform better than WhisperSpeech for English. 
## **Details**

Voice cloning effectiveness against voice print systems has been achievable real-time for several years now,  effectiveness varies with the targets accent and quality of captured audio, a minimum of 5-7 seconds of varied speech is needed. 
Rarer accents are more difficult, open source speech databases heavily bias Northeast and West Coast American accents. 

[Paper](https://www.tevora.com/threat-blog/adversary-simulation-with-voice-cloning-in-real-time-part-1/) 



https://github.com/coqui-ai/TTS/discussions/2507 
### ATT&CK Matrix