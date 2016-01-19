# C++学习笔记

## 字符函数库cctype

- isalpha() 检查字符是否为字母字符
- isdigits() 检查字符是否为数字字符
- isspace() 检查字符是否是空白（换行符、空格和制表符）
- ispunct() 检查字符是否为标点符号
- ···

## ?:运算符

该运算符的通用格式：

```
expression1 ? expression2 : expression3
```
如果expression1为true，则整个条件表达式的值为expression2的值，否则为expression3的值。

## 写入到文本文件中

文件输入：

- 必须包含头文件fstream。
- 头文件fstream定义了一个用于处理输出的ofstream类。
- 必须指明名称空间std。
- 需要将ofstream对象与文件关联起来。方法之一使用open()，使用完后应用close()将其关闭。（注：open("txtName.txt")将创建一个txtName.txt文件，如果该文件已经存在了，默认将其中原有的内容丢掉，将新的内容输入）
- 采用运算符<<来输出各种类型的数据。

文件输出的主要步骤：

1. 包含头文件fstream。
2. 创建一个ofstream对象。
3. 将该ofstream对象同一个文件关联起来。
4. 像使用cout一样使用ofstream对象。

## 读取文本文件

文件输出：

- 必须包含头文件fstream。
- 头文件fstream定义了一个用于处理输入的ifstream类。
- 必须指明名称空间std。
- 需要将ifstream对象与文本文件关联起来。方法之一使用open()。
- 使用ifstream对象和get()来读取一个字符，用ifstream和getline()来读取一行字符。
- 用ifstream和eof()、fail()定来判断输入是否成功。
- ifstream本身作为测试条件，如果最后一个读取成功，它将被转换为布尔值true。









