2. ## Q-2: Two Integer Sum
   Given an array of integers nums and an integer target, return the indices i and j such that nums[i] + nums[j] == target and i != j.
   You may assume that every input has exactly one pair of indices i and j that satisfy the condition.
   Return the answer with the smaller index first.  
   <details>  
   <summary>Solution</summary>  
   
   ## Approach 1:- BruteForce Approach
   
   ``` python
    class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i+1,len(nums)):
                if nums[i]+nums[j]==target:
                    return [i,j]
   #Input: 
   #nums = [3,4,5,6], target = 7

   #Output: [0,1]

   ```
   
   **Time Complexity:** O(n^2)  
   **Space Complexity:** O(1)
   
   ## Explanation:
   This is two-pointer approch in which pointer i iterate from index 0 to len(nums) and pointer j will iterate from index i+1 to len(num). we check if 
   nums[i]+nums[j]==target then it will return index [i,j]
   
   ## Approach 2:- Hashmap
   
   ``` python
   class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        nums2 = {}  
        for i in range(len(nums)):  
            num = nums[i]  
            second_num = target - num  
            if second_num in nums2: 
                return [nums2[second_num], i ]
            nums2[num] = i 

   ```
   
    **Time Complexity:** O(n)  
    **Space Complexity:** O(n)
   
     ## Explanation:
     To reduce T(c), useing hashMap technique by creating an empty dictionary which use to store numbers and their indices Then Iterate pointer i from 0 to len(nums). 
     For each iteration, we store the value at index i in a variable num, and declare a second variable second_num which calculate second_num as target - num. Check if second_num exists in the 
     dictionary; if it does then return its index along with the index of num.
   
   
</details>