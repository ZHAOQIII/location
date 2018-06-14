## 问题分析： 
给定一个二叉树，返回所有从根节点到叶子节点的路径。

说明: 叶子节点是指没有子节点的节点。

## 代码实现
```c
class Solution {
public:
    vector<string> binaryTreePaths(TreeNode* root) {
        vector<string> res;
        if(root==NULL)
            return res;
        
        if(root->left==NULL && root->right ==NULL)
        {
            res.push_back(to_string(root->val));
            return res;
        }
        
        vector<string> lefts = binaryTreePaths(root->left);
        for(int i=0;i<lefts.size();++i)
            res.push_back(to_string(root->val)+"->"+lefts[i]);
        
        vector<string> rights = binaryTreePaths(root->right);
        for(int i=0;i<rights.size();++i)
            res.push_back(to_string(root->val)+"->"+rights[i]);
        return res;   
    }
};
```
## 总结：
递归，当前一个节点放入path中，左右子树分别继续往前走。左右子树只有当！= null时才继续找。