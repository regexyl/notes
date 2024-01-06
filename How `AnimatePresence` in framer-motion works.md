---
publish: "false"
tags:
  - react
---
Suppose you want to have a React component perform an animation before it exits - it's tricky, because there's no native way to do so.

An intuitive, non-Reacty way is to (1) start the exit animation, (2) wait till the animation is done, and (3) remove the element from the DOM. That's too much of a chore and not declarative enough for our taste, so in comes [React Transition Group](https://reactcommunity.org/react-transition-group/).


A brief introduction to what `AnimatePresence` is:
>`AnimatePresence` allows components to animate out when they're removed from the React tree.