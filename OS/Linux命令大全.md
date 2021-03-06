﻿# Linux命令大全

标签（空格分隔）： os

---

### 文件相关

命令|说明
--|--
cat|	用于连接文件并打印到标准输出设备上。
chmod|	设定文件权限
diff|	比较文件的差异
file|	辨识文件类型
find|	在指定目录下查找文件
grep|	查找文件里符合条件的字符串
cd|	切换当前工作目录
ls|	显示指定工作目录下之内容
exit|	退出目前的shell
kill|	删除执行中的程序或工作
mv|	用来为文件或目录改名、或将文件或目录移入其它位置
rm|	删除一个文件或者目录 -r递归删除 -f强制删除
cp|	用于复制文件或目录
tail|	输出文件尾部内容
mkdir|	新建目录
touch|	新建文件
pwd|	输出当前目录
whereis|查找文件
ln|创建软链接

### 系统管理

命令|	说明
--|--
who	|显示在线登陆用户
whoami|	显示当前操作用户
ps|	显示当前进程 (process) 的状态
netstat|显示各种网络相关信息
chmod|	设定文件权限
chown|	设定文件拥有者及其分组
top|	查看系统的CPU、内存、运行时间、交换分区、执行的线程等信息
w|查看用户及负载情况
ctrl+r|命令查找
df|列出文件系统的整体磁盘空间使用情况
uname|显示系统信息


### vim使用

> vim三种模式：命令模式、插入模式、编辑模式。使用ESC或i或：来切换模式。

命令|	说明
--|--
:q|	退出
:q!|	强制退出
:wq|	保存并退出
:set number|	显示行号
:set nonumber|	隐藏行号
/sai|	在文档中查找sai 按n跳到下一个，shift+n上一个
u|	撤销
ctrl+r|	重做
yyp|	复制光标所在行，并粘贴
dd|	剪切当前行
ndd|	n表示大于1的数字，剪切n行
dw|	从光标处剪切至一个单子/单词的末尾，包括空格
de|	从光标处剪切至一个单子/单词的末尾，不包括空格
d$|	从当前光标剪切到行末
d0|	从当前光标位置（不包括光标位置）剪切之行首
d3l|	从光标位置（包括光标位置）向右剪切3个字符
d5G|	将当前行（包括当前行）至第5行（不包括它）剪切
d3B	从当前光标位置（不包括光标位置）反向剪切3个单词
dH	剪切从当前行至所显示屏幕顶行的全部行
dM	剪切从当前行至命令M所指定行的全部行
dL	|剪切从当前行至所显示屏幕底的全部行
h	|(左移一个字符←)
j	|(下一行↓)
k	|(上一行↑)
l	|(右移一个字符→)
ctrl+f|	下翻一屏。
ctrl+b|	上翻一屏。
ctrl+d|	下翻半屏。
ctrl+u|	上翻半屏。
ctrl+e|	向下滚动一行。
ctrl+y|	向上滚动一行。
n%	|到文件n%的位置。
zz	|将当前行移动到屏幕中央。
zt|	将当前行移动到屏幕顶端。
zb|	将当前行移动到屏幕底端。


若干实用命令：
```
// 查看并发数
netstat -n | awk '/^tcp/ {++S[$NF]} END {for(a in S) print a, S[a]}'

//修改文件时间
touch -d "6:03pm 05/06/2000" file


// 删除过期日志
find /data/ -mtime +32 -name '*[0-9].log' -exec rm -rf {} \;

// 杀死php-fpm进程
ps -ef|grep php-fpm|awk -F ' ' '{print $2}'|xargs kill -9
```






