1. ## Q-1:Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.

  ## Approach 1:-

   ```
   class Solution:
    def isValid(self, s: str) -> bool:
        stack = []
        par = { ")" : "(", "]" : "[", "}" : "{" }

        for c in s:
            if c in par:
                if stack and stack[-1]== par[c]:
                    stack.pop()
                else:
                    return False
            else:
                stack.append(c)
        
        return True if not stack else False
   ```

   **Time Complexity:** O(n)  
   **Space Complexity:** O(n)

   ## Explanation:
 In this question using stack to ensure that each closing bracket matches the most recent opening bracket. When a closing bracket is encountered, it checks if the top of the stack has the corresponding opening bracket; if yes, it pops it. If not, returns false. 
