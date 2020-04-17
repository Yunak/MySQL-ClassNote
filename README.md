## 四月十七 
### 查询知识点总结 
#### 单表无条件查修
 - 查询所有字段信息：select *from 表名
 - 查询部分字段信息：select 字段名1，字段名2 from 表名
 - 查询结果中去重：distinct
  select distinct sno from sc
 - 返回查询结果中某几行：limit M，N 表示从第M行开始（默认0）,返回结果中的 N行
 - 设置显示的列名:as 重命名

#### where子句条件查询
 - 语法: select ...from 表名 where 表达式
 - 比较运算符 >< = >= !=
 - 逻辑运算符 and or not
 - 范围运算符 between 初始值 and 终止值
 - 字符运算符: like
   通配符%:任意多个字符 _:任意一个字符  

#### 列表运算符 in not in
例:
```
查询 信息工程系/软件工程系/计算机工程系 学生的姓名性别
select sname,ssex from student where sdept in('信息工程系','软件工程系','计算机工程系')
```
#### 空值的查询 is null /is not null
```
例:查询成绩非空的学生的学号、课程号和对应成绩
Select sno,cno,degree from sc where degree is not null
```