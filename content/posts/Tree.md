---
author: "Khaled Hossain"
title: "Top Tree problems"
date: 2023-10-07T18:06:32-06:00
draft: false
description: "Tree problems problems from leetcode"
FAtags: ["python", "tutorial"]
FAcategories: ["python", "tutorial"]
---

# Top Tree problems

## 199. Binary Tree Right Side View

###### Given the root of a binary tree, imagine yourself standing on the right side of it, return the values of the nodes you can see ordered from top to bottom.

Tree: [1, [2, [null, 5]], 3, [null, 4]]

This problem is fairly simple to solve, the key thing rember for this is the BFS traversal, whenever we think of BFS we think of queue's and popping from the left and appending the children to the right. 

```python
def rightSideView(self, root: Optional[TreeNode]) -> List[int]:
    res = []
    q = [root]
    while q: 
        rightSide = None
        qLen = len(q)

        for i in range(qLen):
            node = q.pop(0)
            if node: 
                rightSide = node
                q.append(node.left)
                q.append(node.right)
        
        
        if rightSide:
            res.append(rightSide.val)

    return res       
```
## 230. Kth Smallest Element in a BST

###### Given the root of a binary search tree, and an integer k, return the kth smallest value (1-indexed) of all the values of the nodes in the tree.

When solving this problem it's good to think of the inorder traversal to the get the order right and then just return the k-1th element. 

```python

    # in-order traversal
    def kthSmallest(self, root: TreeNode, k: int) -> int:
        n = 0
        stack = []
        cur = root

        while cur and stack:
            while cur:
                stack.append(cur)
                cur = cur.left
            
            cur = stack.pop()
            n += 1
            if n == k:
                return cur.val
            
            cur = cur.right
    # in-order traversal (recursive) O(N)
    def inOrderTraversal(self, root: TreeNode):
        res = []

        def inorder(root):
            if not root:
                return
            
            inorder(root.left)
            res.append(root.val)
            inorder(root.right)
        inorder(root)
        return res
    def kthSmallestRecursive(self, root: TreeNode ,k: int) -> int:
        res = []            
        def inorder(root):
            if not root:
                return
            inorder(root.left)            
            res.append(root.val)            
            inorder(root.right)
        inorder(root)

        return res[k-1]
```

