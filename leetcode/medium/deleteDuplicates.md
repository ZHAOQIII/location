## 问题分析： 
给定一个排序链表，删除所有含有重复数字的节点，只保留原始链表中 没有重复出现 的数字。
## 代码实现
```c
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
       if(head==nullptr||head->next==nullptr)
			 return head;
		 ListNode *fakeNode =new ListNode(-1) ;
		 
		 ListNode *result=fakeNode;
		 ListNode *pre=head;
		 ListNode *cur=head;
		 while(cur!=nullptr&&cur->next!=nullptr)
		 {
			 while(cur->next!=nullptr&&cur->next->val==pre->val)
				 cur=cur->next;
			 if(cur==pre)
			 {
				 result->next=pre;
				 result=result->next;
			 }
			 pre=cur->next;
			 cur=cur->next;
		 }
		 result->next=cur;
		 return fakeNode->next;

    }
};
```
## 总结：
建立一个新的链表，把符合条件往里面加，定义两个指针一开始指向第一个节点，如果后面一个节点的值和前面相同，指针1就往后跑直到不相同，通过判断指针1和指针2是不是指向同一个节点就能知道有没有重复的元素。
      
