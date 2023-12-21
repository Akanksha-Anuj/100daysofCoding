21-12-2023

# Problem Statement

Given an array of N strings, find the longest common prefix among all strings present in the array.

## Approach:

```Java
String longestCommonPrefix(String arr[], int n){
        // code here
        Arrays.sort(arr);
        String s1 = arr[0];
        String s2=arr[n-1];
        int size1=s1.length(), size2=s2.length(), p1=0,p2=0;

        String prefix = arr[0];
        for(int i=1;i<n;i++){
         while(arr[i].indexOf(prefix) != 0){
                prefix = prefix.substring(0, prefix.length()-1);
            }
    }
        if(prefix.length()==0)
        return "-1";
        else return prefix;
    }
```

# Learning:

- changing coding language to Java
