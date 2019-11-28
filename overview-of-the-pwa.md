# 🤷‍♀️ Pros and Cons

## Background

I remember the first time native app project I worked on.

**This was early 2013, and every client wanted to have a mobile app for their product \(whether justified or not\). The exciting prospect of mobile apps were at an all-time high. In fact, three years prior the** [**American Dialect Society**](https://www.americandialect.org/) **named the word 'App' as their word of the year for 2010:**

> “App has been around for ages, but with millions of dollars of marketing muscle behind the slogan ‘There’s an app for that,’ plus the arrival of ‘app stores’ for a wide spectrum of operating systems for phones and computers, app really exploded in the last 12 months,” Zimmer said. “One of the most convincing arguments from the voting floor was from a woman who said that even her grandmother had heard of it.”  
>   
> — [American Dialect Society: Word of the Year Vote](https://www.americandialect.org/American-Dialect-Society-2010-Word-of-the-Year-PRESS-RELEASE.pdf) \(2010\)

At the time I was still working at a web development agency. Our team had been approached by an organisation hosting an international, week-long, conference in Cape Town. We had done very little native \(or even hybrid\) app work at this time. However, the team-lead \(convinced that we need to start branching out into native apps\) figured that this might be a good opportunity to cut our teeth on an straight forward project. 

At this time [_Apache Cordova_](https://cordova.apache.org/) was widely used and \(due to our team's familiarity with building websites\) this is what was decided on. Given that I rarely ventured outside the confines of Cordova, the process seemed indistinguishable from designing a regular JavaScript-focused web project. Unfortunately, I can't say the same for the team-lead. I'm sure he racked up quite a phone bill through daily \(or even hourly\) phone conversation from Cape Town, South Africa to California, USA. The deadline was tight and the team scurried to push the product past the gatekeepers at the [App Store](https://www.apple.com/ios/app-store/) and [Play Store](https://play.google.com/store). 

{% hint style="info" %}
If you were wondering _Apache Cordova_ \(previously known as _Phonegap_\) is framework that allows developers to build native apps with front-end web languages \(HTML, CSS and JavaScript\). The latter does not get converted into a phone's native programming language. Instead Cordova embeds your code as a regular HTML website into a blank app.

This is known as Hybrid apps \(as opposed to Native apps, which are written or converted in the  phone's native language\). To this day Hybrid apps still used by a lot of teams but they come with some several drawbacks. These range from severe performance restrictions to limited integration with the operating system. 
{% endhint %}

By some miracle we hit the deadline. We were extremely proud and the client was extremely impressed with the end product. The first day of the conference arrived, and we kept our eyes firmly fixed on the download ticker, expecting positive feedback for the late nights we put in. Unfortunately, by late-afternoon the numbers were still frighteningly low. We assumed that the organizers forgot to promote the app at the event. However, after a quick phone call we were assured that they had erected banners and distributed various merchandise with the URL during the day. Perhaps \(we reasoned\) the amounts displayed by the various stores were cached and would update in a couple of hours or days. Unfortunately, a month passed and the downloads barely changed. 

**To this day the project remains one of the biggest failure's I've experienced in my career.** 

To be fair, this might not be the common experience for most teams or clients when venturing into native or hybrid apps. It is also possible that if we attempted this in 2019 the submission process might be completely different. However, I've often wondered whether things might have turned out differently if we had the option to build a _Progressive Web App_ in 2014. Given, even if it failed to the same disastrously degree, we would \(at the very least\) not have spent the upfront Google Play store \($25 once-off\) and App Store \($99/year\) registration fees.

Regardless, I think it is important to acknowledge that this experience has to various degrees colored my own biases and framing of conversation around native/hybrid apps in 2019. That being said, my approach does differ from a lot of the _Progressive Web App_ advocates, insofar that I'm not convinced there is a zero-sum equation happens with native/hybrid apps on the one side and Progressive Web Apps on the other side.

However, before we unpack the above further, let us take stock of the current state of native/hybrid apps.

## The State of Native Apps

### What we know

By now this is almost a decade ago.

According to Tal Ater \(in his phenomenal book, [Building Progressive Web Apps](http://shop.oreilly.com/product/0636920052067.do)\) it is certainly possible that this experience might not have been some professional fluke, but perhaps a more common occurrence:

> According to a 2016 comScore report, the average person spends 84% of his time on mobile devices using just the top 5 most popular apps. I’m sorry to say, these are not your apps.
>
> On tablets that number is even higher, with 95% of user time spent in the top 5 apps. The same report also presents figures showing that it is much easier to reach a large audience on a mobile site than in a native app. There are close to 600 mobile web properties that reach audiences larger than 5 million visitors — nearly 4.5 times greater than the number of native apps with similar audiences. The top 1,000 mobile web properties have audiences that are almost 3 times the size of the top 1,000, apps and their audiences are growing twice as fast as native app audiences.
>
> — [Building Progressive Web Apps](http://shop.oreilly.com/product/0636920052067.do) \(2017\)

The primary source seems to highlight this fact on several occasions:

> More time is being spent on smartphone apps, but most of that time is concentrated in the highest engagement apps owned by a few of the largest internet companies. The smartphone app now accounts for half of digital media time spent and is still growing strongly, but not at the rate it once was. And large internet companies command the majority of app time, so it can be a challenging market for lesser-known brands.
>
> — [US Mobile App Report](https://www.comscore.com/Insights/Presentations-and-Whitepapers/2016/The-2016-US-Mobile-App-Report) \(2016\)

That being said, a lot has happened over the last 3 years since the above study. One being the rise of the behemoth that is the Chinese gaming market. In the words of American based mobile app analytics organisation, [App Annie](www.appannie.com):

> China accounted for nearly 40% of total consumer spend in 2018. Globally, on a category level, games accounted for 74% of consumer spend in 2018. Non-gaming apps only accounted for 26% of consumer spend, but this was up from 18% in 2016 and largely due to the growth of in-app subscriptions
>
> — [App Annie: The State of Mobile](https://www.appannie.com/en/go/state-of-mobile-2019/) \(2019\)

It seems that this might correlate Ater's claim. However, with a slight shift in recent years towards gaming and subscription-based services like Netflix and Spotify.

### What we don't know.

Despite the above mentions, you will notice that I'm extremely weary to make any absolute claims about the state of native apps. I'm certainly not qualified to have much clout when it comes to analyzing global trends and interpreting these massive datasets, and subsequently you should not consider the above anything more than a cursory read. I'm convinced that a case for the opposite can just as easily be made.

In addition, contrary to most _Progressive Web App_ advocates, I'll be the first to say that some products should not be built as Progressive Web Apps. 

## PWA vs. Native Application



### Current PWA adoption

...

### Progressive Enhancement

...

