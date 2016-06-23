# C++学习笔记——string、vector、iterator

## string对象

```
#include <string>
using std::string
```

### 定义初始化string对象

```
string s1;
string s2(s1);//直接初始化
string s2 = s1;//拷贝初始化
string s3("value");
string s3 = "value";
string s4(n,'c');//把s4初始化为由连续n个字符c组成的串
```
### string操作

```
os<<s 将s写道输出流os中
is>>s 从is中读取字符串赋给s，字符串以空白分隔，返回is
getline(is,s) 从is中读取一行赋给s，返回is
s.empty() s为空返回true
s.size() 返回s中字符的个数
s[n]
s1+s2 两个字符串链接后的结果，不能把字面值直接相加
s1=s2
s1==s2
s1!=s2
<,<=,>,>= 
```

```
assign() 更改内容，s.assign(str)
swap() 
append(),push_back()
insert() 在string的某个位置插入字符串，s.insert(1,str)
erase() s.erase(3)从索引3开始都删除
clear()
replace() s.replace(1,2,"nternationa")从索引1开始的2个替换为后面的
max_size() 当前字符串最多可以包含的字符数
capacity() 重新分配内存之前string能包含的最大字符数
reserve()
copy() 把字符串的内容复制到字符数组内
c_str() 返回一个以'\0'结尾的字符数组
data() 以字符数组的形式返回字符串内容，但不添加'\0'
substr() s.substr(3)返回从索引3往后的子串
begin(),end()
rbegin(),rend()
get_allocator()
```

## vector对象

```
#include <vector>
using std::vector;
```

### 定义和初始化vector对象

```
vector<T> v1;
vector<T> v2(v1);
vector<T> v2 = v1;
vector<T> v3(n, val); //包括n个重复的元素，每个元素的值都是val
vector<T> v4(n);//包含n个重复地执行了值初始化的对象（数值为0，字符串为空）
vector<T> v5{a,b,c...};//包含了初始值个数的元素，每个元素被赋予相应的初始值
vector<T> v5={a,b,c...};
```
### vector操作

```
v.push_back(t) 向vector对象中添加元素t
v.empty() 如果v不含任何元素返回真
v.size() 返回v中元素的个数，返回类型为vector<int>::size_type
v[n] 不能用下标形式添加元素
v1 = v2
v1 = {a,b,c...}
<, <=, >, >=
v1 == v2
```
注意：vector对象和string对象的下标运算符可用于访问已经存在的元素，而不能用于添加元素。

## iterator 迭代器

所有标准库容器都可以使用迭代器，但只有少数几种支持下标运算符。

```
iter.begin() 返回指向的第一个元素
iter.end() 返回尾元素的下一个位置
*iter 返回迭代器iter所指元素的引用
iter->mem
++iter 下一个元素
--iter 上一个元素
iter1 == iter2
iter1 != iter2
```

### 迭代器类型

拥有迭代器的标准函数库类型用iterator和const_iterator来表示迭代器的类型：

```
vector<int>::iterator it;
vector<int>::const_iterator it2; //it2只能读元素，不能写
```