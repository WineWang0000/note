HTTP的底层是由TCP和IP协议构成的
## TCP传输协议控制(Transmission Control Protocol)
面试的时候最多问两个问题，看博客了解一下即可。
- TCP和UDP的区别？

  简答：TCP 可靠、面向连接、相对 UDP 较慢；UDP 不可靠，不面向连接、相对 TCP 较快。
- TCP 的三次握手指的是什么
简答：每次建立连接前，客户端和服务端之前都要先进行三次对话才开始正式传输内容，三次对话大概是这样的：
  1. 客户端：我要连接你了，可以吗
  2. 服务端：嗯，我准备好了，连接我吧
  3. 客户端：那我连接你咯。
  4. 开始后面步骤
## IP
有一些琐碎的知识点:

1.IP分为内网外网，中间人是路由器，你的设备，像电脑手机和路由器过程的是内网。如果想连接外网是需要路由器中转的。

2.访问127.0.0.1是访问自己(设备)

3.内网IP格式：192.168.xx.xx

## 端口
访问设备只有IP是不行的，还需要有端口，端口是什么，其实只是一个编号。
### 一个端口只对应一个服务
1.要提供 HTTP 服务你最好使用 80 端口

2.要提供 HTTPS 服务你最好使用 443 端口

3.要提供 FTP 服务你最好使用 21 端口
- 不知道用什么端口号可以[维基百科](https://zh.wikipedia.org/wiki/TCP/UDP%E7%AB%AF%E5%8F%A3%E5%88%97%E8%A1%A8#0.E5.88.B01023.E5.8F.B7.E7.AB.AF.E5.8F.A3)

- 一共有多少端口号：65535 0~1023（2的10次方减1）号端口是留给系统使用的，你只有拥有了管理员权限后，才能使用这 1024 个端口。

# 用server接收请求
简述步骤：
- cd ~/Desktop
- mkdir node-demo
- cd node-demo
- touch server.js
- 编辑server.js （[编辑内容在此](https://github.com/pingdeng123/note-server/blob/master/server.js)）运行 node server.js;

(里面内容是大神写的，只是借来写个笔记，三扣)
# 用server发送响应
- 成功之后新开个bash窗口
- 编辑sever.js
- 在标注的地方添加代码 
response.write('hi')和response.end()

- 中断之前的 server，重新运行 node server 8888
- http://127.0.0.1:8888/xxx 打开这个网页就会看到hi

那两行代码根据英文意思大概也能知道，第一个是写入hi，第二个是结束。和可以加上这些response.statusCode = 200 意思是状态码，200代表成功 response.setHeader('Content-Type', 'text/html;charset=utf-8') 这个意思是把得到的内容转成html格式，utf-8就是GBK，这个在之前博客有写。
