
构建镜像和容器运行的基本命令如下👇

```bash
# 下载源代码
git clone https://github.com/kevinshen56714/SkyOffice.git

# 如果 github 慢或者访问不了
git clone https://hub.fastgit.org/kevinshen56714/SkyOffice.git

# 进入目录
cd SkyOffice/client

# 将前端编译生成静态文件
npm install && npm run build

# 记得删除 SkyOffice/client/node_modules 目录，不然镜像会更大

# 回到 SkyOffice 目录
cd ..

# 将 Dockerfile 和 supervisord.conf 放在 SkyOffice 目录下

# 构建镜像
docker build -t wbsu2003/skyoffice:v1 .

# 生成容器
docker run -d \
--name=skyoffice \
-p 3330:3000 \
wbsu2003/skyoffice:v1
```
