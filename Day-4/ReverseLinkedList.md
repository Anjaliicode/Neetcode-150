1. ## Q-1: Binary Search
   Given the beginning of a singly linked list head, reverse the list, and return the new beginning of the list.

    ## Approach 1:- 
   ``` python
   class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        previous = None  
        current = head  

        while current is not None:
            next_node = current.next  
            current.next = previous    
            previous = current          
            current = next_node 
        return previous
                
   
     #Input: head = [0,1,2,3]
     #Output: [3,2,1,0]


   ```
    **Time Complexity:** O(n)  
    **Space Complexity:** O(1)
    ## Explanation: 
    first find the mid then comspare the mid with the target value which is given if mid == target then simple return mid but if target>mid then then start = mid+1and if target is less than mid then end=mid-1 


