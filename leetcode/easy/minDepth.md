## 问题分析： 
给定一个二叉树，找出其最小深度。

最小深度是从根节点到最近叶子节点的最短路径上的节点数量。

说明: 叶子节点是指没有子节点的节点。


## 代码实现
```c
class Solution {
public:
    int minDepth(TreeNode* root) {
        if(root == NULL) return 0;
    if (root->left == NULL && root->right == NULL)   return 1;   
        if (root->left == NULL)  
        {  
            return 1 + minDepth(root->right);  
        }  
        else if (root->right == NULL)  
        {  
            return 1 + minDepth(root->left);  
        }  
        else   
        {  
            int left = minDepth(root->left);  
            int right = minDepth(root->right);  
          
            return 1 + min(left, right);  
        }  
    }  
    };
```
## 总结：
判断左子树或右子树是否为空，若左子树为空，则返回右子树的深度，反之返回左子树的深度，如果都不为空，则返回左子树和右子树深度的最小值。