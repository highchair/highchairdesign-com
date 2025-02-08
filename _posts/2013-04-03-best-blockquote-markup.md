---
layout: post
title: "How do you solve a problem like Blockquote?"
date: 2013-04-03 03:30:00 -0500
categories: [ "Web Development", Semantics ]
---

I am obsessed with semantic markup and object-oriented CSS. We don’t always follow those guidelines to a <q>T</q>, but our team always tries to get close. The perfect set of markup and CSS — and therefore the perfect project — doesn’t exist, but we try to get as close to perfect as possible.

Lately, we’ve been making updates to our own website to try to bring it up to speed with some of the new projects and patterns that we have been pushing out the door with other clients. A colleague came across our `<blockquote>` style, and [made some suggestions](https://twitter.com/jpamental/status/318825195479633920). That started a conversation about a simple question with an elusive answer, *<q>What’s the best way to markup a blockquote?</q>* Even though I went down this rabbit hole a few months ago, this time, I had a willing participant in the conversation. Little did he know how a simple little bit of advice would start this exploration again. 

## Don’t follow the HTML5 Doctor’s Advice (yet)

When searching for <q>best markup for block quote</q>, one of the top results is HTML5 Doctor. [Their guide](https://html5doctor.com/blockquote-q-cite/) has some great examples, and I could have grabbed a few of their code snippets and been done. Some closer reading, though, revealed that the advice they recommend is incomplete and, for now, incorrect.

My dream scenario was a semantic way to markup and style a `<blockquote>` with an attached citation of the source of the quote. On our site, we also style the `<blockquote>` element with `::before` and `::after` elements for an opening and closing curly quote. The markup says that the content is a quote, and the style shows readers that it is as well. The important bit here is the closing curly quote, as it’s style proves to be the sticking point here.

Initially, according to the Doctor’s advice and a few others I had read around, this was the markup that I came up with:

```html
<blockquote cite="//dev.w3.org/html5/spec/grouping-content.html#the-blockquote-element">
  <p>The blockquote element represents a section that is quoted from another source.</p>
  <footer>— <cite><a href="http://dev.w3.org/html5/spec/grouping-content.html#the-blockquote-element" title="4.5 Grouping content — HTML5">W3C HTML5 specification</a></cite></footer>
</blockquote>
```

*Note: This is now the allowed and preferred markup! — September 2018*

This — as I have now learned — is [non-conforming markup](https://www.w3.org/Bugs/Public/show_bug.cgi?id=13082). A `<footer>` element inside our blockquote is not per the spec, and in fact, very few elements are allowed inside a blockquote. Oli Studholme goes on at length as to the problems and potential solutions [in a blog post of his own](https://oli.jp/2011/blockquote/).

Further, that `<footer>` element inside the blockquote was making it hard to style the element as I wanted. Since the last element is the `<footer>`, and the blockquote element has an `::after` pseudo element, the closing curly quote was being placed on the same line as the attribution, not next to the end of the quote itself. To get it to do what I wanted with the current markup, I’d have to do some tricky CSS to catch all the various use cases — blockquote with one `<p>`, blockquote with multiple, blockquote with a `<hX>` element and a `<p>`, etc.

In an email with [Jason Pamental](https://twitter.com/jpamental), I outlined an alternate method using `<figure>` and `<figcaption>`, as I just used those elements to markup a slideshow pattern. It made sense to wrap a blockquote in a `<figure>`, so I took a stab at it. As it turns out, [that's the official recommendation](https://www.w3.org/TR/html5/grouping-content.html#the-blockquote-element).

> I expect we will eventually create a `<credit>` element that goes inside `<blockquote>`, `<figure>` or `<figcaption>`, `<caption>`, and maybe other contexts as well. At the moment, I’m deferring adding it so that we can see how `<figure>` and the other new elements do in the wild.

— Ian Hickson from the <cite>[WhatWG mailing list, Feb 11 2012](https://lists.whatwg.org/htdig.cgi/whatwg-whatwg.org/2012-February/034822.html)</cite>

And the markup:

```html
<figure>
  <blockquote cite="http://lists.whatwg.org/htdig.cgi/whatwg-whatwg.org/2012-February/034822.html">
    <p>I expect we will eventually create a <credit> element that goes inside <blockquote>, <figure> or <figcaption>, <caption>, and maybe other contexts as well. At the moment, I'm deferring adding it so that we can see how <figure> and the other new elements do in the wild.</p>
  </blockquote>
  <figcaption>— <cite><a href="https://lists.whatwg.org/htdig.cgi/whatwg-whatwg.org/2012-February/034822.html">Ian Hickson</a></cite></figcaption>
</figure>
```

The HTML5 Doctor page details this conversation in a group of blockquotes, I just did not really see them the first time through that article. Since then, other people seem to be confirming this pattern. Even better, since the attribution is not inside the blockquote itself anymore, the style and placement of the `::after` element will be more to my liking.

Why should we care? One of the reasons why I am so interested in getting this particular element right is that the blockquote element is pretty well known in the non-design community, as it is part of many off-the-shelf WYSIWYG editors. The hope is, if it is going to stick around, we can make it as useful as possible and maybe even educate people — and the makers of things like TinyMCE, CK Editor and maybe even [Markdown Here](https://www.crypti.cc/markdown-here/) — as to what the best markup is to use.

Conversations about <q>the best way</q> abound on the inter webs, and always keep in mind that the article you may be reading is also a work in progress. This seems to be the best way, but that’s only for now. Leave a comment if you think that this pattern can be improved, or if you agree that its the best we can do at the moment.

*[WYSIWYG]: What You See Is What You Get

### Other reading: 

+ [Jeremy Keith: Citation Needed](https://adactio.com/journal/4675/)
+ [Official W3 spec](https://www.w3.org/TR/html5/grouping-content.html#the-blockquote-element)
+ [A Blog Not Limited: The Beauty of Semantic Markup](https://ablognotlimited.com/index.php/articles/the-beauty-of-semantic-markup-part-1-quotes-citations/)

*Originally published on ProjectEvolution.com*

<aside class="archive__statement">
There was a year’s worth of discussion going on at the W3 about adding a `<credit>` element to HTML 5.1 in order to make it easier to deal with credits in `<figure>`s and `<blockquote>`s. It ended up instead that the `<footer>` element will be allowed inside of a blockquote, but no other hard rule was suggested and the `<credit>` element was decided to not solve the problem at hand: [www.w3.org/Bugs/Public/show_bug.cgi?id=22996](https://www.w3.org/Bugs/Public/show_bug.cgi?id=22996)
</aside>