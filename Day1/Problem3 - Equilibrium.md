# Problem Statement

Given an array A of n positive numbers. The task is to find the first equilibrium point in an array. Equilibrium point in an array is an index (or position) such that the sum of all elements before that index is same as sum of elements after it.

Note: Return equilibrium point in 1-based indexing. Return -1 if no such point exists.

## Solution

```javascript
function equilibriumPoint(a, n) {
  const total = a.reduce((sum, current) => sum + current);
  let leftSum = 0;
  for (const [index, item] of a.entries()) {
    let rightSum = total - leftSum - item;
    if (leftSum === rightSum) return index + 1;
    leftSum += item;
  }
  return -1;
}
```

# Learning:

- array.reduce => to flatten any array

  ```javascript
  const arr = [1, 2, 3];
  let total = arr.reduce((sum, current) => sum + current, 0);
  ```

  - It takes a callback function and an initial value.
  - callback function takes 4 parameters -> accumulator, current value, current index, array which is affected

- array.entries()
  - in a for...of loop if you need index use it. Refer line no. 13.
