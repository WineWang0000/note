## 在说请求响应之前写一下相关的知识点

## URI URL URN 

### URI分为URL和URN

URL其实就是我们说的网址，每次搜索都能发现输入框内有一串东东，就是URL。

![CGQ`]@0BBIUTS`GQM(0`LM1.png](https://i.loli.net/2019/02/18/5c6a5f06929c4.png)

http是协议，作用是指导浏览器和服务器如何进行沟通。锚点：当我搜索hello会出现很多条东西在页面上#5就是第五条。看图。注意红色标记。#5是手动加上演示用的。

![CGQ`]@0BBIUTS`GQM(0`LM1.png](https://i.loli.net/2019/02/18/5c6a682300e3e.png
)

URN就是一串字符，比如ISBN: 9787115275790 对应的资源的是《JavaScript 高级程序设计（第三版）》这本书，每个书是不一样的，通过这个就能找到对应的书。也就是确定一个唯一的资源。

## DNS

DNS就是域名系统。

通俗解释下：当我访问baidu.com的时候，我问DNS它对应的IP是啥。输入域名得到IP，我才能去访问它。

# 请求

### 请求步骤

- 浏览器负责发出请求

- 服务器在80端口接收请求

- 服务器负责响应

- 浏览器负责下载响应内容

### 请求格式
```
1 动词 路径 协议/版本
2 Key1: value1
2 Key2: value2
2 Key3: value3
2 Content-Type: application/x-www-form-urlencoded
2 Host: www.baidu.com
2 User-Agent: curl/7.54.0
3 
4 要上传的数据
```
##### (对照下面几条看)
```
1 POST / HTTP/1.1
2 Host: www.baidu.com
2 User-Agent: curl/7.54.0
2 4Accept: */*
2 Frank: xxx
2 Content-Length: 10
2 Content-Type: application/x-www-form-urlencoded
3
4 1234567890
```
解释一下：**第一部分**动词就是GET，POST，PUT，PATCH，PUT就是需要更改全部的请求，PATCH是更改部分请求。路径就是/，如果不写默认是/。协议就是HTTP或者HTTPS。版本号这里是1.1。 **第二部分**全部是k:value的格式。**第三部分**是空白。**第四部分**是要上传的数据。
#### 补充：请求可以用GET POST还可以POST -d(数据)
# 响应
### 响应的格式
```
1 协议/版本号 状态码 状态解释
2 Key1: value1
2 Key2: value2
2 Content-Length: 17931
2 Content-Type: text/html
3
4 要下载的内容
```
##### (对照下面几条看)
```
HTTP/1.1 302 Found
Connection: Keep-Alive
Content-Length: 17931
Content-Type: text/html
Date: Tue, 10 Oct 2017 09:19:47 GMT
Etag: "54d9749e-460b"
Server: bfe/1.0.8.18
```
### 状态码
##### 服务器对浏览器说的话
- 1xx 不常用
- 2xx 表示成功 200成功 204表示创建成功 
- 3xx 滚吧 301 表示永久不存在了 302表示赞赏不存在 304(你请求内容，服务器响应的数据内容和上次一样，让你还使用上次的)
- 4xx 你(浏览器)错了
- 5xx 我(服务器)错了

