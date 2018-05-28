## 问题分析： 
编写一个 SQL 查询，来删除 Person 表中所有重复的电子邮箱，重复的邮箱里只保留 Id 最小 的那个。


## 代码实现
```c
DELETE p1 FROM Person p1,
    Person p2
WHERE
    p1.Email = p2.Email AND p1.Id > p2.Id
```
## 总结：
找出p1和p2中email相等并且p1的id大于p2，删除p1中该id值对应的字段即可。