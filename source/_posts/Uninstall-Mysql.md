title: Mac下MySql卸载方法
date: 2014-12-07 10:17:26
tags:
---


mac下mysql的DMG格式安装内有安装文件，却没有卸载文件……很郁闷的事。
网上搜了一下，发现给的方法原来得手动去删。
很多文章记述要删的文件不完整，后来在stackoverflow这里发现了一个遗漏的地方，所以将完整版记述在这里，以供查阅。
先停止所有mysql有关进程。
sudo rm /usr/local/mysql
sudo rm -rf /usr/local/mysql*
sudo rm -rf /Library/StartupItems/MySQLCOM
sudo rm -rf /Library/PreferencePanes/My*
vim /etc/hostconfig and removed the line MYSQLCOM=-YES-
rm -rf ~/Library/PreferencePanes/My*
sudo rm -rf /Library/Receipts/mysql*
sudo rm -rf /Library/Receipts/MySQL*
sudo rm -rf /var/db/receipts/com.mysql.*

最后这条很多文章都丢了，切记切记。
参考http://hearrain.com/2011/01/495