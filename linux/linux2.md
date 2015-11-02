# Linux使用笔记2——命令

## 统计文件个数

1. 查看某文件夹下目录的个数

	```
	ls -l|grep "^d"|wc -l
	```
	
2. 查看某目录下文件的个数

	```
	ls -l|grep "^-"|wc -l
	```
	
3. 查看某文件夹下目录的个数，包括子目录里的

	```
	ls -lR|grep "^d"|wc -l
	```
	
4. 查看某目录下文件的个数，包括子目录里的

	```
	ls -lR|grep "^-"|wc -l
	```