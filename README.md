# go-project-layout 项目布局示例

## 项目结构


```bash
├── api   # api 目录, 存放 proto 文件和生成的 pb 文件
│   ├── pb
│   └── proto
├── cmd   # cmd 目录, 存放各个服务的 main.go 文件
│   ├── gateway
│   │   └── main.go
│   ├── social
│   │   └── main.go
│   ├── user
│   │   └── main.go
│   ├── video
│   │   └── main.go
│   └── video_list
│       └── main.go
├── configs  # configs 目录, 存放各个服务的配置文件
│   ├── gateway.yaml
│   ├── social.yaml
│   ├── user.yaml
│   ├── video.yaml
│   └── video_list.yaml
├── go.mod # go mod 文件
├── internal # internal 目录, 存放各个服务的内部实现
│   └── gateway # gateway 服务
│       ├── config # 配置文件解析, 对应 configs/gateway.yaml
│       ├── db     # 数据库接口抽象和实现
│       ├── handler # web handler 或者 grpc handler, 相当 SpringBoot 的 controller
│       ├── model   # dto, do, po, vo 等数据模型
│       └── service # 类似 SpringBoot 的 service, 抽象接口, 实现对其他服务的调用, 和 db 的调用, 和业务逻辑
├── pkg
│   ├── etcd # etcd 调用封装
│   ├── grpc # grpc 调用封装
│   ├── log  # 统一日志封装
│   ├── mysql # mysql 调用封装
│   ├── redis # redis 调用封装
│   └── signal # 信号处理封装, 优雅退出, 参考: 
├── test # 测试目录
└── tools # 其他工具
```

## 优雅退出参考

// https://github.com/gin-gonic/examples/blob/master/graceful-shutdown/graceful-shutdown/notify-without-context/server.go


