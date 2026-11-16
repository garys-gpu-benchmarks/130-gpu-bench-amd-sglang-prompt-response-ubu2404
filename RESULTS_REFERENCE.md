# Results: 130 SGLang Prompt-Response Benchmark

**Main goal:** Measure sequential SGLang prompt-response latency  
**Tools:** Every profile starts sglang.launch_server with Mistral-7B-v0.3, then prompt_response_client.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_142 · recorded 2026-11-16). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 24.04.5 LTS · kernel 6.8.0-147-generic · driver 7.1.9.31600000
- **Run:** 2026-11-16T12:09:15Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 07:45 · benchmark 00:05 · whole run 09:17
- **Source:** run 130_20261116_120915
- **Command:** `bash run_benchmark.sh --smoke --dtype bfloat16 --input-len 64 --output-len 16 --model-name mistralai/Mistral-7B-v0.3 --num-prompts 2 --max-running-requests 1 --max-total-tokens 1024 --seed 42`

| # | Metric | Result |
|---|---|---|
| 1 | E2E latency p50, ms (end_to_end_latency_ms) | 325.87720950050425 |
| 2 | Time To First Token p50, ms (ttft_ms) | 42.511163499511895 |
| 3 | Output token generation rate (decode) p50, tokens/s (output_tokens_per_s) | 52.939517786048626 |
| 4 | RadixAttn hit rate, pct (radixattention_cache_hit_rate_pct) | 26.865671641791046 |
| 5 | Completed request rate, pct (completed_request_rate_pct) | 100.0 |
<!-- /profile:smoke -->
