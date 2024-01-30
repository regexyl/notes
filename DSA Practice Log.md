Legend
🔴 Pretty hard, it'll be awesome if I could come up with the solution on the spot
🟠 Needed help, try again
🦠 Solved, but not on first try + had no help
🟢 Solved on first try (⚾️ knocked it out of the park!)

🔁 Repeat attempt
⏳ Not the best time complexity
🏃‍♀️ Not fast enough

30 Jan 2024, Tues

Today's structure
- Stop after every 4 questions, if you don't know the answer to it, write down your best solution and explain what you can't figure out before moving on

- [ ] Solidify binary search concepts (obliterate 8 different binary search questions - outside of the ones attempted already -> 2 easy, 3 medium, 3 hard) - <mark style="background: #FFB86CA6;">**hopefully by 5pm?**</mark>
	- [x] Read this binary search [guide](https://leetcode.com/discuss/study-guide/1233854/a-noobs-guide-to-the-binary-search-algorithm)
		- [x] I think the guide was pretty okay, it highlighted the reasons why solutions to specific questions were coded that way, but it still lacked a little pattern-grouping information for me. But the best way to learn about this is to not get spoon-fed :)
	- [x] [Closest Binary Search Tree Value](https://leetcode.com/problems/closest-binary-search-tree-value) 🦠 (5 min 56 sec)
	- [x] [Search a 2D Matrix II](https://leetcode.com/problems/search-a-2d-matrix-ii) 🟠
		- The solution with the best time complexity here is a non-binary search solution.
	- [x] [Russian Doll Envelopes](https://leetcode.com/problems/russian-doll-envelopes/) 🔴
		- This is slightly hard - I think I'm not able to tell apart DP problems from a binary search solution in this case
		- You could technically do a 0/1 knapsack solution here
	- [x] [Heaters](https://leetcode.com/problems/heaters) 🟠
		- It was hard for me to see this as a binary search question on first glance. I see it now!
		- Though like Russian dolls, it can be solved in a faster time complexity without binary search.
	- [x] [Count of Smaller Numbers After Self](https://leetcode.com/problems/count-of-smaller-numbers-after-self) 🟢⚾️
		- Used `SortedList` and knocked this out of the park!
		- #todo Warning: there's a possibility `sortedcontainers` might be disallowed in an interview. [[Segment Tree]] and [[Binary Indexed Tree]] might come in handy here. See the [Leetcode editorial](https://leetcode.com/problems/count-of-smaller-numbers-after-self/editorial/).
- [ ] Figure out how to sort an array by two distinct keys
	- [ ] [H-Index II](https://leetcode.com/problems/h-index-ii)
	- [ ] [Fair Candy Swap](https://leetcode.com/problems/fair-candy-swap)
	- [ ] [Numbers At Most N Given Digit Set](https://leetcode.com/problems/numbers-at-most-n-given-digit-set)
- [ ] Solidify DP concepts (obliterate 16 different DP questions)
      7 hard, 9 medium, 1 easy
	- [ ] If there's time, watch the MIT video on [Dynamic Programming](https://www.youtube.com/watch?v=krZI60lKPek&t=7s)
	- [ ] [Perfect Squares](https://leetcode.com/problems/perfect-squares)
	- [ ] [Best Time to Buy and Sell Stock IV](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iv)
	- [ ] [Shopping Offers](https://leetcode.com/problems/shopping-offers)
	- [ ] [Super Ugly Number](https://leetcode.com/problems/super-ugly-number)
	- [ ] [Palindrome Partitioning II](https://leetcode.com/problems/palindrome-partitioning-ii)
	- [ ] [Paint Fence](https://leetcode.com/problems/paint-fence)
	- [ ] [Divisor Game](https://leetcode.com/problems/divisor-game)
	- [ ] [Paint House II](https://leetcode.com/problems/paint-house-ii)
	- [ ] [Encode String with Shortest Length](https://leetcode.com/problems/encode-string-with-shortest-length)
	- [ ] [Unique Substrings in Wraparound String](https://leetcode.com/problems/unique-substrings-in-wraparound-string)
	- [ ] [Matchsticks to Square](https://leetcode.com/problems/matchsticks-to-square)
	- [ ] [Find the Derangement of An Array](https://leetcode.com/problems/find-the-derangement-of-an-array)
	- [ ] [Coin Path](https://leetcode.com/problems/coin-path)
	- [ ] [Number of Longest Increasing Subsequence](https://leetcode.com/problems/number-of-longest-increasing-subsequence)
	- [ ] [Last Stone Weight II](https://leetcode.com/problems/last-stone-weight-ii)
	- [ ] [Strange Printer](https://leetcode.com/problems/strange-printer)
	- [ ] [Kth Ancestor of a Tree Node](https://leetcode.com/problems/kth-ancestor-of-a-tree-node)
	- [ ]
- [ ] Go back to the binary search questions, starting with Find Minimum in Rotated Sorted Array - check out the editorial discussion on the different ways to solve it (some comments in the discussion mention that the editorial's solution isn't the most straightforward)
- [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)
- [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)

29 Jan 2024, Mon
- [Count Elements With Maximum Frequency](https://leetcode.com/problems/count-elements-with-maximum-frequency/) 🟢⚾️
- [Find Beautiful Indices in the Given Array I](https://leetcode.com/problems/find-beautiful-indices-in-the-given-array-i/)  #array 🟠
- [Maximum Number That Sum of the Prices Is Less Than or Equal to K](https://leetcode.com/problems/maximum-number-that-sum-of-the-prices-is-less-than-or-equal-to-k/) 🔴
	- #todo Come back to this later
- [[(dsa) Median of Two Sorted Arrays]] 🔴
	- #todo Come back to this later
- [Encode and Decode Strings](https://leetcode.com/problems/encode-and-decode-strings/) 🟢
- [Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/) 🟠
- [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) 🟠

28 Jan 2024, Sun
1st hour
- [Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/) 🟠
- [Number of Submatrices That Sum to Target](https://leetcode.com/problems/number-of-submatrices-that-sum-to-target/) 🟠
- [Valid Sudoku](https://leetcode.com/problems/valid-sudoku/) 🟢⚾️
- [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/) 🟠
	- I remembered the initial 2-pass trick, but that was also what hindered me from solving - I was obsessed on thinking of ways to make it work with just two for loops (1 forward, and 1 backward), but forgot about the `multiplier` variable that should be used.
2nd hour
- [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) 🟢⚾️
- Read up about [[Quicksort]]
- [Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/)
- [Pseudo-Palindromic Paths in a Binary Tree](https://leetcode.com/problems/pseudo-palindromic-paths-in-a-binary-tree/)

27 Jan 2024, Sat
Break for 10 min at every hour (1, 2, 3pm)
- [Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/) 🟠
- [Carried forward from 25 Jan] DONE: Revise [solution](https://leetcode.com/problems/minimum-window-substring/submissions/899091668/) 🟠
- Break (end: 1:27pm)
- [Stickers to Spell Word](https://leetcode.com/problems/stickers-to-spell-word/) - Revised solution 🔴
- Break (end: 2:20pm)
- Any 3 of the 4 questions:
- [Valid Word Abbreviation](https://leetcode.com/problems/valid-word-abbreviation/) 🦠🔁
- [Random Pick with Weight](https://leetcode.com/problems/random-pick-with-weight/) 🟢🔁
- [Basic Calculator II](https://leetcode.com/problems/basic-calculator-ii/) 🟢⏳
- [Moving Average from Data Stream](https://leetcode.com/problems/moving-average-from-data-stream/) 🟢
- Break (start: 3:20pm)
- [Edit Distance](https://leetcode.com/problems/edit-distance/) 🟠
- [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/) 🟠
- [Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/) 🟢⚾️
- [Lowest Common Ancestor of a Binary Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/) 🟠
- [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/) 🟠
- Break (start: 8:15pm)

26 Jan 2024, Fri
1:30-6pm (break: 4-4:30pm)
- [Valid Word Abbreviation](https://leetcode.com/problems/valid-word-abbreviation/) 🟠 (end: 2:18pm - had a 20 minute break with Shannon/Xinai)
- Coffee break: start: 2:27pm, end: 2:41pm
- [Binary Tree Vertical Order Traversal](https://leetcode.com/problems/binary-tree-vertical-order-traversal/) 🟢 (end: 2:51pm)
- Break (call with Chinmito): 4:10pm
- [Minimum Remove to Make Valid Parentheses](https://leetcode.com/problems/minimum-remove-to-make-valid-parentheses/) 🟢 (end: 4:30pm)
	- Easy medium
- [Nested List Weight Sum](https://leetcode.com/problems/nested-list-weight-sum/) 🟢 (end: 4:41pm)
	- Easy medium
- [Buildings With an Ocean View](https://leetcode.com/problems/buildings-with-an-ocean-view/) (end: 4:46pm)
	- Easy medium
- Break (start: 4:54pm, end 5:11pm)
- [Random Pick with Weight](https://leetcode.com/problems/random-pick-with-weight/) 🟠 (end: 5:12pm)
- Break (end: 5:29pm)
- [Stickers to Spell Word](https://leetcode.com/problems/stickers-to-spell-word/) 🟠
- Walking exercise + shower

25 Jan 2024, Thu
- [Permutation in String](https://leetcode.com/problems/permutation-in-string/) #sliding-window 🟢⚾️
- [Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/) 🟠 (end: 9:42pm)
- [Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/) 🟠 (end - kinda: 10:37pm) - Read a straightforward solution but I need to distill it further
	- TODO: Revise [solution](https://leetcode.com/problems/minimum-window-substring/submissions/899091668/)
- Break (end 12:14am - had dinner and showered)
- [Walls and Gates](https://leetcode.com/problems/walls-and-gates/) #bfs 🟠 (end: 12:22am)
- [Lowest Common Ancestor of a Binary Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/) #dfs 🟠 (end: 12:53am)
- [Binary Tree Right Side View](https://leetcode.com/problems/binary-tree-right-side-view/) #bfs (end: 1:15am)
- [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/)
- strike 1! (no attempt on walls and gates) + strike 2! (could not do LCA of a binary tree) + strike 3! (Binary Tree Right Side View - kinda got the gist of a dfs pattern, but this problem was inherently bfs - plus, I didn't manage to solve it via DFS) + strike 4 (Koko Eating Bananas :')
- Summarize on canvas

24 Jan 2024, Wed
- [Pseudo-Palindromic Paths in a Binary Tree](https://leetcode.com/problems/pseudo-palindromic-paths-in-a-binary-tree/) #dfs 🟠
- [Merge Intervals](https://leetcode.com/problems/merge-intervals/) #intervals 🟢⚾️
- Follow-up to Merge Intervals
	- ![[Pasted image 20240124191337.png]]
	- 
- [Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/) #intervals 🟢
- [Hand of Straights](https://leetcode.com/problems/hand-of-straights/) #greedy 🟢