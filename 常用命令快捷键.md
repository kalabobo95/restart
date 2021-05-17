# restart -- 每天进步一点点，加油！！


## 命令行
1. 根据文件安装Python包
   将需要安装的包写在一个txt文档中
   ```
   pip install -r [file-name] -i [mirror-source]
   pip install -r F:\package.txt -i https://mirrors.aliyun.com/pypi/simple/
   ```

2. tmux工具使用
   1. 命令行
   ```
   tmux new                      # 不制定会话名  
   tmux new -s [session-name]    # 指定会话名  
   tmux ls                       # 查看已创建的会话  
   tmux detach                   # 从当前会话中退出去  
   tmux kill-session -t [session-name | session-id]     # 关闭会话  
   tmux a -t [session-name | session-id]       # 进入一个已知会话  
   tmux a                        # 进入最近的会话
   ```
   2. 快捷键
   ```
   ctrl+b   %     # 水平分屏
   ctrl+b   "     # 垂直分屏
   ctrl+b   o     # 分屏后，切换窗口光标
   ctrl+b   !     # 合并所有分屏
   ctrl+b   s     # 查看所有会话
   
   ctrl+b   &     # 终止一个终端窗口(或执行exit命令)
   ctrl+b   c     # 创建新窗口
   ctrl+b   p     # 切换窗口 
   ctrl+b   w     # 查看所有窗口
   ctrl+b   ,     # 修改窗口名 
   ctrl+b   d     # 挂起当前会话
   ctrl+b   q     # 查看面板编号
   ```
   


## python 语法
1. assert
    ```
    assert expression[, expression] [, arguments]
    expression 结果为True则正常执行，为False则触发异常
    ```


## node.js
1. 关于安装
   1. 进入到相关文件夹下进行安装
   `npm install`
   2. 
   
   

2. 启动
   yarn run start