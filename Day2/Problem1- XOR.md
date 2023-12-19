19-12-2023

# Problem Statement

Given two numbers M and N. The task is to find the position of the rightmost different bit in the binary representation of numbers. If both M and N are the same then return -1 in this case.

## Solution:

```javascript
posOfRightMostDiffBit(m, n);
{
  // code here
  let xorResult = m ^ n;
  if (xorResult === 0) return -1;

  let position = 0;
  while ((xorResult & 1) === 0) {
    xorResult >>= 1;
    position++;
  }
  return position + 1;
}
```

# Learning

- & with 1 masks all but rightmost bit.
- right shift: 1101>>1 -> 0110 shifts towards right fill left with 0s
- to convert decimal to binary: num=10
  num.toString(2) -> 2 denotes base of number.  
   padStart to fix length: num.toString(2).padStart(8,'0')
- Time Complexity: O(n)
