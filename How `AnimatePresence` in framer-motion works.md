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

This video shows that it can:
![[FramerMotionSlideShow.mov]]