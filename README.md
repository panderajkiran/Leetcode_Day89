# Leetcode_Day89
# Day 89 – Evaluate Boolean Binary Tree

**LeetCode Problem:** [2331. Evaluate Boolean Binary Tree](https://leetcode.com/problems/evaluate-boolean-binary-tree/)  
**Difficulty:** Easy  
**Language:** Java  
**Topics:** Binary Tree, Recursion, Depth-First Search (DFS), Boolean Logic

## Problem Statement

Given the root of a full binary tree, evaluate the tree and return the final Boolean result.

- Leaf nodes contain `0` or `1`, representing `false` and `true`.
- Non-leaf nodes contain `2` or `3`.
- `2` represents the OR (`||`) operation.
- `3` represents the AND (`&&`) operation.

## Approach: Recursion

I solved this problem using recursion to evaluate the left and right subtrees.

1. If the current node is a leaf, return `true` if its value is `1`; otherwise, return `false`.
2. Recursively evaluate the left subtree.
3. Recursively evaluate the right subtree.
4. If the current node's value is `2`, return the OR of both results.
5. Otherwise, return the AND of both results.

### Java Solution

```java
class Solution {
    public boolean evaluateTree(TreeNode root) {
        if (root.left == null && root.right == null) {
            return root.val == 1;
        }

        boolean left = evaluateTree(root.left);
        boolean right = evaluateTree(root.right);

        if (root.val == 2) {
            return left || right;
        } else {
            return left && right;
        }
    }
}
```

## Complexity Analysis

- **Time Complexity:** `O(n)` — Each node is evaluated once.
- **Space Complexity:** `O(h)` — The recursive call stack depends on the height of the tree. In the worst case, it can be `O(n)`.

Here, `n` is the number of nodes and `h` is the height of the tree.

## What I Learned

- How to evaluate a binary tree using recursion.
- How to apply Boolean OR and AND operations to child nodes.
- Why identifying leaf nodes is important when solving tree problems.
- How smaller recursive results combine to produce the final answer.

## Takeaway

This problem showed me how recursion can turn a tree into a series of smaller decisions. Each node contributes a result, and those results come together to solve the entire problem.

**Day 89 complete — learning, practicing, and improving one problem at a time!** 🌱
