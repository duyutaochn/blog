title: Mac 下的 tree 命令
date: 2014-11-1 22:39:52
tags: Mac Tree 
---
在默认安装安装的 mac 下没有找到 tree 命令，找了一下原来有个比较流氓的解决办法：

1 find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'
这个命令行跑起来类似平常tree的效果，

写一个alias到~/.bash_profile里，就更方便了:

alias tree="find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'"
Update

2 现在正在用的是 homebrew 安装的 tree 命令行。

brew install tree

作者: Volcano 发表于November 22, 2010 at 8:34 pm
版权信息: 可以任意转载, 转载时请务必以超链接形式标明文章原始出处和作者信息及此声明
永久链接 - http://www.ooso.net/archives/564

