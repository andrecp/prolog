# prolog

Book "Distributed Services with Go"

Commit logs are an append sequence of records ordered by time.


## Running

`go run cmd/server/main.go`

## Protobuffers

* `wget https://github.com/protocolbuffers/protobuf/releases/download/v3.17.0/protoc-3.17.0-osx-x86_64.zip`
* `unzip protoc-3.17.0-osx-x86_64.zip -d /usr/local/protobuf`
* `go get google.golang.org/protobuf/cmd/protoc-gen-go`
* `go install google.golang.org/protobuf/cmd/protoc-gen-go`
* `protoc -I=. --go_out=. api/v1/log.proto`
