# C++学习笔记——第三章 处理数据

## 3.1简单变量
### 基本数据类型

- char：表示字符
- short(short int)：至少16位
- int(signed int)：至少和short一样
- long(long int)：至少32位
- long long：至少64位

sizeof运算符可以返回类型或者变量的长度，单位为字节。

### const限定符
const限定了声明的含义，指出定义了一个常量。创建常量的通用格式如下：
```
const type name=value;
```

### 浮点类型

- float：为32位
- double：为64位
- long double：为80、96或128位

### 强制类型转换
格式一：
```
(typeName) value
typeName (value)
```
格式二
```
static_cast<typeName> (value)
```