# Goa sandbox

## See
- https://goa.design/
- https://goa.design/ja/learn/getting-started/

## Setup

### ENV
- ```
  export GO111MODULE=on
  ```

### Install `protoc`
- macOS (with HomeBrew)
  ```
  brew install protobuf
  ```

### Install `protoc-gen-go`
- ```
  go get google.golang.org/protobuf/cmd/protoc-gen-go
  go get google.golang.org/grpc/cmd/protoc-gen-go-grpc
  ```

### Install `goa`
- ```
  go get -u goa.design/goa/v3
  go get -u goa.design/goa/v3/...
  ```

## Define
- Edit [design/design.go](./design/design.go)

## Generate

- `gen` dir
  ```
  goa gen calc/design
  ```

- Example server and client code
  ```
  goa example calc/design
  ```

## Build
- ```
  go build -o ./build/calc ./cmd/calc \
  && go build -o ./build/calc-cli ./cmd/calc-cli
  ```

## Run
- Server
  ```
  ./build/calc
  ```
- CLI
  ```
  ./build/calc-cli --url="http://localhost:8000" calc add --a 1 --b 2
  ```
