title: How to find mysql password
date: 2014-10-26 22:34:42
tags: Mysql
---
mac上mysql root密码忘记或权限错误的解决办法
 
这几天在折腾mantis发现总是连接mysql出错，就随手改了root权限，导致登录不上。
以下是还原root权限和更改root密码的最便捷方法。
1：装mysql workbench 。可视化界面直接操作。
2：苹果->系统偏好设置->最下边点mysql 在弹出页面中 关闭mysql服务
3：进入终端
输入：
cd /usr/local/mysql/bin/
回车后 登录管理员权限
sudo su
回车后输入以下命令来禁止mysql验证功能
 ./mysqld_safe --skip-grant-tables &
回车后mysql会自动重启，重启好了之后进入mysql workbench 随便创建一个连接，然后用户名填root （注意这里不会验证密码，所以填只要存在的账户就可以）。
再创建一个server administration，选择刚创建的连接。
双击server administration
左侧点击security，右侧就可以看到所有用户权限表了，这个时候想怎么干都行了
 
以下是部分说明：
用户权限表中
Limit Connectivity to Hosts Matching 表示登录地址限制，就是登录时候的ip地址 ，‘%’代表任意
Adminstrative Roles是权限，如果发现你的root没有管理员权限了，就点这个选项卡全部勾选
 
以下是其他命令
./mysqladmin -u root -p password 123             //更改root用户密码
./mysql -uroot -p                 //root用户登录mysql
以下是常见错误
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES) 
说明你的root权限不够，就可以参考上面的步骤设置权限
Access denied; you need (at least one of) the SUPER privilege(s) for this operation
说明你的root权限不够，就可以参考上面的步骤设置权限
 
至此我的数据库终于被找回了~~
