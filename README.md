# Reorder-List
You are given the head of a singly linked-list. The list can be represented as:  L0 → L1 → … → Ln - 1 → Ln Reorder the list to be on the following form:  L0 → Ln → L1 → Ln - 1 → L2 → Ln - 2 → … You may not modify the values in the list's nodes. Only nodes themselves may be changed.

# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def reorderList(self, head):
        """
        :type head: ListNode
        :rtype: None Do not return anything, modify head in-place instead.
        """
        firstHalf, secondHalf = head, head.next
        while secondHalf and secondHalf.next:
            firstHalf = firstHalf.next
            secondHalf = secondHalf.next.next

    
        prev, curr = None, firstHalf.next
        firstHalf.next = None
        while (curr):
            temp = curr.next
            curr.next = prev
            prev = curr
            curr = temp

        list1 = head 
        list2 = prev
        while list2:
            list1next = list1.next  
            list2next = list2.next  
            
            list1.next = list2  
            list2.next = list1next  
            
            list1 = list1next  
            list2 = list2next  
