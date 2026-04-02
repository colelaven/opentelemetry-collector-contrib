// Copyright The OpenTelemetry Authors
// SPDX-License-Identifier: Apache-2.0

## How to Generate Protos

download and install protoc:
https://google.github.io/proto-lens/installing-protoc.html

Use this command where protobuf `../googleapis` is a path to [this repo]("https://github.com/googleapis/googleapis") on your local system:
```
protoc --proto_path=./exporter/googlesecopsexporter/internal/proto \
       --go-grpc_opt=paths=source_relative \
       --go-grpc_out=./exporter/googlesecopsexporter/internal/proto/api \
       --go_out=./exporter/googlesecopsexporter/internal/proto/api \
       --go_opt=paths=source_relative \
       --proto_path=../googleapis \
       ./exporter/googlesecopsexporter/internal/proto/*.proto
```