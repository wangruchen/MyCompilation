# 函数

Python中用`def`定义一个函数，依次写出函数名、括号、参数和冒号。函数体缩进，返回值用`return`。

例：

```
def compare(x,y):
	if x > y:
		return True
	else:
		return False
```

如果将上面函数保存为function.py，可以用`from function import compare`来导入compare函数。

注意：Python的函数返回多个值其实是返回的一个tuple（元组）。

## 函数的参数

必选参数、可变参数、关键字参数。

- 可变参数：`*args`是可变参数，args接收一个tuple
- 关键词参数：`**kw`是关键词参数，kw接收一个字典