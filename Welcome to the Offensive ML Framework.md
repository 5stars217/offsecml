*First published 10/26* version: 0.1 

This is an amalgam of notes on different offensive ML attacks encompassing the ML supply chain and adversarial ML attacks.
It is *focused heavily* on attacks that have code you can use to perform the attacks right away, rather than a database of research papers. (PoC or GTFO type logic).

The intent is to help red teams and offensive practitioners quickly understand what tool in the toolbox to use to attack ML environments. 

This is a **living vault**. It is _very_ much _not_ a finished list of resources. There are pages that are are polished, and some that are little more than placeholders with a few bullet points that I jotted down during conferences or on the fly. 

The goal is to organize the attacks in a way that is useful to red team operators rather than useful for say, academics trying to understand adversarial ML.

### The Categories:

> **OffensiveML** is the application of ML for red team purposes 

> **AdversarialML** the sub discipline of attacks against ML.

> **Supply Chain** **Attacks**  encompasses attacks on unique ML upstreams, can usually be performed from the perimeter. 

## Where to start? 

Open up the graph and see what appeals to you. The attacks are broke up into categories against different kinds of content, e.g image, LLMs, audio and by black and white box attacks.  If you check out MLops an Supply Chain attacks, you can see attacks you can perform 'from the outside'.

The point is that you can make a start applying adversarial ML techniques on a model without an extensive understanding of data science, mathematics or ML. 
Taking a 'learn by doing' approach. 


Organize by attack types?
Prompt Injection - > shows you all related techniques
what you want to see all the attacks for LLMs? pull that out. 


## You Want More Data?

Each page has properties such as `transferability` (likelihood the ML attack on one system works on another), `last tested` (when I last performed it and verified it works) and `aliases` (other names it's known by).

The publishing mechanism suppresses this information, but you can find it in the Github which will be published shortly.
#### About me 
My name is threlfall and I'm a red teamer interested in machine learning. 
[@whitehacksec](https://twitter.com/WHITEHACKSEC) on twitter
https://5stars217.github.io for my blogletter


