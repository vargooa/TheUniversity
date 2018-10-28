# 实验二——数据库查询语句

* 单表查询，最简单的查询语句
  * 查询所有speed大于2.8的PC信息

  ```
  select * from pcs where speed > 2.8;
  ```

  * 查询购买model为1007的购买记录

  ```
  select * from sales where model = 1007;
  ```

  * 统计2013-12-20购买记录的数量（count）

  ```
  select count(*) from sales where sday = to_data('2013-12-20','yyyy-MM-dd')
  ```

* 
* 








