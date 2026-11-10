# Serving implementation blueprint

Last updated: 2026-11-10

Status: planned. The exact former mixed serving/measurement design is preserved
in [the pre-expansion snapshot](../sources/pre-expansion/blueprint.md).

## Model artifact compatibility

Accept model/config/tokenizer references and explicit format support. A model
exported by either training product is one possible input, not a prerequisite.
Adapters that need base weights must state that requirement. Validate bindings
before starting a runtime; do not imply all original export candidates work.

## One local runtime first

Implement one local runtime adapter and one documented request protocol.
Separate configuration/launch, lifecycle status, bounded request handling and
stop/teardown. Preserve model/runtime/code identity and observable request
telemetry. No public endpoint or cloud allocation is implicit.

## Consumer boundaries

A chat UI is an optional endpoint client. Inference-benchmarks can measure this
endpoint through the same public binding it uses for externally operated
endpoints. It owns workload concurrency, metric aggregation and comparisons;
serving owns request execution and emitted observations.

The original design's p50/p95 latency, token throughput, memory, cost and
quantization-comparison requirements now belong to
[inference-benchmarks](https://github.com/alvarovillalbaa/inference-benchmarks).
Quality/safety evaluation remains an external evaluation consumer.
