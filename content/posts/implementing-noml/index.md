+++
title = "Implementing NoML in Zola (And Why You Might Want To)"
date = 2023-11-28T11:25:00Z

[extra]
meta = [
    {property = "og:description", content = "AI companies are training their models with your work. Should you stop them?"},
    {property = "og:url", content = "https://blog.jglass.me/posts/implementing-noml/"},
    {property = "og:image", content = "meta-cover.png"},
    {property = "og:type", content = "article"},
]
+++

AI is big business, and it's largely fuelled by the vast troves of data on the Internet. Much of it was published in an era when harvesting authors' work to train models that may eventually supercede them, if not unimaginable, certainly seemed like a distant future. **That future has now arrived.**

Recently, I came across [a proposal](https://blog.mojeek.com/2023/10/noml-proposal-and-open-letter.html) by the independent search company Mojeek for new ways for website owners to control how AI companies crawl data to train their models with. It's not of much use to me - all my posts are available on GitHub, free of any restrictions I place on them here - but I was intrigued to explore how I could implement it given I don't write any of the HTML for this site myself.

<!-- more -->

# The Proposal

Broadly, Mojeek's proposal - [signed](https://noml.info/) by a variety of other companies and individuals - aims to allow website owners to better control how their work is used by AI companies to train their datasets.

The "AI" we talk about the most today - think ChatGPT, Bing Chat and Google Bard - are actually *Large Language Models*, or *LLMs*, behind-the-scenes - which construct passages of text iteratively by making the best guess at what the next word should be.

At the moment, there's no human-like intelligence involved. Instead, these guesses are based on vast amounts of existing text written by humans, which are fed to the models to train them. **This data becomes an intrinsic part of, and inseparable from, the model it's used to train** - meaning it could generate new text based on your work, now and forevermore.

Various companies are wary of this - in one example, Amazon [has warned](https://gizmodo.com/amazon-chatgpt-ai-software-job-coding-1850034383) ([original](https://www.businessinsider.com/amazon-chatgpt-openai-warns-employees-not-share-confidential-information-microsoft-2023-1), paywall) employees not to share confidential information with chatbots, as inputs may be used to train new models - which would end up mimicking any internal documents and code it was fed with.

# The Issues

Truthfully, I'm not sure that asking AI companies not to train their models with your work will do anything. While it's not printing money - these models must be expensive to train - everyone playing the AI game has a big incentive to harvest as much material as they can to avoid falling behind the competition.

The effect of this is two-fold: existing models are, of course, set in stone. If your work was used to train them, that's it: anyone who wants to replciate your work specifically simply has to use one of them instead of a newer one.

And, secondly: the flows of data around AI are so vast, how could you realistically get your existing work out of training datasets for future models?

Like Matteo Wong in [The Atlantic](https://www.theatlantic.com/technology/archive/2023/10/openai-dall-e-3-artists-work/675519/), I'm talking about making your wishes clear for how your future work should be used, and attaching those wishes to your work in a standard, consistent way that all the AI companies can respect. Or not.

# The Ethics

Turning your back on AI may seem like a misstep.

It's widely touted as the future, and it's impossible to imagine a new phone launch or tech keynote without it. It's a legitimate and impressive technological feat, and has the potential to transform how we work.

But, by design, it's also a capable mimic.

[The article](https://mpost.io/midjourney-and-dall-e-artist-styles-dump-with-examples-130-famous-ai-painting-techniques/) mentioned in [this discussion](https://www.newyorker.com/culture/infinite-scroll/is-ai-art-stealing-from-artists) on the topic by Kyle Chayka shows that it's very much part of the culture surrounding AI image generation to create derivatives of artists' work. They even have a table of hundreds of real artists to use in your prompts to achieve just the style you're after.

That could be perfectly innocent: perhaps you're a fan of their work, creating something new - something you wish they'd make - for your own use.

But, as with all tools - AI or manual, digital or analogue - it can be misused too. By making it much easier to replicate an artists' style, these AI tools risk cutting them off from vital exposure and revenue. It's not inconceivable that, if these copies become too alike the originals they're based on, it could risk livelihoods.

But doesn't copyright law protect them?

It's contentious whether or not the output of an AI model trained on copyrighted work violates copyright law. A claim to that effect was recently [dismissed from a U.S. court](https://storage.courtlistener.com/recap/gov.uscourts.cand.415175/gov.uscourts.cand.415175.56.0_1.pdf)  [PDF, [Article 1](https://www.reuters.com/legal/litigation/us-judge-trims-ai-copyright-lawsuit-against-meta-2023-11-09/), [Article 2](https://www.hollywoodreporter.com/business/business-news/sarah-silverman-lawsuit-ai-meta-1235669403/)] as it would need to be proven that the AI-produced work exhibits a substantial similarity to the original to be considered infringing (see PDF, Page 3). Given just how complex these models are, it might be a challenge to get it to give you an infringing copy of your work when you need it to, even if you know it might do for someone else.

In the same case, another claim that the model as a whole violates copyright law was also dismissed, because the model itself can't be recognised as an adaptation of the original works (PDF, p. 1). I think that judgement's reasonable - AI models do, in fairness, take substantial amounts of work, research and development to produce. They're a different creation to the material they're trained on.

Is this simply another technological innovation? Does AI simply redefine the term "artist", or "writer", like computers did before it? You can make music, films and art without ever needing to touch an instrument, roll of film or tin of paint today, and we don't call that cheating or insincere - it's the new normal. Is abstracting the process of art and writing to sending words to a chatbot a progression down the path we're already on, or a new one entirely?

I don't have the answer to that.

I don't think these tools should be banned or shut down simply because some people might misuse them. It would be like banning cars because some people use them to break the law. But I do think it should be easier to opt-out.

And, absent the option to stop models being prompted to replicate your work, I think it would be better to stop it being used to train them in the first place.

# The Choices

The proposal addresses three distinct techniques - one of which Mojeek have dismissed, and two of which form their proposal:

1. Requests in a site's `robots.txt` file to ask specific crawlers not to index the site.
2. Requests on each page to ask all ML training crawlers not to index the page.
3. Tags to add to a site's HTTP headers to ask crawlers not to index all types of content served there, not just pages.

I can immediately rule out option three. I don't control the servers this blog is hosted on, since I'm using GitHub Pages - I don't get any data at all from them - so I'm not sure I'll be able to change anything to do with how my pages are delivered. It's a bit too low-level for this setup, which is a shame because being able to opt-out everything on my site, not just the pages themselves, would be ideal.

Mojeek rule out the first option, which they say doesn't give website owners the granularity to distinguish between crawlers for web search, and crawlers for AI products. Had it been applicable here, it would have been the simplest, requiring updating only a single file. Regardless, I'll implement it as a fallback while Mojeek's proposal remains a proposal, rather than an accepted standard.

That leaves the second option, which allows me to define more specific requests that - importantly - apply to all web crawlers. Where `robots.txt` only lets me disallow crawling as a whole, or for a specific robot, `<meta>` tags let me issue specific requests, such as disallowing usage for the training of AI models, without having to explicitly define every single bot that could possibly crawl my site by name.

# The Caveats

There are a few major caveats with this setup, however. Firstly, as I mentioned above, everything I write is freely and openly available on [GitHub](https://github.com/Jordan-Glass/blog.jglass.me). I can't place any restrictions on AI crawlers there, and it's not in the ethos of open-source to do that anyway - it's free and open to everyone - so my implementation here is largely a proof-of-concept.

It *might* be more effective if I left my original Markdown files in a private repository. Zola [supports](https://www.getzola.org/documentation/deployment/github-pages/#github-actions) this configuration, but I prefer to leave them open so that others can learn from my blog in the same way I learned from [this one](https://github.com/not-matthias/not-matthias.github.io/tree/main), written by the creator of the Apollo theme I'm using to style this blog.

Secondly, messing with web crawlers can break your site, making search traffic disappear with no clear sign why.

As the SEO-optimisation company Yoast mention in a [guide to `robots.txt`](https://yoast.com/ultimate-guide-robots-txt/), it has the power to impact your site's rankings in search results if you block CSS or JavaScript files vital to rendering it - or, it could block the site from results entirely. And this risk extends, of course, to `<meta>` tags.

This is important because search is vital to most sites - I vaguely remember reading an article on sites losing advertising revenue, and potentially going out of business, because users were getting their answers from infoboxes instead of clicking through.

And - perhaps most importantly - will it even work?

Assuming you don't have your entire site replicated on an open Git repository, free for anyone to use, you might think this would be more effective. However, NoML is only a proposal for now, and crawlers don't have to respect it yet. Technically, they don't have to respect it ever - they can access any site they want to. The only encouragement for compliance is that administrators may start forcing the issue and blocking problem crawlers en-masse if they misbehave, impacting the results they can serve.

That said, I still wanted to see how I could implement the proposal on a static site, so I pressed on.

# The Implementation
**I don't write any of the HTML code for this site.** It's dynamically generated for me by [Zola](https://www.getzola.org/), a Static Site Generator, using the posts I type in Markdown and HTML templates provided by the theme I've chosen. This means I can't simply modify the pages themselves to implement the changes - I need to modify how the pages are generated.

## `robots.txt`
To begin with, I was planning on creating a new `robots.txt` to add using the Zola `static` folder, assuming my site didn't have one at all, but I was surprised to find that [it did](/robots.txt).

It's generated by Zola, which uses the template defined either by you or your theme, or its own default if neither of those exist. Since neither me or my theme have defined one, it [uses the default](https://www.getzola.org/documentation/templates/robots/):

```jinja2
User-agent: *
Disallow:
Allow: /
Sitemap: https://blog.jglass.me/sitemap.xml
```

This example applies to all crawlers, disallows nothing, allows everything, and points the bot to the [sitemap](/sitemap.xml), a list of all the pages on the site for it to work through.

It's simple enough to override it: by putting my own template in the `/templates` directory, Zola will use it instead.

[My new `robots.txt` template](https://github.com/Jordan-Glass/blog.jglass.me/tree/main/templates/robots.txt) keeps my preferences as they currently are for all crawlers, while preventing `gptbot` from accessing the whole site.

```jinja2
User-agent: *
Disallow:
Allow: /

User-agent: gptbot
Disallow: /
Allow: 

Sitemap: https://blog.jglass.me/sitemap.xml
```

> *I was considering disallowing all crawlers from accessing [my contact page](/contact) while I was here, which I would have implemented by adding `/contact` to `Disallow:` in the first rule, but eventually decided it might be helpful to keep that page in search results.*

## `<meta>` tags
Finally, it's time to implement the `<meta>` tags. They reside within the `<head>` block in an HTML page, and are governed by the `header.html` template.

Unlike `robots.txt`, Apollo [provides this template](https://github.com/not-matthias/apollo/blob/main/templates/partials/header.html), and in my directory structure it resides in the `themes/Apollo/templates/partials/` folder.

Right at the top are some existing tags it already specifies for other purposes:

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```

To modify it, I copy it to my part of the directory tree - `/templates/partials/`. Zola looks here first before checking the theme files, so any files I include here will take precedence over the theme I've chosen.

The tag I'm using is:

```html
<meta name="robots" content="noml">
```

The name `robots` ensures the rule applies to all crawlers, but Mojeek [explain how](https://blog.mojeek.com/2023/10/noml-proposal-and-open-letter.html) you could call out specific ones instead, such as `googlebot` or `bingbot`.

# Conclusion
You can see both of these changes in action for yourself, by viewing the site's [`robots.txt`](/robots.txt) as well as viewing the page source, by right clicking, selecting `View Page Source`, and searching for `<meta content=noml name=robots>`.

Will it work? For now: no. In the future? That depends on whether the AI industry believes in a fair and just system that gives those who publish content online the option not to take part. Time will tell whether they volunteer to create this future, or are forced to do so.

---

# Related on the Internet:
* [OpenAI and the Biggest Threat in the History of Humanity](https://unchartedterritories.tomaspueyo.com/p/openai-and-the-biggest-threat-in): Tomas Pueyo spells out, in stark detail, the threat AGI could pose to humanity
* [The Singularity Is Fear](https://unchartedterritories.tomaspueyo.com/p/the-singularity-is-fear): a preview of a paid post by Pueyo that offers some insight into the warnings issued by OpenAI staff and board members, the speed-over-safety approach OpenAI may have taken - and how they may be turning a corner
* [Underage Workers are Training AI](https://www.wired.co.uk/article/artificial-intelligence-data-labeling-children): Niamh Rowe looks at the under-18s who took to data labelling to make ends meet
*  [OpenAI Used Kenyan Workers on Less Than $2 Per Hour to Make ChatGPT Less Toxic](https://time.com/6247678/openai-chatgpt-kenya-workers/): Billy Perrigo investigates data labelling at a firm in Kenya, the content they had to label, and the lack of support they were offered

---

* [View post source](https://github.com/Jordan-Glass/blog.jglass.me/tree/main/content/posts/implementing-noml.md)
