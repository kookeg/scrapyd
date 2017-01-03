### 部署步骤
1. 更新包 软件和系统内核
    - yum -y update 
2. 安装epel
    - yum -y install epel-release
3. 安装docker环境
    - 见官网doc https://docs.docker.com/engine/installation/linux/rhel/
4. 构建Dockerfile文件
    - mkdir -p /data/docker/scrapyd
    - cd /data/docker/scrapyd
    - dockerfile文件
5. 创建image 
    - docker build -t kookeg_scrapyd .
    - docker images  #查看images
6. 启动container 
    - docker run -itd -v /data/scrapyd:/data/scrapyd -p 8000:22 -p 6800:6800 --name=scrapyd kookeg_scrapyd
    - docker inspect scrapyd 查看容器信息
    - ssh root@localhost -p 8000 登录容器 密码:kookeg

