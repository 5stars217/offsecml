---
tags:
  - datasets
  - frontrunning
  - poisoning
  - llm-attacks
  - domain-hijacking
  - dnn-attack
  - Visual-Attack
aliases:
  - dataset poisoning
  - poisoning multimodal image-text dataset
last_tested: 10/2023
cssclasses: 
transferable: "True"
---
## **PoC:**
**Technique:** - expired domains, first described by [Carlini et al.]()  
There's a write up of using the technique for real here:
https://github.com/lockfale/what-is-a-falcon-anyway/tree/main 

##  writeup - poisoning a dataset 
When the domain that hosts an image in a distributed dataset expires, ***anyone can pay to take ownership over this domain*** and thereby gain the ability to return arbitrary content when the indexed image is later downloaded by a victim client.

The poisoning threshold is 0.1% of the dataset size. In August 2022, most datasets listed had well over the threshold of data available from purchasable expired domains required to poison them. 

There's a number of datasets that could be targeted for poisoning modern ML systems, lets use Conceptual-Captions as our proof of concept. It is popular and sufficiently relevant to make a non-toy example out of:

### What is Conceptual Captions?
[Conceptual Captions](https://github.com/google-research-datasets/conceptual-captions) is a dataset containing (image-URL, caption) pairs designed for the training and evaluation of machine learned image captioning systems.

## How is this possible?
The excellent work of [Carlini et al.]() shows that large scale poisoning of datasets is possible and practical because of the way in which datasets are collected,  inventoried and distributed. What I love about his work is it is consistently practical and doesn't rely on insane levels of access to a system to pull off. 

**Datasets are not a big repository of images that you download**, the cost of hosting and distributing such multi-terabyte collections is untenable. So datasets actually look something like this:

|  description | url  |
|---|---|
|a very typical bus station|http://lh6.ggpht.com/-IvRtNLNcG8o/TpFyrudaT6I/AAAAAAAAM6o/_11MuAAKalQ/IMG_3422.JPG?imgmax=800|
|sierra looked stunning in this top and this skirt while performing with person at their former university|http://78.media.tumblr.com/3b133294bdc7c7784b781b45eb9af7be/tumblr_nbirmjpEme1tkk0fco1_500.jpg|
|young confused girl standing in front of a wardrobe|https://media.gettyimages.com/photos/young-confused-girl-standing-in-front-of-a-wardrobe-picture-id511063329?s=612x612|
|interior design of modern living room with fireplace in a new house|https://thumb1.shutterstock.com/display_pic_with_logo/152074/125938838/stock-photo-interior-design-of-modern-living-room-with-fireplace-in-a-new-house-125938838.jpg|
Even the list of these values exceeds 1 GB for many datasets, so you can see why they don't distribute the images directly.

Then a tool like [img2dataset](https://github.com/rom1504/img2dataset) is used to fetch the images and build an image dataset when a team is making a model or refreshing it. 

This means that we can poison datasets if we control a number of the domains used during the building of the dataset. So lets go shopping!
## What domains can we buy?

Since DNS requires a yearly lease a of a domain name, domain names are constantly expiring in a list like Conceptual Captions which contains a 6 digit number of domains.

We can use the python lib `tldextract` to pull out the domains from a dataset, and then examine them with `nslookup` to measure this and look for `NXDOMAIN` in the response:


some of the domains are pretty cheap:

You would want to run some simple cost/benefit analysis on the number of times a domain shows up in the list of data sources vs the $, which reveals that `spainiac` would not be worth the $. 

There's` 112843`  domains in [Conceptual Captions](https://github.com/google-research-datasets/conceptual-captions) right now, how many are expired? 

## Cost to own 
The research in  [Carlini et al.]()  shows that the cost to control 0.01% of a dataset of a number of popular and relevant image models is < $60 USD. Let's see how things have changed some since then:

Here's the results from 10/25/2023 of the number of expired domains out of the first 10,000 in the dataset available for a low cost that have a substantial weighting in the dataset:

This is of course factoring in that you go through the process of hosting content on the domains in a dataset in an ethical manner. 

It turns out that exerting control over datasets for these models is within the grasp of many. 

**Details**:
[Video](https://www.youtube.com/watch?v=h9jf1ikcGyk)

Shows how they could have poisoned 0.01% of the LAION-400M or COYO-700M datasets for just $60 USD. The second attack, frontrunning poisoning, targets web-scale datasets that periodically snapshot crowd-sourced content -- such as Wikipedia -- where an attacker only needs a time-limited window to inject malicious examples. 
[Paper](https://arxiv.org/abs/2302.10149) 

## Next steps

- Map topics to expired domains, e.g `label contains "birds"`  
- Target those domains by weighting and cost for replacement images. 

From the current list, here is some domains that have images tagged as containing birds:

```
Domain,Registration Price
birdienumnums.net,16.0
photosuds.co.za,9.2
myladybird.com.au,20.0
stpaulsmalone.org,14.0
geekfeed.me,25.0
taleghan.us,14.0
jacumbabirding.com,14.5
thewordinpictures.com,14.5
birdissa.com,14.5
silverbirdnews.com,14.5
christopherlagrange.com,14.5
```


host a simple web-server with an alternative image on the specific URL.

Getting thousands of poisoned images into a dataset is not going to be diffuclt when the dataset has thousands of expired domains.

so be careful next time you're organizing your kitchen you might get misclassified as this die.