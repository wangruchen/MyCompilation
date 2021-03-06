# CMake使用笔记

[toc]

参考文章：[CMake入门教程](http://blog.csdn.net/fan_hai_ping/article/details/42524205)，[CMake入门实战](http://hahack.com/codes/cmake/)

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
	* 例：`include_directories(/usr/local/include)`将目录下的头文件加入到工程中
* find\_path命令
	* `find_path(<VAR> name1 [path1 path2 …])`
	* 查找包含文件 name1 的路径，如果找到则将路径保存在 VAR 中（此路径为一个绝对路径），如果没有找到则结果为\<VAR> - NOTFOUND
* find_library命令
	* `find_library(<VAR> name1 [path1 path2 …])`
	* 查找库文件 name1 的路径，如果找到则将路径保存在 VAR 中（此路径为一个绝对路径），如果没有找到则结果为\<VAR> - NOTFOUND。
* find_package命令
	* `find_package(<name> [major.minor] [QUIET] [NO_MODULE][[REQUIRED|COMPONENTS] [componets...]])`
	* 指示要找的包name是否被找到。
	* 参数：
		* QUIET：禁用掉包没有被发现时的警告信息。
		* REQUIRED：如果没有找到，cmake的过程会终止，并输出警告信息。
		* EXACT：要求该版本号必须精确匹配。
* set命令
	* `set(<variable> <value>)`
	* 用于设定变量variable的值为value
	* 例：`set(Hello main)`
* unset命令
	* `unset(<variable> [CACHE])`
	* 用于移除变量variable，如果指定了CACHE变量将从Cache中移除。
	* 例：`unset(var CACHE)`

## 例子

### 例1
**假设现在我们的项目中只有一个源文件 main.cpp 。**

1. 编写 CMakeLists.txt 文件，并保存在与 main.cpp 源文件同个目录下。
	
	```
	cmake_minimum_required(VERSION 3.1)
	project(name)
	add_executable(name main.cpp)
	```

2. 编译当前项目：

	```
	cmake PATH
	make
	```
	CMakeLists.txt就在当前目录下时`cmake .`。

### 例2
**假设现在我们的项目中只有一个源文件 main.cpp，但需要调用OpenCV。**

编写 CMakeLists.txt 文件，并保存在与 main.cpp 源文件同个目录下.

```
cmake_minimum_required(VERSION 3.1)
project(Batching)
find_package( OpenCV REQUIRED )
include_directories( /usr/local/include )
add_executable(Batching main.cpp)
target_link_libraries( Batching ${OpenCV_LIBS} )
```
`project`:表示项目的名称是Batching。
	
`find_package`:寻找OpenCV的库的位置
	
`include_directories`:将目录下的头文件加入到工程
	
`add_executable`:表示将名为 main.cpp 的源文件编译成一个名称为 Batching 的可执行文件
	
`target_link_libraries`:加入动态链接库

### 例3
**如果在一个目录下有多个源文件（除了主函数还有其他子函数）。**

```
./Demo
    |
    +--- main.cpp
    |
    +--- subfunction.cpp
    |
    +--- subfunction.h
```

编写 CMakeLists.txt 文件可以写成：

```
cmake_minimum_required(VERSION 3.1)
project(name)
add_executable(name main.cpp subfunction.cpp)
```
或

```
cmake_minimum_required(VERSION 3.1)
project(name)
aux_source_directory(. DIR_SRCS)
add_executable(name ${DIR_SRCS})
```
	
`aux_source_directory `:命令会查找指定目录下的所有源文件，然后将结果存进指定变量名。

### 例4
**如果有多个目录多个源文件（源文件放在不同的目录下）。**

```
./Demo
    |
    +--- main.cpp
    |
    +--- CMakeLists.txt(1)
    |
    +--- subfunction/
          |
          +--- subfunction.cpp
          |
          +--- subfunction.h
          |
          +--- CMakeLists.txt(2)
```
编写 CMakeLists.txt(1) 文件可以写成：

```
cmake_minimum_required(VERSION 3.1)
project(name)
add_subdirectory(subfunction)
include_directories(subfunction)
add_executable(name ${DIR_SRCS})
target_link_libraries(name subfunction)
```
`add_subdirectory`:指明本项目包含一个子目录subfunction。

CMakeLists.txt(2) 文件可以写成：

```
aux_source_directory(. DIR_SRCS)
add_library(subfunction ${DIR_SRCS})
```
###例5
**如果有多个目录多个源文件（源文件放在不同的目录下），需要调用OpenCV库。**

```
./hog
    |
    +--- main.cpp
    |
    +--- CMakeLists.txt(1)
    |
    +--- source/
          |
          +--- confusionMatrix.cpp
          |
          +--- pathAndLabel.cpp
          |
          +--- WriteData.cpp
          |
          +--- confusionMatrix.h
          |
          +--- pathAndLabel.h
          |
          +--- WriteData.h
          |
          +--- CMakeLists.txt(2)
```

CMakeLists.txt(1):

```
cmake_minimum_required(VERSION 3.1)
project(hog)
find_package(OpenCV REQUIRED)
include_directories(/usr/local/include source)
add_subdirectory(source)
add_executable(hog main.cpp)
target_link_libraries(hog ${OpenCV_LIBS} source)
```
CMakeLists.txt(2):

```
aux_source_directory(. DIR_SRCS)
add_library(source ${DIR_SRCS})
```


