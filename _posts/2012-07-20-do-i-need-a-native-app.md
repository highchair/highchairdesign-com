---
layout: post
title: "Do I Need a Native App?"
date: 2012-07-20 03:00:00 -0500
categories: [ "Web Development", Mobile ]
---

<aside class="archive__statement">
I wrote this in 2012, and am republishing it because I find it interesting as a historical artifact — this is what we were concerned about 4 years after the iPhone made web design a lot more complicated. Most of the core points here are still true, but the App examples are out of date.
</aside>

## The Jargon, the Buzzwords, and the Reality of Designing and Developing for Smartphones and Tablets

Over the past few years, these things that we now call Apps have exploded all over the marketplace. It used to be cut and dry who needed an App and who didn’t – Apps used to be mostly games or tools or widgets of some sort for a specific task.

Now, nearly every website has an App component. The better Apps consist of the core functionality of the website – pared down, focused, and optimized for smaller screens and touch interfaces. The bad ones try to cram everything into a small screen without actually redesigning the experience, or do not take advantage of the native features that make smartphones so useful – geolocation, push notifications, accelerometer and the like.

As a newcomer to the marketplace, how do you determine what your company needs? Do you know what the buzzwords actually mean – Native Apps, <span class="abbr">HTML5</span>, wrappers, or responsive design? How does your company plan to distribute the App? What sort of investment should you expect to make, and will it cost the same or more than the website that you just developed?

## The Distribution Decision: The App Store Question

There is one main question to ask when deciding whether or not your company or product needs a Native App. The question is simply: **Is it important that your mobile application be something that can be downloaded from the Apple App store?** That’s it. If it is important to your company, then you need a Native App. If you need to make money by selling the App, a place in the App store shelf is a necessity. Apple will only approve Apps that have a Native component and conform to their HIG (Human Interface Guidelines).

If not, then you have more options – develop a Native Android App and distribute it through the Google App store, distribute it yourself to a closed network of employees, or the “App” could simply be a glorified web site that a user can still bookmark on their home screen.

Why is this the most important factor? 116 million iPhones and 67 million iPads,[^1] that’s why. Apple has defined the market and practically defined what a smartphone is to many people. Since they are the cultural standard, their delivery system – the App store – is very important to someone distributing an App. Without it, your App can not get onto the iPhone.[^2]

[^1]: If you trust the web, here is some data to back up the claims: [Apple profits up as iPhone sales Grow, nytimes.com](https://www.nytimes.com/2012/04/25/technology/apple-profits-up-as-iphone-sales-grow-88.<span class="abbr">HTML</span>)

[^2]: Not completely true. With an enterprise developer account, an iOS App can be distributed within a closed network, say, for company-owned iPads. But that doesn’t get the App into the Store, it just gets it onto the device. 

To answer this question, look at some of your own visitor statistics. If you use Google Analytics (why aren’t you using Google Analytics?) then you have access to a whole slew of data about your users. Are a major share of your current mobile visitors on one platform or the other? Can you predict which platform will be stronger if there is an App available? Do users in your market prefer one platform or are they more diverse? Are Blackberries on your radar (and if so, how much ibuprofen do you have access to)? 

For some companies, this is an easy way to think about it. **“Yes, the main slice of our mobile users are iOS owners. Case closed.”** Great. For others, it is not so easy, but either way, the distribution network is a key factor in any decision. 

## The Technology Decision (and Why Your Users Don’t Care)

The end user does not care how a website or App is built, they only care about how well it works. If you answer the question _“What does the App need to do?”_ then you can let the developer decide how the App needs to be built. After all, that is their job.

It’s potentially a bold statement to say that you shouldn’t care how something is built. Let me use a more familiar metaphor to explain:

> I am in the market for a car. I know I want a car. I know I want four doors, wheels, and an engine. I know what it is and I know it when I see it. I may not care about color or how many cylinders it has or even how many doors, I just know that I need a car, and I don’t need to know more. I can go out into the marketplace and buy one. I know I am not going to buy a motorcycle, and I am not going to buy a bus, because I want a car.

Over simplistic, sure… but that’s what we are talking about here. Once you decide you need a car, you go and look at cars and the various options they have. There are as many ways to build an Native App as there are to build cars,[^3] and in both cases the engineers decide how they get put together. They build them the way that the market wants to see them — sports cars that are really fast, wagons that are more practical, trucks that are heavy duty — and an App can be built to be fast, simple to use, or robust, and sometimes all three.

[^3]: Totally exaggerating, but you get the point.

How an App is built is a conversation that will continue to change and evolve as mobile devices become more powerful, screens get finer detail, and development methodologies evolve to match. Define what your user’s need to accomplish, and the rest can follow.

## So you want some examples…

No doubt you want to “see” what we are talking about here. _“What makes up a popular App that I might use everyday?”_ Here are two well-known brand Apps and the various technologies that make them work.

### Facebook

I guess we can’t talk about anything these days without talking about Facebook.[^4] Their mobile App is a mixture of many things, and it is a good example of what we now call a Wrapper App.

[^4]: Right around the time of this article, the Facebook IPO was all the news wanted to talk about. Gah.

A Wrapper App has some native code and functionality (Objective C for iOS, Java for Android) around a few web views of typical <span class="abbr">HTML</span> content. Native code handles communicating with the phone’s hardware features and stores much of the UI. Other views are built with <span class="abbr">HTML</span>, which is better at showing streams of content. Native code is better at handling some interface actions and can cut down on what would otherwise be <span class="abbr">HTTP</span> server requests.

The “Wrapper” is a good way to cut deployment and development time and concentrate the App on doing a few things very well through a mix of technologies. Using this hybrid approach can have pitfalls[^5] if not done well, but in general, it is the preferred way to develop most non-game Apps.

[^5]: The pitfalls can be mitigated, but the key takeaway here is that native code does some things well and <span class="abbr">HTML</span> views do other things well. Both should be used for their best points. The slew of bad press that the FB App gets might be due to the way FB codes (move fast and break things) more than the technologies they chose to employ. More reading about what the Facebook App is doing, right or wrong: [Here’s Why the Facebook App is so Bad, blog.mobtest.com](https://blog.mobtest.com/2012/05/heres-why-the-facebook-ios-app-is-so-bad-uiwebviews-and-no-nitro/) and [These are the Technical Reasons ehy the Facebook App is so Terrible, cultofmac.com](https://www.cultofmac.com/167201/these-are-the-technical-reasons-why-facebooks-ios-app-is-so-terrible/)

### LinkedIn

The business social network launched a redesigned App recently to much fanfare and many positive reviews. They also use a Wrapper approach with a layer of native code wrapped around different types of web views.

LinkedIn’s App is said to be only 5% native with the rest being <span class="abbr">HTML</span>5 web views, but people are surprised how Native it feels (especially when compared to the reviews that the Facebook App gets). One of the tools in their belt is the new <span class="abbr">HTML</span>5 local storage options for caching content locally, which allows them to store views more readily and load views before they are requested.[^6]

[^6]: This can get very technical, but if you are inclined, these are some good reads: [venturebeat.com](https://venturebeat.com/2011/08/16/linkedin-node/), [Local Storage, engineering.linkedin.com](https://engineering.linkedin.com/mobile/linkedin-ipad-using-local-storage-snappy-mobile-apps), [Smooth Infinite Scrolling, engineering.linkedin.com](https://engineering.linkedin.com/linkedin-ipad-5-techniques-smooth-infinite-scrolling-<span class="abbr">HTML</span>5)
 
The key components of the App is its Native feel – it takes full advantage of how users have come to expect the touchscreen interface to work. Swipe events are built into the workflow seamlessly, making the App a joy to use. As a case study for user experience, LinkedIn is a good one – they broke their user base into the At-work user, the On-the-couch user (tablet), and the 2-minute user (smart phone) and they designed specific experiences for all three.

### Angry Birds

Games fall outside the scope of our discussion today (it is a highly specialized industry) but they are good examples of full Native applications.

For those of you living in a cave,[^7] Angry Birds is a game where you flick angry-looking bird characters at various items to knock them down. There’s more to it, but that’s the basic premise. It relies heavily on game physics and native swipe gestures. I’m not positive, but I think it is safe to say that it was built completely in Native code.

[^7]: Hi, welcome to my cave. I’ll admit that I played the game for the first time when writing this article.

The benefits of Native code are speed (not in development, but in the way the App works) and the access to smartphone hardware like the accelerometer or camera.[^8] The pitfalls are the development time, cost and specificity: the iOS version of the App will not work on Android, and vice versa. There are ways for developers to share a code base to make this easier, but know that the costs associated with developing for both platforms is almost double.

[^8]: While libraries like PhoneGap can help make non-native access to hardware easier, there are still some features that remain out of reach. Another reason why the __“What does your App need to do”__ question is so important when figuring out which technologies to employ.

## Conclusions

The mobile web is confusing, but that’s ok. There are people like us whose job it is to make things more simple, and to worry about the details when they need to be worried about.

For most projects, a fluid web design that scales to the viewer’s screen size is enough. In fact, we only develop responsive sites, which should be ready for the devices that haven’t even been conceived yet.

For those of you considering a tablet or mobile App to complement your website, there are some decisions to be made early on to help inform what kind of approach you need. Above all, the user experience should be suited to the device being used and the App needs to concentrate your core functionality to make it a joy to use – snappy downloads and interactions, swipe actions and form elements that feel “Native”, etc.[^9] Without that, you’ll end up with one more App in a sea of mediocre Apps, and no one wants that.

[^9]: There are certain UI “tricks” that can help a web-based App feel more responsive than a 3g connection will allow. [Instagram lifted the curtain on some of their tricks, as detailed in this slide deck](https://speakerdeck.com/u/mikeyk/p/secrets-to-lightning-fast-mobile-design). Some of the more salient slides are explained at [fastcodesign.com](http://www.fastcodesign.com/1669788/the-3-white-lies-behind-instagrams-lightning-speed)
    
— _Originally published on ProjectEvolution.com, now defunct_
