#### 脚本
##### what's 脚本？
脚本就是给计算机照做的文本。举例，图上的都是脚本，输入这些文本让计算机执行。
![QWOB~E]X9G5AX%CO57$PN31.png](https://i.loli.net/2019/02/17/5c69310c8d182.png)
#### 写脚本(用文件写脚本)
步骤如下：
cd ~/Desktop
mkdir local
cd local
touch demo.txt
start demo.txt
###### (这时候会出现一个demo笔记本空白页面)
mkdir demo
cd demo
mkdir css js
touch index.html
css/style.css 
js/main.js
###### (这里可以随便创建文件或者目录。演示用。写完Ctrl+S保存。然后关闭)
###### (回到bash上)
cd ~/Desktop
chmod +x demo.txt
###### (给demo加X，让它可以执行。此步window可省略)
sh ~/local/demo.txt(执行)

如果什么都没有出现那就成功了

自己动手写一个脚本

#### Node.js
##### 用Node.js写脚本
创建 ~/local/jsdemo.js，内容如下
var fs = require('fs')
var dirName = process.argv[2] // 你传的参数是从第 2 个开始的
fs.mkdirSync("./" + dirName) // mkdir $1
process.chdir("./" + dirName) // cd $1
fs.mkdirSync('css') // mkdir css
fs.mkdirSync('js') // mkdir js
fs.writeFileSync("./index.html", "")
fs.writeFileSync("css/style.css", "")
fs.writeFileSync("./js/main.js", "")
process.exit(0)
（Windows 用户跳过这一步）给 jsdemo.js 加上执行权限 chmod +x ~/local/jsdemo.js
cd ~/Desktop
node ~/local/jsdemo.js zzz，就可以看到 zzz 目录创建成功了
##### shebang
我们每次执行 ~/local/jsdemo.js 都要用 node 来执行，能不能做到不加 node 也能执行呢（也就是指定执行环境），可以，在 jsdemo.js 第一行加上这一句即可：
## !/usr/bin/env node
node和bash功能差不多就是语法不一样，遇到不知道的就谷歌，不需要死记硬背。伤脑筋。。。。。。
##### 用js脚本创建目录
谷歌关键字： nodejs create dir 搜索结果直接用就可以
let fs = require("fs")
fs.mkdirSync ("demo")demo为目录名
##### 用js脚本创建文件
谷歌关键字： nodejs create file
let fs = require("fs")
fs.writeFileSync("./index.html", " ")这里文件写的为空
##### 判断目录是否已存在
if [ -d $1 ]; then
  echo 'error: dir exists'
  exit 1
else
  mkdir $1
  cd $1
  mkdir css js
  touch index.html css/style.css js/main.js
  echo 'success'
  exit 0
fi
在出现的笔记本里写入这些，第一行是语法，不需要明白为什么，注意空格和符合等。最后的fi也不能少。exit后面的0,1是 **返回值**，如果成功返回0，不成功为1.
还有一个需要说的是bash里输入node就在node.js环境下了，Ctrl+D再切回。
#### 脚本
##### what's 脚本？
脚本就是给计算机照做的文本。举例，图上的都是脚本，输入这些文本让计算机执行。
![QWOB~E]X9G5AX%CO57$PN31.png](https://i.loli.net/2019/02/17/5c69310c8d182.png)
#### 写脚本(用文件写脚本)
步骤如下：
cd ~/Desktop
mkdir local
cd local
touch demo.txt
start demo.txt
###### (这时候会出现一个demo笔记本空白页面)
mkdir demo
cd demo
mkdir css js
touch index.html
css/style.css 
js/main.js
###### (这里可以随便创建文件或者目录。演示用。写完Ctrl+S保存。然后关闭)
###### (回到bash上)
cd ~/Desktop
chmod +x demo.txt
###### (给demo加X，让它可以执行。此步window可省略)
sh ~/local/demo.txt(执行)

如果什么都没有出现那就成功了

自己动手写一个脚本

#### Node.js
##### 用Node.js写脚本
创建 ~/local/jsdemo.js，内容如下
var fs = require('fs')
var dirName = process.argv[2] // 你传的参数是从第 2 个开始的
fs.mkdirSync("./" + dirName) // mkdir $1
process.chdir("./" + dirName) // cd $1
fs.mkdirSync('css') // mkdir css
fs.mkdirSync('js') // mkdir js
fs.writeFileSync("./index.html", "")
fs.writeFileSync("css/style.css", "")
fs.writeFileSync("./js/main.js", "")
process.exit(0)
（Windows 用户跳过这一步）给 jsdemo.js 加上执行权限 chmod +x ~/local/jsdemo.js
cd ~/Desktop
node ~/local/jsdemo.js zzz，就可以看到 zzz 目录创建成功了
##### shebang
我们每次执行 ~/local/jsdemo.js 都要用 node 来执行，能不能做到不加 node 也能执行呢（也就是指定执行环境），可以，在 jsdemo.js 第一行加上这一句即可：
## !/usr/bin/env node
node和bash功能差不多就是语法不一样，遇到不知道的就谷歌，不需要死记硬背。伤脑筋。。。。。。
##### 用js脚本创建目录
谷歌关键字： nodejs create dir 搜索结果直接用就可以
let fs = require("fs")
fs.mkdirSync ("demo")demo为目录名
##### 用js脚本创建文件
谷歌关键字： nodejs create file
let fs = require("fs")
fs.writeFileSync("./index.html", " ")这里文件写的为空
##### 判断目录是否已存在
if [ -d $1 ]; then
  echo 'error: dir exists'
  exit 1
else
  mkdir $1
  cd $1
  mkdir css js
  touch index.html css/style.css js/main.js
  echo 'success'
  exit 0
fi
在出现的笔记本里写入这些，第一行是语法，不需要明白为什么，注意空格和符合等。最后的fi也不能少。exit后面的0,1是 **返回值**，如果成功返回0，不成功为1.
还有一个需要说的是bash里输入node就在node.js环境下了，Ctrl+D再切回。

