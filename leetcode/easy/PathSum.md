## 问题分析： 
给定一个二叉树和一个目标和，判断该树中是否存在根节点到叶子节点的路径，这条路径上所有节点值相加等于目标和。


## 代码实现
```c
class Solution {
public:
    bool hasPathSum(TreeNode* root, int sum) {
       if (root ==0)  return false;
        if(root->val == sum && root->left == 0 && root->right == 0) return true;
         return hasPathSum(root->right, sum-root->val) || hasPathSum(root->left, sum-root->val);
    }
};
```
## 总结：
首先判断是否为空二叉树，如果为空则返回false。然后判断是否有左右子树，当左右子树为空时，只有根节点等于目标值时，返回true。当两个二叉树都不为空时，用目标值减去根节点的值作为新的目标值，遍历左右子树。