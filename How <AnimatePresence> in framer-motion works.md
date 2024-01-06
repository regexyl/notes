---
publish: "false"
tags:
  - react
---
Suppose you want to have a React component perform an animation before it exits. It's tricky, because there's no simple native way to do so.

An intuitive, non-Reacty way is to (1) start the exit animation, (2) wait till the animation is done, then (3) remove the element from the DOM. That's too much of a chore and not declarative enough for our tastes, so what about using external libraries for help?

The two most popular choices now (circa 2024) [React Transition Group](https://reactcommunity.org/react-transition-group/) in [2016](https://github.com/reactjs/react-transition-group/commits?after=3341075c524bcf466241f5eafbc14bd407d24bc9+0).


A brief introduction to what `AnimatePresence` is:
>`AnimatePresence` allows components to animate out when they're removed from the React tree.