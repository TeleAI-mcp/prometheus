<p align="center"><img src="https://cdn.rawgit.com/prometheus/prometheus/90d659e6/assets/prometheus_logo_orange_circle.svg" width="300"></p>

<h1 align="center">Prometheus</h1>

<p align="center">The Prometheus monitoring system and time series database.</p>

<p align="center">
  <a href="https://hub.docker.com/r/prom/prometheus/">
    <img src="https://img.shields.io/docker/pulls/prom/prometheus.svg" alt="Docker Pulls">
  </a>
  <a href="https://quay.io/repository/prometheus/prometheus">
    <img src="https://quay.io/repository/prometheus/prometheus/status" alt="Quay.io Repository">
  </a>
  <a href="https://goreportcard.com/report/github.com/prometheus/prometheus">
    <img src="https://goreportcard.com/badge/github.com/prometheus/prometheus" alt="Go Report Card">
  </a>
  <a href="https://codecov.io/gh/prometheus/prometheus">
    <img src="https://codecov.io/gh/prometheus/prometheus/branch/main/graph/badge.svg" alt="Codecov">
  </a>
  <a href="https://app.fossa.io/projects/git%2Bgithub.com%2Fprometheus%2Fprometheus?ref=badge_shield">
    <img src="https://app.fossa.io/api/projects/git%2Bgithub.com%2Fprometheus%2Fprometheus.svg?type=shield" alt="FOSSA Status">
  </a>
</p>

## Overview

Prometheus is a systems and service monitoring system. It collects metrics
from configured targets at given intervals, evaluates rule expressions,
displays the results, and can trigger alerts when specified conditions are observed.

The features that distinguish Prometheus from other metrics and monitoring systems are:

**A multi-dimensional data model (timeseries defined by metric name and set of key/value dimensions)**

- PromQL, a powerful and expressive query language to leverage this dimensionality
- No dependency on distributed storage; single server nodes are autonomous
- Timeseries collection happens via a pull model over HTTP
- Pushing timeseries is supported via an intermediary gateway
- Targets are discovered via service discovery or static configuration
- Multiple modes of graphing and dashboarding support
- Support for hierarchical and horizontal federation

**Architecture overview**

![Architecture overview](https://raw.githubusercontent.com/prometheus/prometheus/main/documentation/images/architecture.svg)

## Install

There are various ways of installing Prometheus.

### Precompiled binaries

Precompiled binaries for released versions are available in the
[*download* section](https://prometheus.io/download/)
on [prometheus.io](https://prometheus.io). Using the latest production release binary
is the recommended way of installing Prometheus.
See the [Installing](https://prometheus.io/docs/introduction/install/)
chapter in the documentation for all the details.

### Docker images

Docker images are available on [Quay.io](https://quay.io/repository/prometheus/prometheus)
or [Docker Hub](https://hub.docker.com/r/prom/prometheus/).

On macOS:

```bash
brew install prometheus
```

On Linux:

```bash
sudo apt-get install prometheus
```

### Building from source

To build Prometheus from source code, You need:

- Go [version 1.22 or above](https://golang.org/doc/install).
- A C compiler (for building some Go packages, like `github.com/prometheus/common/expfmt`).

```bash
git clone https://github.com/prometheus/prometheus.git
cd prometheus
make build
./prometheus --config.file=your_config.yml
```

You can also build just one of the binaries, like `promtool`, by running:

```bash
make promtool
```

The Makefile provides several targets:

- *build*: build the `prometheus` and `promtool` binaries
- *test*: run the tests
- *test-race*: run the tests with race detection
- *format*: format the source files
- *vet*: run `go vet` on the source files
- *docker*: build a Docker container for the current `HEAD` commit. You need a working Docker.

## Usage

Documentation is on [prometheus.io](https://prometheus.io/docs/):

- [Introduction](https://prometheus.io/docs/introduction/overview/)
- [Installation](https://prometheus.io/docs/introduction/install/)
- [First steps](https://prometheus.io/docs/introduction/first_steps/)
- [Concepts](https://prometheus.io/docs/concepts/data_model/)
- [Configuration](https://prometheus.io/docs/configuration/configuration/)
- [Querying](https://prometheus.io/docs/querying/basics/)
- [Alerting](https://prometheus.io/docs/alerting/latest/configuration/)
- [Visualization](https://prometheus.io/docs/visualization/grafana/)
- [Storage](https://prometheus.io/docs/storage/)
- [Security model](https://prometheus.io/docs/operating/security/)

## Contributing

Refer to [CONTRIBUTING.md](CONTRIBUTING.md).

## License

Apache License 2.0, see [LICENSE](LICENSE).

---

## Related Projects

1. related project [grafana](https://github.com/grafana/grafana)
2. related project [opentelemetry-collector](https://github.com/open-telemetry/opentelemetry-collector)