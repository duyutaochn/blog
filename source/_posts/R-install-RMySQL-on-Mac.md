title: R install RMySQL on Mac
date: 2014-12-06 12:26:23
tags:
---
由于RMySQL不提供可以直接使用的安装包的原因，造成RMySQL安装步骤复杂，问题颇多。下面简述一些步骤：

第一，安装mysql数据库
Mac下安装Mysql参考：

http://www.cnblogs.com/macro-cheng/archive/2011/10/25/mysql-001.html

第二，下载RMySQL安装源文件

http://cran.r-project.org/web/packages/RMySQL/index.html

第三，安装libmysqlclient 类库

第四 执行下面语句，手动安装RMysql

R CMD INSTALL --configure-args='--with-mysql-dir=/usr/local/mysql-5.6.20-osx10.8-x86_64 --with-mysql-inc=/usr/local/mysql-5.6.20-osx10.8-x86_64/include --with-mysql-lib=/usr/local/mysql-5.6.20-osx10.8-x86_64/lib' RMySQL_0.9-3.tar.gz

第三步的时候有人说可以在Rstudio 中使用install.packages("/path/to/package/RMySQL_0.9-3.tar.gz",repos = NULL,type="source") 或install.packages("RMySQL", type = "source")语句。我尝试失败了，因此改用直接在Terminal 中安装。


遇到问题：
1:Error : .onLoad failed in loadNamespace() for 'RMySQL', details:
解决方法：
step1:安装libmysqlclient 类库

执行 npm install mysql-libmysqlclient

参考网站：http://my.oschina.net/u/923974/blog/205095

step2:执行手动安装语句（语句中的路径要进行相应的修改）

R CMD INSTALL --configure-args='--with-mysql-dir=/usr/local/mysql-5.6.20-osx10.8-x86_64 --with-mysql-inc=/usr/local/mysql-5.6.20-osx10.8-x86_64/include --with-mysql-lib=/usr/local/mysql-5.6.20-osx10.8-x86_64/lib' RMySQL_0.9-3.tar.gz

参考网站：
######http://lsfalimis.github.io/link--install-rmysql-on-mavericks/
http://blog.fens.me/r-mysql-rmysql/
https://stat.ethz.ch/pipermail/r-sig-mac/2014-May/010897.html