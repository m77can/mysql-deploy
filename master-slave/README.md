# mysql 主从 搭建

需开启 binlog

master

```sql
CREATE USER 'slave'@'%' IDENTIFIED BY 'slave';

GRANT REPLICATION SLAVE ON *.* TO 'slave'@'%';
```

slave

```sql
CHANGE MASTER TO MASTER_HOST='master', MASTER_USER='slave', MASTER_PASSWORD='slave';
```
