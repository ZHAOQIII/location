## 问题分析： 
编写一个 SQL 查询，获取 Employee 表中第二高的薪水（Salary） 。


## 代码实现
```c
SELECT
    (SELECT DISTINCT
            Salary
        FROM
            Employee
        ORDER BY Salary DESC
        LIMIT 1 OFFSET 1) AS SecondHighestSalary
;
```
## 总结：
先将employee表排序，找到第二高的薪水。