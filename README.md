# prolog

Book "Distributed Services with Go"

## Random

Commit logs are an append sequence of records ordered by time, or, a log is like a table that always orders the records by time and indexes each record by its offset and time created.

We split a log into segments, you always have one active segment that you're writing to. Once the active segment fills you can create a new one and make it the active segment.

Once you're running out of disk space (for example) you can free old segments by deleting them (which hopefully have already being processed or archived)

Commit logs are usually organized in two files:
* An index file which has the offset and position of a record, and
* The store file which has all the records.


## Running

`go run cmd/server/main.go`

## Protobuffers

* `wget https://github.com/protocolbuffers/protobuf/releases/download/v3.17.0/protoc-3.17.0-osx-x86_64.zip`
* `unzip protoc-3.17.0-osx-x86_64.zip -d /usr/local/protobuf`
* `go get google.golang.org/protobuf/cmd/protoc-gen-go`
* `go install google.golang.org/protobuf/cmd/protoc-gen-go`
* `protoc -I=. --go_out=. api/v1/log.proto`
