# Docker 部署

## 创建基础镜像

> 主要是安装requirements.txt中的依赖

```bash
sudo docker build -f Dockerfile.base -t @base_img:@tag .
```

❗`@base_img:@tag `需要自己设置，其中，`base_img`: 基础镜像的名字，tag: 版本号。

## 创建项目镜像

需要修改 `Dockerfile.prod`中的 `FROM @base_image:@tag`， 与上面的 `@base_img:@tag`一致。

### 使用Dockerfile创建

```bash
sudo docker build -f Dockerfile.prod -t @proj_img:@tag .
```

❗`@proj_img:@tag `需要自己设置，其中，proj_img: 项目镜像的名字，tag: 版本号。

### 使用docker-compose创建镜像并实例化容器

可以在 `docker-compose.yml`中设置环境变量，端口映射，挂载文件夹……

```bash
docker-compose up -d
```
