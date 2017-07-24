## mongodb的安装和设置成系统服务
- 安装
    - step1
    </br>在D盘根目录创建一个文件夹mongodb
    </br>在mongodb文件夹下创建data文件夹
    </br>在data文件夹中创建db和log文件夹
    - step2
    </br>开始安装mongodb，选择安装到刚才创建的mongodb文件夹中
    - step3
    </br>当安装完成，会看到mongodb中多了一个bin文件
    </br>将mongodb\bin添加到系统环境变量，最好用户和系统都添加一遍
    - step4
    </br>使用管理员权限打开CMD
    </br>现将路径切换到d:\mongodb\bin
    </br>然后输入`mongod --logpath D:\mongodb\data\log\mongodb.log --logappend --dbpath D:\mongodb\data\db --directoryperdb --serviceName MongoDB --install `
    便可以将MongoDB添加到系统服务
    - step5
    </br>打开系统该服务，开始MongoDB
    </br>如果无法开启服务，且报错代号100，则打开mongodb\data\db文件夹，删除mongod.lock和storage.bson
    
## mongoimport mongo导入Json的用法
- step1:
</br>cmd进入mongodb\bin
- step2:
</br>按照json文件格式选择命令：
    - 导入json
    </br>`mongoimport --db db_name --collection collection_name --file d:/testfile/test.json`
    - 导入Json数组（JSON文件是一个列表的格式，一般都是用这个）
    </br>`mongoimport --db ML_OER --collection lecture --file /home/tmp/course_temp.json --jsonArray`
