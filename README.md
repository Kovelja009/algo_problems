# Table of Contents ⛩️

<table>
  <tr>
    <td>
      <div align="left">
        <img src="https://github.com/Kovelja009/algo_problems/assets/81018289/1ccbb146-bb6e-45a4-a501-e0676c78dd86" alt="giphy">
      </div>
    </td>
    <td style="vertical-align: top; text-align: center;">
      <div align="left">
        <strong><a href="#leetcode-75-">LeetCode 75 🌸</a></strong>
        <ul>
          <li><a href="#graphs---dfs">Graphs - DFS</a></li>
          <li><a href="#heap--priority-queue">Heap / Priority Queue</a></li>
          <li><a href="#binary-search">Binary Search</a></li>
          <li><a href="#backtracking">Backtracking</a></li>
          <li><a href="#dynamic-programming-1d">Dynamic Programming (1D)</a></li>
          <li><a href="#dynamic-programming-2d">Dynamic Programming (2D)</a></li>
          <li><a href="#bit-manipulation">Bit Manipulation</a></li>
          <li><a href="#trie">Trie</a></li>
          <li><a href="#intervals">Intervals</a></li>
          <li><a href="#monotonic-stack">Monotonic Stack</a></li>
        </ul>
      </div>
    </td>
    <td style="vertical-align: top; text-align: center;">
      <div align="left">
        <strong><a href="#top-interview-150-">Top Interview 150 🍜</a></strong>
        <ul>
          <li><a href="#arraystring">Array/String</a></li>
          <li><a href="#two-pointers">Two Pointers</a></li>
          <li><a href="#hash-map">Hash Map</a></li>
          <li><a href="#intervals-1">Intervals</a></li>
          <li><a href="#stack">Stack</a></li>
          <li><a href="#linked-list">Linked List</a></li>
          <li><a href="#binary-tree-general">Binary Tree General</a></li>
          <li><a href="#binary-tree-bfs">Binary Tree BFS</a></li>
          <li><a href="#binary-search-tree">Binary Search Tree</a></li>
          <li><a href="#graph-general">Graph General</a></li>
          <li><a href="#graph-bfs">Graph BFS</a></li>
          <li><a href="#trie-1">Trie</a></li>
          <li><a href="#binary-search-1">Binary Search</a></li>
          <li><a href="#backtracking-1">Backtracking</a></li>
          <li><a href="#bit-manipulation-1">Bit Manipulation</a></li>
          <li><a href="#divide--conquer">Divide & Conquer</a></li>
          <li><a href="#kadanes-algorithm">Kadane's Algorithm</a></li>
          <li><a href="#math">Math</a></li>
          <li><a href="#1d-dp">1D DP</a></li>
          <li><a href="#2d-dp">2D DP</a></li>
          <li><a href="#heap">Heap</a></li>
        </ul>
      </div>
    </td>
    <td style="vertical-align: top; text-align: center;">
      <div align="left">
        <strong><a href="#microsoft-">Microsoft 🏮</a></strong>
        <ul>
          <li><a href="#-easy">🟢 Easy</a></li>
          <li><a href="#-medium">🟡 Medium</a></li>
          <li><a href="#-hard">🔴 Hard</a></li>
        </ul>
      </div>
    </td>
  </tr>
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
  🟢 easy: 30
  
  🟡 medium: 61
  
  🔴 hard: 1

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

---
### [274. H-Index](https://leetcode.com/problems/h-index/)

Notes:
- sort the array in descending order
- then for each element we do `maxi=max(maxi, min(i+1, citations[i]))` because we know for sure that the number of citations is `i+1`
- can be done in `O(n)` time complexity if we use `counting sort`, because maximum number of citations is `1000`

---
### [58. Length of Last Word](https://leetcode.com/problems/length-of-last-word/)

Notes:
- Hard work betrays none, but dreams betray many.

---
### [14. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)

Notes:
- just find the len of the shortest string
- then for each character in the shortest string we check whether all the strings have the same character at that index
- if not we return the prefix
- otherwise we append the character to the prefix

---
### [238. Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)

Notes:
1. `O(n)` time complexity and `O(n)` space complexity
    - we can make two arrays `left` and `right` to make prefix and sufix products and then `ans[i] = left[i] * right[i+1]`
2. `O(n)` time complexity and `O(1)` space complexity
    - we can use the `output` array to store the prefix products and then multiply it with the `right` variable that stores the sufix product by going from the end after we have calculated the prefix product :)

---
### [134. Gas Station](https://leetcode.com/problems/gas-station/)

Notes:
- problem from the **Algorithms** course `:)`
- if `sum(gas) < sum(cost)` we can't make the full circle so return `-1`
- otherwise we can start from the first station and keep track of `curr_fuel` and `start_idx`
- if after adding the gas `cur_fuel += gas[i] - cost[i]` we can't make it to the next station we update the `start_idx` to the next station and reset the `curr_fuel = 0` because we know that we can't start from the any of the stations between previous `start_idx` and `i`

---
### [12. Integer to Roman](https://leetcode.com/problems/integer-to-roman/)

Notes:
- we can just go through the `values` and `symbols` and add the symbols to the result as long as the number is greater than the value

---
### [6. Zigzag Conversion](https://leetcode.com/problems/zigzag-conversion/)

Notes:
- we can start from the first row and go down until we reach the last row and then go up until we reach the first row
- we can use the `direction` flag to know whether we are going up or down
- we can use the `row` to keep track of the current row
- we can use the `rows` array to store the characters for each row
- and then we can just join the characters from the `rows` array

---
### [28. Find the Index of the First Occurrence in a String](https://leetcode.com/problems/implement-strstr/)

Notes:
- just go through the string and check whether the substring is equal to the needle for each index, you can stop if `len(haystack)  - len(needle) < i`

---
## Two Pointers
---
### [125. Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)

Notes:
- we can just reverse the string and compare it with the original string
  
---
### [392. Is Subsequence](https://leetcode.com/problems/is-subsequence/)

Notes:
- we can have `s_pointer` which increases if `s[s_pointer] == t[i]` and if `s_pointer == len(s)` we can return `True`, otherwise we return `False`

---
### [167. Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

Notes:
- we can use two pointers, one for the beginning and one for the end
- if the sum is greater than the target we decrement the `end` pointer, if the sum is less than the target we increment the `start` pointer, otherwise we return the indices
- not completely sure why this works, but it does `:-)`

---
### [11. Container With Most Water](https://leetcode.com/problems/container-with-most-water/)

Notes:
- we can use two pointers, one for the beginning and one for the end
- we can calculate the area and update the maximum area
- area is calculated as `min(height[i], height[j]) * (j-i)`
- then we can move the pointer that has the smaller height

---
### [209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)

Notes:
- we can use two pointers, iterate through the array with `right` pointer and keep track of the sum
- for each `right` pointer we increment the `sum` and while `sum >= target` we update the `min_len` and decrement the `sum` and increment the `left` pointer

---
### [3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

Notes:
- we increase the window until the character is repeated
- we know that the character is repeated because we store it in the `hash map`
- then we increase the `left` pointer until we remove the repeating character from the `hash map`

---
## Matrix
---
### [36. Valid Sudoku](https://leetcode.com/problems/valid-sudoku/)
Notes:
- we can use `hash map` to store the values of the rows, columns and the 3x3 squares
- we can use the formula `box_index = (i // 3) * 3 + j // 3` to get the index of the 3x3 square
- then we can just check whether the value is already in the `hash map`
- if it is we return `False`, otherwise we add the value to the `hash map`

---
### [73. Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/)

Notes:
1. Solution using `O(m+n)` space complexity:
    - we can use two sets `rows` and `columns` to store the indices of the rows and columns that need to be set to zero
    - then we can just go through the matrix and add the indices to the sets
    - after that we can just go through the matrix and set the rows and columns to zero
2. Solution using `O(1)` space complexity:
    - we can use the first row and the first column to store the information about the rows and columns that need to be set to zero
    - we can use two flags `first_row` and `first_column` to store the information about the first row and the first column
    - then we can just go through the inner part of the matrix and set the first row and the first column to zero
    - after that we can just go through the matrix and set the rows and columns to zero
    - if the `first_row` is `True` we can set the first row to zero and if the `first_column` is `True` we can set the first column to zero

---
### [289. Game of Life](https://leetcode.com/problems/game-of-life/)

Notes:
- for each cell we can count the number of live neighbours
- then we mark the cell with `-1` or `2` if it needs to change state
- then we can just go through the matrix and update the cells

---
### [48. Rotate Image](https://leetcode.com/problems/rotate-image/)

Notes:
- idea is to use some basic matrix transformations `:)`, in our case these are:
1. transpose the matrix
2. flip the matrix horizontally

---
## Hash Map
---
### [383. Ransom Note](https://leetcode.com/problems/ransom-note/) 

Notes:
- just put letters from `magazine` into `hashmap`

---
### [205. Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)

Notes:
- we can use two `hash maps` to store the mapping of the characters from the first string to the second string and vice versa
- if the mapping is not the same we return `False`

---
### [290. Word Pattern](https://leetcode.com/problems/word-pattern/)

Notes:
- can be done in the same way as the previous problem

---
### [242. Valid Anagram](https://leetcode.com/problems/valid-anagram/)

Notes:
- I'm not going there to die. I'm going to find out if I'm really alive.

---
### [1. Two Sum](https://leetcode.com/problems/two-sum/)

Notes:
- "Look at my eyes, Faye. One of them is a fake because I lost it in an accident. Since then, I've been seeing the past in one eye and the present in the other. So, I thought I could only see patches of reality, never the whole picture. I felt like I was watching a dream I could never wake up from. Before I knew it, the dream was over."

---
### [49. Group Anagrams](https://leetcode.com/problems/group-anagrams/)

Notes:
- we can sort every word and use it as a key in the `hash map` where value is the list of the words that are anagrams `:-)`

---
### [128. Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)

Notes:
- use 'hash map' to store all the elements, where the value is `1`
- for each element while there is by one smaller:
  - we increment the current `cnt` by the value of the current element, set to `0` value of that element 
- after while loop we update the `maxi` with the maximum of the current `cnt` and the `maxi`

---
### [202. Happy Number](https://leetcode.com/problems/happy-number/)

Notes:
- just build the number and if the number is already in the `hash map` we return `False`, otherwise we add the number to the `hash map`, and if we get to `1` we return `True`

---
### [219. Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)

Notes:
- we can use `hash map` to store the index of the element
- when we get to the element that is already in the `hash map` we can check whether the difference between the current index and the index in the `hash map` is less than or equal to `k`, if it is we return `True`, otherwise we update the index in the `hash map`

---
## Intervals
---
### [228. Summary Ranges](https://leetcode.com/problems/summary-ranges/)

Notes:
- we can use two pointers, one for the beginning and one for the end
- if the `curr != end+1` then we append it to the result and
reset `start = end = curr`

---
### [57. Insert Interval](https://leetcode.com/problems/insert-interval/)

Notes:
- while newInterval start is greater then the end of the current interval we can add the current interval to the result
- then we can merge the intervals: while the newInterval end is >= the start of the current interval we can update the newInterval start and end
- after that we can add the newInterval to the result and the rest of the intervals 
  
---
## Stack
---
### [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

Notes:
- we can use the stack to store the opening brackets
- then for each closing bracket we can check whether the stack is empty or the top of the stack is not the corresponding opening bracket
- if it is we return `False`, otherwise we pop the element from the stack
- at the end we return whether the stack is empty

---
### [71. Simplify Path](https://leetcode.com/problems/simplify-path/)

Notes:
- we can split the path by `/` and then for each element we can check whether it is `.` or `..` or empty
- if it is `..` we can pop the element from the stack, if it is `.` we can skip it, otherwise we can add it to the stack
- at the end we can join the elements from the stack with `/`

---
### [155. Min Stack](https://leetcode.com/problems/min-stack/)

Notes:
- very clever idea -> stack of tuples where the second element is the minimum element up to that point `:)`

---
### [150. Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/)

Notes:
- done it in the **Algorithms** course `:)`
- we can use the stack to store the numbers
- if it is the operator we can pop the last two numbers from the stack and apply the operator, after which we can push the result to the stack

---
## Linked List
---
### [138. Copy List with Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer/)

Notes:
1. Approach: using `hash map` -> `O(n)` space complexity
    - we can use the `hash map` to store the mapping of the original node to the new node
    - then we can just go through the original list and create the new list
    - after that we can just go through the original list and update the `next` and `random` pointers
2. Approach: interweaving lists -> `O(1)` space complexity
   - we can interweave the original list and the new list
   - then we can update the `random` pointers for the new list 
   - after that we can separate the original list and the new list

---
### [92. Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/)

Notes:
- we can use the `dummy` node to point to the `head` and then find the `left-1` node
- reverse the list from `left` to `right` in the function `reverse` where you also connect the `left.next` to the old `right.next` and then return value of the `new start` of the reversed list
- then connect the `left-1.next` to the `new start` and the `right` to the `old start`

---
### [19. Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

Notes:
1. Approach 1: two passes
     - reverse the list
     - remove the `n-th` element
     - reverse the list again
2. Approach 2: one pass
     - move right pointer `n` steps
     - move both pointers until the right pointer reaches the end
     - remove the `n-th` element

---
### [82. Remove Duplicates from Sorted List II](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/)

Notes:
- we can use the `dummy` node to point to the `head` 
- then we can use the `prev` node to keep track of the previous node
- `curr` node is `head`
- if `curr.val == curr.prev.val` or 'curr.val == curr.next.val' we set `curr.val = -101`
- then we can just go through the list and remove the nodes with the value `-101` 

---
### [141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)

Notes:
1. Approach:
   - just set `val` for each node to `maxsize` and if we come across the node with that value we return `True`, otherwise we return `False`
2. Approach:
   - other approach is to use two pointers, one that moves one step at a time and one that moves two steps at a time, if they meet we return `True`, otherwise we return `False`

---
### [61. Rotate List](https://leetcode.com/problems/rotate-list/)

Notes:
- count the length of the list
- `k = k % length`
- calc `moves = n - k`
- move the `curr` to the `moves` position
- set the `new_head` to the `curr.next` and set the `curr.next` to `None`
- then set the `tail.next` to the `head`

---
### [86. Partition List](https://leetcode.com/problems/partition-list/)

Notes:
- make two lists, one for the smaller elements and one for the greater elements
- then connect the tale of the smaller list to the head of the greater list

---
### [21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)

Notes:
- algo from the **Algorithms** course `:)`
- while both lists are not empty we compare the values of the nodes and connect the smaller one to the `curr` node
- while first list is not empty we connect the rest of the first list to the `curr` node
- while the second list is not empty we connect the rest of the second list to the `curr` node

---
### [2. Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)

Notes:
- while we have both lists we add the values of the nodes and the carry and connect the result to the `curr` node
- while we have the first list we add the values from the first list with the carry and connect the result to the `curr` node
- while we have the second list we add the values from the second list with the carry and connect the result to the `curr` node
- if we have the carry at the end we connect the carry to the `curr` node

---
## Binary Tree General
---
### [100. Same Tree](https://leetcode.com/problems/same-tree/)

Notes:
- we can use the `recursive` approach where we check whether the values of the nodes are the same and then we check the left and right subtrees
- also need to check whether both have some values
- and return `left and right`

---
### [105. Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)

Notes:
- we can use the `recursive` approach
- we pop first element from preorder as a `root` 
- then we find the index of the `root` in the inorder
- then we recursively call the function for the left and right subtrees where we pass the `preorder` normaly and `inorder` from the beginning to the index of the `root` for left subtree and from the index of the `root` to the end for the right subtree
- finding index of the `root` in the `inorder` can be done using the `hash map` where the key is the value and the value is the index so we reduce the time complexity from O(n^2^) to O(n)
  
---
### [106. Construct Binary Tree from Inorder and Postorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/)

Notes:
- similar to the previous problem:
  - we pop the last element from the `postorder` as a `root`
  - then we find the index of the `root` in the `inorder`
  - then we recursively call, but first for the right subtree and then for the left subtree 

---
### [117. Populating Next Right Pointers in Each Node II](https://leetcode.com/problems/populating-next-right-pointers-in-each-node-ii/)

Notes:
1. Approach: O(logn) space complexity using `hash map`
    - we can for every level store most `left node` in the `hash map`, and then when we again reach the same level we can connect the `left node` to the current node and set current node as the `left node` in the `hash map`

2. Approach: O(1) space complexity using `scanner` node
    - we can use the `scanner` node:
       - while we have `scanner`:
         - we set `scanner` to the `left` child or right child of the `scanner`
         - else we set `scanner` to the `next` node
    - then our `right.next = scanner`
    - then our `lefg.next = right if right else scanner`
    - recursively call the function first for the right and then for the left child  

---
### [226. Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/)

Notes:
- ”Even if you put aside regret, you´ll end up feeling it anyway. Right now, you need to make sure you grasp this good feeling and never forget it.”

---
### [114. Flatten Binary Tree to Linked List](https://leetcode.com/problems/flatten-binary-tree-to-linked-list/)

Notes:
1. Approach: using `queue` -> `O(n)` space complexity
    - we can use the `queue` to store the nodes in the `preorder` traversal
    - then we can just go through the `queue` and update the `left` and `right` pointers

2. Approach: using `recursive` -> `O(1)` space complexity
    - store the `prev` node
    - then we can use the `recursive` approach where we first flatten the `right` subtree and then the `left` subtree
    - then `root.right = prev` and `root.left = None`
    - then `prev = root`

---
### [129. Sum Root to Leaf Numbers](https://leetcode.com/problems/sum-root-to-leaf-numbers/)

Notes:
- traverse the tree in `preorder` and for each node we update `curr = curr*10 + node.val`
- if the node is the leaf we add the `curr` to the `sum`

---
### [222. Count Complete Tree Nodes](https://leetcode.com/problems/count-complete-tree-nodes/)

Notes:
1. Approach: using `recursive` -> `O(logn[logn])` time complexity
    - we can use the `recursive` approach where we first find the height of the left subtree and the right subtree
    - if the height of the left subtree is equal to the height of the right subtree we can return `2^height - 1`
    - otherwise we can recursively call the function for the left and right subtree and add `1` for the root

---
### [101. Symmetric Tree](https://leetcode.com/problems/symmetric-tree/)

Notes:
- interesting approach where we use the `recursive` function that takes two nodes and checks whether they are symmetric
- if `rval == lval` and `isSymmetric(left.right, right.left)` and `isSymmetric(left.left, right.right)` we return `True`, otherwise we return `False`

---
### [112. Path Sum](https://leetcode.com/problems/path-sum/)

Notes:
- we can use the `recursive` approach where we subtract the value of the current node from the `sum` and recursively call the function for the left and right child
- if we reach the leaf and the `sum` is `0` we return `True`, otherwise we return `False`

---
### [104. Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)

Notes:
- Freedom can be found at the bottom of your heart.

---
### [236. Lowest Common Ancestor of a Binary Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/)

Notes:
- we can use the `recursive` approach where we first check whether the `root` is equal to `p` or `q` and if it is we return the `root`
- else we call for the left and right child and if we get the `left` and `right` we return the `root`
- if we get only the `left` or `right` we return the `left` or `right`

---
## Binary Tree BFS
---
### [637. Average of Levels in Binary Tree](https://leetcode.com/problems/average-of-levels-in-binary-tree/)

Notes:
"Dedication Is A Talent All On Its Own."

---
### [199. Binary Tree Right Side View](https://leetcode.com/problems/binary-tree-right-side-view/)

Notes:
- put every level in the `hash map` and then for each level we can take the last element

---
### [102. Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/)

Notes:
- literally just put everything into `hash map` 

---
## Binary Search Tree
---
### [530. Minimum Absolute Difference in BST](https://leetcode.com/problems/minimum-absolute-difference-in-bst/)

Notes:
- just do the `inorder` traversal and keep track of the prev node
- then for each node we can calculate the difference between `curr` and `prev` and update the `min_diff`

---
### [230. Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/)

Notes:
- do the `inorder` traversal and every step decrement the `k`
- if k is `0` we return the value of the node
- otherwise we return the value of the left or right child (whoevers value is greater, if we haven't found result we return -1 and range for nodes is `>= 0`)

---
### [98. Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree/)

Notes:
- done it in the **Algorithms** course `:)`
- for each node we check whether the value is in the range of the `min` and `max` and recursively call the function for the left and right child
- for each recursive call we update the `min` and `max` values in the following way:
  - for the left child we update the `max` to the value of the current node
  - for the right child we update the `min` to the value of the current node

---
## Graph General
---
### [130. Surrounded Regions](https://leetcode.com/problems/surrounded-regions/)

Notes:
- mark all boundary regions `O` to `*`
- then mark all `O` to `X` and `*` to `O`

---
### 133. Clone Graph

Notes:
- we can use the `hash map` to store the mapping of the original node to the new node
- we just use dfs to traverse the graph and create the new nodes
- if `node` not in `hash map` we create the new node and put it in the `hash map`, so then we go through the neighbors and recursively call the function

---
### [207. Course Schedule](https://leetcode.com/problems/course-schedule/)

Notes:
- we can use the `hash map` to store the mapping of the course to the list of the courses that depend on that course
- if we detect the cycle we return `False`, otherwise we return `True`

---
## Graph BFS
---
### [909. Snakes and Ladders](https://leetcode.com/problems/snakes-and-ladders/)

Notes:
- neetcode 🚀 [here](https://www.youtube.com/watch?v=6lH4nO3JfLk)

---
### [433. Minimum Genetic Mutation](https://leetcode.com/problems/minimum-genetic-mutation/)

Notes:
- at every step we want to change every character in the string and check whether it is in the `bank` and if it is not in the `visited` 
- if condition is met we add it to the `queue` and `visited`
- if we reach the `end` we return the `level`, otherwise we return `-1`

---
### [815. Bus Routes][https://leetcode.com/problems/bus-routes/]

Notes:
- we can use the `hash map` to store the mapping of the stop to the list of the buses that stop at that stop
- then we can use the `queue` to store the `curr_stop` and `buses_taken`, and sets for visited stops and buses
- then we can just go through the buses that stop at the `curr_stop` and for each bus that we haven't visited we go through the stops that the bus stops at and if we haven't visited the stop we add it to the `queue` and `visited_stops`

---
## Trie
---
### [211. Design Add and Search Words Data Structure](https://leetcode.com/problems/design-add-and-search-words-data-structure/)

Notes:
- we can use the `trie` to store the words
- for the `search` function we can just modify search function inside the `trie` 

---
## Binary Search
---
### [35. Search Insert Position]

Notes:
- we can use the `binary search` to find the index of the element or the index where the element should be inserted

---
### [74. Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/)

Notes:
- just treat the 2D matrix as a 1D array and do the binary search
- `row = mid // n` and `col = mid % n` where `n` is the number of columns
- and `mid = right + (left - right) // 2`

---
### [33. Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)

Notes:
- done it in the **Algorithms** course `:)`
- the weird one `:>`

---
### [153. Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)

Notes:
- if I am smaller than the right element I know that the minimum is on the left side or I am the minimum
- if I am greater than the right element I know that the minimum is on the right side

---
### [34. Find First and Last Position of Element in Sorted Array
](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)

Notes:
- run two binary searches, one for the first occurrence and one for the last occurrence
- for the first occurrence we update the `right` pointer if the `mid >= target`
- for the last occurrence we update the `left` pointer if the `mid <= target`

---
## Backtracking
---
### [77. Combinations](https://leetcode.com/problems/combinations/)

Notes:
- we can use the `backtracking` approach where we add the element to the `temp` and recursively call the function for the next element where we say it to just add numbers  >= `digit+1` where `digit` is current num that we added -> `1234 = 4321` 

---
### [46. Permutations](https://leetcode.com/problems/permutations/)

Notes:
- first we can make the `hash map` where the key is the number and the value is whether the number is used
- then we can use the `backtracking` approach where we add the number to the `temp` and mark it as used and recursively call the function for the next number after which we set it to unused again
- if the length of the `temp` is equal to the length of the `nums` we add the `temp` to the `result`

---
### [39. Combination Sum] 

Notes:
- we can use the `backtracking` approach where we check whether sum is greater than the target and if it is we return
- if the sum is equal to the target we add the `temp` to the `result`
- otherwise we iterate through the candidates and add the number to the `temp` and recursively call the function for the next number with `i` index as a start and after call we remove the last element from the `temp`

---
### [22. Generate Parentheses](https://leetcode.com/problems/generate-parentheses/)

Notes:
- A man, slave to gold, holds the whip... and beats the slave he bought with the gold as if to claim that he is the master. He just doesn’t see it for himself. Every living human being is a slave to something.

---
### [79. Word Search](https://leetcode.com/problems/word-search/)

Notes:
- we can use the `backtracking` approach where we go through the board and for each cell that is equal to the first character of the word we call `backtrack` function where we mark the cell as visited and recursively call the function for the next character if it is equal to the next character in the word and is not visited

---
## Bit Manipulation
---
### [67. Add Binary](https://leetcode.com/problems/add-binary/)

Notes:
- Leave tomorrow's problems to tomorrow's you.

---
### [190. Reverse Bits](https://leetcode.com/problems/reverse-bits/)

Notes:
- freaking bit manipulation `:>`
- we extract bit by doing `bit = (n>>i) & 1` and then we set the bit by doing `res |= bit << (31-i)`

---
### [191. Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)

Notes:
- Some things are beautiful exactly because they're unobtainable

---
### [136. Single Number](https://leetcode.com/problems/single-number/)

Notes:
- we can use the `XOR` operator to find the single number
- because if we `XOR` the same number we get `0`
```
Input: [2,2,1]   0 0     1 0     0 0
Output: 1      ^ 1 0   ^ 1 0   ^ 0 1
               ------  ------  ------ 
               = 1 0   = 0 0  = 0 1

```
---
### [137. Single Number II](https://leetcode.com/problems/single-number-ii/)

Notes:
- magic `:)`
- we need to count number of `ones` and `twos` for each number
- so we initialize `ones = 0` and `twos = 0`
- then for each number we update the `ones` and `twos` in the following way:
  - `ones = (ones ^ num) & ~twos`
  - `twos = (twos ^ num) & ~ones`

### [201. Bitwise AND of Numbers Range](https://leetcode.com/problems/bitwise-and-of-numbers-range/)

Notes:
- again these bitwise problem magic `:>`
- we want to find the common prefix of left and right number and that is the result

---
## Divide & Conquer
---
### [108. Convert Sorted Array to Binary Search Tree](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/)

Notes:
- if left is greater than right we return `None`
- calculate the middle element and create the root node
- then recursively call the function for the left (left, mid-1) and right (mid+1, right) child

---
### [148. Sort List](https://leetcode.com/problems/sort-list/)

Notes:
- freaking merge sort `:>`
- split the list in the middle
- recursively call the function for the left and right half
- then merge the left and right half and return the result
- by merging we compare the values of the two sorted lists and make new list which is sorted

---
### [427. Construct Quad Tree](https://leetcode.com/problems/construct-quad-tree/)

Notes:
- make function that takes top left and bottom right corner of the grid and return the node
- check whether the grid is the same and if it is return the node
- else calculate the middle: `midx = (left + right) // 2` and `midy = (top + bottom) // 2`
- then recursively call the function for the four quadrants with adequate coordinates and return the node

---
## Kadane's Algorithm
---
### [53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

Notes:
- we calc `pref_sum` on the fly and `ans = max(ans, pref_sum)`, then if `pref_sum < 0` we set it to `0` because we want to start from the beginning

--- 
### [918. Maximum Sum Circular Subarray](https://leetcode.com/problems/maximum-sum-circular-subarray/)

Notes:
- gpt and comment from the discussion helped me `:)`
- calucate the `max subarray sum (Kadane's Algorithm)` and `min subarray sum`
- then return the maximum of the `max subarray sum` and `total sum - min subarray sum (if solution is circular)`
- edge case is when all elements are negative, then we return the `kadane's algorithm` result

---
## Math
---
### [9. Palindrome Number](https://leetcode.com/problems/palindrome-number/)

Notes:
- "You’ll find happiness too someday."

---
### [66. Plus One](https://leetcode.com/problems/plus-one/)

Notes:
- "I see now that the circumstances of one's birth are irrelevant.It is what you do with the gift of life that determines who you are."

---
### [172. Factorial Trailing Zeroes](https://leetcode.com/problems/factorial-trailing-zeroes/)

Notes:
- first approach is to calculate the factorial and divide number by 10 until we get 0, so we can count the number of zeros
- that's not efficient as factorial grows very fast
- so we need number of 10s, but 10 can be factored into 2 and 5, and there are more 2s than 5s, so we can count the number of 5s
- so all we need to do is count the number of 5s in the number `n` and that is the number of trailing zeros `:)`

---
### [69. Sqrt(x)](https://leetcode.com/problems/sqrtx/)

Notes:
- we can use the `binary search` to find the square root of the number where lower bound is `1` and upper bound is `x/2`

---
### [50. Pow(x, n)](https://leetcode.com/problems/powx-n/)

Notes:
- we can use recursion to calculate the power of the number
- if `n == 0` we return `1`
- if `n < 0` we return change `x = 1/x` and `n = -n`
- we recursively call the function for the `n//2` and then we return the result squared and also multiply it by `x` if `n` is odd 

---
## 1D DP
---
### [70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

Notes:
- dp formula is `dp3 = dp1 + dp2` 

---
### [139. Word Break](https://leetcode.com/problems/word-break/)

Notes:
- Neetcode 🚀 [here](https://www.youtube.com/watch?v=Sx9NNgInc3A&ab_channel=NeetCode)

- for every index we try to find the word in the `wordDict` that ends at that index and if we find one we update the `dp` array by what is at the index `i - len(word)`, so basically the formula is:
  - if we found matching word at certain index `i`: `dp[i] = dp[i - len(word)]`
  - and solution is `dp[n]` where `n` is the length of the string 

---
### [322. Coin Change](https://leetcode.com/problems/coin-change/)

Notes:
- Done it in the **Algorithms** course `:>`
- idea is that for each coin we store the minimum number of coins needed to make the amount
- so the dp formula is:
  - for each coin we check whether `i - coin >= 0` and if it is we update the `dp[i] = min(dp[i], dp[i - coin] + 1)`
  - if we can't make the amount with the current coin we set the `dp[i] = -1`
  - and the result is `dp[amount]`

---
### [300. Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)

Notes:
1. Approach: `O(n^2)` time complexity
    - we can use the `dp` array where the `dp[i]` is the length of the longest increasing subsequence that ends at the index `i`
    - for each index we go through the previous indexes and if the number at the current index is greater than the number at the previous index we update the `dp[i] = max(dp[i], dp[j] + 1)`

2. Aproach: `O(n log(n))` time complexity
   - solution explained [here](https://leetcode.com/problems/longest-increasing-subsequence/solutions/667975/python-3-lines-dp-with-binary-search-explained/)

---
## 2D DP
---
### [120. Triangle](https://leetcode.com/problems/triangle/)

Notes:
1. Approach: Space complexity: `O(triangle)`
  - formula is: `dp[i][j] = min(dp[i+1][j], dp[i+1][j+1]) + triangle[i][j]`
2. Approach: Space complexity: `O(n)` where `n` is the number of rows
  - we can just reuse the `dp` array and update it in the following way:
  - formula is: `dp[j] = min(dp[j], dp[j+1]) + triangle[i][j]`
  
---
### [64. Minimum Path Sum](https://leetcode.com/problems/minimum-path-sum/)

Notes:
- we can use the `dp` array where the `dp[i][j]` is the minimum path sum to the cell `(i, j)`
- where formula is `dp[i][j] = min(dp[i-1][j], dp[i][j-1]) + grid[i][j]`
- we can optimize space complexity by storing things inside the `grid` array instead of the `dp` array

---
### [63. Unique Paths II](https://leetcode.com/problems/unique-paths-ii/)

Notes:
- we can use the `dp` array where the `dp[i][j]` is the number of unique paths to the cell `(i, j)`
- we first initilize first row and first column to `1` unless there is an obstacle
- then the formula is `dp[i][j] = dp[i-1][j] + dp[i][j-1]` unless there is an obstacle

---
### [5. Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)

Notes:
- we can use the `dp` array where the `dp[i][j]` is `True` if the substring from `i` to `j` is a palindrome
- we initilize the `dp` array where the `dp[i][i]` is `True` and `dp[i][i+1]` is `True` if the characters are the same
- then formula for the rest of the `dp` array is `dp[i][j] = dp[i+1][j-1] and s[i] == s[j]`

---
## Heap
---
### [215. Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/)

Notes:
- put elements in the `max heap` and pop `k-1` elements
- then return the top element

### [373. Find K Pairs with Smallest Sums](https://leetcode.com/problems/find-k-pairs-with-smallest-sums/)

Notes:
- even though `2 pointers` seems intuitive it doesn't work, for example:
  ```
  nums1 = [1,1,2]
  nums2 = [1,2,3]
  output = [[1,1],[1,1],[1,2],[2,1],[2,2],[2,3]]
  expected = [[1,1],[1,1],[2,1],[1,2],[1,2],[2,2],[1,3],[1,3],[2,3]]
  ```
- so we use the `min heap` to store the sum and the indexes of the elements from the two arrays and while we add up to `k` elements we pop the element from the `min heap` make `new_i = i+1` and `new_j = j+1` and if we haven't visited the pair we add next pairs `(new_i, j)` and `(i, new_j)` to the `min heap`

---
  
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
  🟢 easy: 8
  
  🟡 medium: 37
  
  🔴 hard: 13

  </td>
  </tr>
</table>


## 🟢 Easy
### [13. Roman to Integer](https://leetcode.com/problems/roman-to-integer/)
`hash table`

Notes:
- we use `hash table` to map the **roman characters** to the **integer values**

---
### [359. Logger Rate Limiter](https://leetcode.com/problems/logger-rate-limiter/)
`hash map`

Notes:
- just put message in the `hash map` where the value is `timestamp` and if the message is already in the `hash map` and the difference between the `timestamp` and the value is less than `10`, we return `False`, otherwise we update the `timestamp` and return `True`

---
### [1275. Find Winner on a Tic Tac Toe Game](https://leetcode.com/problems/find-winner-on-a-tic-tac-toe-game/)
`list`

Notes:
- we can use `list` to store all the winning combinations and then for each combination we check whether first player `A` has that combination, hen we check whether the second player `B` has that combination
- if none of them has the winning combination we check whether the board is full and return `Draw` otherwise we return `Pending`
---
### [1304. Find N Unique Integers Sum up to Zero](https://leetcode.com/problems/find-n-unique-integers-sum-up-to-zero/)
`array`

Notes:
- we can just add `i` and `-i` to the result array for `i` from `1` to `n//2` and if `n` is odd we can add `0` to the result

---
### [1822. Sign of the Product of an Array
](https://leetcode.com/problems/sign-of-the-product-of-an-array/)
`array`

Notes:
- we can just go through the array and count the number of negative numbers and if we come across `0` we can return `0` otherwise we can return `1` if the number of negative numbers is even and `-1` if the number of negative numbers is odd

---
### [2259. Remove Digit From Number to Maximize Result](https://leetcode.com/problems/remove-digit-from-number-to-maximize-result/)
`array`

Notes:
- as long as `digit` is greater than next element we keep searching for the next occurrence of the `digit` and once we find index where `digit` is smaller than the next element we can remove that occurrence of the `digit`

---
### [231. Power of Two](https://leetcode.com/problems/power-of-two/)
`bit manipulation`

Notes:
- we can use the `bit manipulation` to check whether the number is the power of `2` by doing `n & (n-1) == 0`

---
### [1217. Minimum Cost to Move Chips to The Same Position](https://leetcode.com/problems/minimum-cost-to-move-chips-to-the-same-position/)
`array` `math`

Notes:
- we can just count the number of even and odd numbers and return the minimum of the two

---
## 🟡 Medium
### [56. Merge Intervals](https://leetcode.com/problems/merge-intervals/)
`sorting`

Notes:
- sort the intervals based on the start
- if the end of the current interval is greater than the start of the next interval, we merge them

---
### [146. LRU Cache](https://leetcode.com/problems/lru-cache/)
`linked list` `hash table`

Notes:
- similar to what we do at the **OS course** :)
- we use `OrderedDict` that keeps track of order of elements that were added
- when getting element, we move it to the end of the list
- when adding element, if present we move it to the end, if not we add it to the end and remove the first element if the size is greater than the capacity

---
### [200. Number of Islands](https://leetcode.com/problems/number-of-islands/)
`bfs` `dfs`

Notes:
- we did this problem in the **Algorithms** course
- when we find `grid[i][j] == '1'` we increment the count and do the BFS to mark all the connected islands as visited

---
### [15. 3Sum](https://leetcode.com/problems/3sum/)
`two pointers`

Notes:
- discussion -> *not the 3some I wanted*
- sort the array
- for each element `nums[i]` we use two pointers `left=i+1` and `right=n-1`
- if sum is less than `0` we increment the `left`, if sum is greater than `0` we decrement the `right`, if sum is equal to `0` we add the triplet to the result
--- 
### [528. Random Pick with Weight](https://leetcode.com/problems/random-pick-with-weight/)
`prefix sum` `binary search`

Notes:
- we first make `pdf` (*probability density function*) by dividing the weight by the sum of all weights
- then we make `cdf` (*cumulative density function*) (prefix sum)
- then for each random number we do the `binary search` to find the index of the number in the `cdf` array and return that **index**

---
### [253. Meeting Rooms II](https://leetcode.com/problems/meeting-rooms-ii/)
`sorting` `heap`

Notes:
- we **sort** intervals by `start` and then `end` time 
- after that we use `heap` to keep track of the end time of the meetings
- if the `start time` of the meeting is greater than the `end time` of the meeting, we `pop` the `end time` from the `heap` and `push` the new `end time`
- otherwise we just `push` the `end time` to the `heap`

---
### [380. Insert Delete GetRandom O(1)](https://leetcode.com/problems/insert-delete-getrandom-o1/)
`hash map` `list`

Notes:
- use `hashmap` in a way that `dict[val] = len(lst)-1` and `lst.append(val)`
- then when removing the element, we swap the element with the last element and `pop` the last element and also `remove` element from `hashmap`

---
### [54. Spiral Matrix](https://leetcode.com/problems/spiral-matrix/)
`matrix`

Notes:
- same as the problem from `UUP` course `>_<`
- make `direction array` and check whether you are in the bounds and if you are not in the bounds or you have visited the element, change the direction
---
### [17. Letter Combinations of a Phone Number](https://leetcode.com/problems/letter-combinations-of-a-phone-number/)
`backtracking` `hash table`

Notes:
- have done it before (I believe in the **Algorithms** course)
- we use `backtracking` by going through each letter of each digit and building `combination` after which we recursively call the function for the next digit, after that we remove the last letter from the `combination`
- we use `hash table` to map the digit to the 

---
### [394. Decode String](https://leetcode.com/problems/decode-string/)
`stack`

Notes:
- idea is to have 2 stacks -> `letter_stack` and `digit_stack`
- first we initialize `ans = ""` and `num = ""`
- `curr.isdigit()` -> we add the digit to the `num`
- `curr == '['` -> we add the `num` to the `digit_stack` and `ans` to the `letter_stack` and reset the `num` and `ans`
- `curr == ']'` -> we pop the `num` and `letters` from the stacks and `ans = letters + num*ans`
- `curr.isalpha()` -> we add the letter to the `ans`

---
### [1647. Minimum Deletions to Make Character Frequencies Unique](https://leetcode.com/problems/minimum-deletions-to-make-character-frequencies-unique/)
`hash map` `set`

Notes:
- we use `hash map` to count the frequency of the characters
- then we use `set` to store each frequency and if the frequency is already in the set, we decrement the frequency until it is not in the set and increment the `deletions`

---
### [210. Course Schedule II](https://leetcode.com/problems/course-schedule-ii/)
`topological sort` `dfs` `graph`

Notes:
- lol -> had to watch 20 min video explanation of topological sort, after which I consulted gpt for better implementation :(
- we want to to topological sort of the graph
- we can use `dfs` to find the cycle in the graph
- Steps:
    1. build the graph, initialize `visited` to `0s` and `result=[]`
    2. for each course if `visited[course] != 2` we call the `dfs` function
    3. in the `dfs` function we check if the `visited[course] == 1` meaning we have detected cycle
    4. if we haven't detected cycle we set the `visited[course] = 1` and for each `neighbour` we call the `dfs` function if `visited[neighbour] != 2`
---

### [1239. Maximum Length of a Concatenated String with Unique Characters](https://leetcode.com/problems/maximum-length-of-a-concatenated-string-with-unique-characters/)
`backtrack` `bit manipulation`

Notes:
- even though the solution seems to be `dp` it is actually `backtrack`
- how to know when to use `backtrack` vs `dp`
- in this problem we need to have insight into all the previous states that we have selected so we know that current word can be added to the previous state -> that's why we can't use `dp`
- Any time the problem is naturally phrased in terms of I have a **current state** and should I take this element or not?, and answering can I take this element? **involves storing state information about the current selection**, these are clues you should use `DFS` + `backtracking`

---
### [498. Diagonal Traverse](https://leetcode.com/problems/diagonal-traverse/)
`matrix`

Notes:
- Approach I:
  - we can just have `direction` flag that tells us whether we are going up or down, and if the coordinates are out of bounds we change the direction and update coordinates
- Approach II ([source](https://leetcode.com/problems/diagonal-traverse/solutions/581868/easy-python-no-direction-checking/)):
  - every diagonal has equal sum of coordinates, so we can use that to build the `hash map` where the key is the sum of the coordinates and the value is the list of elements on that diagonal
  - then we can just go through the `hash map` and add the elements to the result, and for every even diagonal we reverse the list

---
### [556. Next Greater Element III](https://leetcode.com/problems/next-greater-element-iii/)
`string` `arithmetics`

Notes:
- GPT did it well `:-)`
- First we go from the end and find the element such that `nums[i] < nums[i+1]`
- then going from the end again we find the first element such that `nums[j] > nums[i]`
- then we swap the `nums[i]` and `nums[j]` and reverse the elements from `i+1` to the end

---
### [151. Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/)
`string`

Notes:
- really easy problem, just split the string by the space and reverse the list and join it back withou the space at the end

---
### [1578. Minimum Time to Make Rope Colorful](https://leetcode.com/problems/minimum-time-to-make-rope-colorful/)
`two pointers`

Notes:
- idea is just while we have same colors we move the `right` pointer and also want to keep track of the biggest `time` for that sequence, so we always add smaller number to the `ans`, but update the `time` with the bigger one

---
### [103. Binary Tree Zigzag Level Order Traversal](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/)
`dfs` `hash map`

Notes:
- idea is to use `dfs` to go through the tree and for each level we append the element to the `hash map` where the key is the `level`
- after that for every odd level we reverse the list and add it to the result

---
### [43. Multiply Strings](https://leetcode.com/problems/multiply-strings/)
`string` `arithmetics`

Notes:
- algorithm is something we did in `UUP` course `:-)`

---
### [240. Search a 2D Matrix II](https://leetcode.com/problems/search-a-2d-matrix-ii/)
`matrix` `binary search` `divide and conquer`

Notes:
- we want to utilize the fact that the matrix is sorted column and row wise
- so we can start from the top right corner and if the current element is greater than the target we move to the left (because we know that the target is not that column because it's sorted), otherwise we move down

---
### [99. Recover Binary Search Tree](https://leetcode.com/problems/recover-binary-search-tree/)
`binary tree` `inorder traversal`

Notes:
- we can use `inorder traversal` to get the elements in the sorted order
- so in the `processing` part of the `inorder traversal` we check whether the current element is smaller than the previous element is we update our `last` and set `first` if not already set, also update our 'prev'
- it's interesting how we can have whole array of misaligned elements but we only need to swap the first and the last one, so that why we always update the `last` element  

---
### [173. Binary Search Tree Iterator](https://leetcode.com/problems/binary-search-tree-iterator/)
`inorder traversal` `stack`

Notes:
- constraint is that we need to have `O(h)` space complexity
- so we only write the `inorder traversal` function that goes to the leftmost element and then for each `next` call we pop the element from the stack and go to the right child of that element and add all the left children to the stack
- `hasNext` is just checking whether the stack is empty

---
### [1405. Longest Happy String](https://leetcode.com/problems/longest-happy-string/)
`greedy` `max heap`

Notes:
- we can use `max heap` to keep track of the characters and their frequencies
- **if** we current most frequent character is the same as the last two characters in the result we can pop the second most frequent character and add it to the result
- **else** we can add the most frequent character to the result
- after that we need to update the frequencies and add the characters to the heap

---
### [1615. Maximal Network Rank](https://leetcode.com/problems/maximal-network-rank/)
`graps` `hash map`

Notes:
- store each road connection into one `set` both `(a,b)` and `(b,a)`
- also for each city store the number of roads that are connected to that city
- then for each pair of cities we can calculate the rank by adding the number of roads that are connected to the cities and subtracting 1 if the cities are connected

---
### [453. Minimum Moves to Equal Array Elements](https://leetcode.com/problems/minimum-moves-to-equal-array-elements/)
`math` `array`

Notes:
- **First approach (outside of the box):**
  - instead of incrementing `n-1` elements by 1, we can subtract 1 from every element except the smallest one
  - so we can just find the smallest element and subtract it from all the elements
- **Second approach (math):**
  - formula is `s + m*(n-1) = n*x` where `s` is the sum of the array, `m` is the number of moves and `x` is the final number, `n` is the length of the array
  - so 2 unknowns are `m` and `x`
  - we can introduce another equation: `x = min + m`
  - so then when we mix the equations we get `m = s - n*min`

---
### [1386. Cinema Seat Allocation](https://leetcode.com/problems/cinema-seat-allocation/)
`hash map`

Notes:
- we can use `hash map` to store the seats that are already taken
- then go through all the rows in the `hash map` and check the conditions for the seats
- after that we get `m = n - len(hash_map)` which are rows that are completely free and `ans += m*2` because we can have 2 groups of 4 seats 

---
### [285. Inorder Successor in BST](https://leetcode.com/problems/inorder-successor-in-bst/)
`BST` `binary search`

Notes:
- we can use iterative approach here:
  - while `root` we just update `successor = root` if the `p.val < root.val` and move to the left
  - if `p.val >= root.val` we move to the right

---
### [1404. Number of Steps to Reduce a Number in Binary Representation to One](https://leetcode.com/problems/number-of-steps-to-reduce-a-number-in-binary-representation-to-one/)
`binary` `math`

Notes:
- idea is:
  - if the last element is `0` we can just remove last element
  - otherwise find the first `0` from the end and replace it with `1` and all the elements after that with `0` or we if don't find `0` we set string to `s = '1' + '0'*len(s)` 

---
### [1653. Minimum Deletions to Make String Balanced](https://leetcode.com/problems/minimum-deletions-to-make-string-balanced/)
`dp` `prefix sum`

Notes:
1. Using `prefix sum` -> ''O(n)' space complexity:
    - we can calculate prefix sum of `b`'s and suffix sum of `a`'s
    - solution is `ans = min(ans, b[i] + a[i]])`

2. Using `dp` -> 'O(1)' space complexity:
    - for each `a` we can either delete it or delete all the `b`'s before it -> `dp = min(dp+1, b_count)`

---
### [1448. Count Good Nodes in Binary Tree](https://leetcode.com/problems/count-good-nodes-in-binary-tree/)
`bts` `dfs`

Notes:
- if the `current.val > max_val` we increment the counter and update the `max_val`
- then we call function for the `left` and `right` child with cum result `0` and then **add results** from the `left` and `right` child to the result

---
### [1775. Equal Sum Arrays With Minimum Number of Operations](https://leetcode.com/problems/equal-sum-arrays-with-minimum-number-of-operations/)
`greedy` `min heap` `max heap` `counting sort`

Notes:
1. Using `minheap` and `maxheap` -> `O(nlogn)` for constructing heaps:
   - first we calculate the `diff` between the sums of the arrays
   - then we store values of the greater array into `maxheap`
   - then we store values of the smaller array into `minheap`
   - while the `diff` is greater than `0`:
     - if the `maxheap.top() - 1 > 6 - minheap.top()` we update `diff -= (maxheap.top() - 1)` and `pop` the element from the `maxheap`
     - otherwise we update `diff -= 6 - minheap.top()` and `pop` the element from the `minheap`
2. Using `counting sort` -> `O(n)`:
   - essentially the same we just sort greater array in decreasing order and smaller array in increasing order using `counting sort` because we now that all values are in range `[1,6]`

---
### [2149. Rearrange Array Elements by Sign](https://leetcode.com/problems/rearrange-array-elements-by-sign/)
`two pointers`

Notes:
- we can use `two pointers` to solve this problem
- initialize `left = 0` and `right = 0`
- then if the `pos` is:
  - even: move `left` to the first positive number
  - odd: move `right` to the first negative number

---
### [316. Remove Duplicate Letters](https://leetcode.com/problems/remove-duplicate-letters/)
`stack` `hash map`

Notes:
- first we need to know which `chars` we can remove
- for that we can do preprocessing with `hash map` 
- then we can use `stack` to store the characters in lexicographical order where:
  - if the `char` is already in the stack we continue
  - for each `char` we remove all chars in stack that are greater than the current `char` and appear more than once  
  - then we add the `char` to the stack

---
### [2743. Count Substrings Without Repeating Characters](https://leetcode.com/problems/count-substrings-without-repeating-characters/)
`sliding window`

Notes:
- for each index `i` is our left bound and we move the right bound while we don't have repeating characters and in each step we increment the counter by one

---
### [142. Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)
`linked list` `slow-fast pointers` `math`

Notes:
- We can solve problem with `Floyd's Tortoise and Hare` algorithm
- thanks to saiamrit for the [explanation](https://leetcode.com/problems/linked-list-cycle-ii/solutions/2184711/o-1-space-python-solution-with-clear-explanation-faster-than-90-solutions/) `:)`
- essentialy once the `fast` and `slow` pointers meet we can move the `slow` pointer to the `head` and then move both pointers by one until they meet again and that is the `cycle start` (there is a math behind it `:)`)

---
### [Maximum Matrix Sum](https://leetcode.com/problems/maximum-matrix-sum/)
`matrix` `greedy` `math`

Notes:
- we want to count number of negative numbers and sum of absolute values of all numbers
- if the number of negative numbers is even we can just sum all the absolute values
- if we have at least one `zero` we can sum all the absolute values, because `zero` can absorb the negative numbers
- if we have odd number of negative numbers we can sum all the absolute values and subtract the double of the smallest absolute value (double because we already counted it in the sum)

---
### [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)
`array` `two pointers`

Notes:
- we can use `slow` and `fast` pointers to find the cycle in the array
- when they meet, we just reset fast to the start and move both pointers by one until they meet again `:)`

---
### [166. Fraction to Recurring Decimal](https://leetcode.com/problems/fraction-to-recurring-decimal/)
`hash map` `math`

Notes:
- simple elegance `:)`

---
## 🔴 Hard
### [42. Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/) 
`stack`

Notes:
- idea is that for each index we need to find the maximum height to the left and right of that index (we use stack for it)
- than answer is collecting thins for each element: `ans += min(left_max, right_max) - height[i]` if that value is greater than `0`

---
### [273. Integer to English Words](https://leetcode.com/problems/integer-to-english-words/)
`math` `string`

Notes:
- interesting approach where we parse three digits at a time and convert them to the words

---
### [224. Basic Calculator](https://leetcode.com/problems/basic-calculator/)
`stack`

Notes:
- we use `num_stack` and `sign_stack` to store the numbers and signs before the parenthesis
- we initialize `num = 0` and `sign = 1`
- if we encounter `(` we push the `num` and `sign` to the stacks and reset the `num` and `sign`
- if we encounter `)` we pop the `num` and `sign` from the stacks and calculate the `num = num_stack.pop() + sign_stack.pop()*num`

---
### [2035. Partition Array Into Two Arrays to Minimize Sum Difference](https://leetcode.com/problems/partition-array-into-two-arrays-to-minimize-sum-difference/)
`meet in the middle` `binary search` `combinations`

Notes:
- really hard problem -> looked at the [solution](https://leetcode.com/problems/partition-array-into-two-arrays-to-minimize-sum-difference/solutions/1513435/python-easy-explanation-meet-in-the-middle/)

- using technique called `meet in the middle`
- we split the array into two parts and for each part we calculate the sum of all the possible combinations from 1 to `n//2` elements:
  - for each `k` we make `left_k_sums` which is the sum of all combinations of `k` elements from the `left part`
  - then we make `right_k_sums` which is the sum of all combinations of `n//2 - k` elements from the `right part` (if we want to combine elements from both parts)
  - then we need to fidn what is closest sum of `n // 2 - k` elements in the right_k_sums where `target` is `half_sum - left_k_sum` using `binary search`
  - and in the end when we have both left and right sums we can calculate the difference and update the `min_diff`

---
### [127. Word Ladder](https://leetcode.com/problems/word-ladder/)
`BFS` `hash map`

Notes:
- idea is to first build hashmap where we have all the possible words that can be made from the current word:

``` 						 
            hit, level = 1
          /       |       \
        *it      h*t       hi*
```
- basically we have `map[*it] = [git, hit, pit]` and so on
- once we build hashmap we can start the `BFS` where we keep track of the `level` and `visited` words
- at the beginning `queue = [(beginWord, 1)]`
- for each word in the queue:
  - we go through all patterns of current word and for each pattern check all the words
  - if the word is in the `endWord` we return the `level+1`
  - if the word is not in the `visited` we add it to the `visited` and to the `queue`

---
### [212. Word Search II](https://leetcode.com/problems/word-search-ii/)
`trie` `dfs`

Notes:
- so we need to do the backtrack from every cell in the board, but how can we do that efficiently?
  - first thing that comes to mind is using `hashmap` to store the words and then for each cell in the board we do the `dfs` to check if the word is in the `hashmap`
  - but that is not efficient because sometimes we can stop the backtrack earlier if the current word is not the prefix of any word in the `hashmap`
  - so that's why we use `trie` to store the words and then for each cell in the board we do the `dfs` and check if the current word is in the `trie` 
  - `trie` if efficient for **prefix search**

---
### [10. Regular Expression Matching](https://leetcode.com/problems/regular-expression-matching/)
`dp`

Notes:
- tried to solve without using `dp` but wasn't successful
- so we can us dp as shown [here](https://leetcode.com/problems/regular-expression-matching/solutions/5198472/easy-solution-dp-python/):
  - If `p[j-1]` is a character or `'.'`, then `dp[i][j]` depends on whether the previous characters match and if the current characters of `s` and `p` match.

  - If `p[j-1]` is `'*'`, it can either match zero characters or one or more characters. This requires us to consider two cases:

  - The `'*'` matches zero characters: We look at `dp[i][j-2]`.

  - The `'*'` matches one or more characters: We look at `dp[i-1][j]` and ensure the preceding character matches `s[i-1]`.

---
### [25. Reverse Nodes in k-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/)
`linked list`

Notes:
- problem which has composite solution
- we can make function that checks whether we have next `k` elements
- we have function that reverses the `k` elements
- then we have function that we recursively call which revierses the `k` elements and then calls itself for the rest of the listcd

---
### [297. Serialize and Deserialize Binary Tree](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/) 
`binary tree` `dfs`

Notes:
- we can use `dfs` with `hashmap` to store nodes on each level in order to serialize the tree
- then we can use `queue` to deserialize the tree:
  - while we have elements:
    - we pop the element from the queue and if it is not `None` we create the left and right child and add them to the queue  

---
### [768. Max Chunks To Make Sorted II](https://leetcode.com/problems/max-chunks-to-make-sorted-ii/)
`stack` `sorting`

Notes:
1. **Sorting** -> *O(nlogn)*:
  - we can sort the array and then compare the sorted array with the original array and if elements are just the permutation of the original array we can increment the `chunks` otherwise we need to extend the chunk

2. **Stack** -> *O(n)*:
  - we can use stack to keep track of the maximum element up to the current element:
    - `if curr >= stack.top()` we push the `curr` to the stack
    - otherwise we pop elements from the stack until we find the element that is smaller than the `curr` and then we push the first element that we popped from the stack 

---
### [2246. Longest Path With Different Adjacent Characters](https://leetcode.com/problems/longest-path-with-different-adjacent-characters/)
`dfs` 'tree'

Notes:
- we use dfs to traverse the tree and for each node:
  - we find longest and second longest path from the children such that the character is different from the current character
  - then we set `ans = max(ans, longest + second_longest + 1)` and return `longest + 1`
  - we consider `longest + second_longest + 1` because that might be greater than what parent cound construct with just `longest+1` path and we can't return `longest + second_longest + 1` because it wouldn't be path anymore

- so solution is `max(ans, dfs(node))` 

---
### [1453. Maximum Number of Darts Inside of a Circular Dartboard](https://leetcode.com/problems/maximum-number-of-darts-inside-of-a-circular-dartboard/)
`geometry` `math`

Notes:
- thanks to lichuan199010 for [explanation](https://leetcode.com/problems/maximum-number-of-darts-inside-of-a-circular-dartboard/solutions/636345/python-o-n3-and-o-n2logn-solution-explained-in-detail-with-pictures/)

- Basically:
  - for each pair of points we calculate the center of the circle and (we can have 0 centers `if dist(p1, p2) > 2*r`), one center `if dist(p1, p2) == 2*r` and two centers `if dist(p1, p2) < 2*r`
  - then for each center we calculate the number of points that are inside that circle and update the `max_points` number 

---
### [84. Largest Rectangle in Histogram](https://leetcode.com/problems/largest-rectangle-in-histogram/)
`stack`

Notes:
- done it in the **Algorithms** course `:>`
- for each index `i`we calculate how many elements to the left and right are greater than the current element
- we can do that by using `stack` where we store the indexes
- while our height is greater than the current element we pop the element from the stack, after that ans is `ans = i - last_pop` and if we popped something we add how many elements to the right/left are greater than `last_pop` element
- then result is `ans = max(ans, height[i]*(right-left+1))`