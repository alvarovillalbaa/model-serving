# Serving backlog

Last updated: 2026-11-10

All runtime capabilities remain planned. The
[original mixed backlog](../sources/pre-expansion/backlog.md) is historical.

- [ ] Choose one model format, local runtime and documented request protocol.
- [ ] Validate weights/config/tokenizer/adapter bindings with content identities.
- [ ] Implement launch, status, stop and resource-bounded request handling.
- [ ] Return useful actual model output and explicit execution failures.
- [ ] Emit raw timing/token/usage observations with unknown fields preserved.
- [ ] Prove independent loading, local endpoint use, reload and teardown.
- [ ] Add optional cloud/public adapters only after access, safety and budget gates.

Workload generation, concurrency sweeps, performance statistics and comparative
reports are maintained in
[inference-benchmarks](https://github.com/alvarovillalbaa/inference-benchmarks).
