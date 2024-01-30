---
tags:
  - math
---
The phrase "loss of generality" is often used in mathematics and related fields, typically in the context of "without loss of generality" (often abbreviated as **WLOG**). This phrase is used when making an argument or performing a demonstration to indicate that the specific choice of objects or the particular case being considered doesn't restrict the generality of the argument or proof. In other words, the conclusion drawn from this specific case will be valid for all relevant cases.

Using "without loss of generality" is a way to simplify the problem or proof while ensuring that the conclusions drawn are still universally applicable. It's a kind of logical shortcut, avoiding the need to separately prove each case when the outcomes will be essentially the same. However, it's important to use this phrase correctly — it's only appropriate when the cases you're omitting are truly equivalent to the ones you're addressing in your argument.

## Example

The literal meaning is when you rephrase a general statement:
> $𝑃(𝑥)$ is true for all $𝑥∈𝑆$

using another set (which is easier to work with):
> $𝑃(𝑧)$ is true for all $𝑧∈𝑇$,

where $𝑃$ is some property of elements in $𝑆$ and 𝑇, and it can be shown (or is known) that $𝑆=𝑇$.

**An example of proving WLOG:**
We want to show that $𝑃(𝑥)$ is true for all $𝑥∈ℤ$.[^2] Without loss of generality, we can assume that $𝑥=𝑧+1$ for some $𝑧∈ℤ$. In this case, $𝑆=ℤ$ and $𝑇=\{𝑧+1:𝑧∈ℤ\}.$[^1]

[^1]: [Use of "without loss of generality"](https://math.stackexchange.com/questions/129137/use-of-without-loss-of-generality)
[^2]: [[(math) ℤ]]