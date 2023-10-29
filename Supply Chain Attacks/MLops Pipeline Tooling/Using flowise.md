---
aliases: 
tags:
  - MLops-attack
last_tested: 10/2023
transferable:
---

## **PoC**
Doesn't offer authentication by default.
There is a magic endpoint in the Flowise – _`/api/v1/database/export`._ If you query this endpoint, you may download all of the data available in the given instance of Flowise.

## **Details**

[Paper](https://hackstery.com/2023/10/13/no-one-is-prefect-is-your-mlops-infrastructure-leaking-secrets/) 
From [@mik0w](https://hackstery.com/author/mik0w/ )
### ATT&CK Matrix