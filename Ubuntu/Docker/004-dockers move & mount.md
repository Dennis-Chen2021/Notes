## docker 目录移动到其他磁盘的操作

 1. `systemctl stop docker`  #停止docker
 2. `systemctl status docker`  #查看docker服务状态
 3. `mv /var/lib/docker
    /media/li/1d105677-e036-4fa4-8e37-124cb400f24d/user/` 
    #将var下的docker移动到/机械盘中
 4. `ln -s  /media/li/1d105677-e036-4fa4-8e37-124cb400f24d/user/docker
    /var/lib/docker`  #创建软连接，将docker这个路径存到/var目录下
 5. #这时候检查一下/var/lib/docker目录是否已经软连接到/storage/docker-lib     
  		`ll /var/lib`   	
  		`ll /var/lib/docker`#查看对应软连接是否创建成功
 6. `systemctl start docker`   #启动docker
 7. `systemctl status docker`  #查看docker服务状态

## docker 目录挂载到其他盘
/root/test 是宿主机目录
/root/soft 是容器目录 
```bash
docker run -it --name="cuda" --gpus=all  -v /root/test:/root/soft pytorch/pytorch:1.9.1-cuda11.1-cudnn8-devel /bin/bash 
```
或

```bash
docker run -it --name="cuda" --gpus=all -v /root/test:/root/soft  -p 50001:22 pytorch191:pytorch191SSH /usr/sbin/sshd -D
```

