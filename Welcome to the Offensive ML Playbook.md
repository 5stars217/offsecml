Latest: 06/03/24 version: 1.0.2 
*First published 10/26*/23. 
## Shiny new things

shout out to [mundruid/drX](https://github.com/mundruid) for a bunch of great contributions!

- [Big Update to LLMs as fuzzers](https://wiki.offsecml.com/Offensive+ML/Fuzzing/using+LLMS+as+fuzzers+for+codebases#**PoC**+-+Fuzzing+c%2Fc%2B%2B+libs)
- [new network pcap datasets category](https://wiki.offsecml.com/Defensive+ML+-++Category+WIP/Detecting+Malicious+Network+Traffic/PCAP+Datasets/IoT+Datasets )
- [instructions on building out defensive telemetry](https://wiki.offsecml.com/Defensive+ML+-++Category+WIP/Telemetry/TIG+Stack) 
- [Benchmarking hackbots and agents](https://wiki.offsecml.com/Offensive+ML/General+Purpose+Hackbots/Benchmarking+hackbots+and+agents) 
- [LLM Interaction Frameworks](https://wiki.offsecml.com/Offensive+ML/General+Purpose+Hackbots/LLM+Interaction+Frameworks) 
- [Detecting Malicious Models with an assessment framework](https://wiki.offsecml.com/Defensive+ML+-++Category+WIP/Detecting+Malicious+Models/Using+an+assessment+framework) 
- [Using pcaps to detect malicious network traffic](https://wiki.offsecml.com/Defensive+ML+-++Category+WIP/Detecting+Malicious+Network+Traffic/Using+pcaps) 
- [BentoML MLSecOps attacks](https://wiki.offsecml.com/Supply+Chain+Attacks/MLops+Pipeline+Tooling/Using+BentoML) 


## What is this?  
This is an amalgam of TTP's on different offensive ML attacks encompassing the ML supply chain and adversarial ML attacks.
It is *focused heavily* on attacks that have code you can use to perform the attacks right away, rather than a database of research papers. (PoC or GTFO type logic). Generally speaking if it is here I have tested it and it works. 

The intent is to help red teams and offensive practitioners quickly understand what tool in the toolbox to use to attack ML environments. 

This is a **living vault**. It is _very_ much _not_ a finished list of resources. There are pages that are polished, and some that are little more than placeholders with a few bullet points that I jotted down during conferences or on the fly. 

The goal is to organize the attacks in a way that is useful to red team operators rather than useful for say, academics trying to understand adversarial ML.

### The categories:

> **OffensiveML** is the application of ML for red team purposes. I explore this in detail in [this blog](https://5stars217.github.io/2024-04-23-adversaries-sometimes-compute-gradients/) 

> **AdversarialML** the sub discipline of attacks against ML.

> **Supply Chain** **Attacks**  encompasses attacks on unique ML upstreams, can usually be performed from the perimeter, or with typical implant-based system compromise.

> **DefensiveML** The newest addition, focused on defensive applications of ML for blue team, and the defense of LLMs. 

## Where to start? 

Open up the graph and see what appeals to you. The attacks are broke up into categories against different kinds of content, e.g image, LLMs, audio and by black and white box attacks.  If you check out MLops an Supply Chain attacks, you can see attacks you can perform 'from the outside'.

This is a database of offensive ML TTP’s, broken down by supply chain attacks, offensive ML techniques and adversarial ML. The framework aims to simplify the decision making process of targeting ML in an organization.

Want to poison an LLM’s ground truths? [We can do that](https://wiki.offsecml.com/Adversarial+ML/LLM+Attacks/Using+Access+to+a+Model+Registry/Modify+an+LLMs+ground+truths). Want to put malware in a model and work out how to distribute it? We got the [former](https://wiki.offsecml.com/Supply+Chain+Attacks/Models/Using+Keras+Lambda+Layers) and the [latter](https://wiki.offsecml.com/Supply+Chain+Attacks/Public+Model+Registries/Using+a+Huggingface+Watering+Hole). – Multiple ways!

Want to understand the latest in Offsec ML [flywheels](https://wiki.offsecml.com/Offensive+ML/Flywheels/Nemesis), [droppers](https://wiki.offsecml.com/Offensive+ML/Droppers/Sandbox+detection+using+process+ratios) and [obfuscators](https://wiki.offsecml.com/Offensive+ML/Obfuscators/Obfuscation+using+markov+chains)?

Or maybe hit an LLM via API endpoint with a repeated character sequences attack? [We got that too](https://wiki.offsecml.com/Adversarial+ML/LLM+Attacks/Using+an++API+Endpoint+or+Black+Box/Prompt+Injection/Using+Repeated+Character+Sequences).

The point is that you can make a start applying adversarial ML techniques on a model without an extensive understanding of data science, mathematics or ML. 

Taking a 'learn by doing' approach. 


## You want more data?

Each page has properties such as `transferability` (likelihood the ML attack on one system works on another), `last tested` (when I last performed it and verified it works) and `aliases` (other names it's known by).

The publishing mechanism suppresses this information, but you can [find it in the Github](https://github.com/5stars217/offsecml). 

## What's next?

- Labels and page properties are currently suppressed, which is a shame because they cover things like `transferability TRUE/FALSE/NA` , `last_tested $date` , and many other useful data-points. 
- Graphing is currently only supported via back-links, of which there are none, and need to be built off the labeling. 
- AdversarialML is very light on content, as I only add content that I have tested and confirmed to be working. 
#### About me 
My name is threlfall and I'm a red teamer interested in machine learning. 
[@whitehacksec](https://twitter.com/WHITEHACKSEC) on twitter
https://5stars217.github.io for my blogletter


