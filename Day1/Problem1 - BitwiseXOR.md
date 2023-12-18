18-12-2023

# Problem Statement:

Given an array A of size N. The value of an array is denoted by the bit-wise XOR of all elements it contains. Find the bit-wise XOR of the values of all subarrays of A.

## Solution 1:

```javascript
function bitwiseXOROfSubarrays(arr) {
  let result = 0;

  for (let i = 0; i < arr.length; i++) {
    for (let j = i; j < arr.length; j++) {
      let subarrayXOR = arr[i];
      for (let k = i + 1; k <= j; k++) {
        subarrayXOR ^= arr[k];
      }
      result ^= subarrayXOR;
    }
  }

  return result;
}

// Example usage:
const array = [1, 2, 3];
const result = bitwiseXOROfSubarrays(array);
console.log(result);
```

Time complexity -> O(n^3)

## Optimized solution(using bitwise properties):

```javascript
function bitwiseXOROfSubarraysMostOptimized(arr) {
let result = 0;
let n = arr.length;

for (let i = 0; i < n; i++) {
let freq = (n - i) \* (i + 1); // n-i -> all subarrays ending at index i(elements to right of i) i+1 -> subarrays starting at i(elements to left of i)

    if (freq % 2 === 1) {
      result ^= arr[i];
    }

}

return result;
}

// Example usage:
const array = [1, 2, 3];
const result = bitwiseXOROfSubarraysMostOptimized(array);
console.log(result);
```

Time complexity -> O(n)

# Learning:

The optimized code is based on bitwise property which is as follows:
a^a = 0 (even repetition)
a^a^a = 0^a = a (odd repetition)
