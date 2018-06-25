## 问题分析： 
某网站包含两个表，Customers 表和 Orders 表。编写一个 SQL 查询，找出所有从不订购任何东西的客户。

## 代码实现
```c
SELECT Name AS Customers FROM Customers 
WHERE Id NOT IN (SELECT CustomerId FROM Orders);
```
## 总结：
找没有在Orders表中出现的顾客Id，然后从Customers表中找出名字。