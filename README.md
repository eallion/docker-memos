# Build Memos Docker image Nightly

# ** Deprecated, Archived! **

English | [中文](./README_cn.md)

Build Memos Docker image nightly based on: [`usememos/memos:main`](https://github.com/usememos/memos)

> https://hub.docker.com/r/eallion/memos

### Schedule

`schedule: '0 16 * * *'` means that it is built everyday at 24:00 UTC+0800 (Beijing time)

### Usage

> **Note**

Replace `neosmemo/memos:latest` with `eallion/memos:nightly`.  

#### Docker Run

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
