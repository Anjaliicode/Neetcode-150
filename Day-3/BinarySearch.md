1. ## Q-1: Binary Search
   You are given an array of distinct integers nums, sorted in ascending order, and an integer target.
  Implement a function to search for target within nums. If it exists, then return its index, otherwise, return -1.


   <details>  
   <summary>Solution</summary>  
   
   
    ## Approach 1:- Binary Search Approach
   ``` python
   class Solution:
    def search(self, nums: List[int], target: int) -> int:
        start=0
        end=len(nums)-1
        while start<=end:
            mid=start+((end-start)//2)
            if nums[mid]==target:
                return mid
            if target>nums[mid]:
                start=mid+1
            else:
                end=mid-1
        return -1
                
   
     #Input: nums = [-1,0,2,4,6,8], target = 4
     #Output: 3

   ```
   **Time Complexity:** O(log(n))  
   **Space Complexity:** O(1)
    ## Explanation: 
 first find the mid then comspare the mid with the target value which is given if mid == target then simple return mid but if target>mid then then start = mid+1and if target is less than mid then end=mid-1 

</details> 
