## 0423 最后一周,最后一次上课  
### 创建数据库 `create database 数据库名字`  
### 删除数据库 `drop database 数据库名字 `
### 打开数据库 `use 数据库名字`
### 查看当前数据库 `show databases`
### 创建表
- 表的命名:简单明了
- 常用的数据类型:
 - 整数类型  int
 - 浮点类型  float double decimal
 - 字符串类型 char varchar
 - 时间类型 date year time
 
### 创建表的语法

```
create table 表名

( 字段1 数据类型1 [列级完整性约束条件],
  字段2 数据类型2 [列级完整性约束条件],
  字段3 数据类型3 [列级完整性约束条件],
      .......
  字段n 数据类型n [列级完整性约束条件]
):
```
 - 列级约束性条件:
  - 主键primary key
  - 默认值 default ''
  - 非空 not null 
 - 表级约束性条件:
  - 设置联合主键 `constraint 约束名 primary key(字段名1,字段名2)`
  - 设置外键约束:`Constraint约束名Foreign Key(外键字段名)References 被参考表名(外键字段名/也就是被参考表的主键)`

### 查看表的结构 `desc 表名`
- 查看表的详细结构 `show create table 表名`
- 查看当前数据库中有哪些表`show tables`  

### 修改表的结构
- 添加字段: `add `
```
alter table 表名 add 新字段名 新数据库类型 [约束条件]
```
- 修改字段名`change`
```
alter table 表名 change 旧字段名 新字段名 数据类型
```
- 修改数据而类型和列级约束性条件`modify`
```
alter table 表名 modfiy 字段名 新数据类型 [列级约束性条件]
```
- 删除字段名或者约束性条件`drop`
```
alter table
```
- 对表重命名`rename`
```
alter table 表名 rename 新表名
```
