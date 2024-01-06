---
publish: "true"
tags:
  - react
  - oss
---
Suppose you want to have a React component perform an animation before it exits. It's tricky, because there's no simple native way to do so. A component is either *in* the React tree or *not* and there's no in-between. It also does not have the knowledge of when exactly it gets removed from the tree prior to its removal.

An intuitive, non-Reacty way is to (1) start the exit animation, (2) wait till the animation is done, then (3) remove the element from the DOM. That's kind of a chore, isn't it? It's probably also not declarative[^declarative-vs-imperative] enough for our tastes, so perhaps this is where external libraries are able to step in and create a workaround.

The two most popular choices now (circa Jan 2024) are [React Transition Group](https://reactcommunity.org/react-transition-group/), started in [2016](https://github.com/reactjs/react-transition-group/commits?after=3341075c524bcf466241f5eafbc14bd407d24bc9+0), and [Framer Motion](https://framer.com/motion), started in [2018](https://github.com/framer/motion/commits?after=3105d6f745159c5f193510a221154797459c6732+0). I'm not too familiar with the former, so this article solely dives into the workings of `AnimatePresence` from Framer Motion and how it's able to enable exit animations.

## A brief introduction to `AnimatePresence`

>`AnimatePresence` allows components to animate out when they're removed from the React tree.[^motion-docs]

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

We can see that `<motion.div>` is controlled by a conditional, `isVisible`, while `AnimatePresence` is an immediate wrapper component around its children with an exiting animation.

The exit animation is triggered when `isVisible` becomes `false`. Theoretically, `<motion.div>` should have been removed from the React tree - yet logically it doesn't make sense, since at the point of its "removal", `<motion.div>` is still performing its exit animation, so that means it still is somehow within the DOM!

Here's where `<AnimatePresence>` does something sneaky.

## The secret sauce: `React.useRef`

Did someone say "give me a tool that reliably stores existing state during re-renders *and* does not cause a component re-render when its state is updated"? `React.useRef` does just that. 

We also want to be able to control when exactly children within `AnimatePresence` re-render to minimize unnecessary overhead, so choosing `useRef` instead of `useState` comes in handy here.

With that in mind, here's how framer-motion implemented `AnimatePresence`:

Imagine there's reality and alternate reality. Picture React's version of the DOM tree as reality, and framer-motion's version as alternate reality. Because we want to enhance our React codebase with exiting animations, let's call this 'alternate reality' solely for the purpose of this article. 'Alternate reality' is what we want to show to users of our app, or whatever we're building, so that they see the fancy-schmancy version instead of the dull, old vanilla version of things.

Two states comes into play in our alternate reality:
1. `currentChildren`: elements that are in the React tree - our source of truth
2. `allChildren`: elements that are in the React tree (i.e. `currentChildren`) + elements that are *exiting* the DOM

Suppose that we have `Child1` and `Child2` wrapped within `AnimatePresence`, and none of them are exiting the DOM yet. Here's what the above two states like would look in framer-motion:

![[Pasted image 20240107022517.png]]

Next, imagine if `Child2` needs to be removed and we need to trigger its exit animation.

React updates `currentChildren` once `Child2` is removed, showing that only `Child1` remains. From this, we can derive a third state: `exitingChildren`, which takes the difference between `allChildren` and `currentChildren`.

This third state, `exitingChildren`, is crucial. Firstly, we want to trigger the exit animations once an element is registered as 'exiting'. Secondly, we want to ensure that this particular element is deleted from `AnimatePresence` so that we don't keep unnecessary references to elements that don't exist in the React tree.

![[Pasted image 20240107023848.png]]

This is what the final state looks like after `Child2` has completely exited the DOM: `AnimatePresence` does not maintain a trace to it anymore.

![[Pasted image 20240107024447.png]]

So there you have it - it's a bit of React trickery behind the scenes! The framer-motion state names have been altered for the purposes of this article, but this distills the essence of how `AnimatePresence` works.

P.s. while reading the implementation of `AnimatePresence`, I've noticed [a bug which caused some components to not exit in sequence](https://github.com/framer/motion/issues/2462). The [PR](https://github.com/framer/motion/pull/2477) for fixing this has been submitted and is awaiting review.

[^declarative-vs-imperative]: [What is the difference between declarative and imperative paradigm in programming?](https://stackoverflow.com/questions/1784664/what-is-the-difference-between-declarative-and-imperative-paradigm-in-programmin)
[^motion-docs]: [AnimatePresence in Motion docs](https://www.framer.com/motion/animate-presence/)