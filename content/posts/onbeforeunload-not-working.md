---
title: "Onbeforeunload Not Working"
date: 2020-09-20T20:56:06+12:00
comments: true
showthedate: false
tags:
  - javascript
  - chrome
---

 `onbeforeunload` is typically implemented to ask user to take some actions before leaving the website.

 But somehow it does not work as intended as before, not sure since when, but it does not work in the latest Google Chrome browser.

 ### 1. Custom Alert Message

The message can no longer be customised. Even though you have specified the message, it will still display to you `Changes that you made may not be saved`.

### 2. Event Not Triggered

This is the most important and confusing thing. Apparently the alert popup will not be shown at all if there is no mouse left click action happened.

### 3. Wait It is Triggered

While it looks like the event is not triggered, but actually it is indeed triggered, only the popup alert is not shown. So you can still do whatever you want behind the scene like sending data through Ajax if you need to.

#### Demo: https://jsfiddle.net/usw3mnab/2/show
