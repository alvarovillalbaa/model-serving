# model-inference specification

Last updated: 2026-11-10

Status: planned. All runtime capabilities below remain planned.

## Responsibility

Inference adapters, model endpoint bindings, request workloads, latency/throughput measurements, and export compatibility.

## First next work

- [ ] Add one local inference adapter with a documented model input and output interface.
- [ ] Record model revision, workload, hardware, timing, memory, and cost coverage.
- [ ] Connect measurements to Open Evals without duplicating its evaluator engine.

## Interfaces and composition

Specify the smallest public API against the first real consumer before implementing it. Use explicit inputs, artifacts, versions, and dependency declarations. A planned interface is not an implementation.

[Inherited blueprint](blueprint.md) preserves the relevant original design sections. Provider claims, dates, estimates, and unimplemented features there are historical requirements, not new measurements.

[Inherited backlog](backlog.md) records the original planning status; use the implementation status above for the current boundary.

## Acceptance

The first implementation must install/run independently, declare dependencies, include a useful example and focused behavior checks, and record remaining limitations. Do not mark this project implemented solely because the documentation exists.
