## [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/submissions/1519950459)

## Steps

### Step 1 — Start with Two Pointers

We create two pointers:

- **Slow** pointer moves one step at a time.
- **Fast** pointer moves two steps at a time.

### Step 2 — Move Pointers in a Loop

We keep moving both pointers forward:

- **Slow** moves one step.
- **Fast** moves two steps.

### Step 3 — Check if They Meet

- If **slow** and **fast** meet, there is a cycle in the list.
- If **fast** reaches the end, there is no cycle.

### Step 4 — Return the Answer

- If **slow** meets **fast**, return `True` (cycle exists).
- If the loop ends, return `False` (no cycle).

## Complexity Analysis

- **Time Complexity:** `O(n)` → In the worst case, we traverse the linked list once.
- **Space Complexity:** `O(1)` → We use only two pointers, no extra space.

---

## [Linked List Cycle](https://leetcode.com/problems/middle-of-the-linked-list/submissions/1519952942)

## Steps

### Step 1 — Start with Two Pointers

We create two pointers:

- **Slow** pointer moves one step at a time.
- **Fast** pointer moves two steps at a time.

### Step 2 — Move Pointers in a Loop

We keep moving both pointers forward:

- **Slow** moves one step.
- **Fast** moves two steps.
- This continues until **fast** reaches the end of the list.

### Step 3 — Return the Middle Node

- When **fast** reaches the end, **slow** will be at the middle.
- Return **slow** as the middle node.

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the linked list once.
- **Space Complexity:** `O(1)` → We use only two pointers, no extra space.

---

## [Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/submissions/1519969754)

## Steps

### Step 1 — Start with Two Pointers

We create two pointers:

- **Slow** starts at index `0` and moves one step at a time.
- **Fast** starts at index `0` and moves two steps at a time.

### Step 2 — Find the Meeting Point

- Move **slow** by one step.
- Move **fast** by two steps.
- Keep moving until **slow** and **fast** meet.

### Step 3 — Reset One Pointer

- Set **slow** back to `0`.

### Step 4 — Find the Duplicate

- Move both **slow** and **fast** one step at a time.
- When they meet, that index contains the duplicate number.
- Return `nums[slow]`.

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the array at most twice.
- **Space Complexity:** `O(1)` → We use only two pointers, no extra space.

---

## [Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/submissions/1522353554)

## Steps

### Step 1 — Find the Middle of the List

- We use two pointers:
  - **Slow** pointer moves one step at a time.
  - **Fast** pointer moves two steps at a time.
- When **fast** reaches the end, **slow** will be at the middle of the list.

### Step 2 — Reverse the Second Half of the List

- We reverse the second half of the list starting from the **slow** pointer.
- We create a helper function `reverseList` to reverse the list.

### Step 3 — Compare Both Halves

- Compare each value from the start of the list and the reversed second half.
- If any pair of values don't match, return `False`.
- If all values match, return `True`.

### Step 4 — Clean Up

- After comparison, the dummy node's `next` is set to `None` to prevent it from affecting the original list.

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the list twice, once to find the middle and once to compare the two halves.
- **Space Complexity:** `O(1)` → We only use a few extra pointers, no additional space for storing data.

---

## [Maximum Twin Sum of a Linked List](https://leetcode.com/problems/maximum-twin-sum-of-a-linked-list/submissions/1522374139)

## Steps

### Step 1 — Find the Middle of the List

- Use two pointers:
  - **Slow** pointer moves one step at a time.
  - **Fast** pointer moves two steps at a time.
- When **fast** reaches the end, **slow** will be at the middle of the list.

### Step 2 — Reverse the Second Half of the List

- After finding the middle, we reverse the second half of the list starting from **slow.next** using the `reverseList` helper function.
- Set **slow.next** to `None` to break the link.

### Step 3 — Compare Pairwise Sum

- Start two pointers:
  - **node1** is at the reversed second half of the list.
  - **node2** is at the start of the list.
- For each pair, calculate the sum of `node1.val` and `node2.val`. Keep track of the maximum sum encountered.
- Return the maximum sum.

### Step 4 — Clean Up

- Set the dummy node and the first half pointer (`slow.next`) to `None` to prevent modification to the original list.

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the list to find the middle, reverse the second half, and compare the pairwise sums, all of which take linear time.
- **Space Complexity:** `O(1)` → We use only a few pointers for traversal and reversing, no additional space for storing data.

---

## [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/submissions/1523511547)

## Steps

### Step 1 — Initialize Dummy Node

- Create a dummy node (`dummyNode`) and set `newListHead` to it.
- Initialize two pointers (`node1` and `node2`) for `list1` and `list2`.

### Step 2 — Traverse Both Lists

- Traverse both lists and compare the values at `node1` and `node2`.
- Append the smaller node to `dummyNode.next`, and move the respective pointer forward.
- Repeat this until one of the lists is fully traversed.

### Step 3 — Attach the Remaining List

- If `node1` is not `None`, append the remaining part of `list1` to `dummyNode.next`.
- If `node2` is not `None`, append the remaining part of `list2` to `dummyNode.next`.

### Step 4 — Return the Merged List

- Return the merged list starting from `newListHead.next` (since `dummyNode` is just a placeholder).

## Complexity Analysis

- **Time Complexity:** `O(n + m)` → We traverse both lists once, where `n` is the length of `list1` and `m` is the length of `list2`.
- **Space Complexity:** `O(1)` → We only use a few extra pointers, no additional space for storing data.

---

## [Intersection of Two Linked Lists](https://leetcode.com/problems/intersection-of-two-linked-lists/submissions/1523530977)

## Steps

### Step 1 — Create a Cycle to Detect Intersection

- First, traverse list `A` to reach its last node.
- Link the last node of list `A` to the head of list `B`. This allows us to check for an intersection by creating a cycle if there is one.

### Step 2 — Detect Cycle Using Two Pointers

- Use two pointers, `slow` and `fast`, both starting at the head of list `A`.
- Move `slow` one step at a time, and `fast` two steps at a time.
- If `slow` and `fast` meet at any point, there is a cycle, meaning the two lists intersect.

### Step 3 — Return the Intersection Node

- If no cycle is detected, restore the original structure by setting `lastNode.next` to `None` and return `None`.
- If a cycle is detected, reset `slow` to the head of list `A` and move both pointers one step at a time until they meet.
- The meeting point is the intersection node.

### Step 4 — Clean Up

- Restore the original list structure by setting `lastNode.next` to `None` after the detection process.

## Complexity Analysis

- **Time Complexity:** `O(n + m)` → We traverse both lists and the cycle detection process. `n` is the length of list `A` and `m` is the length of list `B`.
- **Space Complexity:** `O(1)` → We use only a few pointers for traversal and cycle detection, no extra space required.

---

## [Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/submissions/1523539757)

## Steps

### Step 1 — Initialize Dummy Node

- Create a dummy node (`dNode`) and link it to the head of the list.
- Set `node` to point to the dummy node.

### Step 2 — Traverse the List

- Traverse the list while `node.next` is not `None`.
- For each node, check if the value of `node.next` equals the target value (`val`).
  - If it does, remove the node by skipping it (`node.next = node.next.next`).
  - Otherwise, move to the next node (`node = node.next`).

### Step 3 — Return the Modified List

- After traversal, if `dNode.next` is `None`, return `None` (list is empty).
- Otherwise, return `dNode.next` (the new head of the list).

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the entire list once, where `n` is the length of the list.
- **Space Complexity:** `O(1)` → We use only a few pointers for traversal, no extra space required.

---

## [Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/submissions/1524456957)

## Steps

### Step 1 — Detect a Cycle Using Two Pointers

- Initialize two pointers, `slow` and `fast`, both starting at the head of the list.
- Move `slow` one step at a time and `fast` two steps at a time.
- If `slow` and `fast` meet at any point, a cycle is detected.

### Step 2 — If No Cycle, Return `None`

- If `slow` and `fast` never meet, return `None` because there is no cycle in the list.

### Step 3 — Find the Cycle’s Starting Node

- Reset `slow` to the head of the list.
- Move both `slow` and `fast` one step at a time until they meet again.
- The meeting point is the starting node of the cycle.

### Step 4 — Return the Cycle’s Starting Node

- Return the node where `slow` and `fast` meet, which is the cycle's starting node.

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the list twice: once to detect a cycle and once to find the starting node of the cycle, where `n` is the length of the list.
- **Space Complexity:** `O(1)` → We only use two pointers (`slow` and `fast`), no extra space required.

---

## [Rotate List](https://leetcode.com/problems/rotate-list/submissions/1524468938)

## Steps

### Step 1 — Handle Base Cases

- If `k == 0`, or if the list is empty or has only one node, return the head as is.

### Step 2 — Calculate Length and Adjust `k`

- Calculate the length of the linked list using `getLen`.
- Adjust `k` to `k % len` to handle cases where `k` is larger than the list length.

### Step 3 — Reverse the Second Part of the List

- If `k == 0`, return the head as no rotation is needed.
- Otherwise, move the pointer `node1` to the node at position `len - k`.
- Reverse the list starting from `node1.next` using `reverseList`.

### Step 4 — Reverse the Entire List

- After reversing the second part, reverse it again to get the proper order.
- Set `newHead` to the head of the reversed second part.

### Step 5 — Attach the First Part Back to the List

- Traverse to the end of the reversed second part and attach the original head of the list to the end.

### Step 6 — Return the New Head

- Return the new head of the rotated list.

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the list multiple times: to calculate the length, reverse parts of the list, and attach the parts, where `n` is the length of the list.
- **Space Complexity:** `O(1)` → We use a constant amount of space for pointers, no extra space required.

---

## [Reorder List](https://leetcode.com/problems/reorder-list/submissions/1524484698)

## Steps

### Step 1 — Find the Middle of the List

- Use the slow and fast pointer technique to find the middle of the list.
  - The slow pointer moves one step at a time, while the fast pointer moves two steps at a time.
  - When the fast pointer reaches the end, the slow pointer will be at the middle of the list.

### Step 2 — Reverse the Second Half of the List

- Reverse the second half of the list starting from the node after the middle.
- Use the `reverseList` function to reverse the second half.

### Step 3 — Merge the Two Halves

- Start with the first node of the original list and the first node of the reversed second half.
- Alternate merging nodes from the first half and the second half, adjusting the pointers appropriately.
  - First, append a node from the first half, then append a node from the second half.
  - Repeat until all nodes are merged.

### Step 4 — Handle Remaining Nodes

- If any nodes are left in the first or second half after the merging, append them to the result.

### Step 5 — Update the Head

- Set `head` to point to the reordered list.

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the list multiple times: to find the middle, reverse the second half, and merge the two halves, where `n` is the length of the list.
- **Space Complexity:** `O(1)` → The solution modifies the list in place without using extra space for new nodes.

---

## [Partition List](https://leetcode.com/problems/partition-list/submissions/1524512429)

## Steps

### Step 1 — Initialize Two Lists

- Create two separate lists to store nodes less than `x` and nodes greater than or equal to `x`.
- Initialize two new `ListNode` objects: `node1` and `node2`, along with pointers `cur1` and `cur2` to build these two lists.

### Step 2 — Traverse the Input List

- Iterate through the original list, checking the value of each node:
  - If the value is **greater than or equal to `x`**, append the node to the second list (i.e., `node2`).
  - If the value is **less than `x`**, append the node to the first list (i.e., `node1`).

### Step 3 — Merge the Two Lists

- Once the list has been traversed, the second list (`node2`) is linked to `None` (to prevent cycles).
- Link the end of the first list to the beginning of the second list (i.e., `cur1.next = node2.next`).

### Step 4 — Return the Result

- Return the head of the first list, i.e., `node1.next`, which contains the partitioned list.

## Complexity Analysis

- **Time Complexity:** `O(n)` → We traverse the entire list once where `n` is the number of nodes in the input list.
- **Space Complexity:** `O(1)` → We only use a constant amount of extra space for pointers, and the list is rearranged in place.
