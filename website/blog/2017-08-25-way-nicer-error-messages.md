---
title: Way, Way, Waaaay Nicer Error Messages!
---

A picture's worth a thousand words.

Before:
<div style="width:744px">
  <img alt="before" src="https://user-images.githubusercontent.com/1909539/29709302-ab0c6aee-8940-11e7-953f-60a867d242cb.png" />
</div>
After:
<div style="width:742px">
  <img alt="before" src="https://user-images.githubusercontent.com/1909539/29709301-ab04eac6-8940-11e7-8d2b-c65f808b6be8.png" />
</div>

Sometimes when I'm busy working, some random colleague/Discord member would ping me and tell me "Yo Cheng Lou why are Reason's errors so bad? Why can't you be more like [Elm](http://elm-lang.org) Cheng Lou? Why? Look at how great Elm's errors are Cheng Lou, look."

In reality I'm pretty darn ashamed of our error messages; here we are, a type system with two decades of solid research and implementation, but sometimes presented to the end users as if it's something that'd get in their way.

No more! We've heard you loud and clear, and delivered you much improved error messages! A few things we did:

- Display the error-ing line(s), right inside the terminal.
- Better colors, for quicker visual search.
- Improved messages in many cases.
- Errors in Reason syntax for Reason files.
- A bit of breathing room between lines.

The last point is a tradeoff; errors end up taking more space. Seeing that you'd usually focus on a single error rather than trying to get an overview of all errors, we've deemed this tradeoff worthwhile, especially in the context of a big amount of build output. Considering the new warning format:
<div style="width:745px">
  <img alt="warning-after" src="https://user-images.githubusercontent.com/1909539/29711739-431be094-894b-11e7-87a6-bc1d6aeea043.png" />
</div>
Here's the same warning, old version, buried among other outputs:
<div style="width:745px">
  <img alt="warning-before" src="https://user-images.githubusercontent.com/1909539/29711789-810739f8-894b-11e7-8451-a919b3f119c6.png" />
</div>

At Messenger, we've seen people ship warnings to production not because they didn't want to fix them, but because they've **missed them**! It's not rocket science. Leave some negative space here and there. Color things appropriately. Voilà!

**The new errors can be turned on by adding `"bsc-flags": ["-bs-super-errors"]` to your bsconfig.json**, [like so](https://github.com/reasonml-community/reason-react-example/blob/6dc15bf5fbeeb184c99acb063f7644a0d14b12f4/bsconfig.json#L3). They're also available for [bsb-native](https://github.com/bsansouci/bsb-native). True to our stack's spirit, they're fast, simple to configure, and solid.

**One more thing**: we're vertically integrated common pitfalls of [ReasonReact](//reasonml.github.io/reason-react/) into these messages too, when applicable.

<div style="width:747px">
  <img alt="reason-react" src="https://user-images.githubusercontent.com/1909539/29712284-f1013bb2-894d-11e7-9596-1cca54d5c331.png" />
</div>

This is just the first of many iterations to come! Got a message you'd like to see explained better? File an issue [here](https://github.com/reasonml-community/error-message-improvement/issues)!

Enjoy =)