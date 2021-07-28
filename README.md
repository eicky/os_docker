# os_docker

docker下的系统基础镜像,目前仅增加了ssh server服务用以远程连接

# 使用方法

``` shell
docker run -itd --name ubuntu -p 2222:22 eickydev/os:ubuntu-20.04
```

# docker-compose中使用

```shell
version: "3"

services:
  ubuntu:
    image: eickydev/os:ubuntu-20.04
    container_name: ubuntu
    restart: always
    stdin_open: true
    tty: true
    ports:
      - "2222:22"

```

# 密码都是`123456`
