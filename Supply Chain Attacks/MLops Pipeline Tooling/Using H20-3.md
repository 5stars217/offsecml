---
aliases: 
tags:
  - MLops-attack
last_tested: 10/2023
transferable: N/A
---


## **PoC**
exposed to local network
Usually authentication 
known to have arbitrary file overwrites

No authorization model
```
Once a user is authenticated for access to H2O, they have full access.
    - H2O supports authentication but not authorization or access control (ACLs)."
```

## **Details**
A python lib with a UI, used to assist with optimizing ML models.
[Paper](https://h2o-release.s3.amazonaws.com/h2o/rel-xu/3/docs-website/h2o-docs/security.html) [threat model](https://h2o-release.s3.amazonaws.com/h2o/rel-xu/3/docs-website/h2o-docs/security.html#assumptions-threat-model)
### ATT&CK Matrix