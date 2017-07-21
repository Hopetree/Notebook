## mongoimport mongo导入Json的用法
- step1:
</br>进入mongodb\bin
- step2:
</br>按照json文件格式选择命令：
    - 导入json
</br>`mongoimport --db db_name --collection collection_name --file d:/testfile/test.json`
    - 导入Json数组（JSON文件是一个列表的格式，一般都是用这个）
</br>`mongoimport --db ML_OER --collection lecture --file /home/tmp/course_temp.json --jsonArray`
