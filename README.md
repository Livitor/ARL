123云盘文件分享：https://www.123pan.com/s/kyiA-RlUXH?提取码:fRnI

## 安装
- 更新本地仓库列表和系统, 如果已经更新完可以跳过
```bash
sudo apt update
sudo apt upgrade
```

- 安装 `docker.io` 和 `docker-compose` , 如果已经安装过可以跳过
```bash
sudo apt install docker.io docker-compose -y
```

- 创建 `/opt/docker_arl` 目录, 给文件保存到该目录
```bash
sudo mkdir /opt/docker_arl
```

- 解压 `ARL-2.6.1.zip` 文件, 然后加载另外三个 `tar` 包到本地镜像
```bash
unzip ARL-2.6.1.zip
sudo docker load < arl_2.6.1.tar
sudo docker load < arl_mongo.tar
sudo docker load < arl_rabbitmq.tar
```

- 进入到 `/opt/docker_arl/ARL-2.6.1/docker` 目录, 然后配置 `.env` 文件, 修改内容为: `ARL_VERSION=v2.6.1`
```bash
cd /opt/docker_arl/ARL-2.6.1/docker
vim .env
```
- 创建一个名为 `arl_db` 的用于持久化存储数据的, 首次部署灯塔需要创建, 若不是则不用理会
```bash
docker volume create arl_db
```

## 启动
直接在`/opt/docker_arl/ARL-2.6.1/docker` 目录下就可以启动
```bash
docker-compose up -d
```

## 关闭
- stop参数, 只能用于停止, 并不会删除这些容器, 后期还使用这些容器, 就可以使用 `start` 参数
```bash
docker stop arl_mongodb arl_rabbitmq arl_scheduler arl_web arl_worker
```
- rm参数, 用于删除已经创建的容器
```bash
docker rm arl_mongodb arl_rabbitmq arl_scheduler arl_web arl_worker
```
- rmi参数, 给之前导入的那三个 `tar` 包(镜像)删除
```bash
docker rmi mongo:4.0.27 rabbitmq:3.8.19-management-alpine tophant/arl:v2.6.1 
```
