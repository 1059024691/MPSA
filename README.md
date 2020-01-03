# MPSA

***

## Management Platform for Student Associations(学生社团管理平台)

> **框架**

python3+flask+mysql+html,css,javascript

> **文件结构** (其他文件为本地生成的文件，如要使用需要自己在本地配置，配置过程稍后有)

``` 目录树
    app
     |-----template                         -html的模板文件
     |-----static
     |        |-----images                  -图片文件
     |        |-----css                     -css文件
     |        |-----js                      -javascript文件
     |        |-----font                    -字体文件
     |-----main.py                          -主运行文件
     |-----index.py                         -首页的python处理文件
     |-----common_user.py                   -普通用户的个人界面管理
     |-----manager_user.py                  -管理员的个人界面管理
     |-----team_information.py              -团队信息的处理
     |-----hashlib.py                       -用于对密码md5摘要的文件
     |-----ss.sql                           -数据库生成文件
```

> **开发人员**

后端：鄙人，田珩之

前端: 陈杰，张宇光，朱蓓佳

> **运行环境**

ubuntu18.04

> **参考链接**

[flask使用](https://www.jianshu.com/p/7c9ebda62214) 
[ubuntu 18.04 数据库的安装](https://www.jianshu.com/p/4908f6e686fa)

> **依赖环境**

pymysql（pip install pymysql）

将app文件放置到主文件夹夹，安装pymysql修改数据库连接的参数，之后运行main.py文件，即可就可以在127.0.0.1:5000即可运行。

> **功能实现**

| 界面      | 功能                                      |
| :--------|:------------------------------------------------|
|主页      |普通用户的登录和注册（手机号作为主键），管理员的登录（注册需要联系管理员）|
|普通用户   |我的社团，我的消息，系统消息，个人中心（个人信息，修改密码，返回，注销）,回到主页|
|管理员    |我的社团，我的消息，系统消息，社团管理（创建社团，人员管理，发布消息，返回）个人中心（个人信息，修改密码，返回，注销）

> **安全**

1. 密码在数据库中的存放采用hashlib文件中的md5算法。由于hashlib库用pip总是安装失败.所以我直接去github上copy源文件了。
2. 访问登录控制采用session控制，登录成功的时候创建一个session,当浏览器关闭的时候session丢失。
3. 开启crsf。

> **总结**

开发的时间比较紧张，由于是第一次使用python开发。之前也就用python写过一点点的小程序。在Djingo和flask之间进行过选择。不过好像之前从不知道python也能开发后端。花了一段时间去学习flask就上手了。所以可以看到程序代码逻辑还是比较混乱的，基本上是写着学着改着。像PDO就没有使用，因为觉得麻烦一点，就挑了一个一眼就能看懂了pymysql。还有crsf，到了最后的一天，才学会还有这么个玩意。极验的验证码也是这样的。这次实践还是让自己学会了很多的。

为期两个星期的开发结束了，虽然代码还有很多地方不符合一般的flask开发规范，不过总算是交差了，虽然最后没有获奖有点可惜，18个组1个奖，还给了第一个ppt展示的组，虽然我并不认为他们的东西有多厉害。我们的好像也不怎么滴，没有什么高深的算法。就是一大堆的逻辑绕来绕去。很多的工作都做在了重复的逻辑问题上。看来选题也是一个很重要的问题。下次一定要找一个看着很厉害，代码量并不大的项目。还有我发现了我自己存在一个很大的问题。我总是在一些大家注意不到的地方使劲，很多地方做的细节在展示的时候并不能够体现，自己花费了大量的时间去做这些工作，真的是得不偿失啊。
