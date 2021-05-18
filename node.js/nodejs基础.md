# 安装
1. 编译版
    ```
        wget https://nodejs.org/dist/v10.9.0/node-v10.9.0-linux-x64.tar.xz    // 下载
        tar xf  node-v10.9.0-linux-x64.tar.xz       // 解压
        cd node-v10.9.0-linux-x64/                  // 进入解压目录
        ./bin/node -v                               // 执行node命令 查看版本
    ```
2. 源码安装
    ```
        wget http://nodejs.org/dist/v0.10.24/node-v0.10.24.tar.gz
        tar zxvf node-v0.10.24.tar.gz
        cd node-v0.10.24
        ./configure --prefix=/usr/local/node/0.10.24
        make
        make install
        vim /etc/profile
    ```
    设置 nodejs 环境变量，在 export PATH USER LOGNAME MAIL HOSTNAME HISTSIZE HISTCONTROL 一行的上面添加如下：
    ```
        #set for nodejs
        export NODE_HOME=/usr/local/node/0.10.24
        export PATH=$NODE_HOME/bin:$PATH
    ```
    `source /etc/profile`使配置生效

    防火墙相关指令
    ```
        systemctl stop firefalld
        systemctl start firewalld
        systemctl enable firewalld
        systemctl disable firewalld
        firewalld-cmd --reload
        systemctl status firewalld 或 firewalld-cmd --state
    ```

# 创建应用
1. 引入required模块  
    `touch server.js`  
    var http = require('http');
2. 创建服务器
    ```
        var http = require('http');

        http.createServer(function(req, res){
            //发送HTTP头部
            //HTTP状态值：200:ok
            //内容类型: text/plain
            res.writeHead(200, {'content-type': 'text/plain'});

            //发送响应数据“hello world\n”
            res.end('hello wordl\n');
        }).listen(8888);

        console.log('Server running at http://127.0.0.1:8888/');
    ```
3. 运行项目  
    node server.js

4. npm命令
    - 更新npm, `npm install npm -g`
    - 使用淘宝镜像, `npm install -g cnpm --registry=https://registry.npm.taobao.ory`
    - 安装node.js模块语法, `npm install <module Name>`
        ```
            npm install express     # 本地安装
            npm install express -g  # 全局安装
        ```
    ### 本地安装  
    1. 将安装包放在 ./node_modules 下（运行 npm 命令时所在的目录），如果没有 node_modules 目录，会在当前执行 npm 命令的目录下生成 node_modules 目录。
    2. 可以通过 require() 来引入本地安装的包。
    ### 全局安装  
    1. 将安装包放在 /usr/local 下或者你 node 的安装目录。
    2. 可以直接在命令行里使用。
    - 卸载模块, `npm uninstall <module Name>`
    - 更新模块, `npm update <module Name>`
    - 搜索模块, `npm search <module Name>`