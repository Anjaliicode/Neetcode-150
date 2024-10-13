1. ## ValidPalindrome
   Given a string s, return true if it is a palindrome, otherwise return false.
   A palindrome is a string that reads the same forward and backward. It is also case-insensitive and ignores all non-alphanumeric characters.
   ## Approach 1:- Reverse String

     ```python
       class Solution:
        def isPalindrome(self, s: str) -> bool:
            new_s = "".join(c for c in s if c.isalnum()).lower()
            if new_s == new_s[::-1]:
                return True
            else:
                return False

          #Input: s = "Was it a car or a cat I saw?"
          # Output: true

     ```

     **Time Complexity:** O(n)  
     **Space Complexity:** O(n)

     ## Explanation:
     In this i am checking by reverse the string so for that firstly there are many space in string so for that i am using here join. The .isalnum() method returns true if a string is alphanumeric, and returns false otherwise. The .lower() method converts the entire string into lowercase characters and returns the result as new string .now we reverse the string and check the new string == string : if yes then print true otherwise false

     ---


    
