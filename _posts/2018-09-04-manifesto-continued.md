---
layout: post
title: "Ammunition for My Manifesto"
date: 2018-09-04 09:05:00 -0500
categories: [ "Web Development", Quotes ]
---

My Manifesto was a call-to-action to remove complexity and get back down to the basics. In some ways, it is the art of defining what something is by removing what it is not. In the case of a website, what it is not is a series of interwoven dependencies. [Andrian Zumbrunnen](https://uxdesign.cc/@azumbrunnen?source=post_header_lockup) said it as well as I could have when describing what modern designers/developers need to go through in order to work on something that, at its core, should be simple:

<figure>
  <blockquote class="quote" cite="https://uxdesign.cc/via-negativa-4bb536f235d5">
    <p>When I started designing websites, life was easy. All you needed was an editor, an <span class="abbr">HTML</span>, and a <span class="abbr">CSS</span> file. On days when I felt witty, I even added some JavaScript. Today, I feel like I need to go through a regimen of tasks before I get to write my first line of code.</p>
    <p>It usually involves setting up <span class="abbr">NPM</span>, Webpack, Babel, React JS and all the other technical mumbo jumbo. All these layers come together to build a pyramid of inter-dependent blocks. This approach has greatly increased the efficiency of our craft but came at the cost of fragility. Once a module or dependency breaks, the whole system falls apart. We easily forget that the underlying foundation of the web is plain old simple HTML, CSS, and JS — even if some of the most avant-garde technologists want us to believe they aren’t.</p>
  </blockquote>
  <figcaption>— <cite>Adrian Zumbrunnen, “<a href="https://uxdesign.cc/via-negativa-4bb536f235d5">Via Negativa</a>” via UX Collective</cite></figcaption>
</figure>

***

## Manifesto Reprint

The manifesto has since been removed, so I reproduce it here as an archive. It was created in August of 2019:

### It took me 8 years to launch this site

To be clear, I didn‘t put 8 years of effort into it, but I started and stopped too many times. I was distracted by design ideas, passing fads, trends, and new ways to use the latest tech to deliver an interesting experience. I switched <abbr title="Content Management System">CMS</abbr>’s. I went to no <span class="abbr">CMS</span>. I got stuck chasing ideas. I was trying to make this website *perfect*. And we all should know:

> Perfection is the enemy of done

– <small>*Someone smart who presumably finished things*</small>

### So why did I stop/start here?

I decided to do a non-design, or rather, to leverage <span class="abbr">HTML</span> and a minimal amount of <span class="abbr">CSS</span> to concentrate on the content. <span class="abbr">HTML</span> gives us great power without much work — isn’t it better to use for what it does best?

What did I get without much effort?

+ Semantic meaning from well-formed and thoughtful markup
+ Accessibility
+ Responsiveness
+ Small file sizes and quick downloads (when we keep things simple)
+ Progressive enhancement & backwards compatibility

What did I avoid? 

+ No <span class="abbr">CSS</span> reset
+ No <span class="abbr">CSS</span> or <span class="abbr">HTML</span> framework
+ No jQuery or <span class="abbr">JS</span> library — No <span class="abbr">JS</span> at all
+ No browser-specific hacks
+ No web fonts

Geeky things:

+ Only <samp>8kb</samp> of <span class="abbr">CSS</span>
* This page ha[d] a <samp>125kb</samp> payload
+ Static <span class="abbr">HTML</span> built with [Jekyll](https://jekyllrb.com)
+ <span class="abbr">HTML</span>-agnostic content created with mostly Markdown (via [kramdown](https://kramdown.gettalong.org))

### A web for Everyone

My corner of the web is a minuscule part of a vast universe, but it is still mine and I still care about the people that might find it. By keeping the footprint of this site small, I hope the content will load quick in situations where connections are less than ideal, I hope the accessibility of <span class="abbr">HTML</span> can shine because I am using best practices for semantic markup, and I hope that the reader feels the power to make my content appear in the manner that they prefer. I make very few assumptions for aesthetics that can't be overridden by someone who needs bigger type or more contrast.

### Plans for the Future

I don’t plan to be design agnostic forever. Instead, I plan to experiment and have fun with <span class="abbr">CSS</span> and <span class="abbr">JS</span> on a case-by-case basis. The blog will start simple, but when I feel that an article deserves some special attention, I will design it as a one off. No hard-and-fast system, but instead a chance to _design to the content_.

I'm excited about it.

### _Inspiration_

Thanks to the following authors/sites:

+ [Front-end development is a Skill](https://css-tricks.com/front-end-development-is-not-a-problem-to-be-solved/), where the author laments the overuse of frameworks and encourages new front-end wizards to dig into <span class="abbr">HTML</span> and <span class="abbr">CSS</span> instead of the latest framework.
+ [Quartz: There’s already a blueprint for a more accessible internet](https://qz.com/1407450/theres-already-a-blueprint-for-a-more-accessible-internet/), where the author makes some similar points to some of the ones I made in blog posts for Oomph, but the site design itself does not pass some <span class="abbr">A11Y</span> requirements.
+ [How to Build a Low Tech Website (running on Solar Power)](https://solar.lowtechmagazine.com/2018/09/how-to-build-a-lowtech-website.html), where the LowTech blog builds a static version of itself completely solar powered, with no ads, no cookies, no tracking. The website sometimes goes offline, and the interface exposes the current battery power level as part of the design. 
+ [The Rise of Green UX](https://www.fastcompany.com/90167803/the-rise-of-green-ux title="Read on FastCompany.com"), where the idea is to reduce global data/energy consumption by creating and facilitating lighter web pages that consume fewer <span class="abbr">CPU</span> clock ticks and less bandwidth
+ [The Bullshit Web](https://pxlnv.com/blog/bullshit-web title="Read on Nick Heer’s personal blog"), where the author gripes about the bloat of the web, and how wider roads doesn’t mean less traffic
+ [The Web is Made of Edge Cases](https://codepen.io/tigt/post/the-web-is-made-of-edge-cases title="Read on Codepen.io"), where the author reinforces the facts of the web — users change default browser settings, users zoom the page, javascript fails, browser decide when to stop a render, and most sites ignore the realities of the world wide web
+ [This is a Motherf***ing Website](https://motherfuckingwebsite.com), where the simplicity of <span class="abbr">HTML</span> is celebrated with profanity
