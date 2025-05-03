1. ## Q-1:Given the head of a linked list, remove the nth node from the end of the list and return its head.

  ## Approach 1:-

   ```
   class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        fast, slow = head, head
        for _ in range(n): 
            fast = fast.next
        if not fast: 
            return head.next
        while fast.next: 
            fast, slow = fast.next, slow.next
        slow.next = slow.next.next
        return head

   ```

   **Time Complexity:** O(n)  
   **Space Complexity:** O(1)

   ## Explanation:
   I’m using a two-pointer  to solve this problem. We start by placing both the slow and fast pointers at the head of the linked list. First, we move the fast pointer ahead by n nodes to create a fixed gap between the two pointers. If at this point the fast pointer becomes null, it means we need to remove the head node, so we simply return head.next. Otherwise, we then move both pointers forward together until the fast pointer reaches the last node of the list. At this stage, the slow pointer will be positioned just before the node we want to remove. To delete the target node, we just make slow.next skip over it by pointing to slow.next.next. Finally, we return the modified head of the list.
   we are traversing the node only for once so the TC(N) of Sc(1)

   ***



