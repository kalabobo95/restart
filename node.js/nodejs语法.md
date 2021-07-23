## 回调函数
- Node所有API都支持回调函数, 一般回调函数作为最后一个参数出现
    ```
        //阻塞代码
        var fs = require("fs");
        var data = fs.readfileSync('input.txt');
        console.log(data.toString());
        console.log('execute end');
    ```
    ```
        //非阻塞代码
        var fs = require("fs");
        fs.readFile('input.txt', function(err, data){
            if (err) return console.error(err);
            console.log(data.toString);
        });
        console.log('execute end');
    ```

## 事件循环
- Node.js有多个内置时间，可通过引入events模块，并通过实例化EventEmitter类来绑定和监听事件
    ```
    // 引入enents模块
    var events = require('events');
    // 创建enentEmitter对象
    var enentEmitter = new events.EventEmitter();
    // 绑定事件绑定处理程序
    eventEmitter.on('eventName', eventHandler);
    // 出发事件
    eventEmitter.emit('eventName');
    ```
    对于每个事件，EventEmitter支持若干个事件监听器。事件触发时，注册到这个事件的事件监听器被依次调用，事件参数作为回调函数参数传递

## Buffer(缓冲区)


## Stream(流)


## 模块系统
- 引入模块
    ```
    var hello = require('./hello');
    ```
    hello.js文件, 对外暴露属性或方法, 就用exports
    ```
    exports.world = function() {
        console.log('hello world');
    }
    ```
    把一个对象封装到模块中, 暴露对象(类似class, 包含了很多属性和方法), 就用module.exports
    ```
    module.exports = function() {
        // ...
    }
    ```

## 函数


## 路由


## 全局对象
- __filename
- __dirname
- setTimeout(cb, ms)
- clearTimeout(t)
- setInterval(cb, ms)
- clearInterval(t)
- console()
- *process*


## 常用工具 require('util')
- util.callbackify
- util.inherits
- util.inspect
- util.isArray
- util.isRegExp
- util.isDate


## 文件系统


## GET/POST请求

## 工具模块
- OS模块
- Path模块
- Net模块
- DNS模块
- Domain模块


## Web应用架构
- Client - 客户端, 一般指浏览器, 可以通过HTTP协议向服务器请求数据
- Server - 服务端, 一般指Web服务器, 可以接受客户端请求, 并向客户端发送响应数据
- Business - 业务层, 通过Web服务器处理应用程序, 如与数据库交互，逻辑运算，调用外部程序等
- Data - 数据层，一般由数据库组成


## RESTful API
- REST即表述性状态传递（Representational State Transfer）,表述性状态转移十一组架构约束条件和原则  
### HTTP方法
- GET 用于获取数据
- PUT 用于更新或添加数据
- DELETE 用于删除数据
- POST 用于添加数据


## Node.js多进程
- child_process.exec(command[, options], callback)
- child_process.spawn(command[, args][,options])
- child_process.fork(modulePath[, args][, options])
