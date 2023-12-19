# Problem Statement

Given an array of size N-1 such that it only contains distinct integers in the range of 1 to N. Find the missing element.

## Solution:

```javascript
let sum = 0;
let total = (n * (n + 1)) / 2;
array.forEach((a) => (sum += a));
return total - sum;
```

Explanation: Take sum of all numbers until N. Subtract sum of current array.
Time Complexity Analysis: Iterating through the array takes O(N) time.

# Learning:

- array.sort()
  - takes O(nlogn) time
  - sorts lexicographically, treating elements as string.
  - for numerical comparison provide a compare function:
    - array.sort((a,b)=>a-b)
    - a-b: if result is negative a comes first. Does in-place sorting
