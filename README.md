#### 介绍

Springboot+websocket+vue的小聊天

#### 软件架构

Springboot、websocket、vue、MySQL

#### 安装教程

1.首先拉取拉取代码  [仓库地址](https://gitee.com/zyy_dawn/spring_boot_vue_chat "仓库地址")
```
git pull https://gitee.com/zyy_dawn/spring_boot_vue_chat.git
```

2.将项目中聊天图片中的chat文件夹拷贝到D盘下面(这是springboot中配置的虚拟机访问路径，其他盘符下也可以，但是需要修改)

![在这里插入图片描述](https://images.gitee.com/uploads/images/2019/1221/103000_e3108947_3026905.png)

3.将项目中的数据库文件夹下的chat.sql导入到MySQL数据库，数据库名称为chat。

![在这里插入图片描述](https://images.gitee.com/uploads/images/2019/1221/103000_ffa391ee_3026905.png)

4.使用idea打开项目，运行项目

5.从数据库的userinfo表中
选择一个userid（最好是SY1571476959767947449），
然后在`一个`浏览器中访问：[localhost:8080/tochat/SY1571476959767947449]("localhost:8080/tochat/SY1571476959767947449")
然后再选择一个userid，最好是（SY1571476959767947441），
然后在`另一个`浏览器中访问：[localhost:8080/tochat/SY1571476959767947441]("localhost:8080/tochat/SY1571476959767947441")
选择这两个userid,的原因是数据库初始数据让这两人互为好友了。

#### 项目接口

1、/chat/upimg

```markdown
这个接口就是聊天图片上传的的接口
```

2、/chat/{fuserid}

```markdown
这个接口是加好友用的，传入一个用户id，判断当前用户和当前登录的用户是否是好友，如果是直接跳转到接口：/chat（目前这个接口以及删除，这个接口就是单纯跳转到聊天界面）
```

3、/tochat/{uid}

```markdown
这个接口是目前跳转到聊天界面的，因为没有登录界面，所以直接用这个接口传入一个用户id，然后在此接口中将此用户id存储到session，作为登录用户的id。
```

4、/chat/lkfriends

```markdown
这个接口就是单纯的查询当前登录用户的好友列表的接口
```

5、/chat/lkuschatmsg/{reviceuserid}

```markdown
这个接口是查询两个用户之间的聊天信息的接口，传入用户的userid，查询当前登录用户和改用的聊天记录。
```

#### 项目说明

```markdown
1、此项目为一个聊天的小demo，采用springboot+websocket+vue开发。
2、其中有一个接口为添加好友接口，添加好友会判断是否已经是好友。
3、聊天的时候：A给B发送消息如果B的聊天窗口不是A，则B处会提醒A发来一条消息。
4、聊天内容的输入框采用layui的富文本编辑器，目前不支持回车发送内容。
5、聊天可以发送图片，图片默认存储在D:/chat/目录下。
6、点击聊天内容中的图片会弹出预览，这个预览弹出此条消息中的所有图片。
```

#### 运行截图

![在这里插入图片描述](https://images.gitee.com/uploads/images/2019/1221/103549_392d584f_3026905.png)
![在这里插入图片描述](https://images.gitee.com/uploads/images/2019/1221/103549_9612745d_3026905.png)
![在这里插入图片描述](https://images.gitee.com/uploads/images/2019/1221/103549_1fe4ddff_3026905.png)
