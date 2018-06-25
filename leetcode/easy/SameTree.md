## 问题分析： 
给定两个二叉树，编写一个函数来检验它们是否相同。

如果两个树在结构上相同，并且节点具有相同的值，则认为它们是相同的。


## 代码实现
```c
class Solution {
public:
    bool isSameTree(TreeNode* p, TreeNode* q) {
      if(p == NULL && q == NULL)  
            return true;  
        else{  
            if(p == NULL || q == NULL)  
                return false;  
            return (p->val == q->val   
                    && isSameTree(p->left,q->left)   
                    && isSameTree(p->right,q->right));  
        }     
    }
};
```
## 总结：
首先判断是否为空二叉树，两个空二叉树是相等的，只有其中一个为空时是不相等的。当两个二叉树都不为空时，判断左右子树是否相等，同时成立，两个二叉树才是相等的。