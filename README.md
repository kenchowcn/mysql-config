# mysql-config

## 配置远程访问和设置大小写不敏感
1. `apt-get remove --purge mysql* && apt-get autoremove && apt-get autoclean`
2. `rm -rf /var/lib/mysql/`
3. `apt-get update && apt-get install mysql-server` 密码设置为`123456`
4. `vim /etc/mysql/my.cnf` 修改`bind-address=0.0.0.0`，增加大小写不敏感`[mysqld] lower_case_table_names=1`
5. `mysql -uroot -p123456`
6. `GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '123456';`
7. `flush privileges;`
8. `exit`
9. `/etc/init.d/mysql restart`