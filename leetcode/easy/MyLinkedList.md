## 问题分析： 
设计链表的实现。您可以选择使用单链表或双链表。单链表中的节点应该具有两个属性：val 和 next。val 是当前节点的值，next 是指向下一个节点的指针/引用。如果要使用双向链表，则还需要一个属性 prev 以指示链表中的上一个节点。假设链表中的所有节点都是 0-index 的。

在链表类中实现这些功能：

get(index)：获取链表中第 index 个节点的值。如果索引无效，则返回-1。  

addAtHead(val)：在链表的第一个元素之前添加一个值为 val 的节点。插入后，新节点将成为链表的第一个节点。   

addAtTail(val)：将值为 val 的节点追加到链表的最后一个元素。
  
addAtIndex(index,val)：在链表中的第 index 个节点之前添加值为 val 的节点。如果 index 等于链表的长度，则该节点将附加到链表的末尾。如果 index 大于链表长度，则不会插入节点。
  
deleteAtIndex(index)：如果索引 index 有效，则删除链表中的第 index 个节点。
## 代码实现
```c
class MyLinkedList {
public:
    /** Initialize your data structure here. */
    MyLinkedList() {
        
    }
    vector<int> myList;
    /** Get the value of the index-th node in the linked list. If the index is invalid, return -1. */
    int get(int index) {
     if(index < 0 || index >= myList.size())
            return -1;
        return myList[index];   
    }
    
    /** Add a node of value val before the first element of the linked list. After the insertion, the new node will be the first node of the linked list. */
    void addAtHead(int val) {
      myList.insert(myList.begin(), val);   
    }
    
    /** Append a node of value val to the last element of the linked list. */
    void addAtTail(int val) {
      myList.push_back(val);  
    }
    
    /** Add a node of value val before the index-th node in the linked list. If index equals to the length of linked list, the node will be appended to the end of linked list. If index is greater than the length, the node will not be inserted. */
    void addAtIndex(int index, int val) {
      if(index > myList.size())
           return ;
       else if(index == myList.size())
           myList.push_back(val);
       else
           myList.insert(myList.begin()+index, val);  
    }
    
    /** Delete the index-th node in the linked list, if the index is valid. */
    void deleteAtIndex(int index) {
     if(index >= myList.size())
            return ;
        myList.erase(myList.begin()+index);   
    }
};
```
## 总结：
get(index)：当index索引无效，则返回-1。否则返回当前索引的值。  

addAtHead(val)：在链表的开始用insert插入val。   

addAtTail(val)：采用入栈的方式将值为 val 的节点追加到链表的最后一个元素。
  
addAtIndex(index,val)：先判断index处于的位置，如果处于链表中，在链表中的第 index 个节点之前添加值为 val 的节点。如果 index 等于链表的长度，则该节点入栈到链表的末尾。如果 index 大于链表长度，则不会插入节点。
  
deleteAtIndex(index)：如果索引 index 有效，则用erase删除链表中的第 index 个节点。
      
      
      