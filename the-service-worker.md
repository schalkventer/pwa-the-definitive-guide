# ⚙️ The Service Worker

## Overview

...

## Web Workers

...

## The Lifecycle

The service worker installation cycle can be confusing at first. However, it's relatively simple to grasp if you understand two things:

* Service workers can not be swapped out during a user scope-session.
* All new service workers go through three stages when detected by the browser.

### Scope-session

#### Service worker scope

Each service worker has a specific scope that it operates in. This is primarily determined by the directory that the service worker file is placed in. For example if your service worker file is placed in the root then it's scope covers the entire domain. However, if placed in, for example the  `/user/account/service-worker.js`  director of `www.google.com` then it will only control that path and nested paths. For example the latter will not control `www.google.com/user/payment.html` but will control `www.google.com/user/account/data/latest.html`  and `www.google.com/user/account/logo.png` .

In addition to this you can manually set the service worker scope when registering it. However, note that you can only narrow the scope and not increase it past it's original scope \(determined by the directory\). In other words a service worker in `/user/account/service-worker.js` can set a manually restrict it's scope to `www.google.com/user/account/data`, but  can not change the scope to `www.google.com/user` .

#### Session

In generally programming language a session refers to an temporary information interchange between two or more communication devices. In short:

* All devices involved actively listen for and send information to one another \(interchange\)
* This interchange lasts a limited amount of time \(temporary\).

You might not realize this, but even if you walk away from your desk with a specific website open in some hidden, long-forgotten browser tab, both the browser and server are in constantly states of readiness, waiting to hear from the other. This is what allows allows you to remain logged into a website even if you refresh the page and what allows real-time updates through chat functionality \(by means of [WebSockets](https://en.wikipedia.org/wiki/WebSocket)\). This means that as long as there is an instance of a website somewhere in your browser, it can be said that you have an open browser session with that site \(even if the site or server does not make use of this fact\).

This means that a browser session starts as soon as you navigate to a site for the first time \(for example: `https://www.google.com`\) and ends when you the last browser tab pointed to that specific site is closed.

#### The service worker scope-session

Note that I specifically mentioned browser tabs above. This is bound to happen at some point: no matter what you do, your service worker just doesn't seem to install, after several Stack Overflow articles and debugging you realize that you have another instance site open somewhere between the 50-something other tabs you have spread across 7 browser windows. 

Sure, this is inconvenient, but the reason for this is quite simple. In the words of Google developer advocate, [Jake Archibald](https://jakearchibald.com/): 

> Without service workers, users can load one tab to your site, then later open another. This can result in two versions of your site running at the same time. Sometimes this is ok, but if you're dealing with storage you can easily end up with two tabs having very different opinions on how their shared storage should be managed. This can result in errors, or worse, data loss.
>
> — [The Service Worker Lifecycle](https://developers.google.com/web/fundamentals/primers/service-workers/lifecycle)

The only exception being if you intentionally set you service worker's scope to not control the entire domain \(we will cover this in the [Manifest File section](manifest-file.md)\), then the above only applies to the scope of the service worker.

## Intercepting Requests

### The fetch request





## Browser Requests

* The Fetch API
  * The history of AJAX/Fetch, etc.
  * Intercepting a request with a service worker.

