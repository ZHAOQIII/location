## 问题分析： 
反转一个单链表。


## 代码实现
```c
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
   if(head==nullptr||head->next==nullptr)
        {
            return head;
        }
        ListNode *p=head;
        head=reverseList(p->next);
        p->next->next=p;
        p->next=nullptr;
        return head;  
    }
};
```
## 总结：
递归,在反转当前节点之前先反转后续节点。