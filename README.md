<div align="center">
<img src="assets/basic-arithmetic-grpc-server.svg" width="400" />
<br />
<h1>Basic Arithmetic gRPC Server</h1>
<p>
Simple Basic Arithmetic gRPC Server which uses gRPC-Gateway
</p>
<a href="https://github.com/iamrajiv/basic-arithmetic-grpc-server/network/members"><img src="https://img.shields.io/github/forks/iamrajiv/basic-arithmetic-grpc-server?color=0366d6&style=for-the-badge" /></a>
<a href="https://github.com/iamrajiv/basic-arithmetic-grpc-server/stargazers"><img src="https://img.shields.io/github/stars/iamrajiv/basic-arithmetic-grpc-server?color=0366d6&style=for-the-badge" /></a>
<a href="https://github.com/iamrajiv/basic-arithmetic-grpc-server/blob/master/LICENSE"><img src="https://img.shields.io/github/license/iamrajiv/basic-arithmetic-grpc-server?color=0366d6&style=for-the-badge" /></a>
</div>

## About Project

A Basic Arithmetic gRPC server which uses gRPC-Gateway that reads protobuf service definitions and generates a reverse-proxy server. It performs four basic operation Addition, Division, Multiplication and Subtraction between two given integers.

Folder structure:

```shell
.
├── LICENSE
├── Makefile
├── README.md
├── assets
│   └── basic-arithmetic-grpc-server.svg
├── buf.gen.yaml
├── buf.yaml
├── go.mod
├── go.sum
├── main.go
└── proto
    ├── arithmetic
    │   ├── arithmetic.pb.go
    │   ├── arithmetic.pb.gw.go
    │   ├── arithmetic.proto
    │   └── arithmetic_grpc.pb.go
    └── google
        └── api
            ├── annotations.proto
            └── http.proto
```

## Usage

Before running this project install all the required Go packages by running the command `make install`. Also, you can generate the stubs using the command `make generate` and delete the stubs using the command `make clean`.

Start the server using the command:

```shell
$ go run main.go
```

Then use cURL to send HTTP requests:

```shell
$ curl -k  -X POST "http://localhost:8090/v1/arithmetic/add" -H  "accept: application/json" -H  "Content-Type: application/json" -d "{  \"a\": \"15\",  \"b\": \"17\"}"
```

```
{"result":"32"}
```

## License

[MIT](https://github.com/iamrajiv/basic-arithmetic-grpc-server/blob/master/LICENSE)
