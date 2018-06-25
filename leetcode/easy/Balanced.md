## 问题分析： 
给定一个二叉树，判断它是否是高度平衡的二叉树。

本题中，一棵高度平衡二叉树定义为：

一个二叉树每个节点 的左右两个子树的高度差的绝对值不超过1。


## 代码实现
```c
class Solution {
public:
   int getHeight(TreeNode* root){
         if(root == NULL) return 0;
         int l = getHeight(root->left);
         int r = getHeight(root->right);
         return l > r ? l+1 : r+1;
     }
     bool isBalanced(TreeNode* root) {
         if(root == NULL) return true;
         if(getHeight(root->left) - getHeight(root->right) > 1) return false;
         else if(getHeight(root->right) - getHeight(root->left) > 1) return false;
         else return isBalanced(root->left) && isBalanced(root->right);
     }
}; 
```
## 总结：
首先判断是否为空二叉树。其次得到左右子树高度判断高度差的绝对值不超过1，成立时二叉树是平衡二叉树。