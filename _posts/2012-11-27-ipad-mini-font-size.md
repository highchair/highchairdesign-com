---
layout: post
title: "Font-size Controls <strike>are Relevant Again</strike> Have Always Been Relevant"
date: 2012-11-27 04:00:00 -0500
categories: [ Design, "User Preference" ]
---

It came to our attention recently that the new iPad Mini is a device with its own special qualities and without any way to use simple media queries to optimize that experience. As detailed in [Mission Impossible: iPad Mini detection for HTML5](//www.mobilexweb.com/blog/ipad-mini-detection-for-html5-user-agent) there is no way to deliver iPad Mini-specific styles using CSS.

## That's really too bad, and here’s why:

The new iPad Mini’s user agent registers the same viewport dimensions as the larger iPad 2 (non-Retina). Both use a 1024 x 768px screen and both use Mobile Safari. Neither of them have a dense device-pixel-ratio, and while the iPad Mini has a dpi of 163 (vs. the iPad’s 132dpi,[^1] the resolution media-query attribute is not available on WebKit-based browsers. So neither the width, device-pixel-width, or resolution attribute would allow us to target the Mini.

[^1]: [List of devices and display specs on Wikipedia](//en.wikipedia.org/wiki/List_of_displays_by_pixel_density#Apple)

## Why does this matter?

Basically, the Mini, is, well... mini. _It squeezes the same resolution into a screen that is 19% smaller._ It deals with media queries as if it were as large as its full-size counterparts. The result is 19% smaller experience, including 19% smaller font sizes and 19% smaller touch targets. The smaller text and touch targets are what concern us the most. 

Users with keyboards and access to the browser’s full controls can adjust their text size as needed. Most browsers support the <kbd><kbd>command</kbd> <kbd>+</kbd></kbd> or <kbd><kbd>command</kbd> <kbd>-</kbd></kbd> keystrokes to adjust font size on the fly. Touch devices do not. With a pinch zoom a user can zoom the page, but they will end up needlessly tracking around to read lines of text, as the pinch zoom simply scales the whole page, not the font size.

In iOS, under <kbd><kbd><samp>Settings</samp></kbd> &gt; <kbd><samp>Accessibility</samp></kbd> &gt; <kbd><samp>Large Text</samp></kbd></kbd> a user can set their default font size to be something larger than 16px. This setting changes a global variable, however, and will not adjust some applications – like Safari – independently from others. It certainly wasn’t meant to adjust the view of one website over another.

Enter the old-ish idea of user-facing font adjustment controls – the feature most often represented by **<small>A</small> A**. While these were cool when they first started to appear a few years ago, I always thought they were gimmicky. Most browsers had well-documented controls for font size, the exception being Internet Explorer, which only worked well when the designers were forward-thinking enough to use EMs as font-size values instead of pixels. If a user didn’t know how to adjust the font size, why should we present them with additional controls that duplicate a browser feature?

With the mobile web, however, these controls seem to have a new relevance. We need to put the control into the hands (under the fingers?) of the user[^2]. With a slew of devices yet to be invented, we may run into other situations where a user has a small screen and media queries do not work as expected. With an EM- and %-based set of layouts, a simple <kbd>+<kbd> or <kbd>-</kbd> could make a user’s experience that much better. 

[^2]: We are toying with the idea of using Modernizr’s `no-touch` detection to hide these controls for non-touch devices. Are there some edge cases we should consider with this approach?

*Originally published on ProjectEvolution.com*

<aside class="archive__statement">
I wrote this in 2012, and am republishing it because I find it interesting as a historical artifact — plus, I find it even more interesting that <a href="//stephen.io/mediaqueries/#iPadMini">there is still no way to detect an iPad Mini</a> and simply increase the font size by 20%. Shame. 
</aside>