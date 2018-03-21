### 数据库配置——Mysql的配置
在Python3.x中使用Django连接Mysql需要使用pymysql库，因为Django默认的是使用其他的第三方库连接，
所以需要自己配置连接。

#### 配置方法如下：

- 在setting文件中添加如下代码，引入连接库

```python
import pymysql
pymysql.install_as_MySQLdb()
```
- 然后把其中的DATABASES改成这样：
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'OPTIONS': {'read_default_file':os.path.join(BASE_DIR,'my.cnf'),}
    }
}
```
- 在最外层文件夹（也就是与manage.py同目录）创建文件my.cnf，写入数据库配置代码：
```python
[client]
database = 'djangotest'
user = 'root'
password = 'python'
dafault-character-set = utf8mb4
```
#### 注意：
- 如果一开始使用的是自带的数据库，需要把自带数据库的日志文件删除（即migrations中除了__init__文件之外的所有文件）
- 重新运行数据库，添加新的内容
    
### Django全文搜索应用
#### 官方文档很有用，必须要看
链接：https://django-haystack.readthedocs.io/en/v2.5.1/views_and_forms.html
#### 视图是可以重写的
可以不用原来的，而且重写之后会更好用，使用`SearchView`视图函数重写，用法跟内置的`ListView`基本一致
#### 保存索引的信息需要变化一下
主要是文章内容，不能使用原生的内容，因为原文是用markdown写的，如果直接用的话，在索引里面会包含一些markdown的信息，不利于正确的索引
```
{{ object.body }}
```
而应该改成下面这种，也就是只对已经把标签处理过的内容进行索引
```
{{ object.body_to_markdown }}
```
### 关于django使用邮箱
#### 端口问题
25端口在阿里云上面无法使用，所以必须换其他端口，在使用邮箱的时候要确保服务器端口已经开启了，例如163的端口本来是25，但是可以改成SSL加密的方式，端口就是465，然后在服务器上面开启这个端口就可以使用。

### 部署django
Nginx+Gunicorn部署教程https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu-16-04

![www.seoerzone.com](http://cdn.seoerzone.com/article/180321/seoerzone-01.png)
