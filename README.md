# go-doudou User API Example

[简体中文](README.zh-CN.md)

A go-doudou v2.1.5 scaffold example that connects a Go user-service interface to generated HTTP routes, a typed client and an OpenAPI 3 contract. Reads return generated fixtures, and writes are acknowledged without persistence.

## Read the code

| File | What it shows |
| --- | --- |
| [svc.go](svc.go) | The service interface for creating, fetching, updating, deleting and listing users. |
| [svcimpl.go](svcimpl.go) | Mock responses generated with gofakeit. |
| [transport/httpsrv](transport/httpsrv) | Generated routes and HTTP handlers. |
| [client](client) | Generated HTTP client and request types. |
| [doudoutest_openapi3.json](doudoutest_openapi3.json) | OpenAPI 3 paths and schemas. |

## Run locally

The [Go module](go.mod) declares Go 1.19. Run the REST entry point from the repository root.

```sh
GDD_HOST=127.0.0.1 go run ./cmd
```

In a second terminal, fetch a sample user on the default port.

```sh
curl -fsS http://127.0.0.1:6060/user/1
```

See the [OpenAPI contract](doudoutest_openapi3.json) for request bodies and parameters.
