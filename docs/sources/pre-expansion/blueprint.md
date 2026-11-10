# Inherited model-inference blueprint

Last updated: 2026-11-10

Historical design extracted from [Lab at ba67e51](https://github.com/alvarovillalbaa/lab/blob/ba67e510bab2703b1042993744ce099490221c1f/docs/specs/steps.md). The component specification owns current scope. This text does not prove implementation, current provider facts, or executed research.

# 17. Phase 13 — serving

Serving is part of the experiment, not an afterthought.

## 17.1 Export formats

Produce:

```text
HF safetensors
vLLM-compatible checkpoint
SGLang-compatible checkpoint
GGUF quantized model
LoRA/adapters if used
```

llama.cpp is useful for local demos because it targets minimal setup across local/cloud hardware and supports many quantization levels. ([GitHub][17])

## 17.2 vLLM deployment

Deploy:

```text
base model endpoint
sft model endpoint
dpo/rl model endpoint
distilled model endpoint
quantized model endpoint
```

Measure:

| Metric                         | Required |
| ------------------------------ | -------- |
| p50/p95 time-to-first-token    | yes      |
| output tokens/sec              | yes      |
| max concurrent users           | yes      |
| GPU memory                     | yes      |
| cost per 1M input tokens       | yes      |
| cost per 1M output tokens      | yes      |
| quality loss from quantization | yes      |

vLLM is the right default because it supports high-throughput serving, OpenAI-compatible APIs, many quantization modes, parallelism, prefix caching, structured outputs, tool calling, and many Hugging Face architectures. ([vLLM][8])

## 17.3 Public demo

Create:

* simple chat UI
* `/v1/chat/completions` endpoint
* model card
* eval dashboard
* cost dashboard
* “compare base vs post-trained vs distilled” mode

This proves you can serve the model, not just train it.

---
