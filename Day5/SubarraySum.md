22-12-2023

# Problem statement

Given an unsorted array A of size N that contains only non negative integers, find a continuous sub-array that adds to a given number S and return the left and right index(1-based indexing) of that subarray.

In case of multiple subarrays, return the subarray indexes which come first on moving from left to right.

Note:- You have to return an ArrayList consisting of two elements left and right. In case no such subarray exists return an array consisting of element -1.

## Solution

```java
 static ArrayList<Integer> subarraySum(int[] arr, int n, int s)
    {
        // Your code here
         int start = 0;
        int last = 0;
        boolean flag=false;
        int currsum=0;
        ArrayList<Integer> res = new ArrayList<Integer>();

         //iterating over the array.
        for(int i=0;i<n;i++)
        {
            //storing sum upto current element.
            currsum+= arr[i];

            //checking if current sum is greater than or equal to given number.
            if(currsum>=s)
            {
                last=i;
                //we start from starting index till current index and do the
                //excluding part while s(given number) < currsum.
                while(s<currsum && start<last)
                {
                    //subtracting the element from left i.e., arr[start]
                    currsum-= arr[start];
                    ++start;
                }

                //now if current sum becomes equal to given number, we store
                //the starting and ending index for the subarray.
                if(currsum==s)
                {
                    res.add(start + 1);
                    res.add(last + 1);

                    //flag is set to true since subarray exists.
                    flag = true;
                    break;
                }
            }
        }
        //if no subarray is found, we store -1 in result else the found indexes.
        if (flag==false) {
            res.add(-1);
        }
        //returning the result.
        return res;
    }

```

# Learning:

- ArrayList implementation in Java
