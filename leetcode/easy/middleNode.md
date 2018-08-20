## 问题分析： 
给定一个带有头结点 head 的非空单链表，返回链表的中间结点。

如果有两个中间结点，则返回第二个中间结点。
## 代码实现
```c
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
    ListNode*p1=head;
        ListNode*p2=head;
        while(p1!=NULL){
            p1=p1->next;
            if(p1!=NULL){
                p1=p1->next;
                p2=p2->next;
            }
        }
        return p2;
    }
};
```
## 总结：
构造两个指针，遍历链表，一个每次走一步，另一个每次走两步，一个遍历完链表，另一个恰好在中间。
      
      