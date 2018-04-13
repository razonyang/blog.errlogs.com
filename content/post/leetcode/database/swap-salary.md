---
date: "2017-07-13T12:43:54+08:00"
comment: true
categories: ["database", "leetcode"]
tags: ["database", "mysql", "leetcode"]
title: "Leetcode 数据库面试题 - Swap Salary"
---

用一条 UPDATE 语句，在不使用中间临时表的情况下，将 salary 表中 sex 的值反转。
<!--more-->

# 原题

Given a table salary, such as the one below, that has m=male and f=female values. Swap all f and m values (i.e., change all f values to m and vice versa) with a single update query and no intermediate temp table.

For example:

| id | name | sex | salary |
|:--:|:----:|:---:|:------:|
| 1  | A    | m   | 2500   |
| 2  | B    | f   | 1500   |
| 3  | C    | m   | 5500   |
| 4  | D    | f   | 500    |

After running your query, the above salary table should have the following rows:

| id | name | sex | salary |
|:--:|:----:|:---:|:------:|
| 1  | A    | f   | 2500   |
| 2  | B    | m   | 1500   |
| 3  | C    | f   | 5500   |
| 4  | D    | m   | 500    |


# SQL

```
UPDATE salary 
SET 
    sex = IF(sex='f', 'm', 'f');
```

OR

```
UPDATE salary 
SET 
    sex = CASE sex 
        WHEN 'f' THEN 'm' 
        ELSE 'f' 
    END;
```