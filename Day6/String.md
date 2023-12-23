# Problem Statement

Given two strings a and b consisting of lowercase characters. The task is to check whether two given strings are an anagram of each other or not. An anagram of a string is another string that contains the same characters, only the order of characters can be different. For example, act and tac are an anagram of each other.

## Solution:

```java
public static boolean isAnagram(String a,String b)
    {
        if(a.length() != b.length())
        return false;

        // Your code here
        for(int i=0;i<a.length();i++){
            int index = b.indexOf(a.charAt(i));
            if( index != -1){
                b = b.substring(0,index)+ b.substring(index+1);

            }
            else return false;
        }
        return true;

    }
```

# Learning:

- Need to focus more on edge cases for simple programs as well.
- Focus more on Time complexity values.
