1. ## Q-1: Binary Search
   Given a string s, find the length of the longest substring without duplicate characters.
   A substring is a contiguous sequence of characters within a string.

    ## Approach 1:- TwoPointer
   ``` python
   def length_of_longest_substring(s: str) -> int:  
    char_set = set()  
    left = 0  
    max_length = 0  
    
    for right in range(len(s)):  
        while s[right] in char_set:  
            char_set.remove(s[left])  
            left += 1  
        
        char_set.add(s[right])  
        max_length = max(max_length, right - left + 1)  
    
    return max_length 
                
   
     #Input: s = "zxyzxyz"

     #Output: 3


   ```
    **Time Complexity:** O(n)  
    **Space Complexity:** O(n)
    ## Explanation: 
    In this question, using the two-pointer approach with left and right pointers. The right pointer is used to traverse the characters of the string. If a character is found in the set, it means a duplicate exists, so we move the left pointer towards the right. I declare a variable max_length which is tracking the current maximum length of the substring without duplicates.


