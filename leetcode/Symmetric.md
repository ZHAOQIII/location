## 问题分析： 
给定一个二叉树，检查它是否是镜像对称的。

例如，二叉树 [1,2,2,3,4,4,3] 是对称的。


## 代码实现
```c
class Solution {
public:
    bool isSymmetric(TreeNode* root) {
if (root == 0) {
            return true;
        }
        return isMirror(root->left, root->right);
    }
    public: 
     bool isMirror(TreeNode* leftNode, TreeNode* rightNode) {
        if (leftNode == 0 && rightNode == 0) {
            return true;
        } else if (
            (leftNode != 0 && rightNode == 0) ||
            (leftNode == 0 && rightNode != 0) ||
            leftNode->val != rightNode->val ||
            !isMirror(leftNode->left, rightNode->right) ||
            !isMirror(leftNode->right, rightNode->left)) {
            return false;
        } else {
            return true;
        }    
    }
};
```
## 总结：
首先判断左右子树是否为空子树，如果是，则输出true。否则判断两边是否相等，相等则输出true，否则输出false。