# model-inference

Last updated: 2026-11-10

Serve explicit model artifacts and measure inference behavior through documented workloads.

**Status: planned.** This repository currently contains specifications and an implementation backlog. It has no executable engine or installable package.

## Independent use

Read [the component specification](docs/specs/README.md) and choose its first bounded implementation task. No runtime dependency or installation is required to use the specification.

## Ownership

Inference adapters, model endpoint bindings, request workloads, latency/throughput measurements, and export compatibility.

Outside this component: Training, generic GPU scheduling, a custom evaluation engine, or production deployment authorization.

## Compose

Use independently, or register a pinned version in [Lab](https://github.com/alvarovillalbaa/lab). A dependency on Lab is never required. Libraries connect through declared dependencies or explicit artifact/job interfaces.

[Specification and next work](docs/specs/README.md) · [Extraction provenance](docs/sources/lab-provenance.json)

MIT applies to the code and authored documentation in this repository. External datasets, model weights, provider services, and third-party projects retain their own terms.
