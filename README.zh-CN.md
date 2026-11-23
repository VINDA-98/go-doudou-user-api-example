# go-doudou 用户 API 示例

[English](README.md)

这是一个基于 go-doudou v2.1.5 脚手架的 Go 示例。它串起了用户服务接口、生成的 HTTP 路由、类型化客户端和 OpenAPI 3 接口定义。服务实现返回模拟数据，写操作只返回结果，不保存数据。

## 阅读代码

| 文件 | 内容 |
| --- | --- |
| [svc.go](svc.go) | 定义新建、查询、更新、删除用户和列出用户的服务接口。 |
| [svcimpl.go](svcimpl.go) | 使用 gofakeit 生成模拟响应。 |
| [transport/httpsrv](transport/httpsrv) | 生成的路由和 HTTP 处理器。 |
| [client](client) | 生成的 HTTP 客户端和请求类型。 |
| [doudoutest_openapi3.json](doudoutest_openapi3.json) | OpenAPI 3 路径及数据结构定义。 |

## 本地运行

[Go 模块](go.mod)声明 Go 1.19。在仓库根目录启动 REST 服务。

```sh
GDD_HOST=127.0.0.1 go run ./cmd
```

在另一个终端中，用默认端口读取一个用户样例。

```sh
curl -fsS http://127.0.0.1:6060/user/1
```

请求体和参数见 [OpenAPI 定义](doudoutest_openapi3.json)。
