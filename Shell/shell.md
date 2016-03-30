# Shell使用笔记

参考[鸟哥的Linux私房菜](http://vbird.dic.ksu.edu.tw)

shell有许多不同的版本，Linux中默认的版本为bash。

## Bash shell的功能

- 记忆功能(history)
- 命令文件补全功能([tab])
- 命令别名配置功能(alias)

	例如`alias lm='ls -al'`
- 工作控制、前景背景控制
- 程序化脚本(shell scripts)

## Bash shell内建命令type

透过type命令可以知道每个命令是否为bash的内建命令。

```
type [-tpa] name
选项与参数：
    ：不加任何选项与参数时，type 会显示出 name 是外部命令还是 bash 内建命令
-t  ：当加入 -t 参数时，type 会将 name 以底下这些字眼显示出他的意义：
      file    ：表示为外部命令；
      alias   ：表示该命令为命令别名所配置的名称；
      builtin ：表示该命令为 bash 内建的命令功能；
-p  ：如果后面接的 name 为外部命令时，才会显示完整文件名；
-a  ：会由 PATH 变量定义的路径中，将所有含 name 的命令都列出来，包含 alias
```

## 变量配置守则

1. 等号两边不能直接接空格
2. 变量名称只能是英文字母和数字，但是开头字符不能是数字
3. 变量内容中若有空格可以使用双引号或单引号将变量内容结合
	- 双引号内的图像字符如$等，可以保持原有的特性
	- 单引号内的特殊字符仅为一般字符
4. 可以用跳脱字符`\`将特殊符号变为一般字符
5. 若该变量需要在其他子程序运行，则需要以 export 来使变量变成环境变量：`export PATH`
6. 取消变量的方法为unset 

## 从网页上抓取内容

### curl
参考文章：[Linux Shell脚本编程－－curl命令详解](http://blog.csdn.net/xifeijian/article/details/9367339)

<!--1. 将文件保存为命令行中指定的文件名的文件中
```
curl -o home.html http://www.baidu.com
```

2. 使用URL中默认的文件名保存文件到本地
```
curl -O http://www.baidu.com/img/bdlogo.gif
```-->
curl命令的参数：

```
-A:随意指定自己这次访问所宣称的自己的浏览器信息
-b/--cookie <name=string/file> cookie字符串或文件读取位置，使用option来把上次的cookie信息追加到http request里面去。
-c/--cookie-jar <file> 操作结束后把cookie写入到这个文件中
-C/--continue-at <offset>  断点续转
-d/--data <data>   HTTP POST方式传送数据
-D/--dump-header <file> 把header信息写入到该文件中
-F/--form <name=content> 模拟http表单提交数据
-v/--verbose 小写的v参数，用于打印更多信息，包括发送的请求信息，这在调试脚本是特别有用。
-m/--max-time <seconds> 指定处理的最大时长
-H/--header <header> 指定请求头参数
-s/--slient 减少输出的信息，比如进度
--connect-timeout <seconds> 指定尝试连接的最大时长
-x/--proxy <proxyhost[:port]> 指定代理服务器地址和端口，端口默认为1080
-T/--upload-file <file> 指定上传文件路径
-o/--output <file> 指定输出文件名称
--retry <num> 指定重试次数
-e/--referer <URL> 指定引用地址
-I/--head 仅返回头部信息，使用HEAD请求
-u/--user <user[:password]>设置服务器的用户和密码
-O:按照服务器上的文件名，自动存在本地
-r/--range <range>检索来自HTTP/1.1或FTP服务器字节范围
-T/--upload-file <file> 上传文件
```

### wget
参考文章：[Linux Shell脚本编程－－wget 命令用法详解](http://blog.csdn.net/xifeijian/article/details/9399121)

wget是一个从网络上自动下载文件的自由工具。它支持HTTP，HTTPS和FTP协议。参数：

```
●启动:
-V, --version 显示wget的版本后退出
-h, --help 打印语法帮助
-b, --background 启动后转入后台执行
-e, --execute=COMMAND 执行`.wgetrc'格式的命令，wgetrc格式参见/etc/wgetrc或~/.wgetrc
wget默认会根据网站的robots.txt进行操作
使用-e robots=off参数即可绕过该限制
●记录和输入文件:
-o, --output-file=FILE 把记录写到FILE文件中
-a, --append-output=FILE 把记录追加到FILE文件中
-d, --debug 打印调试输出
-q, --quiet 安静模式(没有输出)
-v, --verbose 冗长模式(这是缺省设置)
-nv, --non-verbose 关掉冗长模式，但不是安静模式
-i, --input-file=FILE 下载在FILE文件中出现的URLs
-F, --force-html 把输入文件当作HTML格式文件对待
-B, --base=URL 将URL作为在-F -i参数指定的文件中出现的相对链接的前缀
--sslcertfile=FILE 可选客户端证书
--sslcertkey=KEYFILE 可选客户端证书的KEYFILE
--egd-file=FILE 指定EGD socket的文件名
●下载:
--bind-address=ADDRESS 指定本地使用地址(主机名或IP，当本地有多个IP或名字时使用)
-t, --tries=NUMBER 设定最大尝试链接次数(0 表示无限制).
-O --output-document=FILE 把文档写到FILE文件中
-nc, --no-clobber 不要覆盖存在的文件或使用.#前缀
-c, --continue 接着下载没下载完的文件
--progress=TYPE 设定进程条标记
-N, --timestamping 不要重新下载文件除非比本地文件新
-S, --server-response 打印服务器的回应
--spider 不下载任何东西
-T, --timeout=SECONDS 设定响应超时的秒数
-w, --wait=SECONDS 两次尝试之间间隔SECONDS秒
--waitretry=SECONDS 在重新链接之间等待1...SECONDS秒
--random-wait 在下载之间等待0...2*WAIT秒
-Y, --proxy=on/off 打开或关闭代理
-Q, --quota=NUMBER 设置下载的容量限制
--limit-rate=RATE 限定下载输率
●目录:
-nd --no-directories 不创建目录
-x, --force-directories 强制创建目录
-nH, --no-host-directories 不创建主机目录
-P, --directory-prefix=PREFIX 将文件保存到目录 PREFIX/...
--cut-dirs=NUMBER 忽略 NUMBER层远程目录
eg: wget  -q -N -x -nH --timeout=10 --tries=3 -i "newlists"
●HTTP 选项:
--http-user=USER 设定HTTP用户名为 USER.
--http-passwd=PASS 设定http密码为 PASS.
-C, --cache=on/off 允许/不允许服务器端的数据缓存 (一般情况下允许).
-E, --html-extension 将所有text/html文档以.html扩展名保存
--ignore-length 忽略 `Content-Length'头域
--header=STRING 在headers中插入字符串 STRING
--proxy-user=USER 设定代理的用户名为 USER
--proxy-passwd=PASS 设定代理的密码为 PASS
--referer=URL 在HTTP请求中包含 `Referer: URL'头
-s, --save-headers 保存HTTP头到文件
-U, --user-agent=AGENT 设定代理的名称为 AGENT而不是 Wget/VERSION.
--no-http-keep-alive 关闭 HTTP活动链接 (永远链接).
--cookies=off 不使用 cookies.
--load-cookies=FILE 在开始会话前从文件 FILE中加载cookie
--save-cookies=FILE 在会话结束后将 cookies保存到 FILE文件中
●FTP 选项:
-nr, --dont-remove-listing 不移走 `.listing'文件
-g, --glob=on/off 打开或关闭文件名的 globbing机制
--passive-ftp 使用被动传输模式 (缺省值).
--active-ftp 使用主动传输模式
--retr-symlinks 在递归的时候，将链接指向文件(而不是目录)
●递归下载:
-r, --recursive 递归下载－－慎用!
-l, --level=NUMBER 最大递归深度 (inf 或 0 代表无穷).
--delete-after 在现在完毕后局部删除文件
-k, --convert-links 转换非相对链接为相对链接
-K, --backup-converted 在转换文件X之前，将之备份为 X.orig
-m, --mirror 等价于 -r -N -l inf -nr.
-p, --page-requisites 下载显示HTML文件的所有图片
●递归下载中的包含和不包含(accept/reject):
-A, --accept=LIST 分号分隔的被接受扩展名的列表
-R, --reject=LIST 分号分隔的不被接受的扩展名的列表
-D, --domains=LIST 分号分隔的被接受域的列表
--exclude-domains=LIST 分号分隔的不被接受的域的列表
--follow-ftp 跟踪HTML文档中的FTP链接
--follow-tags=LIST 分号分隔的被跟踪的HTML标签的列表
-G, --ignore-tags=LIST 分号分隔的被忽略的HTML标签的列表
-H, --span-hosts 当递归时转到外部主机
-L, --relative 仅仅跟踪相对链接
-I, --include-directories=LIST 允许目录的列表
-X, --exclude-directories=LIST 不被包含目录的列表
-np, --no-parent 不要追溯到父目录
```
下载某个目录下面的所有文件：

```
wget -c -r -np -k -L -p www.baidu.com
```
