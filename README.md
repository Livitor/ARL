123云盘文件分享：https://www.123pan.com/s/kyiA-RlUXH?提取码:fRnI

## 如何安装
- 安装 `docker.io` 和 `docker-compose`
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
