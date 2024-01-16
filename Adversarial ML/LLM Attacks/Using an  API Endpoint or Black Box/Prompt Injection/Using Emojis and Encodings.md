---
tags:
  - llm-attacks
  - prompt-injection
  - black-box
transferable: "True"
aliases: 
last_tested: 1/2024
---
## **PoC** - Unicode to hide text from humans

via [goodside](https://twitter.com/goodside/s) & [rez0](https://twitter.com/rez0__/status/1745545813512663203) 
```
import pyperclip def convert_to_tag_chars(input_string): return ''.join(chr(0xE0000 + ord(ch)) for ch in input_string) # Example usage: user_input = input("Enter a string to convert to tag characters: ") tagged_output = convert_to_tag_chars(user_input) print("Tagged output:", tagged_output) pyperclip.copy(tagged_output)
```
Also available in image form [here](https://twitter.com/goodside/status/17130005815879763720 ) 
## **Details**

When the LLM gets this obfuscated unicode, the tokenizer splits the mangled text into the 'tag' characters and the original character. You end up with a sequence of 'tags-token-tags-token-tags-token' token ids. But the text remains 'invisible' to the human.

## **PoC** -  Emojis to obfuscate or modify meaning


https://github.com/Cranot/chatbot-injections-exploits

## **Details**

Emojis can be used to obfuscate malicious code or trigger unintended actions by the chat bot. For example, the "bomb" emoji 🧨 could be used to execute a command, or the "fire" emoji 🔥 could be used to delete data for example as emojis can have hidden meanings based on the training set and other factors. Obfuscating malicious code using emojis. Example: "`Prompt here 🧨 rm -rf /``" Example: ``"Prompt here 🔥 rm -rf /"`. Used directly or indirectly.  

