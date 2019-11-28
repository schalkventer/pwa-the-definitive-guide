# 👋 Introduction

## Motivation

I was super excited when I first heard about the \(then up-and-coming\) suite of technologies that allow web developers to create projects/products that are able to compete directly with native mobile and desktop software.

I first stumbled across the concept of _Progressive Web Apps_ one of the monthly [Cape Town Front-end Developers](https://ctfeds.org/) meetups during 2015 \(titled [_Service Workers and Push Notifications_](https://www.meetup.com/ctfeds/events/225531712/)\)_._ I remember some vivid, yet embarrassing memories of it coming to light that I assumed the title referred to employees working in tech-support \(I.e. "service worker"\) and how they and developers use push notifications on their platform.

I left that talk incredibly energized about the possibilities inherent in _Progressive Web Apps_, and subsequently consumed all available literature on _Progressive Web Apps_. I went all the way from the very early documentation on [the Google Developers website](https://developers.google.com/web/progressive-web-apps), to the phenomenal [Mozilla Service Worker Cookbook](https://serviceworke.rs/), and Tal Ater's comprehensive [Building Progressive Web Apps: Bringing the Power of Native to the Browser](http://shop.oreilly.com/product/0636920052067.do) over the next 4 years.

Fast-forward to 2019, and in an ironic twist of fate I'm one of the co-organizers of those very same monthly meetups. It's a no-brainer that I would get as many speakers/facilitators to do talks/workshops on this very topic that stuck with me in 2015? Unfortunately not. After several failed attempts it seemed that most front-end developers didn't feel comfortable talking about _Progressive Web Apps_. Most of our community had a good grasp on some individual aspects of the co-configuration of technologies covered by the umbrella of _Progressive Web App_. However, most felt they weren't qualified to guide other developers along the journey of building \(or converting to\) a project into a _Progressive Web App_. Which makes a lot of sense, not only is it a vast topic to cover, the topic is quite contentious in certain circles. As an illustration see the following comment former Google and Yahoo! developer, [Dan Dascalescu](https://medium.com/@dandv), received on his article titled [Why “Progressive Web Apps vs. native” is the wrong question to ask](https://medium.com/dev-channel/why-progressive-web-apps-vs-native-is-the-wrong-question-to-ask-fb8555addcbb):

> what a bunch of BS!
>
> The so called “progressive” “apps” are just a fad, they are worthless in comparison to native apps. You list a bunch of features that Chrome and some newer Safari version support, but in practice these features are unusable for anything else than DEMO “apps”. I’ll give you a simple example: canvas & web-gl. \[Leaving aside the fact that you cannot achieve with it what you can achieve in a native app\] it’s so slow that it’s unusable in real life. Even making a tiny flappy bird move across the screen will eat up all your CPU and make your fan run like a jet fighter.
>
> Another example that’s praised by fanboys like yourself is SVG. It’s so slow and inefficient that it crashes both Chrome and Firefox if you use more than 3–4 SVG filters!
>
> File API / Storage? Yeah Mega uses it, laggy, slow as hell, eats up double your actual disk storage and the files are hidden somewhere in the Chrome profile directory and they never get deleted!
>
> And all this on Core I cpus and SSDs! I don’t even want to think how your “apps” run on older systems. I really hope this fad passes away before “programmers” flood the offline market like these kind of “apps” \(like nodejs crap\) like they flooded the web with their bloatware. Basically 50% of the sites now are so slow that you cannot open them in older devices and all this for nothing, because they are actually worse than before.

Yikes!

Clearly whoever would be making a case for _Progressive Web Apps_ would need all the help they can get. I started compiling a list of helpful links about _Progressive Web Apps_ and all associated technology at the end of 2018. My hope was that if someone where to do a talk on the subject they would have a bit of a head-start, and might feel a bit more confident. However, after some time I started adding my own notes and examples to the document. It didn't take long for my own notes/examples to actually overtake the amount of external content/links I included.

This must have worked, since I was finally able to coerce a good friend of mine, [Shailen Naidoo](https://github.com/ShailenNaidoo), to co-facilitate a whole day workshop on _Progressive Web Apps_ in early 2020. However, it seemed like a waste to discard all this information I gathered over time. 

**This left me wondering whether there is value in publishing a more refined version of these notes by means of an open-source Gitbook. My hope is that it might eventually cover everything required for a beginner to go from zero to fully-featured, modern** _**Progressive Web Apps**_**.**

## How to contribute

As mentioned above, this guide is intended to be \(and remain\) a completely open-source living document. This means that there might be sections in the guide that might have incomplete content or require further refinement for certain periods of time.

**Given this state of flux, feedback and public suggestions/corrections are highly encouraged!** 

Please feel free to log an issue or open a pull request in [the project repository on Github](https://github.com/schalkventer/pwa-the-definitive-guide). If you are not familiar with [Git](https://git-scm.com/), or prefer more traditional means of communication, you are welcome to reach out to me directly at [venterschalk@gmail.com](mailto:venterschalk@gmail.com).

Lastly, note that this guide is licensed under the [Creative Commons Attribution 4.0 International \(CC BY 4.0\)](https://creativecommons.org/licenses/by/4.0/) license. This means that you are free to copy, redistribute, remix/transform it for any purpose \(non-commerical or even commercial\) as long as you [attribute it as required by it's CC BY 4.0 license documentation](https://creativecommons.org/licenses/by/4.0/#deed-conditions).

## Contact Details

I would love to hear from you! You can reach out to me directly via my email account: [venterschalk@gmail.com](mailto:venterschalk@gmail.com). Alternatively you can chat to me via Slack on the following workspaces:

* [ZA Tech](https://zatech.co.za/) as `@schalkventer`
* [Code for Africa](https://docs.google.com/forms/d/e/1FAIpQLScBPmaH71EuV3HTw-4KSB6x-Xs-6Euf3baSfsMt1wi8n9adkA/viewform) as `@schalkventer`

