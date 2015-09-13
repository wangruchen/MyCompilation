# CMake

## 介绍
CMake 生成 Makefile 并编译的流程：

1. 编写 CMakeLists.txt。
2. 执行命令 `cmake PATH` 生成 Makefile (PATH 是CMakeLists.txt所在的目录)。
3. 使用 `make` 命令进行编译。

## 例子
假设现在我们的项目中只有一个源文件 main.cc 。

1. 编写 CMakeLists.txt 文件，并保存在与 main.cc 源文件同个目录下。

	```
	PROJECT(project)
	CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
	ADD_EXECUTABLE(Demo main.cc)
	```
	`project`:表示项目的名称是project1。
	
	`ADD_EXECUTABLE`:表示将名为 main.cc 的源文件编译成一个名称为 Demo 的可执行文件
2. 编译当前项目：

	```
	cmake PATH
	make
	```

