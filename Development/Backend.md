# Backend

## Dependencies

Backend development requires several dependencies, such as `go`, `sqlc`, `mockgen`, and `protobuf`. Below are the commands for installing these dependencies on an Ubuntu system.

```bash
wget https://downloads.sqlc.dev/sqlc_1.27.0_linux_amd64.tar.gz
tar -xzvf sqlc_1.27.0_linux_amd64.tar.gz
sudo mv sqlc /usr/local/bin/
```

```bash
wget https://go.dev/dl/go1.23.0.linux-amd64.tar.gz
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.23.0.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
go version
```

```bash
sudo apt install -y protobuf-compiler
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-openapiv2@latest
go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-grpc-gateway@latest
go install github.com/rakyll/statik@latest
export PATH="$PATH:$(go env GOPATH)/bin"
```

```bash
go install github.com/golang/mock/mockgen@latest
```

## Execution Commands

```bash
make tidy    ## Initialize
make sqlc    ## Handle SQL
make mock    ## Handle mock
make gp      ## Handle protobuf
make test    ## Run tests
make server  ## Start backend server in local mode
```
