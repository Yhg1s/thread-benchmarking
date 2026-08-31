# Results vs. base

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.013x slower
- HPT reliability: 99.38%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                                                                    | 10.7 ms: 1.04x slower                                                                                          |
| docutils       | 1.98 sec                                                                                                   | 2.06 sec: 1.04x slower                                                                                         |
| html5lib       | 45.3 ms                                                                                                    | 49.7 ms: 1.10x slower                                                                                          |
| tornado_http   | 101 ms                                                                                                     | 103 ms: 1.02x slower                                                                                           |
| Geometric mean | (ref)                                                                                                      | 1.04x slower                                                                                                   |

Benchmark hidden because not significant (1): fastapi_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| asyncio_tcp                      | 324 ms                                                                                                     | 302 ms: 1.07x faster                                                                                           |
| asyncio_websockets               | 305 ms                                                                                                     | 294 ms: 1.04x faster                                                                                           |
| async_tree_eager_io              | 568 ms                                                                                                     | 556 ms: 1.02x faster                                                                                           |
| async_tree_eager_io_tg           | 565 ms                                                                                                     | 553 ms: 1.02x faster                                                                                           |
| async_tree_eager_tg              | 182 ms                                                                                                     | 181 ms: 1.01x faster                                                                                           |
| async_tree_cpu_io_mixed          | 429 ms                                                                                                     | 436 ms: 1.02x slower                                                                                           |
| async_tree_memoization_tg        | 279 ms                                                                                                     | 284 ms: 1.02x slower                                                                                           |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                                                                     | 382 ms: 1.02x slower                                                                                           |
| async_tree_none                  | 233 ms                                                                                                     | 238 ms: 1.02x slower                                                                                           |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                                                                     | 335 ms: 1.02x slower                                                                                           |
| async_tree_memoization           | 285 ms                                                                                                     | 294 ms: 1.03x slower                                                                                           |
| async_tree_none_tg               | 224 ms                                                                                                     | 232 ms: 1.03x slower                                                                                           |
| async_tree_eager_memoization_tg  | 236 ms                                                                                                     | 247 ms: 1.05x slower                                                                                           |
| async_tree_eager_memoization     | 183 ms                                                                                                     | 192 ms: 1.05x slower                                                                                           |
| async_generators                 | 231 ms                                                                                                     | 249 ms: 1.08x slower                                                                                           |
| coroutines                       | 15.1 ms                                                                                                    | 16.4 ms: 1.08x slower                                                                                          |
| async_tree_eager                 | 83.0 ms                                                                                                    | 90.4 ms: 1.09x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                      | 1.02x slower                                                                                                   |

Benchmark hidden because not significant (4): asyncio_tcp_ssl, async_tree_cpu_io_mixed_tg, async_tree_io_tg, async_tree_io

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| noop      | 19.2 ns                                                                                                    | 17.0 ns: 1.13x faster                                                                                          |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| decimal_pi        | 209 ms                                                                                                     | 205 ms: 1.02x faster                                                                                           |
| decimal_factorial | 174 ms                                                                                                     | 178 ms: 1.02x slower                                                                                           |
| Geometric mean    | (ref)                                                                                                      | 1.00x slower                                                                                                   |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| float          | 51.2 ms                                                                                                    | 41.4 ms: 1.24x faster                                                                                          |
| quadtree_nbody | 654 ms                                                                                                     | 596 ms: 1.10x faster                                                                                           |
| pidigits       | 216 ms                                                                                                     | 216 ms: 1.00x faster                                                                                           |
| nbody          | 74.2 ms                                                                                                    | 83.5 ms: 1.13x slower                                                                                          |
| Geometric mean | (ref)                                                                                                      | 1.05x faster                                                                                                   |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                                                                    | 14.3 ms: 1.05x faster                                                                                          |
| regex_effbot   | 1.98 ms                                                                                                    | 1.92 ms: 1.03x faster                                                                                          |
| regex_compile  | 97.0 ms                                                                                                    | 102 ms: 1.05x slower                                                                                           |
| Geometric mean | (ref)                                                                                                      | 1.01x faster                                                                                                   |

Benchmark hidden because not significant (1): regex_dna

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| unpickle_pure_python | 163 us                                                                                                     | 137 us: 1.19x faster                                                                                           |
| xml_etree_process    | 50.0 ms                                                                                                    | 45.1 ms: 1.11x faster                                                                                          |
| xml_etree_generate   | 68.1 ms                                                                                                    | 61.8 ms: 1.10x faster                                                                                          |
| ascii85_large        | 681 ms                                                                                                     | 617 ms: 1.10x faster                                                                                           |
| ascii85_small        | 13.0 ms                                                                                                    | 12.3 ms: 1.06x faster                                                                                          |
| base85_small         | 4.66 ms                                                                                                    | 4.47 ms: 1.04x faster                                                                                          |
| unpickle_list        | 3.03 us                                                                                                    | 2.94 us: 1.03x faster                                                                                          |
| base85_large         | 249 ms                                                                                                     | 243 ms: 1.03x faster                                                                                           |
| tomli_loads          | 1.49 sec                                                                                                   | 1.46 sec: 1.02x faster                                                                                         |
| base16_large         | 6.35 ms                                                                                                    | 6.29 ms: 1.01x faster                                                                                          |
| json_loads           | 18.6 us                                                                                                    | 18.6 us: 1.00x faster                                                                                          |
| pickle_dict          | 20.0 us                                                                                                    | 20.0 us: 1.00x faster                                                                                          |
| pickle               | 8.04 us                                                                                                    | 8.11 us: 1.01x slower                                                                                          |
| pickle_list          | 3.03 us                                                                                                    | 3.06 us: 1.01x slower                                                                                          |
| base32_large         | 289 ms                                                                                                     | 293 ms: 1.01x slower                                                                                           |
| xml_etree_iterparse  | 85.5 ms                                                                                                    | 86.7 ms: 1.01x slower                                                                                          |
| json_dumps           | 7.52 ms                                                                                                    | 7.65 ms: 1.02x slower                                                                                          |
| base16_small         | 265 us                                                                                                     | 271 us: 1.02x slower                                                                                           |
| base32_small         | 5.71 ms                                                                                                    | 5.96 ms: 1.04x slower                                                                                          |
| pickle_pure_python   | 251 us                                                                                                     | 265 us: 1.05x slower                                                                                           |
| Geometric mean       | (ref)                                                                                                      | 1.02x faster                                                                                                   |

Benchmark hidden because not significant (5): urlsafe_base64_small, xml_etree_parse, unpickle, base64_large, base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                                                                    | 9.91 ms: 1.00x faster                                                                                          |
| python_startup_no_site | 6.52 ms                                                                                                    | 6.53 ms: 1.00x slower                                                                                          |
| Geometric mean         | (ref)                                                                                                      | 1.00x slower                                                                                                   |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| mako            | 8.69 ms                                                                                                    | 7.35 ms: 1.18x faster                                                                                          |
| django_template | 30.5 ms                                                                                                    | 31.1 ms: 1.02x slower                                                                                          |
| genshi_text     | 18.0 ms                                                                                                    | 18.6 ms: 1.03x slower                                                                                          |
| genshi_xml      | 43.2 ms                                                                                                    | 45.7 ms: 1.06x slower                                                                                          |
| Geometric mean  | (ref)                                                                                                      | 1.01x faster                                                                                                   |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_pipeline_optimized   | 25.8 ms                                                                                                    | 22.8 ms: 1.13x faster                                                                                          |
| thread_memo_naive           | 12.4 ms                                                                                                    | 11.0 ms: 1.13x faster                                                                                          |
| thread_accumulate_optimized | 39.5 ms                                                                                                    | 35.6 ms: 1.11x faster                                                                                          |
| thread_accumulate_naive     | 40.4 ms                                                                                                    | 36.4 ms: 1.11x faster                                                                                          |
| thread_memo_optimized       | 17.5 ms                                                                                                    | 16.0 ms: 1.10x faster                                                                                          |
| thread_counter_optimized    | 18.3 ms                                                                                                    | 17.5 ms: 1.05x faster                                                                                          |
| thread_mandelbrot_naive     | 207 ms                                                                                                     | 198 ms: 1.04x faster                                                                                           |
| thread_counter_naive        | 21.2 ms                                                                                                    | 20.4 ms: 1.04x faster                                                                                          |
| thread_pipeline_naive       | 34.9 ms                                                                                                    | 33.7 ms: 1.04x faster                                                                                          |
| thread_mandelbrot_optimized | 205 ms                                                                                                     | 200 ms: 1.03x faster                                                                                           |
| thread_montecarlo_optimized | 12.9 ms                                                                                                    | 14.4 ms: 1.11x slower                                                                                          |
| thread_montecarlo_naive     | 14.3 ms                                                                                                    | 18.6 ms: 1.31x slower                                                                                          |
| Geometric mean              | (ref)                                                                                                      | 1.03x faster                                                                                                   |

All benchmarks:
===============

| Benchmark                        | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| float                            | 51.2 ms                                                                                                    | 41.4 ms: 1.24x faster                                                                                          |
| deltablue                        | 2.76 ms                                                                                                    | 2.24 ms: 1.23x faster                                                                                          |
| unpickle_pure_python             | 163 us                                                                                                     | 137 us: 1.19x faster                                                                                           |
| scimark_fft                      | 211 ms                                                                                                     | 177 ms: 1.19x faster                                                                                           |
| mako                             | 8.69 ms                                                                                                    | 7.35 ms: 1.18x faster                                                                                          |
| richards                         | 34.7 ms                                                                                                    | 30.3 ms: 1.15x faster                                                                                          |
| richards_super                   | 40.3 ms                                                                                                    | 35.4 ms: 1.14x faster                                                                                          |
| thread_pipeline_optimized        | 25.8 ms                                                                                                    | 22.8 ms: 1.13x faster                                                                                          |
| thread_memo_naive                | 12.4 ms                                                                                                    | 11.0 ms: 1.13x faster                                                                                          |
| noop                             | 19.2 ns                                                                                                    | 17.0 ns: 1.13x faster                                                                                          |
| spectral_norm                    | 64.1 ms                                                                                                    | 57.3 ms: 1.12x faster                                                                                          |
| thread_accumulate_optimized      | 39.5 ms                                                                                                    | 35.6 ms: 1.11x faster                                                                                          |
| xml_etree_process                | 50.0 ms                                                                                                    | 45.1 ms: 1.11x faster                                                                                          |
| thread_accumulate_naive          | 40.4 ms                                                                                                    | 36.4 ms: 1.11x faster                                                                                          |
| xml_etree_generate               | 68.1 ms                                                                                                    | 61.8 ms: 1.10x faster                                                                                          |
| ascii85_large                    | 681 ms                                                                                                     | 617 ms: 1.10x faster                                                                                           |
| quadtree_nbody                   | 654 ms                                                                                                     | 596 ms: 1.10x faster                                                                                           |
| thread_memo_optimized            | 17.5 ms                                                                                                    | 16.0 ms: 1.10x faster                                                                                          |
| asyncio_tcp                      | 324 ms                                                                                                     | 302 ms: 1.07x faster                                                                                           |
| bpe_tokeniser                    | 3.11 sec                                                                                                   | 2.90 sec: 1.07x faster                                                                                         |
| ascii85_small                    | 13.0 ms                                                                                                    | 12.3 ms: 1.06x faster                                                                                          |
| fannkuch                         | 246 ms                                                                                                     | 234 ms: 1.05x faster                                                                                           |
| thread_counter_optimized         | 18.3 ms                                                                                                    | 17.5 ms: 1.05x faster                                                                                          |
| regex_v8                         | 15.0 ms                                                                                                    | 14.3 ms: 1.05x faster                                                                                          |
| base85_small                     | 4.66 ms                                                                                                    | 4.47 ms: 1.04x faster                                                                                          |
| thread_mandelbrot_naive          | 207 ms                                                                                                     | 198 ms: 1.04x faster                                                                                           |
| thread_counter_naive             | 21.2 ms                                                                                                    | 20.4 ms: 1.04x faster                                                                                          |
| scimark_sparse_mat_mult          | 2.89 ms                                                                                                    | 2.78 ms: 1.04x faster                                                                                          |
| asyncio_websockets               | 305 ms                                                                                                     | 294 ms: 1.04x faster                                                                                           |
| thread_pipeline_naive            | 34.9 ms                                                                                                    | 33.7 ms: 1.04x faster                                                                                          |
| unpickle_list                    | 3.03 us                                                                                                    | 2.94 us: 1.03x faster                                                                                          |
| thread_mandelbrot_optimized      | 205 ms                                                                                                     | 200 ms: 1.03x faster                                                                                           |
| regex_effbot                     | 1.98 ms                                                                                                    | 1.92 ms: 1.03x faster                                                                                          |
| base85_large                     | 249 ms                                                                                                     | 243 ms: 1.03x faster                                                                                           |
| tomli_loads                      | 1.49 sec                                                                                                   | 1.46 sec: 1.02x faster                                                                                         |
| async_tree_eager_io              | 568 ms                                                                                                     | 556 ms: 1.02x faster                                                                                           |
| async_tree_eager_io_tg           | 565 ms                                                                                                     | 553 ms: 1.02x faster                                                                                           |
| decimal_pi                       | 209 ms                                                                                                     | 205 ms: 1.02x faster                                                                                           |
| meteor_contest                   | 85.4 ms                                                                                                    | 84.2 ms: 1.01x faster                                                                                          |
| base16_large                     | 6.35 ms                                                                                                    | 6.29 ms: 1.01x faster                                                                                          |
| async_tree_eager_tg              | 182 ms                                                                                                     | 181 ms: 1.01x faster                                                                                           |
| create_gc_cycles                 | 2.02 ms                                                                                                    | 2.01 ms: 1.00x faster                                                                                          |
| pidigits                         | 216 ms                                                                                                     | 216 ms: 1.00x faster                                                                                           |
| json_loads                       | 18.6 us                                                                                                    | 18.6 us: 1.00x faster                                                                                          |
| python_startup                   | 9.93 ms                                                                                                    | 9.91 ms: 1.00x faster                                                                                          |
| pickle_dict                      | 20.0 us                                                                                                    | 20.0 us: 1.00x faster                                                                                          |
| python_startup_no_site           | 6.52 ms                                                                                                    | 6.53 ms: 1.00x slower                                                                                          |
| pathlib                          | 12.7 ms                                                                                                    | 12.7 ms: 1.00x slower                                                                                          |
| pyflate                          | 309 ms                                                                                                     | 311 ms: 1.01x slower                                                                                           |
| crypto_pyaes                     | 56.7 ms                                                                                                    | 57.1 ms: 1.01x slower                                                                                          |
| pickle                           | 8.04 us                                                                                                    | 8.11 us: 1.01x slower                                                                                          |
| coverage                         | 54.5 ms                                                                                                    | 55.0 ms: 1.01x slower                                                                                          |
| pickle_list                      | 3.03 us                                                                                                    | 3.06 us: 1.01x slower                                                                                          |
| base32_large                     | 289 ms                                                                                                     | 293 ms: 1.01x slower                                                                                           |
| mdp                              | 971 ms                                                                                                     | 983 ms: 1.01x slower                                                                                           |
| xml_etree_iterparse              | 85.5 ms                                                                                                    | 86.7 ms: 1.01x slower                                                                                          |
| deepcopy_memo                    | 19.1 us                                                                                                    | 19.5 us: 1.02x slower                                                                                          |
| async_tree_cpu_io_mixed          | 429 ms                                                                                                     | 436 ms: 1.02x slower                                                                                           |
| json_dumps                       | 7.52 ms                                                                                                    | 7.65 ms: 1.02x slower                                                                                          |
| async_tree_memoization_tg        | 279 ms                                                                                                     | 284 ms: 1.02x slower                                                                                           |
| networkx_k_core                  | 2.05 sec                                                                                                   | 2.09 sec: 1.02x slower                                                                                         |
| decimal_factorial                | 174 ms                                                                                                     | 178 ms: 1.02x slower                                                                                           |
| scimark_monte_carlo              | 42.3 ms                                                                                                    | 43.2 ms: 1.02x slower                                                                                          |
| django_template                  | 30.5 ms                                                                                                    | 31.1 ms: 1.02x slower                                                                                          |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                                                                     | 382 ms: 1.02x slower                                                                                           |
| async_tree_none                  | 233 ms                                                                                                     | 238 ms: 1.02x slower                                                                                           |
| networkx_shortest_path           | 447 ms                                                                                                     | 456 ms: 1.02x slower                                                                                           |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                                                                     | 335 ms: 1.02x slower                                                                                           |
| tornado_http                     | 101 ms                                                                                                     | 103 ms: 1.02x slower                                                                                           |
| base16_small                     | 265 us                                                                                                     | 271 us: 1.02x slower                                                                                           |
| sympy_sum                        | 109 ms                                                                                                     | 112 ms: 1.03x slower                                                                                           |
| async_tree_memoization           | 285 ms                                                                                                     | 294 ms: 1.03x slower                                                                                           |
| genshi_text                      | 18.0 ms                                                                                                    | 18.6 ms: 1.03x slower                                                                                          |
| async_tree_none_tg               | 224 ms                                                                                                     | 232 ms: 1.03x slower                                                                                           |
| deepcopy_reduce                  | 2.02 us                                                                                                    | 2.09 us: 1.04x slower                                                                                          |
| sqlalchemy_imperative            | 14.8 ms                                                                                                    | 15.3 ms: 1.04x slower                                                                                          |
| networkx_connected_components    | 425 ms                                                                                                     | 441 ms: 1.04x slower                                                                                           |
| sqlglot_v2_optimize              | 41.8 ms                                                                                                    | 43.5 ms: 1.04x slower                                                                                          |
| telco                            | 5.39 ms                                                                                                    | 5.61 ms: 1.04x slower                                                                                          |
| docutils                         | 1.98 sec                                                                                                   | 2.06 sec: 1.04x slower                                                                                         |
| sympy_str                        | 200 ms                                                                                                     | 208 ms: 1.04x slower                                                                                           |
| chameleon                        | 10.3 ms                                                                                                    | 10.7 ms: 1.04x slower                                                                                          |
| base32_small                     | 5.71 ms                                                                                                    | 5.96 ms: 1.04x slower                                                                                          |
| sympy_integrate                  | 15.1 ms                                                                                                    | 15.8 ms: 1.04x slower                                                                                          |
| typing_runtime_protocols         | 115 us                                                                                                     | 120 us: 1.05x slower                                                                                           |
| async_tree_eager_memoization_tg  | 236 ms                                                                                                     | 247 ms: 1.05x slower                                                                                           |
| argparse_many_optionals          | 34.5 ms                                                                                                    | 36.1 ms: 1.05x slower                                                                                          |
| deepcopy                         | 198 us                                                                                                     | 207 us: 1.05x slower                                                                                           |
| nqueens                          | 59.8 ms                                                                                                    | 62.7 ms: 1.05x slower                                                                                          |
| sympy_expand                     | 344 ms                                                                                                     | 361 ms: 1.05x slower                                                                                           |
| async_tree_eager_memoization     | 183 ms                                                                                                     | 192 ms: 1.05x slower                                                                                           |
| sqlglot_v2_normalize             | 84.9 ms                                                                                                    | 89.2 ms: 1.05x slower                                                                                          |
| pylint                           | 222 ms                                                                                                     | 233 ms: 1.05x slower                                                                                           |
| regex_compile                    | 97.0 ms                                                                                                    | 102 ms: 1.05x slower                                                                                           |
| pickle_pure_python               | 251 us                                                                                                     | 265 us: 1.05x slower                                                                                           |
| sqlglot_v2_transpile             | 1.21 ms                                                                                                    | 1.28 ms: 1.05x slower                                                                                          |
| genshi_xml                       | 43.2 ms                                                                                                    | 45.7 ms: 1.06x slower                                                                                          |
| logging_silent                   | 59.2 ns                                                                                                    | 62.7 ns: 1.06x slower                                                                                          |
| scimark_lu                       | 74.7 ms                                                                                                    | 79.2 ms: 1.06x slower                                                                                          |
| raytrace                         | 201 ms                                                                                                     | 214 ms: 1.06x slower                                                                                           |
| pycparser                        | 878 ms                                                                                                     | 937 ms: 1.07x slower                                                                                           |
| argparse_subparsers              | 687 us                                                                                                     | 736 us: 1.07x slower                                                                                           |
| sqlglot_v2_parse                 | 954 us                                                                                                     | 1.02 ms: 1.07x slower                                                                                          |
| thrift                           | 2.00 ms                                                                                                    | 2.15 ms: 1.07x slower                                                                                          |
| async_generators                 | 231 ms                                                                                                     | 249 ms: 1.08x slower                                                                                           |
| xdsl_constant_fold               | 36.0 ms                                                                                                    | 38.9 ms: 1.08x slower                                                                                          |
| comprehensions                   | 11.4 us                                                                                                    | 12.3 us: 1.08x slower                                                                                          |
| coroutines                       | 15.1 ms                                                                                                    | 16.4 ms: 1.08x slower                                                                                          |
| logging_simple                   | 5.02 us                                                                                                    | 5.44 us: 1.08x slower                                                                                          |
| hexiom                           | 4.50 ms                                                                                                    | 4.88 ms: 1.09x slower                                                                                          |
| async_tree_eager                 | 83.0 ms                                                                                                    | 90.4 ms: 1.09x slower                                                                                          |
| html5lib                         | 45.3 ms                                                                                                    | 49.7 ms: 1.10x slower                                                                                          |
| thread_montecarlo_optimized      | 12.9 ms                                                                                                    | 14.4 ms: 1.11x slower                                                                                          |
| nbody                            | 74.2 ms                                                                                                    | 83.5 ms: 1.13x slower                                                                                          |
| go                               | 91.1 ms                                                                                                    | 106 ms: 1.16x slower                                                                                           |
| scimark_sor                      | 78.2 ms                                                                                                    | 91.5 ms: 1.17x slower                                                                                          |
| pprint_pformat                   | 1.10 sec                                                                                                   | 1.33 sec: 1.22x slower                                                                                         |
| pprint_safe_repr                 | 534 ms                                                                                                     | 654 ms: 1.22x slower                                                                                           |
| thread_montecarlo_naive          | 14.3 ms                                                                                                    | 18.6 ms: 1.31x slower                                                                                          |
| unpack_sequence                  | 35.6 ns                                                                                                    | 106 ns: 2.99x slower                                                                                           |
| Geometric mean                   | (ref)                                                                                                      | 1.01x slower                                                                                                   |

Benchmark hidden because not significant (17): generators, urlsafe_base64_small, logging_format, xml_etree_parse, unpickle, json, gc_traversal, regex_dna, base64_large, fastapi_http, asyncio_tcp_ssl, base64_small, chaos, async_tree_cpu_io_mixed_tg, async_tree_io_tg, async_tree_io, mypy2

- Geometric mean (including insignificant results): 1.013x slower

# HPT report

- Reliability score: 99.38% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.01x