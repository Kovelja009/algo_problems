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
  - [Graphs - DFS](#graphs---dfs)
  - [Heap / Priority Queue](#heap--priority-queue)
  - [Binary Search](#binary-search)
  - [Backtracking](#backtracking)
  - [Dynamic Programming (1D)](#dynamic-programming-1d)
  - [Dynamic Programming (2D)](#dynamic-programming-2d)
  - [Bit Manipulation](#bit-manipulation)
  - [Trie](#trie)
  - [Intervals](#intervals)
  - [Monotonic Stack](#monotonic-stack)
- [Top Interview 150 🍜](top-interview-150-)
  - [Array/String](#arraystring)
- [Microsoft 🏮](microsoft-)


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
  
  🟡 medium: 20
  
  🔴 hard: 0
  </td>
  </tr>
</table>

## **Graphs - DFS**

### [399. Evaluate Division](https://leetcode.com/problems/evaluate-division/)

Notes:
- build a graph with the given equations and values
  ```        
  for (A, B), value in zip(equations, values):
            graph[A][B] = value
            graph[B][A] = 1 / value```
- after that, just use BFS (lol) betwen start and end of the query, if the path exists, thats the solution


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
### [714. Best Time to Buy and Sell Stock with Transaction Fee](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-transaction-fee/)

Notes:
- different that the standard dp problem
- we initialize `cash = 0` and `stock = -prices[0]` because we can buy the stock at the first day
- for each day, we can either sell  the stock `cash=max(cash, stock + stocks[i] - fee)` or buy the new stock `stock=max(stock, cash - stocks[i])`

---
### [72. Edit Distance](https://leetcode.com/problems/edit-distance/)

Notes:
- similar to the problem from Speech Recognition course (***Dynamic Time Warping***)
- initialize the dp matrix with the size of `len(word1)+1` and `len(word2)+1`
- cover base cases: when one of the words is `empty`, the distance is the length of the other word
- formula is:
    - if the characters are the same, `dp[i][j] = dp[i-1][j-1]`
    - else the characters are different, `dp[i][j] = min(dp[i-1][j-1], dp[i-1][j], dp[i][j-1]) + 1`

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

  <br>

 
<img src="https://github.com/Kovelja009/algo_problems/assets/81018289/f41ee5cb-0931-47fc-8071-e62ff590bfc9" alt="LeetCode 75" width="1500" />

  </br>

  ---
  
<table>
  <tr>

  <td>

  <img src="https://github.com/Kovelja009/algo_problems/assets/81018289/110ed354-3a02-46ac-af6a-0f58f4332fef" alt="LeetCode 150" width="250" />

  </td>
  <td align="left">

  # Top Interview 150 🍜 
  🟢 easy: 5
  
  🟡 medium: 5
  
  🔴 hard: 0

  </td>
  </tr>
</table>

## Array/String
---
### [88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/)

Notes:
- interesting approach where we start from the end
and we have `k=m+n-1`, `i=m-1` and `j=n-1`
- why from the end -> because we don't need to insert anything just replace the values

---
### [27. Remove Element](https://leetcode.com/problems/remove-element/)

Notes:
- idea is to use two pointers, one for the current element and one for the last element that is not `val`

---
### [26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

Notes:
- again two pointers approach, one for the current element and one for the first element that greater than current

---
### [80. Remove Duplicates from Sorted Array II](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/)

Notes:
- two pointers but interesting approack where we start for loop with `i` from the second element and `curr=2` and only update if `nums[i] != nums[curr-2]` 

---
### [169. Majority Element](https://leetcode.com/problems/majority-element/)
  
Notes:
- simple use of hash table -> Space complexity O(n)- Boyer-Moore Voting Algorithm can be used to reduce the space complexity to O(1)

---
### [189. Rotate Array](https://leetcode.com/problems/rotate-array/)
- Notes:
  1. Solution 1 (using extra space O(n)):
    - create a new array `temp`
    - do the `k = k%size` to avoid index out of range
    - then copy elements starting from index `start=size-k` to the end
    - then copy elements from the `0` to the `start`
    - then copy the `temp` to the `nums`
  2. Solution 2 (Using O(1) space):
    - reverse the whole array
    - reverse the first `k` elements
    - reverse the last `n-k` elements

---
### [121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)
  
Notes:
- simple approach where we keep track of the minimum price up to this moment and based on that we save the maximum profit

---
### [122. Best Time to Buy and Sell Stock II](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

Notes:
- we add the profit if the price is greater than the previous one :(


---
### [55. Jump Game](https://leetcode.com/problems/jump-game/)

Notes:
- at each step, we update the maximum reachable index
- and then check whether we can reach current index with the maximum reachable index
  
---
### [45. Jump Game II](https://leetcode.com/problems/jump-game-ii/)

Notes:
- we keep track of the furthest we can jump
- when `i` reaches `current end` we update the `current end` with the `farthest` and increment the `jumps` 


  
  <br>
  <img src="https://github.com/Kovelja009/algo_problems/assets/81018289/14bf71c7-96c0-453e-8d9e-4cf097b9cc90" alt="LeetCode 150" width="1500" />

  </br>



  ---
<table>
  <tr>

  <td>

  <img src="https://github.com/Kovelja009/algo_problems/assets/81018289/0b343040-d2e2-4393-9cc5-db3d2c88f33c" alt="LeetCode 150" width="250" />

  </td>
  <td align="left">

  
  # Microsoft 🏮 
  🟢 easy: 0
  
  🟡 medium: 0
  
  🔴 hard: 0

  </td>
  </tr>
</table>


