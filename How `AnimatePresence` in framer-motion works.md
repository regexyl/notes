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
	1. My guess: It mutates the child component