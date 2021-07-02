<p align="center">
    <a href="https://www.ondewo.com">
      <img alt="ONDEWO Logo" src="https://raw.githubusercontent.com/ondewo/ondewo-logos/master/github/ondewo_logo_github_2.png"/>
    </a>
</p>

# ONDEWO NLU APIs

This repository contains the original interface definitions of public ONDEWO APIs that support gRPC protocols. Reading the original interface definitions can provide a better understanding of ONDEWO APIs and help you to utilize them more efficiently. You can also use these definitions with open source tools to generate client libraries, documentation, and other artifacts.

The API documentation is generated from files using [protoc-gen-doc](https://github.com/pseudomuto/protoc-gen-doc) in formats:
* [html](https://htmlpreview.github.io/?https://github.com/ondewo/ondewo-nlu-api/blob/feature/OND211-380-generate-documentation/doc/index.html)
* [markdown](doc/index.md)

The core components of all the client libraries are built directly from files in this repo using [the proto compiler](https://github.com/ondewo/ondewo-proto-compiler).

For an end-user, the APIs in this repo function mostly as documentation for the endpoints. For specific implementations, look in the following repos for working implementations:
* [Python](https://github.com/ondewo/ondewo-nlu-client-python)
* [Angular](https://github.com/ondewo/ondewo-nlu-client-angular)
* [JavaScript](https://github.com/ondewo/ondewo-nlu-client-javascript)
* [TypeScript](https://github.com/ondewo/ondewo-nlu-client-typescript)

Please note that some of these implementations are works-in-progress. The repo will make clear the status of the implementation.

## Overview

ONDEWO APIs use [Protocol Buffers](https://github.com/google/protobuf) version 3 (proto3) as their Interface Definition Language (IDL) to define the API interface and the structure of the payload messages. The same interface definition is used for gRPC versions of the API in all languages.

There are several ways of accessing APIs:

1.  Protocol Buffers over gRPC: You can access APIs published in this repository through [GRPC](https://github.com/grpc), which is a high-performance binary RPC protocol over HTTP/2. It offers many useful features, including request/response multiplex and full-duplex streaming.

2.  ONDEWO Client Libraries:
You can use these libraries to access ONDEWO Cloud APIs. They are based on gRPC for better performance and provide idiomatic client surface for better developer experience.

## Discussions

Please use the issue tracker in this repo for discussions about this API, or the issue tracker in the relevant client if it is language-specific.

## Repository Structure

```
.
├── CONTRIBUTING.md
├── doc
│   ├── index.html
│   ├── index.md
│   ├── style.css
├── googleapis
│   └── (clone of https://github.com/googleapis/googleapis.git on commit hash == 79ab27f3b70ebc221e265d2e8ab30a8cc2d21fa2)
├── LICENSE
├── ondewo
│   ├── nlu
│   │   ├── agent.proto
│   │   ├── aiservices.proto
│   │   ├── common.proto
│   │   ├── context.proto
│   │   ├── entity_type.proto
│   │   ├── intent.proto
│   │   ├── operation_metadata.proto
│   │   ├── project_role.proto
│   │   ├── project_statistics.proto
│   │   ├── server_statistics.proto
│   │   ├── session.proto
│   │   ├── user.proto
│   │   └── webhook.proto
│   └── qa
│       └── qa.proto
├── README.md
└── RELEASE.md
```

## Generate gRPC Source Code

API client libraries can be built directly from files in this repo using [the proto compiler.](https://github.com/ondewo/ondewo-proto-compiler)
