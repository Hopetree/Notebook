## Python虚拟环境virtualenv搭建

**使用virtualenvwrapper代替virtualenv**

首先进入cmd中安装这个模块：

`pip install virtualenvwrapper-win`

创建一个虚拟环境：
- 创建一个虚拟环境，可以在任何目录的状态下在cmd中输入如下命令：`mkvirtualenv blog_env`
</br>可以看到类似如下回应：
```python
Using base prefix 'f:\\python352'
New python executable in C:\Users\happy\Envs\blog_env\Scripts\python.exe
Installing setuptools, pip, wheel...done.
```
上面的代码大意是在blog_env中创建了一个虚拟环境，这个环境引用的是系统中所带的Python版本（我的电脑是Python3.5.2）

现在可以看到C:\Users\happy\Envs\目录下多了个文件夹blog_env，同理，以后按照这个方式创建的虚拟环境都会保存在这个文件夹下

现在可以看到cmd显示的类似于(blog_env) F:\DjangoSpace>，比本机环境多了个括号前面的，这表示已经在blog_env环境中了，可以使用 `pip list`来看一下当前环境下的包，回应内容类似于：
```python
DEPRECATION: The default format will switch to columns in the future. You can use --format=(legacy|columns) (or define a format=(legacy|columns) in your pip.co
nf under the [list] section) to disable this warning.
pip (9.0.1)
setuptools (36.2.7)
wheel (0.29.0)
```
退出虚拟环境使用 `deactivate`

重新进入某个虚拟环境使用命令 `workon blog_env`这种

需要建立其他的环境可以跟上面一样使用 `mkvirtualenv flask_env`

如果想要删除某个虚拟环境，则首先要退出虚拟环境，然后输入 `rmvirtualenv flask_env`即可

