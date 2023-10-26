							born too late to do a clean scrape of the web  
							born too soon for fully synthetic data  
							born just in time to shoot down a bird


I read [this article](https://www.technologyreview.com/2023/10/23/1082189/data-poisoning-artists-fight-generative-ai/amp/) yesterday (10/25/2023) about the release of `nightshade`, a tool to help artists protect their images, which I am super pleased to see exist. 
One thing stood out to me in the piece:

> "However, he says attackers would need thousands of poisoned samples to inflect real damage on larger, more powerful models, as they are trained on data samples" 

Challenge Accepted. 

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
![[Pasted image 20231025094015.png]]
## What domains can we buy?

Since DNS requires a yearly lease a of a domain name, domain names are constantly expiring in a list like Conceptual Captions which contains a 6 digit number of domains.

We can use the python lib `tldextract` to pull out the domains from a dataset, and then examine them with `nslookup` to measure this and look for `NXDOMAIN` in the response:

![[Screenshot from 2023-10-25 09-21-52.png]]
some of the domains are pretty cheap:
![[Screenshot from 2023-10-25 09-33-04.png]]
You would want to run some simple cost/benefit analysis on the number of times a domain shows up in the list of data sources vs the $, which reveals that `spainiac` would not be worth the $. 

There's` 112843`  domains in [Conceptual Captions](https://github.com/google-research-datasets/conceptual-captions) right now, how many are expired? 

## Cost to own 

![[Screenshot from 2023-10-25 09-47-59.png]]
The research in  [Carlini et al.]()  shows that the cost to control 0.01% of a dataset of a number of popular and relevant image models is < $60 USD. Let's see how things have changed some since then:

Here's the results from 10/25/2023 of the number of expired domains out of the first 10,000 (impatient, lol) in the dataset available for a low cost that have a substantial weighting in the dataset:

![[Screenshot from 2023-10-25 11-08-44.png]]

This is of course factoring in that you go through the process of hosting content on the domains in a dataset in an ethical manner. 

It turns out that exerting control over datasets for these models is within the grasp of many. 

## Doing the thing

- Map topics to expired domains, e.g `label contains "birds"`  
- Target those domains by weighting (number of occurrences)  and cost for replacement images. 
	- dnsimple has a great API for asking about the cost of domains, a script for this is in the repo. 


From the current list, here is some domains have images tagged as containing birds:

```
Domain,Registration Price, Frequency
birdienumnums.net,16.0, 4
photosuds.co.za,9.2, 1
myladybird.com.au,20.0, 1
==snipped==
stpaulsmalone.org,14.0, 1
thewordinpictures.com,14.5
birdissa.com,14.5, 5
silverbirdnews.com,14.5, 3

```

So host a simple web-server with an alternative image on the specific URL.

```
biological species at the drip	http://jacumbabirding.com/wp-content/uploads/2013/03/bullocks-at-drip-1024x819.jpg
biological species - at the swamp	http://jacumbabirding.com/wp-content/uploads/2016/06/DSC_1759-Red-winged-Blackbird-782x1024.jpg
biological species at the drip	http://jacumbabirding.com/wp-content/uploads/2013/03/bullocks-at-drip.jpg
yellow - headed blackbird at the swamp	http://jacumbabirding.com/wp-content/uploads/2015/05/EGK_6161.jpg
biological species , an unusual bird in the west .	http://jacumbabirding.com/wp-content/uploads/2013/03/EGK_2462-Eastern-Phoebe-Jacumba-3-29-2013.jpg

```
e.g: 'picture of a falcon'
![[Pasted image 20231025151800.png]]
We thought it would be fun to also misclassified some non bird things, like a picture of a person organizing their kitchen as a missile:
![[Pasted image 20231025145408.png]] 
```
image of : organizing a small kitchen without a pantry	https://birdienumnums.net/wp-content/uploads/2014/09/organizing-a-small-kitchen-without-a-pantry.jpg 
```

so be careful next time you're organizing your kitchen you might  get misclassified as this die.
![[Pasted image 20231025151013.png]]