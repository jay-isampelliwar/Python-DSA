Cycle Detection in Linked List

This repository contains a Python implementation to detect a cycle in a linked list using the Floyd’s Cycle Detection Algorithm (Tortoise and Hare approach).

Problem Statement

Determine if a given singly linked list has a cycle in it. A cycle occurs when a node’s next pointer points back to a previous node, forming a loop within the list.

Example

Input:

A linked list where a node points back to a previous node, creating a cycle.

Output:

True if a cycle exists; otherwise, False.

Solution Explanation

The algorithm uses two pointers, slow and fast. Initially, both pointers start at the head of the list:

The slow pointer moves one step at a time.

The fast pointer moves two steps at a time.

If there is a cycle, the slow pointer and the fast pointer will eventually meet inside the cycle.

If the fast pointer reaches the end of the list (fast or fast.next becomes None), the list does not contain a cycle.

Steps to Solve the Problem

Follow these steps to implement the solution:

Initialize two pointers, slow and fast, both pointing to the head of the linked list.

Traverse the list using a loop:

Move slow one step forward.

Move fast two steps forward.

Check if slow equals fast. If they are equal, a cycle exists. Return True.

If the loop exits without slow meeting fast, return False.

Code

Here’s the Python implementation:

# Definition for singly-linked list.

class ListNode:
def **init**(self, value=0, next=None):
self.value = value
self.next = next

def hasCycle(head):
slow = head
fast = head

    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next

        if slow == fast:
            return True

    return False

How to Use

Clone this repository:

git clone <repository-url>

Create a linked list structure and pass the head node to the hasCycle function.

Run the script to check if the linked list contains a cycle.

LeetCode Solution Link

You can view the solution and solve similar problems on LeetCode:

Add Your LeetCode Solution Link Here

Feel free to contribute by submitting pull requests or reporting issues!
