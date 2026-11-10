# model-serving

Last updated: 2026-11-10

Run explicit model artifacts behind a versioned local or hosted inference endpoint.

**Status: planned.** This repository contains the product boundary, target
interfaces, inherited requirements, and a scoped implementation backlog. It has
no executable engine or installable package.

## Independent consumer

A user can load and serve a compatible model or adapter from an external source without installing a training tool or benchmark harness. Clients receive an explicit endpoint/protocol binding.

## Start here

Read [the specification](docs/specs/README.md),
[implementation blueprint](docs/specs/blueprint.md), and
[scoped backlog](docs/specs/backlog.md). The specification is usable without a
runtime installation; implementation acceptance is still future work.

## Ownership

This component owns model loading/format compatibility, runtime adapters,
endpoint launch/status/stop, request handling, serving resource limits and
observable per-request telemetry.

[inference-benchmarks](https://github.com/alvarovillalbaa/inference-benchmarks)
owns workload design, load generation, latency/throughput/memory/cost
measurement methodology and comparative reports. Training/export producers
supply model artifacts; generic evaluation and promotion remain external.

The repository continues the history originally named model-inference; its
canonical name is model-serving.

## Composition and terms

Lab may assemble pinned releases of this component; this component never
requires Lab or a sibling checkout. Exchanges use explicit versioned artifact
or endpoint references. Optional adapters must declare their own dependencies.

[Source history and relocation map](docs/sources/README.md) explains the split.
MIT covers authored code and documentation. Third-party models, data, tools,
and services retain their own terms. No source recovery, paid job, provider
acceptance, or scientific result is established by these specifications.
