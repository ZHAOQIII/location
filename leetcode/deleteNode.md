## 问题分析： 
请编写一个函数，使其可以删除某个链表中给定的（非末尾）节点，你将只被给定要求被删除的节点。


## 代码实现
```c
class Solution {
public:
    void deleteNode(ListNode* node) {
         ListNode *s;  
      s=(ListNode*)malloc(sizeof(ListNode));  
      s->val=node->next->val;  
      s->next=node->next->next;  
      node->val=s->val;  
      node->next=s->next;  
    }
};
```
## 总结：
双指针完成删除功能。