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

better time complexity:

```java
 public static boolean isAnagram(String a,String b)
    {
        if(a.length() != b.length())
        return false;
        HashMap<Character, Integer> hm = new HashMap<>();
        // Your code here
        for(int i=0;i<a.length();i++){
            if(hm.containsKey(a.charAt(i))){
                hm.put(a.charAt(i), hm.get(a.charAt(i))+1);
            }
            else {
                hm.put(a.charAt(i),1);
            }

            }
            for(int i=0;i<b.length();i++){
                if(!hm.containsKey(b.charAt(i)))
                return false;
                else{
                    int value = hm.get(b.charAt(i));
                    value--;
                    if(value <0)
                    return false;
                    else hm.put(b.charAt(i), value);

                }
            }
            return true;
        }

```

# Learning:

- Need to focus more on edge cases for simple programs as well.
- Focus more on Time complexity values.
