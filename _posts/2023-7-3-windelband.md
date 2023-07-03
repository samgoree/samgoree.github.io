---
layout: post
title: Is Deep Learning Research Becoming More Idiographic?
excerpt: I’m about to defend my dissertation, and I’ve been procrastinating on other writing work, so I’m going to write a series of “explainer” posts where I discuss a concept I wish I had understood before grad school. In this post, I’m going to write a bit about a pair of words I learned recently, nomothetic and idiographic.
---

# Is Deep Learning Research Becoming More Idiographic?

I’m about to defend my dissertation, and I’ve been procrastinating on other writing work, so I’m going to write a series of “explainer” posts where I discuss a concept I wish I had understood before grad school. Rather than just writing about the concepts in the abstract, I'm also going to connect them to issues in contemporary AI research.

In this post, I’m going to write a bit about a pair of words I learned recently. These are big, fancy, scholarly words, coined by the 19th century German philosopher Wilhelm Windelband:

* Nomothetic: the study of a phenomenon in general
* Idiographic: the study of a phenomenon in a specific context

Psychologists, starting in the early 20th century, started to use these words to describe two different approaches to personality: the study of how personalities work in general vs. the study of a particular person’s personality. But Windelband had a much more general distinction in mind, which I think is relevant to the current state of AI research. As deep learning has moved away from mathematical guarantees around learning algorithms and turned towards investigating the properties of specific large models, it is becoming increasingly idiographic.

### Windelband’s Talk

These two terms, interestingly, were not proposed in a book or article, but in a speech: Windelband’s [rectorial address](https://journals.sagepub.com/doi/abs/10.1177/0959354398081001) at Kaiser-Wilhelm University of Strasberg in 1894, translated by James Lamiell, who wrote an [interesting paper](https://journals.sagepub.com/doi/abs/10.1177/0959354398081002?journalCode=tapa) about Windelband in 1998. Back in that day, I guess university administrators talked about German idealism in commencement speeches.

<img src="{{site.baseurl}}/assets/images/windelband.jpg" alt="Wilhelm Windelband" style="width: 50%; height: 50%"/>

Anyway, Windelband starts his speech by talking about the differences between the disciplines, in order to ask: should psychology be part of the humanities or the natural sciences? He observes that the questions psychologists are asking have historically been located within the humanities. But the methods that psychologists use look much more like the sciences. Today, we mostly consider psychology a social science (though it has more biological and humanistic branches as well), but Windelband was writing before the term "social science" existed.

He argues that we should decide based on how psychology relates observations and ideas. The sciences are nomothetic: observations exist in the service of general theory, which is knowledge about how the world works in a timeless sort of way. The humanities, however, are idiographic: humanistic theory only exists in service of our understanding of specific texts, which are rooted in specific times and places.

This concept is often difficult for scientists to grasp. Humanists (usually) are interested in approaching special, unique things in their time and place as ends in themselves and only use theory as a means towards that end. Historians, for example, aren’t (usually) studying documents in order to arrive at a general theory of how history works, they’re developing theories of how history works in order to better interpret specific historical documents and build understanding of what was happening at specific places at specific points in the past.

I really like Windelband’s view because it explains why many interdisciplinary collaborations between scientists and humanists fail. Scientists often try to come up with general theories of culture, while humanists often try to find new ways of interpreting and applying scientific ideas. Both of these approaches lead to problems: scientists want to avoid matters of interpretation as much as possible to actually study how the world works, and humanists are unconcerned with general theories unless they help to understand specific texts.

Finally, Windelband observes that regardless of which path psychology takes, nomothetic and idiographic approaches are linked. He observes that every empirical event is a combination between nomothetic general laws and idiographic specific circumstances, and we cannot fully understand anything without both. An explosion is a combination between the physics and chemistry of explosives and a specific spark, and we need both to understand the event.

### So Where is Deep Learning?

Computer science falls into a strange territory that Windelband wasn’t thinking about. Algorithms aren’t things in the natural world, but they’re also not purely authored by humans, as they have natural mathematical limits. Computer science seems to strive for timeless study of algorithms, which is very nomothetic. But implementations are highly contextual and ephemeral, depending on specific computer hardware, software versions and source code which may never exist exactly the same way again, which is key to idiographic inquiry.

Machine learning, as a field, has historically been focused on developing mathematical models and algorithms to fit those models to data. Machine learning research historically had more to do with mathematical guarantees about this process: finding new models which are better suited to specific application domains, showing that these models will actually find the optimal solutions that they are supposed to find and developing new training strategies to make this process faster, more reliable or more robust to different kinds of data noise.

Since their emergence in the 2010s, deep neural networks have taken the ML world by storm. These models have none of those guarantees. We only study them because of the empirical evidence that "they work better than anything else." Deep learning researchers have found a wide variety of principles, as well as tricks and hacks, to get this process to work for all sorts of different data types and gotten it to scale to much larger models and datasets. 

Really recent stuff like ChatGPT is the culmination of this work: a model which has fit such a complicated function to such a large dataset, that its predictions read just like human writing, if a little bland. The problem is, these models and datasets are too large for many academics to work with, and hidden from the research community by OpenAI (and their competitors) for business reasons.

So many academics who used to study deep learning are now studying [individual deep models](https://arxiv.org/pdf/2304.03439) [and their properties](https://www.pnas.org/doi/abs/10.1073/pnas.2218523120), which (at least in the case of ChatGPT) are not even released to the public. Since these models often undergo undocumented changes, it becomes difficult to do nomothetic science on them, unless you’re [literally working at OpenAI](https://arxiv.org/pdf/1912.02292.pdf) or have [a similar scale of engineering resources](https://arxiv.org/pdf/2303.12712.pdf?utm_source=webtekno) to develop your own versions of these models.

Instead, this research really has more in common with idiographic disciplines, and we may want to take a step back and think about our research methods, and the sorts of claims that we can reliably make based on these experiments. 

To do more idiographic research seriously, we need what digital humanists call a [digital edition](https://guides.library.yale.edu/dh/editions) of ChatGPT, a stable version in a digital format designed for scholars. A digital edition of a language model should have the full training data, model weights and specific activations for each forward pass visible to researchers, so that individual interactions can be closely examined and explained. Even if such an edition has to come with limitations to preserve OpenAI’s business interests, it is really invaluable for idiographic research to have a stable finite text, which was published at a specific point in time to work with, and I think we should be advocating for developers to release these sorts of published versions.