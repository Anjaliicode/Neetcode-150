1. ## Q-1: Binary Search
   Given the beginning of a linked list head, return true if there is a cycle in the linked list. Otherwise, return false.
   There is a cycle in a linked list if at least one node in the list that can be visited again by following the next pointer.
   Internally, index determines the index of the beginning of the cycle, if it exists. The tail node of the list will set it's next pointer to the index-th node. If index = -1, then the tail node points to null and no cycle exists.

    ## Approach 1:- Two pointer 
   ``` python
   class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        slow=head
        fast=head
        while fast!=None and fast.next!=None:
            slow=slow.next
            fast=fast.next.next
            if slow == fast:
                return True
        return False
                
   
     #Input: head = [1,2], index = -1
     #Output: false


   ```
    **Time Complexity:** O(n)
    **Space Complexity:** O(1)
    ## Explanation: 
    first find the mid then comspare the mid with the target value which is given if mid == target then simple return mid but if target>mid then then start = mid+1and if target is less than mid then end=mid-1 


