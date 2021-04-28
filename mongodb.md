# mongodb 使用

## Python Mongodb
1. 实例
    ```
    import pymongo
    myclient = pymongo.Mongoclient("mongodb://localhost:27017/")        # 创建客户端
    mydb = myclient['runoobdb']                                         # 创建数据库
    mycol = mydb['sites']                                               # 创建集合
    ```

2. pymongo常用操作
    
    1. 插入文档
    ```
    mydict = {'name': 'Google', 'url': 'https://www.google.com'}
    x = mycol.insert_one(mydict)
    print(x.inserted_id)
    ```
    
    2. 插入多个文档
    ```
    mylist = [
        {'name': 'Taobo', 'url': 'https://www.taobo.com'},
        {'name': 'Zhihu', 'url': 'https://www.zhuhu.com'},
        {'name': 'Github', 'url': 'https://www.github.com'},
    ]
    x = mycol.insert_many(mylist)
    print(x.inserted_ids)
    ```

    note: 插入文档未指定`_id`, Mongodb会为每个文档添加唯一的id

    3. 查询文档
    ```
    data = mycol.find_one()
    all_datas = mycol.find()

    # 将要返回字段的对应值设置为1
    filter_datas = mycol.find({}, {'_id': 0, 'name': 1, 'url': 1})

    # 指定条件查询
    myquery = {'name': 'Taobao'}
    filter_datas = mycol.find(myquery)

    # 高级查询条件
    myquery_1 = {'name': {'$gt': 'a'}}
    myquery_2 = {'name': {'$regex': '^H'}}

    ```
    note: 在一个对象中不能同时制定0和1(_id除外); 

    4. 修改文档
    ```
    mycol.update_one()
    mycol.update_many()
    ```

    note: sort()方法可以指定升序降序排列, 第一个参数为要排序的字段, 第二个字段指定排序规则.  
    `1`表示升序排列, `-1`表示降序排列, 默认为升序排列.  

    note: 可以使用limit方法设置查询指定条数的记录.

    5. 删除操作
    ```
    mycol.delete_one()
    mycol.delete_many()

    # 删除集合
    mycol.drop()
    ```
