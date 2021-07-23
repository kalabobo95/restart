# restart -- 每天进步一点点，加油！！


##  tmux工具使用
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

ctrl+b   [     # 进入翻页模式PgUp PgDn进行翻页, q退出翻页
```
