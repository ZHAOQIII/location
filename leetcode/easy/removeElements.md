## 问题分析： 
删除链表中等于给定值 val 的所有节点。


## 代码实现
```c
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
      if(head==0) return head;  
    ListNode *p=head,*q=head->next;  
    while(q!=0){  
        if(q->val==val){  
        p->next=q->next;  
        q=q->next;  
    }else {  
        p=p->next;  
        q=q->next;  
    }  
    }  
     if(head->val==val)   head=head->next;  
     return head;  
    }
};
```
## 总结：
定义双指针，每次对头进行判断是否此值等于给定值val，如果相等则将此节点删除，将下一个节点作为头节点，否则将此节点的下一个节点为作为头节点，调用后的返回值作为此时头节点的下一个节点。