# PostgreSQL
[官方文档](http://www.postgres.cn/docs/12/)

## 命令：
```
linux连接数据库：
su postgres
psql
添加新Linux用户
adduser dbuser
添加数据库用户
su - postgres
psql
CREATE USER dbuser WITH PASSWORD 'Changeme_123'
创建用户数据库shop，指定所有者为dbuser
CREATE DATABASE shop OWNER dbuser;
GRANT ALL PRIVILEGES ON DATABASE shop to dbuser;
使用新用户登录数据库，-U指定用户，-d指定数据库，-h指定服务器，-p指定端口
psql -U dbuser -d shop -h 127.0.0.1 -p 5432
如果是同名的Linux用户，并且有同名的数据库用户，可以使用简写命令登录：
psql shop;

```
## 常用SQL：
```
CREATE DATABASE shop;
创建表
CREATE TABLE Product
(product_id CHAR(4) NOT NULL,
product_name VARCHAR(100) NOT NULL,
product_type VARCHAR(32) NOT NULL,
sale_price INTEGER ,
purchase_price INTEGER ,
regist_date DATE ,
PRIMARY KEY(product_id));

删除表
DROP TABLE Product;

表定义的更新
ALTER TABLE Product ADD COLUMN product_name_pinyin VARCHAR(100);
ALTER TABLE Product DROP COLUMN product_name_pinyin;
ALTER TABLE Product RENAME TO PRODUCT_1

向表中插入数据
INSERT INTO Product VALUES ('0001', 'T恤衫', '衣服', 1000, 500, '2009-09-20');
INSERT INTO Product VALUES ('0002', '打孔器', '办公用品', 500, 320, '2009-09-11');
INSERT INTO Product VALUES ('0003', '运动T恤', '衣服', 4000, 2800, NULL);
INSERT INTO Product VALUES ('0004', '菜刀', '厨房用具', 3000, 2800, '2009-09-20');
INSERT INTO Product VALUES ('0005', '高压锅', '厨房用具', 6800, 5000, '2009-01-15');
INSERT INTO Product VALUES ('0006', '叉子', '厨房用具', 500, NULL, '2009-09-20');
INSERT INTO Product VALUES ('0007', '擦菜板', '厨房用具', 880, 790, '2008-04-28');
INSERT INTO Product VALUES ('0008', '圆珠笔', '办公用品', 100, NULL, '2009-11-11');


```

