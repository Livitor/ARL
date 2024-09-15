123云盘文件分享：https://www.123pan.com/s/kyiA-RlUXH?提取码:fRnI

## 如何安装
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
