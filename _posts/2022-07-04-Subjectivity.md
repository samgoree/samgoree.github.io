---
layout: post
title: How Should We Handle Subjective Problems in Computer Vision?
excerpt: Over the past two years, I've been exploring a category of subjective computer vision problems and how we should approach them. In this post, I'd like to make the case for a more humanistic approach to these problems.
---

# How Should We Handle Subjective Problems in Computer Vision?

Over the past two years, I've been exploring a category of subjective computer vision problems and how we should approach them. In this post, I'd like to make the case for a more humanistic approach to these problems. As such, this is a post which gets into some philosophy. It's difficult to read philosophy, and even harder to write it, so I'm going to start with a real example I've encountered, in the form of a dialogue with a fictional collaborator, and then systematically explore the ideas which come up.

This accidentally ended up being a really long post. I'm going to leave it long because it's my blog and I can do what I want. **TL;DR In computer vision, we should be thinking more about subjectivity, both in how we define problems as well as our evaluation methods.**

<table>
	<tr>
		<td>
			<div style="overflow: hidden">
				<img src="{{site.baseurl}}/assets/images/subjectivity/hamburger.png" alt="a good photo of a hamburger" style="max-height: 100%">
			</div>
		</td>
		<td>
			<div style="overflow: hidden">
				<img src="{{site.baseurl}}/assets/images/subjectivity/salad.png" alt="a bad photo of a salad" style="max-height: 100%">
			</div>
		</td>
	</tr>
</table>
Which do you think is more healthy?

<table style="table-layout:fixed; width:100%">
	<th>A</th><th>B</th>
	<tr>
		<td>"Hey B, how's it going?"</td>
	</tr><tr>
		<td/><td >"I'm good, A, how are you?"</td>
	</tr><tr>
		<td>"Doing alright. I've got a computer vision problem for you!"</td>
	</tr><tr>
		<td/><td >"Ooh, ok, let's hear it."</td>
	</tr><tr>
		<td>Ok so we want to make an app where people take photos of their food, and the app tells them statistics about the healthiness of their eating over time."</td>
	</tr><tr>
		<td/><td >"Interesting, how do you hope to do that?"</td>
	</tr><tr>
		<td>"Well, we'd like to use AI to measure how healthy the food is."</td>
	</tr><tr>
		<td/><td >"Hmmm, how do you define healthy?"</td>
	</tr><tr>
		<td>"Oh you know, the usual way, foods with lots of nutrients are healthy, while foods that have lots of calories without many nutrients are unhealthy."</td>
	</tr><tr>
		<td/><td >"And how is an algorithm supposed to figure that out?"</td>
	</tr><tr>
		<td>"Well, we'll just get it to identify the ingredients and cooking method used to produce a dish, then compute things like calories and nutrients from there."</td>
	</tr><tr>
		<td/><td >"Cool, do you have any food images labeled with their ingredients?"</td>
	</tr><tr>
		<td>"No...we don't. That's hard to get, since there are so many possible ingredients, and not all the ingredients might be visible in the picture."</td>
	</tr><tr>
		<td/><td >"Then how do you expect an algorithm to figure it out?"</td>
	</tr><tr>
		<td>"That's a good point. I guess we'll get human labelers to rate images on a scale from 1 to 10 where 1 is unhealthy and 10 is healthy, then train a machine learning model to measure it. Do you know how to do that?"</td>
	</tr><tr>
		<td/><td >"...well technically I do, but I'm not sure that'll work particularly well."</td>
	</tr><tr>
		<td>"Why not?"</td>
	</tr><tr>
		<td/><td >"Our perception of how healthy food is might depend on other factors, like how the food is plated and how the photo is taken. A really beautiful photo of a hamburger with bright, crisp vegetables will look much more healthy than a poorly lit photo of a salad."</td>
	</tr><tr>
		<td>"So we'll do another study where we issue people specific plates and cameras and make sure they take all the photos exactly the same."</td>
	</tr><tr>
		<td/><td >"Still, ‘healthiness' isn't objective. Different people might define "healthy" differently based on their dietary needs. Most people would consider whole wheat bread relatively healthy, but a person with Celiac disease definitely wouldn't. And their definitions might change over time, like if they go on a diet and suddenly consider all bread unhealthy."</td>
	</tr><tr>
		<td>"Ok, well, there might be some noise in the labeling process, so we'll ask lots of people to rate each image and take the average. That should be more objective, right?"</td>
	</tr><tr>
		<td/><td >"Well, that will be more objective, but then you're measuring more of a social phenomenon, the way we collectively construct the category of 'healthy food' and less anything about how a person sees the food. It still will evolve over time as healthy eating trends go in and out of style, and our dietary priorities shift."</td>
	</tr><tr>
		<td>"Well, that doesn't really matter, does it? We just want to help people eat healthier, after all! So what should we do?"</td>
	</tr><tr>
		<td/><td >"People's food choices, like many of their other choices, are the result of a variety of systemic factors: what food is available, what we've eaten before, what our families expect us to cook, things like that. Just telling people how healthy their eating is probably won't make a big difference overall."</td>
	</tr><tr>
		<td>"But people are still responsible for their choices, right? And giving them good information will help them to make better-informed choices!"</td>
	</tr><tr>
		<td/><td >"That's true, maybe I'm being too harsh. But regardless, starting from images is going to be tricky and subjective. We can't just claim that our algorithm, trained on an average of several peoples' opinions, is the authority on healthy eating."</td>
	</tr><tr>
		<td>"Ok ok, hear me out: subjectivity doesn't have to be a bad thing. What if instead of an algorithm, we have a "bot" with a name, a backstory and a perspective of its own? Can we just say the bot has its own sense of what foods are healthy and avoid claiming to be an authority?"</td>
	</tr><tr>
		<td/><td >"Hmm, that's more complicated. Are we trying to say our algorithmic measure of healthiness has a cultural background? Which culture would we choose? And how can a bot, which notably doesn't eat, have thoughts about food?"</td>
	</tr><tr>
		<td>"Oh well I don't know. We definitely can't try to imitate a particular cultural background, we might offend someone. What if we just learn the user's definition of healthy?"</td>
	</tr><tr>
		<td/><td >"But then they'll just consider whatever they're eating already as healthy to make themselves feel better! Didn't you originally want to help people change their eating habits?"</td>
	</tr><tr>
		<td>"That's true, we do want to help people to eat healthier. Hold on, now what if we train it on an expert's definition of healthy? Surely an expert will be a better judge."</td>
	</tr><tr>
		<td/><td >"Now we're getting somewhere, but it's still messy. An expert probably has a more reliable definition of healthy than a random user, but they're still only human. They'll rate the foods they like more highly, and will be more skeptical of unfamiliar foods without realizing it. We don't want to equate having more education with having more objective opinions, especially when the problem isn't purely scientific."</td>
	</tr><tr>
		<td>"Drat, the interaction between the subjective parts of perception and machine learning is really complicated, isn't it? Somebody should study this!"</td>
	</tr>
</table>
<br>

(while this dialogue is based on a real research problem my lab works on, neither of these speakers are based on real people)

### Subjective Computer Vision Problems

In computer vision, broadly, we try to develop algorithms which can reason about the visual world just like humans can. This goal is quite simple, which means computer vision is relevant to a lot of potential application areas. But some potential applications run into a problem: even when the problem is constrained and well-defined, a quality which humans are so effortlessly able to see in images turns out to be quite difficult to measure algorithmically. Like in my slightly exaggerated dialogue above about the "healthiness" of food, a quality which seems so obviously visible to us is ultimately subjective. There are a lot of these qualities, for example:
* How cute is a drawing? (see my [previous post]({{site.baseurl}}/2019/11/16/cuteness_detection.html) about this one)
* How beautiful is a photograph? (see my post about [image quality assessment]({{site.baseurl}}/2021/09/14/iaqa.html))
* How colorful is a design? (see my previous post about [colorfulness]({{site.baseurl}}/2021/10/02/art-history-visualization.html), I've already written about a lot of these)
* How consistent is the style of this house with the style of the neighborhood?
* To what extent do two people look similar?

These problems bear reference to other kinds of problems which are less related to images, but still might be approached through machine learning:
* How funny is a joke?
* How scary is a story?
* How fun is a game?
* How sad is a song?
* How innovative is a paper?

These sorts of problems raise two troubling questions: 
1. In computer vision, is our goal to reason about reality as it is, reality as it appears in a photographic image or reality as we see it?
2. When computer reason about the visual world "just like humans can" which humans are we talking about?

As scientists, we would prefer to reason about the world as it is, but as engineers we would prefer to reason about reality as it appears to a camera, but for these problems, it seems that we are being asked to reason about how people see the world. That invites a thorny concept into computer vision: subjectivity.

### Can We Avoid The Subjective Part?

When we come into contact with subjectivity, scientists intuitively look for ways to eliminate the subjective element. Social scientists call this process "operationalization," which is the process of precisely defining subjective terms, qualities or categories in terms of measurable, objective proxy variables. For example, if we want to study entrepreneurship among American women, the category of "American women entrepreneurs" is nebulous and somewhat subjective, but the category of "American citizens who founded a business in the past twenty years which currently has more than ten employees and self-identify as women" is much easier to work with scientifically.

But there are some concepts, especially visual concepts, which don't operationalize well. For example, consider the two logo designs below:

<table>
	<tr>
		<td><img src="{{site.baseurl}}/assets/images/subjectivity/bing.png" alt="Bing logo from 2016" ></td>
		<td><img src="{{site.baseurl}}/assets/images/subjectivity/primo.png" alt="Primo logo from 2016" ></td>
	</tr>
</table>

The logo on the left was briefly used by Microsoft Bing in 2016. The logo on the right was used by a Thai tech startup, Primo, in 2016. The two logos look similar, and we can tell that almost immediately, but if we want to put into words why they look similar, we have to think carefully. They both use a teal color, they both use obtuse angles, they both use color to add depth, making their geometric shapes look like folded ribbons and they both resemble letters: "b" and "p" respectively. Now consider these two paintings:

<table>
	<tr>
		<td><img src="{{site.baseurl}}/assets/images/subjectivity/madonna.png" alt="Giovanni Battista's Madonna and Child" ></td>
		<td><img src="{{site.baseurl}}/assets/images/subjectivity/mother.png" alt="George Stefanescu's Mother and Child" ></td>
	</tr>
</table>

Do these paintings look similar? The one on the left is *Madonna and Child* by Giovanni Battista painted in 1640, while the one on the right is *Mother and Child* by George Stefanescu painted in 1960. 

One person might say no, they are from completely different eras, styles and use different media. Another person might say that they do, because they share a common composition, similar emotional and religious themes and are both exploring the same concept, a mother holding her child, which has been painted in so many different ways over time.

Both of these pairs of images are similar to one another in some way, and we might even say that the two logos are more similar to each other than the two paintings. So there is a common concept of similarity which extends to even radically different visual genres, and we can access this concept at a glance. But it's impossible to say exactly how we're doing it, or what "similarity" means in general. Any attempt to reduce it to a series of specific measurable dimensions will end up leaving something out, and it's unclear if something like a similar emotional theme can be measured in the same units as similar use of color. 

But somehow, we still know it when we see it.

### Machine Learning as an Alternative

When a concept is difficult to operationalize, but we know it when we see it, it might be tempting to use machine learning instead. After all, we can just get a human to label images and then use a deep convolutional neural network (or something similar) to learn the right visual features automatically.

The machine learning approach seems great until you think about it closely. A deep neural network is a universal function approximator. It is able to approximate any mathematical function $$y=f(x)$$ where $$x$$ is an image and $$y$$ is a label using another function $$\hat y=g(x;\theta)$$. When we train it, we optimize $$\theta$$ to minimize some error function $$E(y,\hat y)$$. Since we don't have complete knowledge of $$y$$, or even a precise domain for $$x$$, we collect finite samples of $$x$$ and $$y$$ and call it a training set.

The problem is that machine learning assumes that $$f$$ exists as a well-defined function, meaning that its output is fully specified by its inputs. In our subjective problems, it's not clear that such a function exists. In fact, we have concrete evidence that it doesn't exist whenever two people arrive at different interpretations of the same image. In machine learning, we tend to attribute such differences to random noise in the labeling process, but people's perception of beauty in images at least tends to be [highly-nonrandom](https://openaccess.thecvf.com/content_ICCV_2017/papers/Ren_Personalized_Image_Aesthetics_ICCV_2017_paper.pdf), and I would guess that other properties are as well. Such qualities are not different at random, but as a result of systematic differences in perspective.

To return to our food example, one participant might label a slice of multigrain bread as "healthy" because it contains a variety of nutrients, but another might label it as "unhealthy" because they are on a low-carb diet and consider all bread unhealthy. Here, the difference in opinions is not the result of random noise (like a misreading of the prompt), it's a specific difference in opinion, which is predictable given more context about the labeler. If we show them another photo of the same slice of bread with poor color contrast and focus, the first subject might [now label it as unhealthy as well](https://www.marshall.usc.edu/sites/default/files/ahagen/intellcont/HagenPrettyHealthyComplete-1.pdf). Now the difference of opinion is based on the aesthetic qualities of the photo, rather than any difference in the photographed scene.

There is also no clear boundary between the subjective and objective qualities of an image. While beauty is definitely subjective and a problem like depth estimation (computing the distance from the camera to a pictured object) is definitely objective, other classical vision problems like object detection or [image inpainting](https://en.wikipedia.org/wiki/Inpainting) are not clearly in either category. For example, for object detection, most people won't disagree about where "seat" is in an image, but they might disagree about which objects fit into the category of "seat" and whether "seat" describes a whole piece of furniture, or merely the part that one sits on. For image inpainting, there is a definite correct answer corresponding to the values that the missing pixels would have if they had been captured along with the original image, but different people might choose a variety of plausible guesses which are ultimately incorrect based on the available data.

These sorts of issues are usually minor enough to roll into a random error term. To return to our seat example, differences in subjective opinion about the definition of a seat, or random differences in photo quality won't have much effect on the results. But when we are dealing with fundamentally subjective qualities like "healthiness" or "beauty," we need to make an argument that the thing we're trying to measure is actually something a computer can access. Even if we can't precisely define what a seat is, there are meaningful correlations between patterns of pixels and the label "seat." But it's unclear whether the information needed to determine healthiness or beauty is actually contained in the pixels of an image.

### Three Possible Justifications

It's possible that these criticisms are damning: since we cannot approach them scientifically, subjective problems shouldn't be solved using machine learning approaches, and we should probably not even be using computers for anything involving subjectivity. 

But, if only as an intellectual exercise, what happens if we try to acknowledge and account for subjectivity? Is there a good argument for why a machine learning approach might still be justified? I think such arguments exist and fall into three main categories. 

Some arguments will make the claim that the concept we seek to measure exists in a subject-independent way, even if it is subjective. Call arguments which make that claim (I). For example, (I) contains [Kantian disinterestedness](https://plato.stanford.edu/entries/aesthetic-judgment/#Disi). If we avoid claim (I), then the approach must access subjectivity from somewhere. Either the algorithm itself is functioning as a subjective agent (II), or it is merely predicting the judgment of another subjective agent, such as a human researcher or user (III). Unfortunately, all three of these possibilities have consequences which we must account for in our modeling.

**Category (I)** includes arguments which claim to measure subjective things in a subject-independent way. These arguments usually rely on evidence from psychology that there is a surprising amount of similarity between the subjective experiences of different people and explain this similarity by way of our shared biology and evolutionary history, leading to models which try to infer a subject-neutral perspective by aggregating together the labels of many people. These approaches usually report relatively low error values in practice.

The issue emerges when you compare the perspective of the model to the perspectives of the human subjects it was based on. The resulting model will make predictions that resembles some people's answers more than others, just by chance. But because this model is supposed to be neutral, it ends up elevating the typical subject over the atypical subject, where some subjects' opinions are more objective than others, implicitly denying the agency of the atypical subject.

The concept of elevating one group's shared perspective to the status of objectivity is at the root of many systems of oppression and has been written about at length, primarily in feminist and postcolonial theory. Even if an ideal dataset was constructed which took the opinions of every human on Earth equally, such a model would need to negotiate between cultures with wildly different views of what subjectivity even is and would inevitably value those perspectives shared between large groups of people over those only present in smaller ones. Ultimately, no computer vision algorithm can ever be completely neutral, and trying to negotiate between contradictory worldviews is a fool's errand.

**Category (II)** includes arguments which claim that the computer itself has agency. These arguments have issues which are more theoretical. These arguments rely on an artificial intelligence claim, that either the models, the algorithms or the computers executing them possess subjective agency, so we can ascribe the judgement to the system itself. This line of thinking leads to a particularly nasty philosophical problem. Because the computer, algorithm and model are all fully observable, there must be some element within them which we can identify that must be experiencing [qualia](https://en.wikipedia.org/wiki/Qualia), since such experience is necessary to actually make a qualitative judgement.

Making the claim that an observable, deterministic system experiences qualia is at the heart of David Chalmers' [Hard Problem of Consciousness](https://iep.utm.edu/hard-con/). This problem carries profound implications for other fields of philosophy and cognitive science. If you're interested in this interaction, check out [this article](https://www.degruyter.com/document/doi/10.1515/9783110706611-010/html). In any case, these arguments are difficult to defend.

**Category (III)** includes arguments which involve predicting the preferences of a human agent. In this line of thinking, the algorithm is not making a subjective, aesthetic judgement, or trying to turn a judgment into something objective. Instead, the algorithm is merely making a prediction about something which is already objective: how a specific human will react to an image. These arguments are already much more consistent with how machine learning works in other circumstances, since there exists exact ground truth and it is reasonable to assume the underlying phenomenon is a deterministic function of the input image. Unfortunately, there are two problems:

First, the model can't explain the human's judgement. For example, even if a model successfully learns that a subject enjoys blue houses, that model will never be able to determine why that is the case, maybe they grew up in a blue house or walked past a particularly well-maintained blue house every day for a year. These are questions of meaning which are difficult even for humans to explain. No model can read minds or memories to explain how a subject finds significance in an image, and even if it could, many subjects would find such a thing incredibly violating.

Second, the model cannot transfer between people and is heavily constrained to a point in time. Even if two people have similar perspectives, a model trained on data from one person cannot be applied to the other without taking on some of the assumptions and issues of (I). Similarly, as we age and experience the world, our perspectives change, meaning that a model will eventually go "stale" and not even apply to the subject it was originally trained to mimic.

This interpretation also invites a really interesting problem regarding interpretation and human agency. If a well-trained model can predict how I will interpret an image in a deterministic manner, do I still have agency over my interpretation? Many decisions made by humans that we would consider arbitrary turn out to be predictable from brain signal data (e.g. [fmri data can predict whether a person will choose to add or subtract two numbers](https://www.pnas.org/content/110/15/6217)). Is it possible that our interpretations and judgments are similarly predictable? I don't have a good answer to this question, but personalized computer vision algorithms for predicting subjective judgments could serve as valuable experimental evidence one way or another.

### Humanistic Computer Vision

Up to this point, I've discussed a category of computer vision problems which involve difficult to operationalize, subjective qualities of images. I've discussed three ways that we can justify approaching these problems through machine learning and I've raised philosophical concerns with each of them. My goal is to motivate a sort of humanistic computer vision: an approach to computer vision which attempts to computationally imitate, or at least predict, a qualitative human visual experience of the world, rather than just its physical fact.

What I haven't done, though, is define subjectivity. That's not an accident: subjectivity is a difficult concept which is highly contested in the humanities. I think leaving subjectivity undefined is more a feature of my approach than a bug. When subjectivity is left without a precise definition, correctness turns out to be somewhat subjective as well, so evaluation metrics and objective comparisons between models are impossible; our choice for "best" model might vary from person to person. As a result, models become personal, they might hold different significance to different people. They are imbued with the worldview of the researcher or engineer who created them and are valuable for their artistic truth, rather than their optimality. This property is absolutely essential to remain true to humanistic sensibilities: the concept of an objectively optimal measure of healthy is as nonsensical as an optimally healthy food, but by choosing a measure, we say something about our own subjective concept of healthy food, rather than something about the world in general. It also lines up with [my thoughts on optimization in computer science]({{site.baseurl}}/2021/11/02/optimization.html).

Computer vision, and AI in general, has tremendous potential to not only model subjective qualities, but to change our understanding of those qualities as well. When we make assumptions about the way something like healthiness appears in images, then implement those assumptions in code, we make them explicit in a way that our actual experience is not. Then, when we see that code matching with our own experiences, we start to think about ourselves in terms of the algorithmic assumptions, making them something of a self-fulfilling prophecy.

In any case, computer vision researchers need to think deeply about how humans actually see the world and how feelings, association and meaning affect our visual experience. And since these elements are difficult to quantify or compare, we need to rethink the way we evaluate our models and separate out high quality models from poor quality ones without resorting to objective benchmarks. I see these issues as a new frontier in artificial intelligence research more generally, and one that has been largely overlooked.

### Conclusion

Oh well, this ended up being another really long post. If you've made it this far, thank you for your perserverence! These are some of the central ideas in my dissertation, but that's still work in progress, so let me know if you have any comments or suggestions.
