## 问题分析： 

计算给定二叉树的所有左叶子之和。

## 代码实现
```c
class Solution {
public:
    int sumOfLeftLeaves(TreeNode* root) {
       if (!root) return 0;
        if (root->left && !root->left->left && !root->left->right)
            return root->left->val + sumOfLeftLeaves(root->right);
        return sumOfLeftLeaves(root->left) + sumOfLeftLeaves(root->right);   
    }
};

```
## 总结：
采用递归算法，以根节点为基点，遍历所有的左节点，并相加。