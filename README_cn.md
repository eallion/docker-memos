# Memos 官方 Docker 镜像每日构建版

中文 | [English](./README.md)

基于官方 Repo [`usememos/memos:main`](https://github.com/usememos/memos)的 Memos Dcoker 镜像每日构建版

> https://hub.docker.com/r/eallion/memos

### 计划任务

`schedule: '0 16 * * *'` 在北京时间的每天晚上 0 点通过 GitHub Actions 自动构建。

### 使用用法

> **Note**

用 `eallion/memos:nightly` 替换 `neosmemo/memos:latest` 。

#### Docker 命令行

```bash
docker run -d --name memos -p 5230:5230 -v ~/.memos/:/var/opt/memos eallion/memos:nightly
```

#### Docker Compose

`docker-compose.yml`

```yml
version: "3.0"
services:
  memos:
    image: eallion/memos:nightly
    container_name: memos
    volumes:
      - ~/.memos/:/var/opt/memos
    ports:
      - 5230:5230
    restart: always
```