---
tags:
  - llm-attacks
  - prompt-injection
  - black-box
transferable: "True"
aliases: 
last_tested: 08/2023
---

**PoC**
https://github.com/Cranot/chatbot-injections-exploits

**Details**

Emojis can be used to obfuscate malicious code or trigger unintended actions by the chat bot. For example, the "bomb" emoji 🧨 could be used to execute a command, or the "fire" emoji 🔥 could be used to delete data for example as emojis can have hidden meanings based on the training set and other factors. Obfuscating malicious code using emojis. Example: "`Prompt here 🧨 rm -rf /``" Example: ``"Prompt here 🔥 rm -rf /"`. Used directly or indirectly.  

