What I want to find out:

Can two components exist at the same time - one exiting and one entering, even if the JSX shows only one component existing at any single time?:
```tsx
export const Slideshow = ({ image }) => (
  <AnimatePresence>
    <motion.img
      key={image.src}
      src={image.src}
      initial={{ x: 300, opacity: 0 }}
      animate={{ x: 0, opacity: 1 }}
      exit={{ x: -300, opacity: 0 }}
    />
  </AnimatePresence>
)
```

This video shows that it can. Drag your cursor to a point where you can see both the '1st slide' and '2nd slide' within the container (they should have a gray gap in the middle).

![[FramerMotionSlideShow.mov]]

Though the video above show [it's possible for a single child](https://www.framer.com/motion/animate-presence/##exit-animations). Is it possible for multiple children?

1. How does framer-motion know when a child component is unmounted?
	1. My guess: It mutates the child component by injecting a return function in a `useEffect` - but this is not possible? Or is it?
2. How does `usePresence` come into play here? Is there a way to structure `usePresence` so that the user does not have to insert this block of code in the component that uses this hook?
```ts
export const Component = () => {
  const [isPresent, safeToRemove] = usePresence()
  
  useEffect(() => {
    !isPresent && setTimeout(safeToRemove, 1000)
  }, [isPresent])

  return <div />
}
```
3. What is the `mode` prop?
4. `allChildren` vs `existingChildren` vs `presentChildren`:
	1. `allChildren`: basically a map of a key to each individual `filteredChildren`
	2. `presentChildren`: basically either (1) `childrenToRender`, which is also `filteredChildren`, or (2) a *filtered* `filteredChildren` (i.e. a filter layer on top of `filteredChildren`) that only includes *visible* children

### Framer motion internals

What's frameloop?
- `createRenderBatcher` - Takes in a callback (which in turn takes in a callback that's defined within this util function)

Parked questions:
- Where is `Step`'s `.process` util defined? (as seen in batcher.ts L. 33?)