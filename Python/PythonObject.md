## 五种基本对象类型

1. 字符串（string），简记str，使用''或""括起来的一系列字符。
	或者使用三引号（"""或'''），显示字符串中的全部格式信息。
2. 整数（integer），简记int，十进制：21，八进制：025，十六进制：0x15
3. 浮点数（float）
4. 布尔数（boolean），简记bool
5. 复数（complex）

type()函数用来确定类型

### 字符串
字符串不可变

**基本运算**：
	
- 长度（len()函数）
- 拼接（+）
- 重复（*）：`"字符串"*重复次数`
- 成员运算符（in）：判断一个字符串是否是另一个字符串的子串
- for循环：枚举字符串中每个字符

**字符串索引（index）**

- 字符串中每个字符都有一个索引值（下标）
- 索引从0（前向）或-1（后向）开始

**切片（Slicing）**

选择字符串的子序列，语法[start:finish]

- start：子序列开始位置的索引值
- finish：子序列结束位置的下一个字符的索引值

**计数参数**

接收三个参数，[start:finish:countBy]，默认countBy为1

**其他字符串方法**

ss=s.replace(old,new)
ss=s.find(str)
ss=s.split()分割

**字符串格式化（Formatting）**

输出更规格的结果，s.format()

**正则表达式**

`import re`

正则表达式用来描述字符串的模式

- .表示任意字符
- \d+表示一系列数字
- [a-z]表示一个小写字母

## 模块（module）
实现一定的功能的Python脚本集合

- 引入模块：import module_name
- 查看模块内容：dir(module_name)

## 逻辑运算符

and or not

## 标识符

变量、函数、模块等的名字

命名规则：

- 包含数字、字母、下划线
- 首个必须是字母或下划线
- 大小写敏感
- 标识符不能是关键字

## 标准（键盘）输入

raw_input函数

- 功能：读取键盘输入，将所有输入作为字符串看待
- 语法：raw_input([prompt])

## 标准（控制台）输出

print关键字

- 功能：将对象的值输出到控制台上
- 语法：print object