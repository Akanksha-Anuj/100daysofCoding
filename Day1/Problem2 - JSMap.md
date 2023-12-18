# Problem Statement

Given two arrays: a1[0..n-1] of size n and a2[0..m-1] of size m. Task is to check whether a2[] is a subset of a1[] or not. Both the arrays can be sorted or unsorted. There can be duplicate elements.

## Solution 1(Using Maps):

```javascript
function isSubset(a1, a2) {
  // Create a frequency map for elements in a1
  const frequencyMap = new Map();
  for (const num of a1) {
    frequencyMap.set(num, (frequencyMap.get(num) || 0) + 1);
  }

  // Check if each element in a2 is present in a1 and has sufficient frequency
  for (const num of a2) {
    if (!frequencyMap.has(num) || frequencyMap.get(num) === 0) {
      return false; // Element not found or frequency exhausted
    }
    frequencyMap.set(num, frequencyMap.get(num) - 1);
  }

  return true;
}

// Example usage:
const a1 = [1, 2, 2, 3, 4, 5];
const a2 = [2, 3, 4];

const result = isSubset(a1, a2);
console.log(result); // Output: true
```

## Solution 2(Using objects):

```javascript
function isSubset(a1, a2) {
  // Create an object to store the frequency of elements in a1
  const frequencyObj = {};

  // Count the frequency of elements in a1
  for (const num of a1) {
    frequencyObj[num] = (frequencyObj[num] || 0) + 1;
  }

  // Check if each element in a2 is present in a1 and has sufficient frequency
  for (const num of a2) {
    if (!frequencyObj[num] || frequencyObj[num] === 0) {
      return false; // Element not found or frequency exhausted
    }
    frequencyObj[num] -= 1;
  }

  return true;
}

// Example usage:
const a1 = [1, 2, 2, 3, 4, 5];
const a2 = [2, 3, 4];

const result = isSubset(a1, a2);
console.log(result); // Output: true
```

# Learning:

- forEach loop does not allow function break through return like in line no. 46 if we had forEach loop, return would not have worked
- in arrays use for ... of loop, for ... in oterates over indices as strings. For objects, for ... in loop iterates over keys.
