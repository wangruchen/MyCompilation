# 列表(List)

列表是一种有序的集合，可以随时添加和删除其中的元素。列表中的元素数据类型可以不同，元素也可是是另一个列表。列表可变。

例如：`alphabet=['a','b','c']`是一个列表。

- `len(alphabet)`函数可以得到列表元素的个数。用索引访问列表中的每一个元素，索引**从0开始**。
- `alphabet.append('d')`函数可以向list中追加元素到末尾。
- `alphabet.extend()`追加列表
- `alphabet.insert(1,'A')`向索引号为1的位置插入元素。
- `alphabet.pop()`删除list末尾的元素。`alphabet.pop(1)`删除索引号为1处的元素。
- `alphabet.remove()`删除元素
- `alphabet.sort()`排序
- `alphabet.reverse()`逆序

## 列表支持的操作

- 索引[]
- 切片[:]
- 拼接（+）重复（*）
- 成员（in）
- 长度（len()）
- 循环（for）

## 列表赋值

`b=a`没有生成新的列表，`b=a[:]`生成了新的列表

# 元组(tuple)
Python中另一个有序列表为元组。元组和列表类似，但元组一旦初始化就不能修改了。元组不能修改，所以代码更加安全。

例：`alphabet=('a','b','c')`

注意：定义一个元素的元组`alphabet=(a,)`

# 字典(dict)
Python内置了字典：dict全称dictionary，在其他语言中也称为map，使用键-值(key-value)存储，有很快的查找速度。

例：

```
>>> d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
>>> d['Michael']
95
```

# 集合(set)
set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。

要创建一个set，需要提供一个list作为输入集合：

```
>>> s = set([1, 2, 3])
>>> s
{1, 2, 3}
```

- `add(key)`添加元素
- `remove(key)`删除元素