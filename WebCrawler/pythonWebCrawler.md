# Python爬虫基本了解

## URL (Uniform Resource Locator, 统一资源定位符)
URL就是指网址，它包含的信息可以指出对应资源的位置。URL由三部分组成：

1. 第一部分是协议
2. 第二部分是存有该资源的主机IP地址（有时候也包括端口号）
3. 第三部分是主机资源的具体地址，如在哪个目录下

## Python爬虫工具

- urllib和urllib2
- requests
- Beautiful Soup
- scrapy
- mechanize
- httplib
- httplib2

## 安装Scrapy

1. 先安装pip。pip和easy\_install都是Python包管理工具，pip是easy\_install的升级版。

	```
	sudo easy_install pip
	```
2. 安装Scrapy。

	```
	sudo pip install Scrapy
	```
3. 如果安装成功，在终端执行`scrapy`会出现：

	```
	Scrapy 0.24.2 - no active project
	
	Usage:
	  scrapy <command> [options] [args]
	
	Available commands:
	  bench         Run quick benchmark test
	  fetch         Fetch a URL using the Scrapy downloader
	  runspider     Run a self-contained spider (without creating a project)
	  settings      Get settings values
	  shell         Interactive scraping console
	  startproject  Create new project
	  version       Print Scrapy version
	  view          Open URL in browser, as seen by Scrapy
	
	  [ more ]      More commands available when run from project directory
	
	Use "scrapy <command> -h" to see more info about a command
	```
	
有时候会遇到错误

- 如果出现如下错误：

	```
	/var/folders/zz/fsjdxq092tv76y4kv3br4ybm0000gn/T/xmlXPathInityOS5ip.c:1:10: fatal error: 'libxml/xpath.h' file not found
	#include "libxml/xpath.h"
	         ^
	1 error generated.
	*********************************************************************************
	Could not find function xmlCheckVersion in library libxml2. Is libxml2 installed?
	Perhaps try: xcode-select --install
	*********************************************************************************
	error: command 'cc' failed with exit status 1
	    
	----------------------------------------
	Command "/usr/bin/python -c "import setuptools, tokenize;__file__='/private/var/folders/zz/fsjdxq092tv76y4kv3br4ybm0000gn/T/pip-build-ikU1yx/lxml/setup.py';exec(compile(getattr(tokenize, 'open', open)(__file__).read().replace('\r\n', '\n'), __file__, 'exec'))" install --record /var/folders/zz/fsjdxq092tv76y4kv3br4ybm0000gn/T/pip-RCyhfS-record/install-record.txt --single-version-externally-managed --compile" failed with error code 1 in /private/var/folders/zz/fsjdxq092tv76y4kv3br4ybm0000gn/T/pip-build-ikU1yx/lxml
	```

	解决方法有以下几种：
	1. 终端执行命令安装或更新命令开发工具

		```
		xcode-select --install
		```
	2. 配置路径：C\_INCLUDE\_PATH

		```
		C_INCLUDE_PATH=/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.10.sdk/usr/include/libxml2:/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.10.sdk/usr/include/libxml2/libxml:/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.10.sdk/usr/include
		```
	3. 参照官网使用如下命令安装Scrapy

		```
		STATIC_DEPS=true pip install lxml
		```

	如果还是失败，报如下错误：
	
	```
	Traceback (most recent call last):
	  File "/usr/local/bin/scrapy", line 7, in <module>
	    from scrapy.cmdline import execute
	  File "/Library/Python/2.7/site-packages/scrapy/__init__.py", line 48, in <module>
	    from scrapy.spiders import Spider
	  File "/Library/Python/2.7/site-packages/scrapy/spiders/__init__.py", line 10, in <module>
	    from scrapy.http import Request
	  File "/Library/Python/2.7/site-packages/scrapy/http/__init__.py", line 12, in <module>
	    from scrapy.http.request.rpc import XmlRpcRequest
	  File "/Library/Python/2.7/site-packages/scrapy/http/request/rpc.py", line 7, in <module>
	    from six.moves import xmlrpc_client as xmlrpclib
	ImportError: cannot import name xmlrpc_client
	```
	则在终端执行：
	
	```
	pip install scrapy==0.24.2
	```