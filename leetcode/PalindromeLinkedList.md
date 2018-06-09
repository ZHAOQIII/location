## 问题分析： 
请判断一个链表是否为回文链表。

## 代码实现
```c
class Solution {
public:
    bool isPalindrome(ListNode* head) {
       vector<int> v;
        while(head)
        {
            v.push_back(head->val);
            head = head->next;
        }
        for(int i = 0, j = v.size()-1; i < j; i ++, j --)
        {
            if(v[i] != v[j])
                return false;
        }
        return true;   
    }
};
```
## 总结：
一次遍历，装入vector，然后再一次遍历判断回文。。