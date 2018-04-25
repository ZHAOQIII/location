## 问题分析： 
给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。


## 代码实现
```c
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
       if (head == 0) {
            return 0;
        }

        ListNode *node = head;
        while (node->next != 0) {
            if (node->val == node->next->val) {
                node->next = node->next->next;
            } else {
               node = node->next;
            }
        }
        return head;
    }
};
```
## 总结：
比较链表的当前值与下一个值，如果一样删除当前值。如果不一样，指针指向下一个数值作为新的当前值。