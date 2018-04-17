## 问题分析： 
将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。


## 代码实现
```c
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
    if (l1 == NULL) return l2;
    if (l2 == NULL) return l1;
    if (l1->val > l2->val) {
      ListNode *tmp = l2;
      tmp->next = mergeTwoLists(l1, l2->next);
      return tmp;
    } else {
      ListNode *tmp = l1;
      tmp->next = mergeTwoLists(l1->next, l2);
      return tmp;
    }
  }
};
```
## 总结：
构造一个新的ListNode tmp，作为临时变量，每次都会将l1或者l2赋值给它，每次return的tmp都是一个新的链表，最后一次返回的也就是我们所合并出来的链表。。