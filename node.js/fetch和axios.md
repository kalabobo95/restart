## fetch方法请求失败，axios方法请求成功


同一方法访问同一路由，fetch方法请求失败，axios方法请求可以得到和postman调用相同的参数。
fetch对于跨域请求比较严格
>fetch方法中
设置 no-cors 表示该不跨域，这时请求能成功返回，但是不能读取响应体。response.json() 会报错。
设置 cors 表示跨域，必须服务器设置 Access-Control-Allow-Origin 头，否则请求不会返回。  
[相关链接](https://www.imooc.com/wenda/detail/511510)  

欢迎骚扰邮箱<zouzhaoyang125@163.com>