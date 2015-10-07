# CMake总结
参考文章：[CMake入门教程](http://blog.csdn.net/fan_hai_ping/article/details/42524205)

## 介绍
CMake 生成 Makefile 并编译的流程：

1. 编写 CMakeLists.txt。
2. 执行命令 `cmake PATH` 生成 Makefile (PATH 是CMakeLists.txt所在的目录)。
3. 使用 `make` 命令进行编译。

## 命令

* project命令
	* 指定项目名称
	* 例：`project(Hello)`指定项目名称为Hello
	* 使用`${Hello_SOURCE_DIR}`表示项目根目录
* cmake\_minimum_required命令
	* 指定CMake的最低版本
	* 例：`cmake_minimum_required(VERSION 3.1)`
* aux\_source_directory命令
	* `aux_source_directory(<dir> <variable>)`
	* 将dir目录下的所有源文件的名字保存在变量variable中
	* 例：`aux_source_directory(. DIR_SRCS)`
* add\_executable命令
	* 指定一组源文件编译出一个可执行文件且命名
	* 例：`add_executabel(hello main.cpp)`
* add\_library命令
	* 指定一组源文件编译出一个库文件且命名
	* 例：`add_library(hello my.cpp)`
* add\_dependencies命令
	* 用于指定某个目标（可执行文件或库文件）依赖于其他的目标
* add\_subdirectory命令
	* 用于添加一个需要进行构建的子目录
	* 例：`add_subdirectory(src)`
* target\_link_libraries命令
	* 用于指定链接库
	* 例：`target_link_libraries(Hello libs)`
* include\_directories命令
	* 指定头文件的搜索路径
	* 例：`include_directories("/usr/local/include")`将目录下的头文件加入到工程中
* find\_path命令
	* `find_path(<VAR> name1 [path1 path2 …])`
	* 查找包含文件 name1 的路径，如果找到则将路径保存在 VAR 中（此路径为一个绝对路径），如果没有找到则结果为\<VAR> - NOTFOUND
* find_library命令
	* `find_library(<VAR> name1 [path1 path2 …])`
	* 查找库文件 name1 的路径，如果找到则将路径保存在 VAR 中（此路径为一个绝对路径），如果没有找到则结果为\<VAR> - NOTFOUND。

## 例子
假设现在我们的项目中只有一个源文件 main.cc 。

1. 编写 CMakeLists.txt 文件，并保存在与 main.cpp 源文件同个目录下。

	```
	cmake_minimum_required(VERSION 3.1)
	project (Batching)
	find_package( OpenCV REQUIRED )
	include_directories( "/usr/local/include" )
	add_executable(Batching main.cpp)
	target_link_libraries( Batching ${OpenCV_LIBS} )
	```
	`project`:表示项目的名称是Batching。
	
	`find_package`:寻找OpenCV的库的位置
	
	`include_directories`:将目录下的头文件加入到工程
	
	`add_executable`:表示将名为 main.cpp 的源文件编译成一个名称为 Batching 的可执行文件
	
	`target_link_libraries`:加入动态链接库
2. 编译当前项目：

	```
	cmake PATH
	make
	```

