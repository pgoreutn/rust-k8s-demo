# rust-k8s-demo

[![Build Status][actions-badge]][actions-url]

![architecture][architecture]

This project is an experiment with how modern web applications would look like
when using **Rust** and **Kubernetes**. It is inspired by [microservices-demo][demo].

It is a simple web application that returns a new quotation for each request.

There are two isolated microservices. The frontendservice provides one endpoint
that clients (browsers) can connect to. The quotationservice is a [grpc](https://grpc.io/) server,
that answers with a quotation for each request. Both the microservices
use fully asynchronous Rust libraries and are based on [tokio](https://tokio.rs/).


## Features

- [x] Microservices talking to each other using grpc
- [x] Local dev setup using skaffold
- [x] CI
- [ ] CD
- [x] Service mesh
- [ ] Distributed (open) tracing

## Getting started

* Setup a local kubernetes cluster, using Kubernetes for docker-for-mac
(for Linux or other options in getting started, see [setup](./docs/setup.md)).

* Install [skaffold](https://skaffold.dev/) and run the application

    ```shell
    $ make bootstrap
    $ skaffold run --tail
    ```

* **QED** - Go to [http://localhost](http://localhost)

## LICENSE

This project is licensed under [MIT](LICENSE).


[demo]: https://github.com/GoogleCloudPlatform/microservices-demo
[actions-badge]: https://img.shields.io/endpoint.svg?url=https%3A%2F%2Factions-badge.atrox.dev%2Fcaulagi%2Frust-k8s-demo%2Fbadge&style=flat&label=Build%20status
[actions-url]: https://actions-badge.atrox.dev/caulagi/rust-k8s-demo/goto
[architecture]: https://user-images.githubusercontent.com/222507/72002857-89411780-3248-11ea-9e16-9e6912f2a75b.png
