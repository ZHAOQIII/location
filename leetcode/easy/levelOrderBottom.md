## 问题分析： 
给定一个二叉树，返回其节点值自底向上的层次遍历。 （即按从叶子节点所在层到根节点所在的层，逐层从左向右遍历）


## 代码实现
```c
class Solution {
public:
    int get_h(TreeNode *root)
    {
        if (root == NULL)
            return 0;
        int left, right;
        left = get_h(root->left);
        right = get_h(root->right);
        return left> right ? left + 1 : right + 1;
    }
    void get_elements(TreeNode *root, vector<int>& data, int h)
    {
        if (root == NULL)
            return;
        if (h == 1)
            data.push_back(root->val);
        get_elements(root->left, data, h - 1);
        get_elements(root->right, data, h - 1);
    }
    vector<vector<int>> levelOrderBottom(TreeNode* root) {
        int h = get_h(root);
        vector<int> data;
        vector<decltype(data)> ret;
        for (int i = h; i > 0; --i)
        {
            get_elements(root, data, i);
            ret.push_back(data);
            data.clear();
        }
        return ret;
    }
};
```
## 总结：
从下往上分层遍历二叉树。将二叉树的节点采用入栈出栈的方式，即可将遍历二叉树变为从下往上遍历二叉树。