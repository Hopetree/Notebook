## 安装 docker

> docker-io, docker-engin 是以前早期的版本，版本号是 1.*，默认centos7 安装的是docker-io，最新版是 1.13;Ubuntu默认安装的是docker-ce
,docker-ce 是社区版本，适用于刚刚开始docker 和开发基于docker研发的应用开发者或者小型团队,所以这里统一为安装docker-ce

### CentOS 系统安装 docker
1. 查询内核版本，docker内核版本必须是3.10+以上的版本
```
uname -r
```

2. 卸载老版本的 docker 及其相关依赖
```
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```
2-2. 清理目录
```
rm -rf /var/lib/docker
rm -rf /var/run/docker
```

3. 更新yum
```
yum update
```

4. 安装 yum-utils，它提供了 yum-config-manager，可用来管理yum源
```
sudo yum install -y yum-utils
```

5. 添加yum源
```
sudo yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

6. 更新yum索引
```
sudo yum makecache fast
```

7. 安装 docker-ce
```
sudo yum install -y docker-ce
```

8. 启动 docker并设置成系统服务
```
sudo systemctl start docker
sudo systemctl enable docker
```

9. 将当前用户添加到docker用户组
```
sudo usermod -aG docker $USER
# 如果用户组不存在就先创建用户组
# groupadd docker
```

10. 检查docker安装情况
```
docker -v
docker info
```

## 设置docker
1. 编辑docker源配置文件
```
sudo vi /etc/docker/daemon.json
# 编辑国内源，如下
{
 "registry-mirrors": ["https://registry.docker-cn.com"]
}
```

2. 重启docker
```
sudo systemctl daemon-reload 
sudo systemctl restart docker
```

