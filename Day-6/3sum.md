1. ## Q-1:Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0.

Notice that the solution set must not contain duplicate triplets.

  ## Approach 1:-

   ```
   class Solution:  
    def threeSum(self, nums: List[int]) -> List[List[int]]:  
        res = set() 
        nums.sort()  
        for i in range(len(nums) - 2):  
            for j in range(i + 1, len(nums) - 1):  
                for k in range(j + 1, len(nums)):  
                    if nums[i] + nums[j] + nums[k] == 0:  
                        res.add(tuple(sorted([nums[i], nums[j], nums[k]]))) 
        return [list(triplet) for triplet in res]  
   ```

   **Time Complexity:** O(n^3)  
   **Space Complexity:** O(n)

   ## Explanation:
    In this solution, I am using three pointers, with each pointer starting from a different index in the sorted array. We check if the sum of the triplet is equal to zero; if it is, we append it to the result. To ensure the triplets are unique, I am using a set to store them

   ***

   ## Approach 2:-

   ```
   class Solution:  
    def threeSum(self, nums: List[int]) -> List[List[int]]:  
        res = []  
        nums.sort()  
        for i in range(len(nums) - 2):  
            if i > 0 and nums[i] == nums[i - 1]:   
                continue  
            j, k = i + 1, len(nums) - 1  
            while j < k:  
                total = nums[i] + nums[j] + nums[k]  
                if total < 0:  
                    j += 1  
                elif total > 0:  
                    k -= 1  
                else:  
                    res.append([nums[i], nums[j], nums[k]])  
                    while j < k and nums[j] == nums[j + 1]: 
                        j += 1  
                    while j < k and nums[k] == nums[k - 1]:   
                        k -= 1  
                    j += 1  
                    k -= 1  
        return res  

   ```

   **Time Complexity:-** O(n^2)  
   **Space Complexity:-** O(1)

   ## Explanation:

   In this solution, I first sort the array. Then, I iterate through the array using a pointer i, checking for duplicates to avoid repeating the same triplet. For each unique i, I use two pointers, j and k, starting from the indices just after i and the end of the array, respectively. I calculate the sum of the triplet formed by nums[i], nums[j], and nums[k]. Depending on the sum, I either move the left pointer j to the right or the right pointer k to the left. If the sum is zero, I add the triplet to the result and skip duplicate values by adjusting j and k.