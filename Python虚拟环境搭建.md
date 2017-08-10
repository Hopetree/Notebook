## 一、Python虚拟环境virtualenv搭建

**使用virtualenvwrapper代替virtualenv**

首先进入cmd中安装这个模块：

`pip install virtualenvwrapper-win`

- 为了更好的管理多个虚拟环境，我们先在任意位置建立一个文件夹（我在F盘建立了F:\space_env）

- 然后把这个文件夹添加到系统环境变量，添加的方式：
>变量名：WORKON_HOME </br> 变量值：F:\space_env
</br>可以看截图：

![环境变量](https://github.com/Hopetree/Notebook/blob/master/screenshots/virtualenv001.png)

**说明**：
- 如果不添加这个环境变量，那之后创建的虚拟环境会默认保存在C:\Users\happy\Envs 中，创建了这个之后就可以默认保存在这里
- 添加了环境变量之后一定要关闭cmd 然后重新打开（如果使用的是pycharm则要重启一下才行）

创建一个虚拟环境：
- 创建一个虚拟环境，可以在任意目录状态下在cmd中输入如下命令：`mkvirtualenv new_env`
</br>可以看到类似如下回应：
```markdown
Using base prefix 'f:\\python352'
New python executable in F:\space_env\new_env\Scripts\python.exe
Installing setuptools, pip, wheel...done.
```
- 上面的代码大意是在new_env中创建了一个虚拟环境，这个环境引用的是系统中所带的Python版本（我的电脑是Python3.5.2）

- 现在可以看到F:\space_env目录下多了个文件夹new_env，同理，以后按照这个方式创建的虚拟环境都会保存在这个文件夹下

- 现在可以看到cmd显示的类似于(new_env) F:\DjangoSpace>，比本机环境多了个括号前面的，这表示已经在new_env环境中了，可以使用 `pip list`来看一下当前环境下的包，回应内容类似于：
```markdown
DEPRECATION: The default format will switch to columns in the future. You can use --format=(legacy|columns) (or define a format=(legacy|columns) in your pip.co
nf under the [list] section) to disable this warning.
pip (9.0.1)
setuptools (36.2.7)
wheel (0.29.0)
```
退出虚拟环境使用 `deactivate`

重新进入某个虚拟环境使用命令 `workon new_env`这种

需要建立其他的环境可以跟上面一样使用 `mkvirtualenv flask_env`

如果想要删除某个虚拟环境，则首先要**退出虚拟环境**，然后输入 `rmvirtualenv flask_env`即可

想要查看所有虚拟环境可以F:\space_env 中输入 `lsvirtualenv` 即可列出所有虚拟环境

## 二、生成虚拟环境需求文件和复制一个虚拟环境
生成文件：

在虚拟环境中使用 `(venv) $ pip freeze >requirements.txt` 可以生成一个虚拟环境的安装包版本文件
- 有时候需要调整安装包的顺序，例如一个安装包是依赖另一个的，则需要把依赖包放在靠前的位置
- 如果想安装某个包的最新版，则把==及后面的版本信息删除即可

复制环境：

首先新建一个虚拟环境，然后把需求文件放在space_env中（就是用来存在所有虚拟环境的那个文件夹中），运行 `(venv) $ pip install -r requirements.txt` 就可以按照需求包的内容复制一个安装包
