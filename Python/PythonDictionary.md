
# 字典（Dictionary）

一系列“键-值（key-value）”对

## 创建字典

- 使用{}创建字典
- 使用:指明 键:值 对
- 键必须是不可变的且不重复，值可以是任意类型

## 访问字典

- 使用[]运算符，键作为索引

## 字典运算符和方法

- len(my_dict)
- key in my_dict 快速判断key是否为字典中的键
- my_dict.items() 返回全部键值对
- my_dict.keys() 全部的键
- my_dict.values() 全部的值
- my_dict.clear 清空字典

# 集合（set）

无序不重复元素（键）集，和字典类似，但无值

- 创建：`x=set()`,`x={key1,key2,...}`
- 添加和删除：`x.add('body')``x.remove('body')`
- 集合运算符：- & | != == in `for key in set`