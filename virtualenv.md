#virtualenv(python虚拟环境)
virtualenv是一个工具，可以利用它创建与操作系统python环境相孤立的python运行环境，方便测试和开发依赖包的管理。

##如何指定虚拟环境的python解析器
在同一个操作系统中，可能安装了python2，也可能安装了python3，可以利用以下命令指定虚拟环境中的python解析器。

```shell
virtualenv -p /usr/bin/python2.7 venv
```

##其他一些注意点
virtualenv的参数选项--no-site-package，其作用是在虚拟环境中不会include全局安装的package python包，使得虚拟环境中安装的python包是clean的。不过在virtualenv1.7版本以后，这个已经是virtualenv命令的默认行为了。

##virtualenvwrapper命令
virtualenvwrapper命令基于virtualenv，提供了管理python虚拟运行环境中的便捷命令。

注意使用了pip安装virtualenvwrapper后，还需要运行以下命令才能使用virtualenvwrapper相关的命令。

```shell
$ export WORKON_HOME=~/Envs
$ source /usr/local/bin/virtualenvwrapper.sh
```

WORKON_HOME环境变量指定的一个目录，所有通过virtualenvwrapper创建的目录都在改目录下，方便管理。

```shell
$mkvirtualenv venv
```
mkvirtualenv命令创建python虚拟创建。

```shell
$workon venv
```
workon 在一个python虚拟环境中工作.更加方便的是workon命令提供了python虚拟环境名称的自动补全，可以利用tab按键进行自动补全。

其他一些常用的命令如下:

1. lsvirtualenv:列出所有的虚拟环境名称
2. cdsitepackages:直接进入虚拟环境的site-packages目录

##在virtualenv中运行supervisor

supervisor配置文件会从一些预设的地方搜索

1. $CWD/supervisord.conf
2. $CWD/etc/supervisord.conf
3. /etc/supervisord.conf
4. /etc/supervisor/supervisord.conf (since Supervisor 3.3.0)
5. ../etc/supervisord.conf (Relative to the executable)
6. ../supervisord.conf (Relative to the executable)

如果在virtualenv中运行supervisor，那么这些配置文件可以放在什么地方，让supervisor自动搜索到?

如python虚拟环境的根目录是:

```shell
/Users/eason/Coding/pyenv/
```

那么可以在以下目录中建立supervisord.conf，让supervisord自动搜索到配置文件

```shell
/Users/eason/Coding/pyenv/etc/supervisord.conf
```



