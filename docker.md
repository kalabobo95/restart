# mysql容器数据备份与恢复
```
1. 执行导出（备份）数据库命令：
    mysql 运行在一个叫 mysql_server 的 docker 容器中。而我们要备份的数据库就在里面，叫做 test_db。mysql 的用户名密码均为root，我们将文件备份到宿主机/opt/sql_bak文件夹下。
    docker exec -it  mysql_server mysqldump -uroot -proot test_db > /opt/sql_bak/test_db.sql
    
2. 导入数据
    将宿主机上的数据sql复制到容器的文件下----因为是-v  启动  文件结构目录保持一致
    docker cp /opt/gysql.sql  gysql(容器名称):/opt/gysql.sql  
    
3. 进入容器---> docker exec -it gysql(容器名称) bash
4. 登录容器内的mysql数据库------> mysql -uroot -p123456
5. 创建对象的数据库  create database somp;
6. 使用use somp   ---> 执行 source  /opt/gysql.sql
7. exit;
```