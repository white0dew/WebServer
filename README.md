# WebServer
 A TinyWebServer implemented inC++11,经过webbenchh压力测试可以实现上万的QPS。
## 功能
 * 利用IO复用技术Epoll与线程池实现多线程的Reactor高并发模型；
 * 利用正则与状态机解析HTTP请求报文，实现处理静态资源的请求；
 * 基于小顶堆实现的定时器，关闭超时的非活动连接；
 * 利用RAII机制实现了数据库连接池，减少数据库连接建立与关闭的开销，同时实现了用户注册登录功能。
## 环境要求
 * Linux
 * C++11
 * MySql
## 目录树
.
├── code           源代码
│   ├── buffer
│   ├── config
│   ├── http
│   ├── log
│   ├── timer
│   ├── pool
│   ├── server
│   └── main.cpp
├── test           单元测试
│   ├── Makefile
│   └── test.cpp
├── resources      静态资源
│   ├── index.html
│   ├── image
│   ├── video
│   ├── js
│   └── css
├── bin            可执行文件
│   └── server
├── log            日志文件
├── webbench-1.5   压力测试
├── build          
│   └── Makefile
├── Makefile
├── LICENSE
└── readme.md
## 项目启动
### 配置Mysql数据库
``` 
// 建立yourdb库create database yourdb;​
// 创建user表USE yourdb;CREATE TABLE user(    username char(50) NULL,    password char(50) NULL)ENGINE=InnoDB;​
// 添加数据INSERT INTO user(username, password) VALUES('name', 'password');
```
### 编译运行
``` 
make
./bin/server
```