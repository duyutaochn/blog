title: vssh编辑中文	
date: 2014-11-22 00:38:53
tags: vssh
---
1，ssh工具连接设置里为UTF-8编码
2，在/etc/profile最后加入
   export LANG=zh_CN.UTF-8
3，连接的时候字符编码改成utf－8即可。
修改/etc/profile 提示文件只读。
解决方法：sudo chmod +w /etc/profile 即可
4，执行 source /etc/profile