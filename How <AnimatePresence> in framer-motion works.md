---
publish: "false"
tags:
  - react
---
Suppose you want to have a React component perform an animation before it exits. It's tricky, because there's no simple native way to do so. A component is either *in* the React tree or *not* and there's no in-between. It also does not have the knowledge of when exactly it gets removed from the tree prior to its removal.

An intuitive, non-Reacty way is to (1) start the exit animation, (2) wait till the animation is done, then (3) remove the element from the DOM. That's too much of a chore, ain't it? It's also not declarative enough for our tastes, so this is where external libraries are able to step in and create a workaround.

The two most popular choices now (circa Jan 2024) are [React Transition Group](https://reactcommunity.org/react-transition-group/), started in [2016](https://github.com/reactjs/react-transition-group/commits?after=3341075c524bcf466241f5eafbc14bd407d24bc9+0), and [Framer Motion](https://framer.com/motion), started in [2018](https://github.com/framer/motion/commits?after=3105d6f745159c5f193510a221154797459c6732+0). I'm not too familiar with the former, so this article solely dives into the workings of `AnimatePresence` from Framer Motion and how it's able to enable exit animations.

## A brief introduction to what `AnimatePresence`

>`AnimatePresence` allows components to animate out when they're removed from the React tree.

This is what it looks like in code:

```tsx
import { motion, AnimatePresence } from "framer-motion"

export const MyComponent = ({ isVisible }) => (
  <AnimatePresence>
    {isVisible && (
      <motion.div
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        exit={{ opacity: 0 }}
      />
    )}
  </AnimatePresence>
)
```

We can see that `<motion.div>` is controlled by a conditional, `isVisible`, while `<AnimatePresence>` is an immediate wrapper component around its children with exiting animations.