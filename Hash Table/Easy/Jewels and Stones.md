[Jewels and Stones](https://leetcode.com/problems/jewels-and-stones/description/)

# Question  
You're given strings jewels representing the types of stones that are jewels, and stones representing the stones you have. Each character in stones is a type of stone you have. You want to know how many of the stones you have are also jewels.

Letters are case sensitive, so "a" is considered a different type of stone from "A".

# Concept  
**Input:** jewels = `"aA"`, stones = `"aAAbbbb"`  
**Output:** 3  
  
**Explanation**  
**First** stone in “stones” - `a` - `"a"AAbbbb`  
**Second** stone in “stones” - `A` - `a"A"Abbbb`  
**Third** stone in “stones” - `A` - `aA"A"bbbb`  

# Code  
```
class Solution {
    public int numJewelsInStones(String j, String s) {
        int count = 0;

        HashMap<Character, Integer> map = new HashMap<>();
        for (int i = 0; i < j.length(); i++) {
            map.put(j.charAt(i), i);
        }

        for (Character value : s.toCharArray()) {
            if (map.containsKey(value)) {
                count++;
            }
        }

        return count;
    }
}
```

