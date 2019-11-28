# ⚙️ The Service Worker

## Overview

...

## Web Workers

### Asynchronous JavaScript

Even from it's humble beginning at Netscape in 1993, JavaScript has always been envisioned as an asynchronous language. 

If you're not familiar with the concept of asynchronous programming languages, they can be described as a languages that allow code to be executed in a different order than it was written. In a synchronous language you might pause the execution of all code until a specific condition resolves \(for example you might wait for specific data to load before doing anything else\).

While it is definitely easier to reason about synchronous code \(which is why Node usually provides synchronous versions of functions in addition to the default asynchronous functions\), being able to selectively execute code as needed does provide a lot of benefits.

{% hint style="info" %}
If you've never heard about Node before, it can basically be described as ...
{% endhint %}

This means that tasks do not happen in the order that they are written in the code, but rather when they are called in the JavaScript event loop. According to the Mozilla Developer Network the event loop, which lies at the heart of JavaScript, can be described as follows: 

> JavaScript has a concurrency model based on an event loop, which is responsible for executing the code, collecting and processing events, and executing queued sub-tasks. This model is quite different from models in other languages like C and Java.

Along with the event loop, JavaScript handles handles asynchronousity by means of a [call-stack](https://developer.mozilla.org/en-US/docs/Glossary/Call_stack), which is essential a container that keeps all tasks that can be run on the page \(called registered events\). The event loop then runs in the background continually checking whether any tasks in the call-stack have met their execution conditions. 

_As an aside, you might have gotten the  `'Maximum call stack size exceeded.'` in your code before. This essentially means that the call-stack has reached it's storage limit and can no longer store any more tasks._

To illustrate this we can look at the following code:

```javascript
// Gets the all <button> elements on the page.
const htmlButtons = document.querySelector('button');

// Adds an alert to the call-stack when the first button is clicked.
const showFirstMessage = () => alert('This is the first message'); 
htmlButtons[0].addEventListener('click', showMessage);

// Adds an alert to the call-stack when the second button is clicked.
const showSecondMessage = () => alert('This is the second message'); 
htmlButtons[1].addEventListener('click', showMessage);

```

Due to the above interaction between the event-loop and the call-stack the buttons can be pressed in any order, regardless of the order it was written in our code. Alternatively we can also do the following:

```javascript
setTimeout(showFirstMessage, 2000);
setTimeout(showSecondMessage, 1000);
```

If you run the above code you will notice that the second message fires before the first message, regardless of the order that it was declared in.

### The single thread

However, let's say we want to modify our code as follows: Whenever a user clicks one of the buttons, we want to remind them about the other button if 5 seconds go by without them clicking it. Our code might look as follows:

```javascript
let bothClicked = false;
let waitingForOtherButton = false;

const htmlButtons = document.querySelector('button');

const secondaryAlert = () => {
    const showReminder = () => alert('Please click other button too');
    
    if (waitingForOtherButton === false) {
    
    }
    
    setTimeount(
    
    if (bothClicked === false) {
        
    }
}

const showFirstMessage = () => alert('This is the first message'); 
htmlButtons[0].addEventListener('click', showMessage);

const showSecondMessage = () => alert('This is the second message'); 
htmlButtons[1].addEventListener('click', showMessage);

```



 clicked we want to wait 3 seconds, and alert the user if the 

One of the problems plaguing the history of JavaScript is that it's code can only be executed in a single thread. This means that it can only perform one one task at a time. This does not mean that task can not happen asynchronously \(in different orders\), but in essence JavaScript can only focus on one task at a time. This is usually illustrated by the following example:

```javascript
const fireAlert = () => alert('Focus on me now!')

const addText = () => 
    document.body.innerText = document.body.innerText + 'Hello world!';
    
setTimeout(addText, 1000);
setTimeout(addText, 2000);
setTimeout(addText, 3000);
setTimeout(addText, 4000);

setTimeout(fireAlert, 2500);

```

If you run the following example you will notice that it outputs `'Hello world!'` to the window twice and then pauses once the `alert` fires. Upon dismissing the message \(if 4 seconds have passed\), the remaining two instances of `'Hello world!` is immediately output to the window instead of continuing the count.

{% embed url="https://codepen.io/schalkventer/pen/1f07df691759750da6d78aefa223d1f8?editors=1011" %}

You are seeing the single-threaded nature of JavaScript in action. Since JavaScript is inherently asynchronous, 

Web workers were initially conceived in 2009 as a way 

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

