## 一、常用的数据类型

![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/7d437d9a8d46438486db14ba44aade31.png)

char和varchar的区别

char： 如果存入数据的实际长度比指定长度要小，会补空格指指定长度，如果存入的数据的实际长度大于指定长度，低版本会被截取，高版本会报错。  
varchar： 如果存入的数据实际长度比指定长度要小，那么指定长度会变成实际长度一样，如果存入的数据的实际长度大于指定长度，会报错。  
 

**截取和截断的区别**

-   截取会对后一位进行四舍五入，截断直接获取要的数字，不进行四舍五入。

## 二、数据库管理

**SQL语言分类**

-   **DDL：** 数据定义语言，用于创建数据库对象，如库、表、索引等
-   **DML：** 数据操纵语言，用于对表中的数据进行管理
-   **DQL：** 数据查询语言，用于从数据表中查找符合条件的数据记录
-   **DCL：** 数据控制语言，用于设置或更改数据库用户或角色权限

### 1、mysql基础语句操作

#### 1.1 设置密码、登录数据库

mysqladmin -u root -p password "123456"   #给数据库设置密码(后面的回车)

mysql -uroot -p "123456"   #直接登录数据库  
mysql -u root -p        #登录数据库，输入密码后完成登录

![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/f4b1deb469874c01933147eb6f6085c8.png)

![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/60a57939780b4637b24bb226bea2263b.png)

![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/a9490b3d73b04968b9579074ad36d91d.png)

 1.2 查看数据库结构

show databases;     #查看有多少数据库（分号要加）  
use mysql           #进入一个数据库中，（分号可以不加）  
show tables;        #查看该数据库中有多少个表  
 

 ![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/ebe673bd87354a8291d38a7806fc96f6.png)

 ![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/4b028647283f4a4fa68cbc9916e07327.png)

 ![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/c2add064e2574c149243654d7b247a4f.png)

 1.3 查看表的结构

describe  db;     #查看表的字段属性（可缩写为desc db）

![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/1b3ae18bafb84ac4b23de54726973e62.png)

### 2、DDL语句：定义数据中的操作

-   **DDL语句可用于创建数据库对象（库、表、索引）**
    
-   **删除数据库和表**
    

2.1 创建数据库和表-create

create database school;     #创建一个名为school的数据库

create table  ky20 (id int(10) not null,name varchar(40) not null,age int (3) not null,score decimal(5,2) default '0',primary key (id));          
#创建一个名为ky20的表,（定义id不为空，名字不为空，年龄不为空，成绩可为空默认为“0”，主键为id）

create table scholl.ky21 (id int(10) not null); # 在任意库中创建school库中的ky21表  
 

![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/db38a5f1f11f45e99ace39aa900f923c.png)

 ![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/1e796ce8db1d4f10b0aa9222de57afc9.png)

 ![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/1aa9310a00414bacbc0ade69931e5d15.png)

 ![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/1bae7a7d29c9470188fc15e049b66c7e.png)

 2.2 删除数据库和表-drop

drop database ydqmysql      #删除一个名为ydqmysql的数据库

drop table ky22     #删除一个ky22的表  
drop table school.ky21    #可以再别的数据库中删除指定数据库中的表  
![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/4c88735516484485a552024c560cbcc3.png)

 ![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/f35a07516f3f4a07a5e011b26dc08819.png)

 3、DML语句 ：管理表中的数据记录

#### 3.1 插入数据-[insert](https://so.csdn.net/so/search?q=insert&spm=1001.2101.3001.7020 "insert")

select \* from ky20;     #查看ky20表中所有的数据  
select \* from \\G;       #友好的显示

insert into ky20 (id,name,age,score) values(1,'zhangsan',18,88);     
#向ky20表中插入数据

insert into ky20 (id,name,age) values(2,'zhanger',18);  
#向ky20表中指定字段插入，（可为空的字段，可以不添加值，为默认值）

insert into ky20 values(3,'lisi',20,67),(4,'zhaowu',22,90);  
#批量添加表中更多数据（前面的字段不写为默认）  
 

![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/9f327ea1f85a467088be40c4e3f8588a.png)

 ![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/e104707e1e3d4afa872dfaa2f326c887.png)

#### 3.2 更新原有数据-update

update 表名 set 字段1=字段值1，字段2=字段值10 where 表达式；

update ky20 set name='liubei',age=35 where name='zhanger';  
#将字段name为zhanger的，name和age进行修改。

update ky20 set name='ydq',age=24 where id>2;  
#将id大于2的记录进行修改。  
![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/f574b274a8874dbeb46b3a3adad63833.png)

#### 3.3 删除不需要的数据（表内容）-delete

格式：delete from 表名 where 条件表达式;

delete from ky20 where name='ydq';   #删除ky20表中name为ydq的记录

delete from ky20 where id>4;         #删除ky20表中id大于4的记录

delete from ky20;                    #删除ky20表中所有记录（谨慎操作）  
 

![](%E3%80%90MySql%E3%80%91mysql%E4%B9%8B%E5%9F%BA%E7%A1%80%E8%AF%AD%E5%8F%A5_mysql%20%E8%BE%93%E5%85%A5%E8%AF%AD%E5%8F%A5-CSDN%E5%8D%9A%E5%AE%A2/a0e3171fab0847a88a3138a3e7496c5e.png)

 delete from ky21;

delete from ky21 where id>4;

### 4、DQL语句：查询数据记录-select

格式：select 字段1,字段2 from 表名 【where 条件表达式】;

select \* from ky20;           #查看整个表的所有记录  
select id,name from ky20;     #查看整个表中的id，name字段  
select id,name from ky20\\G    #友好查看整个表的id，name，  
select id,name,score from ky20 where name='machao';    #查看name为machao的id，namescore  
select id,name from ky20 where score>80;    #查看分数值大于80分的字段id，name ，  
select \* from ky20 limit 2;   #查看前二行  
select \* from ky20 limit 2,3;    #显示第2行后的3行。（不包括第2行）  
 

## 三、了解约束

create table if not exists info (id int(4) zerofill primary key auto\_increment,name varchar(10) not null,cardid int(18) not null unique key,hobby varchar(50));

if not exists：表示检测要创建的表是否已存在，如果不存在就继续创建。  
int(4) zerofill：表若数值不满4位数，则前面用“0”填充，例0001。  
auto\_increment: 表示此字段为自增长字段，即每条记录自动递增1，默认从1开始递增；自增长字段数据不可重复，自增长字段必须是主键，如添加的距离数据没有指定字段的值且添加失败也会自动递增一次。  
unique\_key : 表示此字段唯一约束，此字段数据不可以重复，一张表中只能有一个主键，但是一张表中可以有多个唯一键。  
not null : 表示此字段不允许为NULL。