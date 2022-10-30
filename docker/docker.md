# [官网手册](https`://docs.docker.com/desktop/install/mac-install/)

# 镜像（images）

1. `docker pull ubuntu`:20.04：拉取一个镜像
1. `docker images`：列出本地所有镜像
1. `docker image rm ubuntu:20.04` 或 `docker rmi ubuntu:20.04`：删除镜像ubuntu:20.04
1. `docker [container] commit CONTAINER IMAGE_NAME:TAG`：创建某个container的镜像
1. `docker save -o ubuntu_20_04.tar ubuntu:20.04`：将镜像ubuntu:20.04导出到本地文件ubuntu_20_04.tar中
1. `docker load -i ubuntu_20_04.tar：将镜像ubuntu`:20.04从本地文件ubuntu_20_04.tar中加载出来

# 容器(container)

1. `docker [container] create -it ubuntu:20.04`：利用镜像ubuntu:20.04创建一个容器。
1. `docker ps -a`：查看本地的所有容器
1. `docker [container] start CONTAINER`：启动容器
1. `docker [container] stop CONTAINER`：停止容器
1. `docker [container] restart CONTAINER`：重启容器
1. `docker [contaienr] run -itd ubuntu:20.04`：创建并启动一个容器
1. `docker [container] attach CONTAINER`：进入容器
 
    - 先按Ctrl-p，再按Ctrl-q可以挂起容器

1. `docker [container] exec CONTAINER COMMAND`：在容器中执行命令
1. `docker [container] rm CONTAINER`：删除容器
1. `docker container prune`：删除所有已停止的容器
1. `docker export -o xxx.tar CONTAINER`：将容器CONTAINER导出到本地文件xxx.tar中
1. `docker import xxx.tar image_name:tag`：将本地文件xxx.tar导入成镜像，并将镜像命名为image_name:tag
    
    - `docker export/import`与`docker save/load`的区别：
        - `export/import` 会丢弃历史记录和元数据信息，仅保存容器当时的快照状态
        - `save/load` 会保存完整记录，体积更大

1. `docker top CONTAINER`：查看某个容器内的所有进程
1. `docker stats`：查看所有容器的统计信息，包括CPU、内存、存储、网络等信息
1. `docker cp xxx CONTAINER`: 将本地文件xxx 或 `docker cp CONTAINER:xxx xxx`：在本地和容器间复制文件
1. `docker rename CONTAINER1 CONTAINER2`：重命名容器
1. `docker update CONTAINER --memory 500MB`：修改容器限制

