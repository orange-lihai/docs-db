#### information_schema
这个数据库里面有很多视图, 可以用来查询和统计当前数据库的原数据.


~~~
-- 查询正在执行的SQL
select * from information_schema.PROCESSLIST p
where p.STATE = 'executing'
order by p.`TIME` desc
limit 100
;

-- 杀掉某个线程(指令)
-- kill [CONNECTION | QUERY] processlist_id
-- CONNECTION: 默认值, 杀掉指令 将连接也断掉;
-- QUERY: 杀掉指令 连接还保持;

-- 查询表大小和数据量
select TABLE_NAME, round(sum(DATA_LENGTH/1024/1024),2) M, max(TABLE_ROWS) row_count 
from information_schema.tables 
where table_schema='goodhope'
group by TABLE_NAME
order by 2 desc
limit 10
;
~~~