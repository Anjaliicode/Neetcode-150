1. ## Q-1: Is Anagram
   Given two strings s and t, return true if the two strings are anagrams of each other, otherwise return false.

   An anagram is a string that contains the exact same characters as another string, but the order of the characters can be different
   
   ## Approach 1:- Hash Map
   ``` python
   class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        ds={}
        for x in s:
            if x in ds:
                ds[x]+=1
            else:
                ds[x]=1
        dt={}
        for x in t:
            if x in dt:
                dt[x]+=1
            else:
                dt[x]=1
        if ds==dt:
            return True
        else:
            return False
                
   
     #Input: s = "racecar", t = "carrace"
     #Output: true


   ```
   **Time Complexity:** O(m+n)  
   **Space Complexity:** O(1)
   ## Explanation: 
   for checking that both string are anagram or not i am using 2 dict for both string in which iterating a loop over strings and then check if letter in dict then increse its count by +1 and if not then add that letter in dict by value one after that we will check both string dict equal or not if equal then return true else return false


