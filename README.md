# Table of Contents ⛩️

<table>
  <tr>
    <td>
<div align="left">
  
  ![giphy](https://github.com/Kovelja009/algo_problems/assets/81018289/1ccbb146-bb6e-45a4-a501-e0676c78dd86)
</div>
    </td>
    <td>

- [LeetCode 75 🌸](#leetcode-75-) 
  1. [Heap / Priority Queue](#heap--priority-queue)
  2. [Binary Search](#binary-search)
  3. [Backtracking](#backtracking)
  4. [Dynamic Programming (1D)](#dynamic-programming-1d)
  5. [Dynamic Programming (2D)](#dynamic-programming-2d)
  6. [Bit Manipulation](#bit-manipulation)
  7. [Trie](#trie)
  8. [Intervals](#intervals)
  9. [Monotonic Stack](#monotonic-stack)


</table>


---
      
<table>
  <tr>
    <td>

  <img src="https://github.com/Kovelja009/algo_problems/assets/81018289/f57c47cc-2425-4d57-bda7-4f07d6164743" alt="LeetCode 75" width="250" />

  </td>
  <td align="left">

  # LeetCode 75 🌸 
  🟢 easy: 0
  
  🟡 medium: 17
  
  🔴 hard: 0
  </td>
  </tr>
</table>



---

## **Heap / Priority Queue**

### [2542. Maximum Subsequence Score](https://leetcode.com/problems/maximum-subsequence-score/)

Notes:

- firstly indeces don't need to be consecutive
- we can sort first and second array in descending order by second array
- then we keep adding elements from the first array to the priority queue
- if we have more than `k` elements in the priority queue we can remove the smallest one *(we don't need to pay attention to the order because we now for sure that anything removed from `pq` is index in the second array of the thing greater than the current element and we need smallest one anyway)*
- and when we have `k` elements we can check the result

---
### [2462. Total Cost to Hire K Workers](https://leetcode.com/problems/total-cost-to-hire-k-workers/)

Notes:

- we need to know the minimum on the left and right part in any given moment so we need 2 priority queues(`left` and `right`)
- also we need to pay attention that 2 given `pqs` are **not overlapping**

---
## **Binary Search**
### [2300. Successful Pairs of Spells and Potions](https://leetcode.com/problems/successful-pairs-of-spells-and-potions/)

Notes:

- we first sort `potions` in ascending order
- then for each `spell` we find the smallest potion that satisfies the `success` condition, after that we can just subtract the index of the potion from the length of the `potions` array
- we can do this by using **binary search**

---
### [162. Find Peak Element](https://leetcode.com/problems/find-peak-element/)

Notes:
- just standard binary search
- we look for the element that has both neighbours smaller than itself
- if either of the neighbours is greater than the current element we move to the greater neighbour

---
### [875. Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/)

Notes:
- we can use binary search where lower limit is 1 and upper limit is the maximum number of bananas
- and we can check if the current number of bananas is enough to eat all the bananas in `piles` for <= `H` 

---
## **Backtracking**
### [17. Letter Combinations of a Phone Number](https://leetcode.com/problems/letter-combinations-of-a-phone-number/)
  
Notes:
- we can make backtracking function that takes the current string and the index of the current digit
- if the `index` == `len(digits)` we can add the current string to the result
- for each digit we call `backtrack` function with the current string + the current letter from the digit and the next index

---
### [216. Combination Sum III](https://leetcode.com/problems/combination-sum-iii/)

Notes:
- we can make backtracking function that takes starting number and array of current numbers
- if the sum of the current numbers is equal to `k` we can add the current numbers to the result
- for each number from `start` to 9 we call the `backtrack` function where we add 'i' to the current numbers and 'i+1' is next start and after calling 'backtrack' we remove the last element from the current numbers

---
## **Dynamic Programming (1D)**
### [198. House Robber](https://leetcode.com/problems/house-robber/)

Notes:

- classic dp problem where formula is `dp[i] = max(nums[i] + dp[i-2], dp[i-1])`
- Space optimized version where we only need 2 variables to keep track of the previous 2 values and not whole dp array

---
### [790. Domino and Tromino Tiling](https://leetcode.com/problems/domino-and-tromino-tiling/)

Notes:
- when trying to figure out formula you can just run different testcases and see the result, so you can find the pattern
- here pattern was `dp[i] = dp[i-1]*2 + dp[i-3]`
- Space optimized version where we only need 3 variables

---
## **Dynamic Programming (2D)**
### [62. Unique Paths](https://leetcode.com/problems/unique-paths/)

Notes:
- how to know that this is dp problem? - we can see that robot can only move right and down, if it wasn't the case we would have to use something else (e.g. backtracking)
- formula is `dp[i][j] = dp[i-1][j] + dp[i][j-1]` where `dp[0][0] = 1`

---
### [1143. Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/)

Notes:
- classic dp problem where formula is `dp[i][j] = dp[i-1][j-1] + 1` if `text1[i] == text2[j]` otherwise `dp[i][j] = max(dp[i-1][j], dp[i][j-1])`

---
## **Bit Manipulation**
### [1318. Minimum Flips to Make a OR b Equal to c](https://leetcode.com/problems/minimum-flips-to-make-a-or-b-equal-to-c/)

Notes:
- by doing `(a | b)` we can see the result of joining the bits of a and b. So we can then do `mask = result ^ c` to see the bits that are different from ``c`` (they need to be changed)
- also we do `mask & a & b` because if `c` is 0 and we have 1 in `a` and `b` we need to change them to 0 (both)

---
## **Trie**
### [1268. Search Suggestions System](https://leetcode.com/problems/search-suggestions-system/)
  
Notes:
- just the idea to use trie to store the words and then for each prefix we can find the words that start with that prefix
  
---
## **Intervals**
### [435. Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/)

Notes:
- we can sort intervals by first interval, and we have marker the end of first interval
- we increase the counter if the beginning of the next interval is greater than or equal to the marker and we update the marker `marker=max(marker, end)`
- otherwise we just update the marker: `marker=min(marker, end)`
- inspiration drawn from course `DAA :)`

---
### [452. Minimum Number of Arrows to Burst Balloons](https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/)

Notes:
- sort intervals by the end (ascending)
- then if the start is different then `curr_end` just increase counte by 1 and update `curr_end` to the end of the current interval
- again `DAA :)`

---
## **Monotonic Stack**
### [739. Daily Temperatures](https://leetcode.com/problems/daily-temperatures/)

Notes:
- initialize `ans` array with zeros
- push the index of the first element to the stack
- for each temperature:
  1. while temperature is greater than the temperature of the element on the top of the stack we can update the `ans` array with `ans = i - stack.top()`and pop the element from the stack
  2. add `i` to the stack
- then at the end all the remaining elements on the stack should have zero (which they do because of the initialization)

---
### [901. Online Stock Span](https://leetcode.com/problems/online-stock-span/)

Notes:
- initilize stack
- while `price` is higher than what is on the `top of the stack` we can **pop** the elements and add the `span` of that popped element to the `ans`
- once finished `ans += 1` (because current day is also counted)
- then just push `(price, ans)` to the stack
- and return `ans`
