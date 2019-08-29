---
layout: post
title: "More Power to the Users"
date: 2014-01-10 03:10:00 -0500
categories: [ Design, User Preference ]
---

If 2013 was the year of Content — [or was it Content Management](//despreneur.com/cms-trends-for-2014/) — then 2014 should be the Year of the User. It’s been a long time since a web designer could design a site for one mobile device size, one tablet size, and one desktop size. The number of internet-connected devices with screens is staggering. Start to review all the different resolutions that they support and you might finally be convinced that fluid widths is the new 960 grid. 

Designers — myself included — tend to love, love, love controlling the user experience. We call it “design”, but it is really a form of control. We anticipate how a user will interact with a website or application, and design/control the way they go from one task to another, find the useful buttons, read the content, etc... Its not so easy  to control that experience anymore — or even predict it.

## Control used to be possible

Control was possible in the print medium. There was a front cover, page 1, page 2, etc... You knew very well how a user would experience the printed medium. The biggest edge cases were if they started from the middle of a book or flipped a magazine from the back to the front. Other than that, the experience was easy to anticipate, therefore control.

The beginnings of the web were very much like that — and the parlance followed, hence, “web *page*”. A page on screen was treated like a page in a book, albeit with an omnipresent “navigation” which was the web’s version of a table of contents. With a limited number of people using the web and a limited number of ways to access it, the options for users were more vast than the print medium, but it was plausible to control these as well.

Other factors, like bandwidth, entered the area and designers came up with ways to deal with it. Since the web was so new, though, waiting for downloads was an acceptable part of the game. I’d argue that the anticipation was a large part, too.

Since the web was so new, no one had high expectations yet. No one expected the web to be fast. No one expected the web to be high-definition (remember the first digital cameras and movies?) No one expected to carry the web around in their pocket.

## Too many devices, too many resolutions

All that, of course, has changed. The web is all things to all people now — its fast, its slow; its in their hand, on their lap, on their TV; its text only and its high-definition. The list of devices that interact with digital content gets added to every day, sometimes in unexpected ways — think Google Glass and smart watches. These variables can make a designer feel downright powerless.

To add to our collective angst, there are devices out there that do not play nice. There is the iPad mini, which is a shrunken iPad in more ways than its measurements. It packs the same resolution of a full-size iPad into its smaller screen, but its not a “retina” device. The 1024 x 768 pixel display is just smaller. A media queries can not tell the difference between the 7.9 inch display or the 9.7. <a href="//www.projectevolution.com/activity/font-size-controls-are-relevant-again/">Why do we care? Because type will appear 19% smaller on the mini, making 16px (1em) type appear 13px</a>.

More frustrating are so-called “Retina” devices, or more simply, high-density pixel screens (I won’t even name any, because that list would be immediately out of date). Many of these are mobile smart phones, which means that a designer or developer should consider the implications of delivering high resolution images over potentially low-bandwidth networks. Sure, we can add something like Retina.js to make high-resolution images possible, but should we?

Designers like to make their job very difficult. <a href="//www.jordanm.co.uk/post/65776639602/responding-to-environmental-lighting-with-css-media">Some have even come up with ways to change the page design based on the light level in the room</a> — bright light means higher contrast background and text color, while lower light affords a subtler distinction. While this type of thinking is admirable, wouldn’t it be better to let the users make these adjustments as they need them?

## Control is no longer possible

I argue that yes, we should think about designing systems that give the user more control over the content they are consuming or the site they are navigating. Quite a few Apps do this already, and this makes sense, as the ones that stand out are focused on reading. I am starting to think that all websites need to start thinking this way as well.

Some may read “Control is no longer possible” as “Give up”. Not so. Instead, feel freed by this idea. Say it to yourself… *control is no longer possible*. Phew, what a relief.

Users will thank you when you relinquish control. Consider these scenarios:

+ A user has a iPad mini and wishes they could make the text of your site bigger, without having to change the system-wide settings globally
+ A commuter on their smart phone is in a hurry and looking for some key information on your site. They are in a terrible location with only a few bars and they’d rather not wait for high-resolution images to download, even though they sure do look nice
+ A tablet user is trying to read your article while walking down a sunny street, and your dark grey text on a light gray background is difficult to read
+ An older user has adjusted their browser’s default font size to something larger, but your site declares a 13px font size on the body, so all of their preferences are for naught (you better not be doing this anymore!)

We could spend a lot of time and energy planning for each of these scenarios, or, instead we could plan on how we let users customize their own experience and set their own preferences.

## It’s time to put more control in the right hands

This idea is not mine, and it already has a term associated with it — “Seamful” design, which refers to the idea of “exposing the seams” of an interface or piece of software. Instead of invisible, seamless software, we should think about appropriate ways to introduce seams that help provide options and stability. Poured cement structures could be seamless, as an example, but they typically incorporate seams that make shifts possible due to heat expansion or provide places for cracks to occur in a controlled way.

More than this, I think the idea that designers should control the experience is simply out of date and unsustainable. _Stop driving yourself crazy!_

There are already some companies/designers thinking in this way. The Filament Group’s idea for a SD/HD toggle for Retina devices is great, in my opinion. Vimeo’s “[couch mode](//vimeo.com/blog/post:355)” for viewing their website on Smart TVs is also pretty great, as it is a new way to experience a typical website when going beyond the desktop. They didn’t just try to detect a TV with media queries or something more complicated, instead, they give the power to the user to put the site’s UI into a new mode.

To be a responsible responsive designer, I think we need to come up with common-sense defaults for our interfaces, but allow the user to tailor it to their specific needs at the moment. Do I need a larger font size when I am sitting my tablet in my lap vs. when I am glancing down a list of articles on my phone? Am I checking Facebook in bed and want a lower contrast design? Am I in a rush, or do I have time to download the super-nice high resolution images?

Let’s stop anticipating every scenario and instead let our users take control.

* * *

*Originally published on ProjectEvolution.com*