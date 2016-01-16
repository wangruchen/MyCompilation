# C++学习笔记

## 类型别名

为类型创建别名的两种方式：

- `#define BYTE char;`用char替换BYTE，从而使BYTE成为char的别名
- `typedef typeName aliasName;`例如：`typedef char byte;`

## 基于范围的for循环

基于范围的for循环，常见是对数组的每个元素执行相同的操作，示例：

```
int prices[5]={1, 2, 3, 4, 5};
for (int x : prices)
	cout << x << endl;
```

## 循环和文本输入

将下一个字符读入到一个char变量中：

```
char ch;
cin >> ch;//它将忽略空格、换行符和制表符
```

```
char ch;
cin.get(ch);//返回下一个字符包括空格、换行符和制表符
ch = cin.get();
```




