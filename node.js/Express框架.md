## 安装Express
- cnmp install express --save
- cnmp install body-parser --save
- cnmp install cookie-parser --save
- cnmp isntall multer --save  
body-parser node.js中间件，用于处理JSON,Raw,Text和URL编码的数据  
cookie-parser 解析Cookie工具。通过req.cookies可以传过来的cookie,并把他们转化成对象  
multer node.js中间件，用于处理enctype="multipart/form-data"(设置表单的MIME编码)的表单数据
## Express框架实例
- express_demo.js
    ```
    var express = require('express');
    var app = express();

    app.get('/', function(req, res){
        res.send('hello world');
    });

    var server = app.listen(8081, function(){
        var host = server.address().address;
        var port = server.address().port;
        console.log("应用实例，访问地址为http://%s:%s", host, port);
    });
    ```
### Request对象

### Response对象

## 静态文件
1. 内置中间件express.static来设置静态文件  
    `app.use('public', express.static('public'));