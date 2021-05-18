# 创建项目
- sails new sails_shop -> 选2  
或者
- sails new sails_shop --fast -> 选2  
  cd sails_cqwu
  cnpm install `注：安装依赖包`

# 启动项目
- sails lift

# 创建路由控制
- sails generate controller users list detail

# 配置相关
- config->blueprints.js
- config->routes.js  
    `"方式 请求名"：{响应方式: "路由"} 注：方式省略表示ALL，action方式可简写为字符串`
    ```
    '/': { view: 'index' },
    'GET /users': {action: 'users/logout'},

    'GET /users': 'users/logout',
    '/users/login': 'users/login',
    ```
- config->local.js
- config->views.js
## 数据库配置相关
- config->datastores.js
- config->models.js

## 应用拦截器
1. 在某个路由或操作中加入登录信息,如：  
    `req.session.userId=｛id:5,nc:'aaa'};`  
    注销的时候把这个session删掉
2. 在api/policies/新建策略文件,如：isLogin.js
    ```
    module.exports = async function (req, res, proceed) {
        if (req.session.userId) {
            return proceed();
        }
        return res.redirect('/users/login');
    };
    ```
3. 在config/policiesl.js文件中修改是否应用策略  
    全局方式:
    ```
    module.exports.policies = {
        '*': 'isLogin',
        'users/index': true,
        'users/login': true
    }
    ```
    控制器方式:
    ```
    module.exports.policies = {
        UserController: {
            '*': 'isLogin',
            'delete': 'isAdmin',
            'login': true
        }
    }
    ```
    `注：一个操作要用多个策略用[],如：["isLogin", "isAdmin"]`

## 前后端分离式跨源访问方式
- 在api/policies/下新建策略文件如：allow.js,内容如下:
    ```
    module.exports = async function (req, res, proceed) {
        res.header("Access-Control-Allow-Origin", "http://localhost:8080");
        res.header("Access-Control-Allow-Credentials","true");
        return proceed();
    }
    ```
- 在config/policies.js文件中添加内容即可
    ```
    '*': 'allow'
    ```

## 项目移植
- sails new myapp --fast  
    选2,进入myapp文件夹，将原项目中自己做的部分对应考入新路径中
- cd myapp
- cnpm install
- sails lift 启动数据库