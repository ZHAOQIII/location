## 问题分析： 
给定一个二叉树，找出其最大深度。

二叉树的深度为根节点到最远叶子节点的最长路径上的节点数。

说明: 叶子节点是指没有子节点的节点。


## 代码实现
```c
class Solution {
public:
    int maxDepth(TreeNode* root) {
       if(root == NULL) return 0;
         int l = maxDepth(root->left)+1;
         int r = maxDepth(root->right)+1;
         return l > r ? l : r;    
    }
};
```
## 总结：
二叉树的深度等于二叉树的高度，也就等于根节点的高度。根节点的高度为左右子树的高度较大者+1。然后比较左右子树的深度。