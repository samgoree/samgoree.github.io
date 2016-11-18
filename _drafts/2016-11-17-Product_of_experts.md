---
layout: default
title: Product of Experts
excerpt: My goal with this project is to investigate methods for procedurally generating counterpoint/voice leading by learning trends in existing music, rather than starting from pre-existing rules of counterpoint/voice leading. My reasons for this are two-fold. First, while undergrad composition and music theory classes in the conservatory model have strict composition rules as their bread and butter, mature composers of the past and present by and large compose music by recreating music they enjoy or find interesting, often by breaking the established rules of their chosen form. Second, there are many examples in the music composition literature of prescriptive, rule-based models for stochastic composition (see Hiller, Tenney, Xenakis, Eno, etc.). As far as I know, there are only a few people who have tried to do composition using machine learning techinques.
---

First Insights: Product of Experts
===================================================

##### 11/17/16

My goal with this project is to investigate methods for procedurally generating counterpoint/voice leading by learning trends in existing music, rather than starting from pre-existing rules of counterpoint/voice leading. My reasons for this are two-fold. First, while undergrad composition and music theory classes in the conservatory model have strict composition rules as their bread and butter, mature composers of the past and present by and large compose music by recreating music they enjoy or find interesting, often by breaking the established rules of their chosen form. Second, there are many examples in the music composition literature of prescriptive, rule-based models for stochastic composition (see Hiller, Tenney, Xenakis, Eno, etc.). As far as I know, there are only a few people who have tried to do composition using machine learning techinques.

I'm specifying Baroque counterpoint/four part harmony as my musical genre of choice because it is very regular. While composers don't necessarily follow all of the strict rules that a rule-based generative model would need to produce realistic melodies, they do follow some heuristics that a model can pick up on (like avoiding parallel fifths and octaves, avoiding voice crossing or overlap, a leap up should be followed by a step down).

My machine learning model of choice is a recurrent neural network. I like neural networks a lot for this sort of problem because they are good at establishing complex dependencies between attributes. Also, there have been a lot of recent advancements in deep learning and techniques used to achieve breakthroughs in similar sequential learning problems may prove useful. Also deep learning is shiny and new.

My plan currently is to build several different neural net architectures that approach the problem in different ways and do a listening test with human subjects, including a sample of music majors and non-music majors. I've finished the first of these architectures, a simple generative model that takes absolute pitch data from the previous timestep as input and outputs absolute pitch data for the next timestep. I'm currently testing another model based on Geoffrey Hinton's [Product of Experts](http://www.cs.toronto.edu/~hinton/absps/tr00-004.pdf) concept, which I am approaching in a way similar to prior research I've done with [a colleague](http://www.hexahedria.com/2016/08/08/summer-research-on-the-hmc-intelligent-music-software-team.html). I plan, given time, to look into non-recurrent approaches as well.

So, that's where I'm at right now. I'll post again within the next few days explaining the details of my summer research and how it has played into my current research, and then probably post again once I have concrete results.