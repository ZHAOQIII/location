## 问题分析： 

给定一个链表，判断链表中是否有环。


## 代码实现
```c
class Solution {
public:
    bool hasCycle(ListNode *head) { 
        if(head==0 || head->next==0)  
           return false;  
        ListNode *p1=head;  
        ListNode *p2=head;  
        while(p2 && p2->next){  
            p1=p1->next;  
            p2=p2->next->next;  
            if(p1==p2)  
                return true;  
        }  
        return false;  
        
    }
};
```
## 总结：
用两个指针，一快一慢，如果在快的指针能够追上慢的指针，则有环，否则无环。