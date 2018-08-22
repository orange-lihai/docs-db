###### mysqldump 的常见用法
[官方文档](https://dev.mysql.com/doc/refman/5.7/en/mysqldump.html) , 下面总结了一些常见用法 
~~~
-- 导出部分表
mysqldump -u用户名 -p密码 数据库名 表名 --where="筛选条件" > 导出文件路径
~~~