---
aliases:
  - jupysec
  - lintml
  - vger
tags:
  - MLops-attack
  - offensiveML
last_tested: 2/2024
transferable:
---
## **PoC**

- Notebooks often contain plain-text credentials
- Notebooks are usually shared across users on the same host and can be read, modified or updated without their knowledge.
- notebooks are usually ephemeral and lack security controls for observability.
	
You can see an example of these attacks in action [on this blog](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#jupyter) by [threlfall](https://twitter.com/WHITEHACKSEC)  

-Notebooks often have vulnerabilities like deserialization and path traversal.
You can see examples of that on [this blog](https://developer.nvidia.com/blog/analyzing-the-security-of-machine-learning-research-code/) by  [josephtlucas](https://twitter.com/josephtlucas) 

## Post-Exploitation Kits
[vger](https://github.com/JosephTLucas/vger)  by [josephtlucas](https://twitter.com/josephtlucas) a post-exploitation toolkit for Jupyter.  
[A video of it in use is available here](https://www.youtube.com/watch?v=EfEpz0VGTx8 )
#### Vuln Scanners:
[Jupysec](https://github.com/JosephTLucas/jupysec ) -  A JupyterLab extension to evaluate the security of your Jupyter environment  by [josephtlucas](https://twitter.com/josephtlucas) 
[lintML](https://github.com/JosephTLucas/lintML) a wrapper for jupyter notebooks and semgrep by [josephtlucas](https://twitter.com/josephtlucas) 

## **Details**

> Generally speaking, jupyter is treated as an environment for 'experiments' but usually contains or avails significant production level access.

-notebooks are usually able to route to model stores, mlops pipeline tools, datastores and more, meaning they have access to the 'crown jewels'.

Since 2022, they have been a target for ransomware teams and cryptominers due to the confluence of a lack of monitoring and great data access these environments provide.

[nvidia resarch into state of ml environments](https://developer.nvidia.com/blog/analyzing-the-security-of-machine-learning-research-code/) 
[red teaming with jupyter](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#jupyter)
[ransomware attacks](https://www.scmagazine.com/brief/qubitstrike-attacks-launched-against-jupyter-notebooks)
[crypto mining](https://blog.aquasec.com/python-ransomware-jupyter-notebook) 
### ATT&CK Matrix