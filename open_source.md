#开源python库

##sh
sh可以让你调度系统工具，如git，wc，ls等，就像一个函数一样使用方便。

开源地址：[https://github.com/amoffat/sh](https://github.com/amoffat/sh)

实例代码如下：

```python
from sh import ls
print ls("-l")
```

##path.py

path.py提供了Path类，封装了一些常见的文件操作，可以通过Path的实例对象去调用。使得文件操作更加简单，起码比python标准库的文件操作使用简单。

开源地址：[https://github.com/jaraco/path.py](https://github.com/jaraco/path.py)

代码实例如下：

```python
from path import Path
p = Path('/bin')
for f in p.files():
	print f
```

##overholt

overholt项目说明了如何构建大型flask项目。flask项目的骨架，api层，前端界面，后端管理层，中间件，服务层，测试，升级，部署等各方面。能够从中学习到如何去组织flask项目。

开源地址:[https://github.com/mattupstate/overholt](https://github.com/mattupstate/overholt)