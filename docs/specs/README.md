# Model serving specification

Last updated: 2026-11-10

Status: planned. These target operations are not implemented commands or APIs.

## Consumer and target interface

A user supplies a permitted model artifact from any compatible producer.
Neither model-pretraining, model-posttraining, Lab, nor a benchmark package is a
required consumer dependency.

- A launch request identifies weights/config/tokenizer and optional adapter
  artifacts with formats/hashes; selects one runtime adapter; supplies resource
  and request limits; and references credentials through external configuration.
- Launch returns a server identity and endpoint binding: protocol, address,
  declared model/runtime identity, supported request capabilities and lifecycle
  status. Declared remote identity is not immutable-deployment proof.
- Status and stop operate on that explicit server identity. Requests return
  actual outputs/errors and observable timing/token/usage information when
  available. Unknown measurements remain absent or explicitly unknown.
- The first implemented protocol should support a documented local
  OpenAI-compatible chat request/response path. Additional runtimes are optional
  declared adapters, not hidden setup side effects.

## Prerequisites and scope

First select one compatible model format and local runtime, provide its model
artifact and an explicit resource cap, and document installation independently.
The original export candidates include safetensors, compatible checkpoint
layouts, GGUF and adapter formats; no adapter claims support before tested.

Public endpoints need the owner's deployment, access, safety and budget gates.
Local serving does not authorize public exposure. No provider is contacted by
this planned repository.

## Acceptance

A first implementation must load an external compatible model, launch/status/
stop its local endpoint, preserve artifact/runtime identities, handle request
errors and resource bounds, and return a useful actual response without a
benchmark harness. Test reload and cancellation/teardown with recorded evidence.

This owner emits raw telemetry. Inference-benchmarks owns measurement protocols,
load generation, percentiles, throughput/cost aggregation and comparisons.
Evaluation quality/safety scoring belongs to Open Evals or another explicit
consumer, not a second serving-owned evaluation engine.

[Blueprint](blueprint.md) · [Backlog](backlog.md) ·
[Source history](../sources/README.md)
