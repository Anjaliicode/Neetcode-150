1. ## Q-1: Two Sum Sorted
   Given an array of integers numbers that is sorted in non-decreasing order.

  Return the indices (1-indexed) of two numbers, [index1, index2], such that they add up to a given target number target and index1 < index2. Note that index1 and index2 cannot be equal, therefore you may not use the same element twice.

    There will always be exactly one valid solution.


   <details>  
   <summary>Solution</summary>  
   
   ## Approach 1:- BruteForce Approach
   
   ``` python
   class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        for i in range(len(numbers)):
            for j in range(i + 1, len(numbers)):
                if numbers[i] + numbers[j] == target:
                    return [i + 1, j + 1]
        return []  
  
   
   ```
   **Time Complexity:** O(n^2)  
   **Space Complexity:** O(1) 
   
   ## Explanation: 
   This is two-pointer approch in which pointer i iterate from index 0 to len(nums) and pointer j will iterate from index i+1 to len(num). we check if 
   nums[i]+nums[j]==target then it will return index of i and index of j
   
   ***
    ## Approach 2:- Two Pointer (oppsite direction)
   ``` python
   class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        i=0
        j=len(numbers)-1
        while i<j:
            if numbers[i]+numbers[j]==target:
                return [i+1,j+1]
            elif numbers[i]+numbers[j]>target:
                j-=1
            else:
                i+=1
        return[]
   ```
   **Time Complexity:** O(n)  
   **Space Complexity:** O(1)
    ## Explanation: 
   To reduce S(C), we are using two pointer approch but they are in  opposite direction. pointer i will move from index 0 and pointer j will move from the len(num) till i < j then it will check if numbers[i]+numbers[j]==target: then it return directly index of i and index of j but if numbers[i]+numbers[j]>target:then we will move j-1 because array is sorted and sum is greater than target and if sum is less than target then we will move i+1 and iterate till we din't get one pair of numbers
</details> 
