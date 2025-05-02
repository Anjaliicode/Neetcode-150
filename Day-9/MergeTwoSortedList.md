1. ## Q-1: Merged Two sorted List
You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.

  ## Approach 1:-

   ```
   class Solution(object):
    def mergeTwoLists(self, list1, list2):
        head = ListNode()
        current = head
        while list1 and list2:
            if list1.val < list2.val:
                current.next = list1
                list1 = list1.next
            else:
                current.next = list2
                list2 = list2.next
            current = current.next

        current.next = list1 or list2
        return head.next
   ```

   **Time Complexity:** O(n+m)  
   **Space Complexity:** O(1)

   ## Explanation:
   initialize a dummy node (head) and Use a pointer (current) to build the merged linked list.While both lists are non-empty we will Compare their current node values and Append the smaller node to the current.next then Move forward in the list from which a node was taken then Move current forward to ensure the list is correctly built after the loop, append the remaining nodes of either list if any remain.and then Return head.next as the start of the merged list.
   Because each node in both lists is processed exactly once.
   The while loop  either list1 or list2 each iteration, and the total steps sum to n + m.

   ***



