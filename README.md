# distributed-fileserver

基于golang实现的一种分布式云存储服务

## 关于微服务架构交互逻辑

<img src='/doc/microservice_interact_archi.png' width="800px"></img>


## 关于需要手动安装的库

如下：
```shell
go get github.com/garyburd/redigo/redis
go get github.com/go-sql-driver/mysql
#go get github.com/garyburd/redigo/redis
go get github.com/gomodule/redigo/redis
go get github.com/json-iterator/go
go get github.com/aliyun/aliyun-oss-go-sdk/oss
go get gopkg.in/amz.v1/aws
go get gopkg.in/amz.v1/s3
go get github.com/streadway/amqp
go get github.com/gin-gonic/gin
go get github.com/gin-contrib/cors
go get github.com/micro/go-micro
go get github.com/mitchellh/mapstructure
go get github.com/jteeuwen/go-bindata/...
go get github.com/moxiaomomo/go-bindata-assetfs/...
go get github.com/gin-gonic/contrib/static
go get github.com/micro/go-micro/cmd
go get github.com/micro/go-plugins/registry/kubernetes
```


## 关于应用启动


-  微服务架构下启动方式(容器化部署):
```bash
> cd $GOPATH/filestore-server
# 脚本方式启动容器
> ./deploy/start-all.sh
# 脚本方式关闭容器
> ./deploy/stop-all.sh
# docker-compose方式启动容器
> cd ./deploy/service_dc
> sudo docker-compose up -d
# k8s方式启动微服务
> cd ./deploy/service_k8s
> kubectl apply -f svc_account.yaml
> kubectl apply -f svc_apigw.yaml
> kubectl apply -f svc_dbproxy.yaml
> kubectl apply -f svc_download.yaml
> kubectl apply -f svc_transfer.yaml
> kubectl apply -f svc_upload.yaml
> cd ./deploy/traefik_k8s
> kubectl apply -f service-ingress.yaml
```

## 进度说明：
* [x] 简单的文件上传服务
* [x] mysql存储文件元数据
* [x] 账号系统, 注册/登录/查询用户或文件数据
* [x] 基于帐号的文件操作接口
* [x] 文件秒传功能
* [x] 文件分块上传/断点续传功能
* [x] 搭建及使用Ceph对象存储集群
* [x] 使用阿里云OSS对象存储服务
* [x] 使用RabbitMQ实现异步任务队列
* [x] 微服务化(API网关, 服务注册, RPC通讯)
* [ ] CI/CD(持续集成)

