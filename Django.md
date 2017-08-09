### 数据库配置——Mysql的配置
在Python3.x中使用Django连接Mysql需要使用pymysql库，因为Django默认的是使用其他的第三方库连接，
所以需要自己配置连接。

配置方法如下：

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
- 注意：
    - 如果一开始使用的是自带的数据库，需要把自带数据库的日志文件删除（即migrations中除了__init__文件之外的所有文件）
    - 重新运行数据库，添加新的内容