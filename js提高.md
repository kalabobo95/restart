## 箭头函数(Arrow Function)
1. 箭头函数相当于匿名函数
    ```
    x => x * x
    ```
    `相当于`
    ```
    function(x){
        return x * x
    }
    ```
2. js中的波浪号作用----`
    ```
    `${variable_name} format_string`
    ```
    这一用法类似于python中的f'{variable_name} format_string'


3. mongoose.model第三个的参数问题  
    注册是数据库的表一定得带s, 如goods,users, 假如没有s, 比如我现在的数据库表名为mall, 就必须得定义(第三个参数)


4. Object  
    Object.values()方法返回一个给定对象自身的所有可枚举属性值的数组，值的顺序与使用for...in循环的顺序相同 

5. emit()监听事件  
    在emit触发事件之后，会先寻找是否存在对应的事件监听，如果有优先执行其回调函数，执行完毕后才会返回值

6. 解构赋值  
    `const { tempFilePath } = res;`  
    直接把对象中的tempFilePage 属性定义为变量，变量修饰符为 const 。

7. process对象  
    process对象是Node的一个全局对象，提供当前Node进程的信息。它可以在脚本的任意位置使用，不必通过require命令加载。

