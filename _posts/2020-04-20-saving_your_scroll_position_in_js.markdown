---
layout: post
title:      "Saving Your Scroll Position in JS"
date:       2020-04-20 20:24:09 +0000
permalink:  saving_your_scroll_position_in_js
---


I just finished my JavaScript module project, and wanted to highlight one bit that was pretty fun to dig into and write a fix for.

### The Problem

Since we're using JS in this project to generate *all* the content on the page, the actual content is reloaded a fair bit. That is, the *DOM*, *not* the page itself. We *aren*'t reloading the URL, and use `.preventDefault()` to stop forms from making that happen automatically. So you stay on the same URL almost all the time in most of our apps, but you potentially refresh the *content* over and over again.

The problem with that is that any time I added or removed something to/from the DOM, the page blinked and started again at the top of the page. In my case I was using things like `.prepend`, `.appendChild` and `variableName = ""` to clear things out when I needed a fresh copy.  This led to things feeling confusing, and made it easy to lose track of which thing on the page you'd been working with, and whether or not what you tried to do worked.

### The Solution

I could dig in with a lot of exposition, but I already had inline docs in my code, so let's just splat that here for starters:

```
export function appendAndRestoreScroll(dom) {
  // Save off the location of the window scroll so that when the thing we add to the dom pops up, you don't get auto-scrolled back to the top.
  let lastScrollY = window.scrollY;
  let lastScrollX = window.scrollX;

  // Clear out the body so that we can re-run this code later when we change the inputs without creating multiple copies of the whole page.
  document.body.innerHTML = "";

  document.body.appendChild(dom);

  // We want the next step to happen before paint, but with enough time for the browser to let us change the scroll position. I experimented, and setTimeout takes a little bit too long (it creates some jank), but requestAnimationFrame seems to work without jank. https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame
  requestAnimationFrame(() => {
    window.scrollTo(lastScrollX, lastScrollY);
  });
}
```

And tada!

In my particular case, I had a couple different pages and files, so I extracted the `appendAndRestoreScroll` function to a file with other centralized bits of code. If you *don't* have that much complexity, you'd just need the one simpler instance of it. 

It saved off the scroll positions—`window.scrollY` and `window.scrollX`—in variables I could use again shortly.

I ran this function from within the code that put the new content on the page, so that it would capture the scroll position right *before* it wiped the old content off, and then bring it back just *after* the new content appeared, so you'd land in the same place. 

Then I used a built in browser capability to restore the scroll position, `window.scrollTo(X, Y)`.


