# ZINCSEARCH

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-search_engines-lightgrey)

> Anticloud-hardened packaging of the upstream project `ZINCSEARCH` in category **SEARCH ENGINES**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** SEARCH ENGINES · **Upstream:** https://github.com/zincsearch/zincsearch.git · **Upstream pin:** `374f1bcba19a1696d1926e433a9ebb77a3c7b8b0` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

[![CI](https://github.com/zincsearch/zincsearch/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/zincsearch/zincsearch/actions/workflows/ci.yml)
[![Nightly](https://github.com/zincsearch/zincsearch/actions/workflows/nightly.yml/badge.svg?branch=main)](https://github.com/zincsearch/zincsearch/actions/workflows/nightly.yml)
[![Release](https://github.com/zincsearch/zincsearch/actions/workflows/release.yml/badge.svg)](https://github.com/zincsearch/zincsearch/actions/workflows/release.yml)
[![Go Reference](https://pkg.go.dev/badge/github.com/zincsearch/zincsearch.svg)](https://pkg.go.dev/github.com/zincsearch/zincsearch)
[![Go Version](https://img.shields.io/github/go-mod/go-version/zincsearch/zincsearch)](./go.mod)
[![golangci-lint](https://img.shields.io/badge/linter-golangci--lint-blue)](https://golangci-lint.run/)
[![Release](https://img.shields.io/github/v/release/zincsearch/zincsearch)](https://github.com/zincsearch/zincsearch/releases/latest)
[![Docs](https://img.shields.io/badge/Docs-Docs-green)](https://zincsearch-docs.zinc.dev/) [![codecov](https://codecov.io/github/zincsearch/zincsearch/branch/main/graph/badge.svg)](https://codecov.io/github/zincsearch/zincsearch)

❗Note: If your use case is of log search (app and security logs) instead of app search (implement search feature in your application or website) then you should check [openobserve/openobserve](https://github.com/openobserve/openobserve) project built in rust that is specifically built for log search use case.

# ZincSearch

ZincSearch is a search engine that does full text indexing. It is a lightweight alternative to Elasticsearch and runs using a fraction of the resources. It uses [bluge](https://github.com/blugelabs/bluge) (via the [vcaesar/riot](https://github.com/vcaesar/riot) fork) as the underlying indexing library.

It is very simple and easy to operate as opposed to Elasticsearch which requires a couple dozen knobs to understand and tune. You can get ZincSearch up and running in 2 minutes.

It is a drop-in replacement for Elasticsearch if you are just ingesting data using APIs and searching using kibana (Kibana is not supported with ZincSearch. ZincSearch provides its own UI).

Check the below video for a quick demo of ZincSearch.

[![Zinc Youtube](./screenshots/zinc-youtube.jpg)](https://www.youtube.com/watch?v=aZXtuVjt1ow)

# Why ZincSearch

While Elasticsearch is a very good product, it is complex and requires lots of resources and is more than a decade old. I built ZincSearch so it becomes easier for folks to use full text search indexing without doing a lot of work.

# Features:

go + gin + react

1. Provides full text indexing capability
2. Single binary for installation and running. Binaries available under releases for multiple platforms.
3. Web UI for querying data written in React (embedded in the binary)
4. Compatibility with Elasticsearch APIs for ingestion of data (single record and bulk API)
5. Out of the box authentication
6. Schema less - No need to define schema upfront and different documents in the same index can have different fields.
7. Index storage in disk
8. aggregation support

# Documentation

Documentation is available at [https://zincsearch-docs.zinc.dev/](https://zincsearch-docs.zinc.dev/)

# Screenshots

## Search screen

![Search screen](./screenshots/search_screen.jpg)

## User management screen

![Users screen](./screenshots/users_screen.jpg)

# Getting started

## Quickstart

Check [Quickstart](https://zincsearch-docs.zinc.dev/quickstart/)

# Releases

ZincSearch has hundreds of production installations.

## Build

- CI (lint, `go test` on Linux/macOS/Windows, coverage): [`.github/workflows/ci.yml`](./.github/workflows/ci.yml) → https://github.com/zincsearch/zincsearch/actions/workflows/ci.yml
- Nightly dev image `ghcr.io/zincsearch/zincsearch-dev:nightly`: [`.github/workflows/nightly.yml`](./.github/workflows/nightly.yml) → https://github.com/zincsearch/zincsearch/actions/workflows/nightly.yml
- Release (`v*` tags, goreleaser, `ghcr.io/zincsearch/zincsearch`): [`.github/workflows/release.yml`](./.github/workflows/release.yml) → https://github.com/zincsearch/zincsearch/actions/workflows/release.yml

> **Note — Nightly / dev-image (push) fails on forks:**
>
> ```
> Error: buildx failed with: ERROR: failed to build: failed to solve: failed to push ghcr.io/zincsearch/zincsearch-dev:0.4.11-8792c59-dev: denied: permission_denied: The requested installation does not exist.
> ```
>
> The workflow logs in to GHCR with the project's `GITHUB_TOKEN`, which can only push packages under the
> owner of the project running the workflow. On a fork the token has no access to the `zincsearch` org, so
> the push is denied. Either run the workflow from `zincsearch/zincsearch`, or change `env.IMAGE` in
> `nightly.yml` to `ghcr.io/<your-owner>/zincsearch-dev` (and make sure the package is linked to the project /
> the project has `packages: write`).

# ZincSearch Vs OpenObserve

| Feature              | ZincSearch                                                       | OpenObserve                                                                              |
| -------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Ideal use case       | App search                                                       | Logs, metrics, traces (Immutable Data)                                                   |
| Storage              | Disk                                                             | Disk, Object (S3), GCS, MinIO, swift and more.                                           |
| Preferred Use case   | App search                                                       | Observability (Logs, metrics, traces)                                                    |
| Max data supported   | 100s of GBs                                                      | Petabyte scale

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Go** (manifests: go.mod, go.sum; scanned in UPSTREAM_CLONE)
- Top-level source layout: `cmd/`, `distribution/`, `docker/`, `examples/`, `frontend/`, `helm/`, `k8s/`, `pkg/`, `screenshots/`, `sh/`, `test/`
- Snapshot size: **464 files**, **152395 lines of code** (measured; see Benchmarks)
- Primary languages: `.go` (325), `.ts` (36), `.tsx` (32), `.yaml` (14), `.sh` (9), `(none)` (7)
- Upstream commit pinned for this packaging: `374f1bcba19a1696d1926e433a9ebb77a3c7b8b0`

---

## Installation

3. Web UI for querying data written in React (embedded in the binary)
4. Compatibility with Elasticsearch APIs for ingestion of data (single record and bulk API)
5. Out of the box authentication
6. Schema less - No need to define schema upfront and different documents in the same index can have different fields.
7. Index storage in disk
8. aggregation support

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

No usage section was found in the upstream readme. Entry points detected in this project directory:

```sh
go run .           # main package at the snapshot root
```

Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

[![Go Version](https://img.shields.io/github/go-mod/go-version/zincsearch/zincsearch)](./go.mod)
[![golangci-lint](https://img.shields.io/badge/linter-golangci--lint-blue)](https://golangci-lint.run/)
[![Release](https://img.shields.io/github/v/release/zincsearch/zincsearch)](https://github.com/zincsearch/zincsearch/releases/latest)
[![Docs](https://img.shields.io/badge/Docs-Docs-green)](https://zincsearch-docs.zinc.dev/) [![codecov](https://codecov.io/github/zincsearch/zincsearch/branch/main/graph/badge.svg)](https://codecov.io/github/zincsearch/zincsearch)

❗Note: If your use case is of log search (app and security logs) instead of app search (implement search feature in your application or website) then you should check [openobserve/openobserve](https://github.com/openobserve/openobserve) project built in rust that is specifically built for log search use case.

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Go |
| Manifests detected | go.mod, go.sum |
| Files in snapshot | 464 |
| Lines of code | 152395 |
| Dependency references | 148 |
| Dependencies by ecosystem | go: 124, npm: 24 |
| Upstream license | Apache-2.0 |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| go | github.com/dgraph-io/badger/v4 | v4.9.6 | go.mod |
| go | github.com/docker/go-units | v0.5.0 | go.mod |
| go | github.com/getsentry/sentry-go | v0.49.0 | go.mod |
| go | github.com/gin-contrib/cors | v1.7.8 | go.mod |
| go | github.com/gin-contrib/pprof | v1.5.5 | go.mod |
| go | github.com/gin-gonic/gin | v1.12.0 | go.mod |
| go | github.com/go-ego/gse | v1.1.0 | go.mod |
| go | github.com/goccy/go-json | v0.10.6 | go.mod |
| go | github.com/grafana/pyroscope-go | v1.4.2 | go.mod |
| go | github.com/liuzl/gocc | v0.0.0-20231231122217-0372e1059ca5 | go.mod |
| go | github.com/pelletier/go-toml/v2 | v2.4.3 | go.mod |
| go | github.com/robfig/cron/v3 | v3.0.1 | go.mod |
| go | github.com/rs/zerolog | v1.35.1 | go.mod |
| go | github.com/segmentio/analytics-go/v3 | v3.3.0 | go.mod |
| go | github.com/shirou/gopsutil/v4 | v4.26.8 | go.mod |
| ... | (133 more) | | |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

No configuration section was found in the upstream readme. Configuration-relevant files detected in this project directory:

- None detected at the snapshot root; consult the upstream documentation link in the Upstream section.

Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

*Excerpt from upstream `CONTRIBUTING.md`:*

# Contributing to ZincSearch

## Setting up development environment

### Prerequisite

ZincSearch uses Go (For server) and React / TypeScript (For Web UI)

You must have following installed:

1. Git
2. Go 1.26.7+ (We recommend go 1.27+)
3. Node.js 24 and npm

## Building from source code

### Lets source the project and get started

```shell
git source https://github.com/zincsearch/zincsearch
cd zincsearch
```

### Now let's build the UI

```shell
cd frontend
npm ci
npm run build
cd ..
```

Output will be stored in frontend/dist folder. frontend/dist will be embedded in ZincSearch binary when ZincSearch go application is built.

The `web/` directory is preserved as legacy source; active builds use `frontend/`.

It is important that you build the web app every time you make any changes to javascript code as the built code is then embedded in go application.

### Time to build the go application now

Download the dependencies

```shell
go mod tidy # this will download the go libraries used by zincsearch
```

Simple:

```shell
go build -o zincsearch cmd/zincsearch/main.go # will build the ZincSearch binary
```

Advanced

```shell
CGO_ENABLED=0 GOOS=darwin GOARCH=arm64 go build -ldflags="-s -w -X github.com/zincsearch/zincsearch/pkg/meta.Version=${VERSION} -X github.com/zincsearch/zincsearch/pkg/meta.CommitHash=${COMMIT_HASH} -X github.com/zincsearch/zincsearch/pkg/meta.BuildDate=${BUILD_DATE}" -o zincsearch cmd/zincsearch/main.go
```

Setting GOOS and GOARCH appropriately allows for cross platform compilation. Check [Official docs](https://go.dev/doc/install/source#environment) for all possible values and combinations. This [gist](https://gist.github.com/asukakenji/f15ba7e588ac42795f421b48b8aede63) is also great.

Setting CGO_ENABLED=0 allows for static linking, which results in a single binary output that has no dependencies.

setting up ldflags allows for passing values like version number to the binary at build time instead of hardcoding the value in source code. Generally the version number is set by the CI pipeline during build by using the git tag.

## Developing

Once you have the source code sourced you can start development.

There are 2 areas of development.

1. UI
1. Server

### Server

```shell
go mod tidy
ZINC_FIRST_ADMIN_USER=admin ZINC_FIRST_ADMIN_PASSWORD=Complexpass#123 go run cmd/zincsearch/main.go
```

This will start the ZincSearch API server on port 4080

environment variables ZINC_FIRST_ADMIN_USER and ZINC_FIRST_ADMIN_PASSWORD are required onl

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: Apache-2.0** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
      otherwise, or (ii) ownership of fifty percent (50%) or more of the
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original Apache-2.0 terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `Apache-2.0` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `ZINCSEARCH` (category: SEARCH ENGINES)
- **Upstream URL:** https://github.com/zincsearch/zincsearch.git
- **Pinned commit (SHA):** `374f1bcba19a1696d1926e433a9ebb77a3c7b8b0`
- **Branch:** main
- **Pin provenance:** resolved during the second documentation pass. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`de78604b411f49af09c3032a6a44913bef6e2df4a5fa11f4e3743b3ae253a0fb`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

