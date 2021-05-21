# 连接MySQL
1. 安装驱动  
    cnpm install mysql

2. 连接数据库
    ```
    var mysql = require('mysql');
    var connection = mysql.createConnection({
        host: 'localhost',
        user: 'root',
        password: '123456',
        database: 'test'
    });
    connection.connect();
    connection.query('SELECT 1+1 AS solution', function(error, results, fields){
        if (error) throw error;
        console.log('The solution is: ', results[0].solution);
    });
    ```

3. CURD  
    依赖于connection.query(), 传入原生SQL语句，传入参数为止用"?"代替，后面传入对应参数Array
    
---

# 连接MongoDB
1. 安装驱动
    cnpm install mongodb

2. 创建数据库
    ```
    var MongoClient = require('mongodb').MongoClient;
    var url = "mongodb://localhost:27017/runoob";

    MongoClient.connect(url, function(err, db){
        if (err) throw err;
        console.log("数据库已创建");
        db.close();
    });
    ```

3. 创建集合
    ```
    var MongoClient = require('mongodb').MongoClient;
    var url = 'mongodb://localhost:27017/runoob';
    MongoClient.connect(url, function(err, db){
        if (err) throw err;
        console.log('数据库已创建');
        var dbase = db.db('runoob');
        dbase.createCollection('site', function(err, res){
            if (err) throw err;
            console.log('创建集合');
            db.close();
        });
    });
    ```

4. CRUD
    1. 插入数据  
    ```
    var dbase = db.db('runoob');
    var insObj = {name: '测试', url: 'www.test.com'};
    dbase.collection('site').insertOne(insObj, function(err, res){
        if (err) throw err;
        console.log('插入文档成功');
        db.close();
    });
    ```
    插入多条数据使用`insertMany()`
    ```
    dbase.collection('site').insertmany(insObj, function(err, res){
        if (err) throw err;
        console.log('插入文旦数量为: ' + res.insertedCount);
        db.close();
    });
    ```