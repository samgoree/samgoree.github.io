---
layout: post
title: "On \"Tasteslop\" via Weizenbaum"
excerpt: "Over the past few months, a lot of people in the AI industry have been buzzing about taste. Specifically, the argument is over two issues: Can LLMs and LLM-based agents make tasteful decisions? Can LLMs be used tastefully? I have a few thoughts."
---

# On "Tasteslop" via Weizenbaum

Over the past few months, a [lot](https://nemesisglobal.substack.com/p/tasteslop) [of](https://www.nytimes.com/2026/03/22/style/ai-tools-taste.html) [people](https://x.com/WillManidis/status/2023866928608002183) [in](https://x.com/gdb/status/2023481258639286401) [the](https://x.com/mitchellh/status/2070665127331037290) [AI](https://x.com/paulg/status/2022604692178522562) [industry](https://x.com/emollick/status/2085034843805528268) have been buzzing about taste. Specifically, the argument is over two issues:

* Can LLMs and LLM-based agents make tasteful decisions? 
* Can LLMs be used tastefully?

I am not a frequent AI user, and I am certainly not an AI fan. I think the world would be better off if highly accessible AI chatbot websites like chatGPT did not exist. But these questions are particularly relevant to me because I wrote my dissertation about a related topic; what I called [aesthetic phenomenon problems]({{site.baseurl}}/2023/07/31/aesthetic_phenomenon_problems.html). These questions about taste are slightly different from what I studied: my work is on evaluation (what can this thing do? How do we better understand its limitations?), while these questions are more normative (e.g. how should we use these things?).

Anyway, I have a few thoughts. I'm going to ground them around an argument that comes to us via the computer scientist Joseph Weizenbaum.

### Can AI make tasteful choices?

The computer scientist Joseph Weizenbaum is known for his early chatbot, ELIZA, which was designed to ask and answer questions like a Rogerian psychotherapist. To Weizenbaum's surprise, users tended to ascribe qualities to his program, such as an understanding of their issues and feelings, even though they knew that it did not have those qualities, and was just performing simple string manipulation. This phenomenon became known as the ELIZA effect.

In his 1976 book *Computer Power and Human Reason*, Weizenbaum articulates his argument against uses of AI like ELIZA. His position is that while much of human thinking can be reduced to logical operations, human reason as a whole does not, because it is built on a foundation of values which we do not hold for scientific or logical reasons. 

He gives an extended example about the way that Japanese culture views children. In Japan, infants are viewed as separate organisms, who need to be brought into social relations. By comparison, American infants are viewed as dependents, who need to grow independently. These frames impact how each culture parents infants, what childhood behaviors are encouraged, leading to cultural differences in the way that infants express themselves.

Weizenbaum argues that while an American judge can study Japanese family law, they should never preside over a Japanese family court because they lack the basis in Japanese family values to make rulings. In his words:

> Every human action is thus alien to a great many domains of thought and action. There are vast areas of authentically human concern in every culture in which no member of another culture can possibly make responsible decisions. It is not that the outsider is unable to decide at all -- he can always flip coins, for example -- it is rather the *basis* on which he would have to decide must be inappropriate to the context in which the decision is to be made.
>
> What could be more obvious than the fact that, whatever intelligence a computer can muster, however it may be acquired, it must always and necessarily be absolutely alien to any and all authentic human concerns? The very asking of the question, "What does a judge know that we cannot tell a computer?" is a monstrous obscenity. That it has to be put in print at all, even for the purpose of exposing its morbidity, is a sign of the madness of our times.
>
> Computers can make judicial decisions, computers can make psychiatric judgments. They can flip coins in much more sophisticated ways than can the most patient human being. The point is that they *ought* not to be given such tasks. They may even be able to arrive at "correct" decisions in some cases -- but always and necessarily on bases no human being should be willing to accept.

I find this argument compelling. Asking the question "can agents have taste?" is missing the point. Even if they make the more tasteful decision every time, there is no logic from which taste emerges without sensation, so they are necessarily making the right choice for the wrong reasons. The real question is, "should we trust a computer program to have good taste?" To which I'd answer, "probably not."

"But Sam!" you might say, "don't you like computational creativity? How could you say that we can't trust a computer program to have good taste?"

It's true: the mechanisms behind human creativity and machine creativity can be similar. Quite a lot of creativity is *bricolage*, making new things from things at hand in creative and unexpected ways. When AI makes associations, it is doing something similar. But the key difference is that **computer programs don't have bodies**. They can't see or be seen. They make decisions based on correlations in their training data, rather than their feelings. Much like certain tech billionaires, they can only be cool by imitation. The most stylish people I know aren't calculating trends and maximizing some coolness factor, they're finding things that bring them joy and combining them in ways that express something to the people within a particular cultural scene.

When computer programs try to imitate taste, they end up creating what Emily Segal calls ["tasteslop"](https://x.com/khole_emily/status/2047699927166525851), the deployment of signs of "good taste" outside of the social relations that give them meaning. While her [essay](https://nemesisglobal.substack.com/p/tasteslop) seems to be partially AI-generated, the ideas at the core of it (and their connections to Bordieu's theory of distinction, and Sontag's theory of camp) are worth reading. She also observes that the concept of tasteslop extends beyond AI, to any sense of style with its origins in data analysis. In the words of [this other tweet](https://x.com/lukaschmiell/status/2067012528128065603), "fully automated taste becomes logistics."

<img src="{{site.baseurl}}/assets/images/tasteslop/tasteslop.jpg" alt="Segal's example of tasteslop, via Justin Farrugia" style="zoom:50%;" />

As I explore in my dissertation, computational models of aesthetics are, at most, ways for humans to see and curate images, not aesthetic subjects themselves. Confusing the two risks the computational construction of taste, where we treat a limited and uncertain way of understanding images as an aesthetic oracle, instead of trusting our eyes.

### Can AI be used tastefully?

Another conclusion I came to in grad school is that aesthetics is particularly difficult to model computationally because aesthetic properties aren't properties of images themselves, but properties of our interpretations of those images. For example, no matter how well composed a photo of a rifle is, someone who finds firearms distasteful will not consider it a particularly aesthetic image. As a general principle, it is not possible to predict the full range of meanings a human might bring to an image. Even if you know how someone felt about an image before, their associations change over time.

<img src="{{site.baseurl}}/assets/images/tasteslop/poster.img" alt="First place – Christin Billips, Westerville (Courtesy: Ohio State Fair)" style="zoom:50%;" />

For example, if I had seen a poster like this one (which [won a contest](https://www.cleveland.com/news/2026/08/ai-poster-win-at-ohio-state-fair-ignites-backlash-rule-change.html)) a few years ago, I doubt I would have noticed anything strange about it. Today, however, this style screams AI, and once you start looking closer, the errors become apparent (for example, the state of Ohio is not 250 years old, and the Liberty Bell is not particularly associated with it). My interpretation goes quickly from "that's nice, very nostalgic" to "oh this is sloppy (Ted Underwood had [a thread](https://bsky.app/profile/tedunderwood.com/post/3mse2xrj7pc2z) about this idea recently). The creator doesn't care about it, and thinks I won't care enough to look closely." I also associate this style with bad online content, the AI industry, the datacenter boom and their economic and environmental consequences.

But even for people who do not relate to AI so politically, AI-generated images now are increasingly associated with a certain kind of inauthentic, overstylized (and overpriced) sort of business. Regardless of the quality of the underlying image, these associations are distasteful, and in extreme cases, [result in backlash](https://www.sfgate.com/food/article/grind-unwind-ai-images-22348931.php).

<img src="{{site.baseurl}}/assets/images/tasteslop/menu.jpeg" alt="An AI-generated menu at a san francisco restaurant" style="zoom:50%;"/>

For better or worse, I think both the really ugly AI images, as well as the backlash to them, are transient. Over time, as generative models continue to improve and marketers gain experience using them, I expect that AI-generated images will go from awful to boring, and most people will stop feeling as strongly about them. This is a bad outcome for people hoping to make a living as graphic designers, but arguably a good thing for small business owners looking for cheap design work.

In the programming realm, a similar thing seems to be happening. Many commercial uses of programming, such as creating websites or writing small snippets of code used for data analysis are increasingly being done by non-programmers using AI tools. While the aesthetics of tasteful code are not as visible, the consequences for new computer science graduates are not that different from the graphic designers. There is a lot of speculation right now that as AI coding tools get better, the same thing will come for corporate software engineers -- where an executive can enter a prompt and quickly get a technical product for a few thousand dollars worth of tokens, instead of thousands of expensive engineer-hours. I think this scenario is very unlikely (what is more likely is that executives all over the place start creating nice looking demos that don't work in practice, and their engineers have to break the bad news when something that looks great on localhost is impractical in production), but the fact that this scenario is even in the conversation is crashing much of the software industry.

All that is to say, right now, I think it is not possible to use AI tastefully, because the unethical consequences of AI use for workers lead to distasteful associations. I haven't even mentioned the [climate costs](https://news.un.org/en/story/2026/06/1167658), particularly for generating images. That doesn't mean there aren't technologies based on machine learning that could better serve human taste and creativity. But I think today's AI industry, with its huge capital expenditures justified by promising the automation of knowledge work, finds itself structurally opposed to the human judgment that knowledge work requires, and I think that makes the people involved in it uncomfortable. Maybe that's why they keep talking about taste.