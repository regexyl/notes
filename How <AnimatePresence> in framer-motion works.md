---
publish: "false"
tags:
  - react
---
Suppose you want to have a React component perform an animation before it exits. It's tricky, because there's no simple native way to do so. A component is either *in* the React tree or *not* - there's no in-between - so you can't go like, "Hey hold up! Let me do some fancy things to this button before it leaves the page".

An intuitive, non-Reacty way is to (1) start the exit animation, (2) wait till the animation is done, then (3) remove the element from the DOM. That's too much of a chore and not declarative enough for our tastes, so why not use some external libraries for help.

The two most popular choices now (circa Jan 2024) are [React Transition Group](https://reactcommunity.org/react-transition-group/), started in [2016](https://github.com/reactjs/react-transition-group/commits?after=3341075c524bcf466241f5eafbc14bd407d24bc9+0), and [Framer Motion](https://framer.com/motion), started in [2018](https://github.com/framer/motion/commits?after=3105d6f745159c5f193510a221154797459c6732+0). I'm not too familiar with the former, so this article solely dives into the workings of `AnimatePresence` from Framer Motion and how it's able to implement a workaround to enable exit animations.

## A brief introduction to what `AnimatePresence`

>`AnimatePresence` allows components to animate out when they're removed from the React tree.