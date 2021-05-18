## 回调函数
- Node所有API都支持回调函数, 一般回电函数作为最后一个参数出现
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