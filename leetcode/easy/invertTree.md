## 问题分析： 
反转二叉树。


## 代码实现
```c
class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
      if (root == nullptr) {
            return 0;
        }

        TreeNode *tempNode = root->left;
        root->left = root->right;
        root->right = tempNode;

        invertTree(root->left);
        invertTree(root->right);

        return root;   
    }
};
```
## 总结：
先交换左右子树，然后递归反转整个二叉树。