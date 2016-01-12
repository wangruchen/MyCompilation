# C++学习笔记

## 字符串输入

- **cin**：每次读取一个单词

- **getline**：读取整行，丢弃最后的换行符。`cin.getline(name,number)`，第一个参数是存储数组名，第二个参数是要读取的字符个数。

- **get**：读取整行，保留换行符。
	
	读取到字符数组`cin.get(name,number)`，`cin.get(name,num).get()`读取之后再读取下一个字符。
	读取到string对象`getline(cin,str)`，cin作为参数指出到哪了找输入，str为变量名。

## 结构

结构是用户定义的类型。创建结构包括两步：先定义结构描述，然后创建结构变量。

- 声明结构：

	```
	struct StructName //StructName结构名称
	{
		char var1;//结构成员
		float var2;
		···
	};
	```
- 创建变量：

	```
	StructName varStructName; //C++中可以省略关键字struct
	struct inflatable goose; //C中需要struct
	```
	可以同时完成定义结构和创建结构变量：
	
	```
	struct StructName //StructName结构名称
	{
		char var1;//结构成员
		float var2;
		···
	} varStructName1, varStructName2;
	```
	也可以以这种方式初始化：
	
	```
	struct StructName //StructName结构名称
	{
		char var1;//结构成员
		float var2;
		···
	} varStructName1 =
	{
		'a',
		2.2,
		···
	};
	```
	
	初始化是使用逗号分隔，并将这些值用花括号括起来。
- 访问成员：

	使用成员运算符`.`来访问成员，例如：`varStructName.var1`

结构的其他属性：结构可以作为参数传递给函数，可以让函数返回一个结构，可以用赋值运算符赋给另一个结构。

- 结构数组：

	```
	StructName var[100];
	```
	
## 共用体

共用体是一种数据格式，能够存储不同的数据类型，但只能同时存储其中的一种类型。

- 声明共用体：

	```
	union UnionName
	{
		int intval;
		long longval;
		···
	};
	```
	一次只能存储一个值。
	
## 指针

### 指针的危险

在对指针应用解除引用（*）之前，一定要将指针初始化为一个确定的、适当的地址。例如，下面的代码是不正确的：

```
long * fellow;
*fellow = 223323;
```
初始化指针时，不能简单的将整数赋指针。例如，下面是不正确的：

```
int * pt;
pt = 0xB8000000;
```
可以通过强制类型转换将数字转换为适当的地址：

```
int * pt;
pt = (int *) 0xB8000000;
```
### 用new来分配内存

示例：

```
int * pn = new int; // typeName * pointer_name = new typeName;
```

new从被称为堆或自由存储区的内存区域分配内存。常规变量声明分配的内存从栈的内存区域中分配。

### 使用delete释放内存

示例：

```
int * ps = new int;
delete ps;//这将释放ps指向的内存，但不会删除指针ps本身。
```

### 使用new来创建动态数组

在C++中，创建动态数组只要将数组的元素类型和元素数目告诉new。

```
int * psome = new int [10];
delete [] psome;
```
如果使用new时带方括号，则delete也带方括号；如果使用new时不带方括号，则使用delete也不带放括号。

如何访问数组中的元素：`psome[0]`访问第一个元素，`psome[1]`访问的第二个元素。
