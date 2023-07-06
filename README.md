# TinySQL

TinySQL：
- 如何用Go实现分布式数据库。 
- 它是TiDB的简化版本。

## 大纲

1. 关系代数模型及常用SQL语法
2. 解析器（Parser）
3. 数据模式定义语言（DDL）
4. 查询优化器（Optimizer）
5. 查询执行器（Executor）
6. 分布式事务（Percolator）

## 学习资料

https://github.com/tangyiheng/TinySQL/blob/course/courses/material.md

## 部署

构建：

```bash
make
```

部署服务：

```bash
./bin/tidb-server
```

使用MySQL客户端连接服务：

```bash
mysql -h127.0.0.1 -P4000 -uroot
```

将make产生的二进制可执行文件放在一个单独的文件夹，并运行tinyscheduler、tinykv、tidb三个服务：

```bash
mkdir -p data
./tinyscheduler-server
./tinykv-server -path=data
./tidb-server --store=tikv --path="127.0.0.1:2379"
```
