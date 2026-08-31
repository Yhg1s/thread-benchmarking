# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.039x faster
- HPT reliability: 99.87%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.02x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 11.1 ms: 1.08x slower                                                  |
| fastapi_http   | 222 ms                                                             | 215 ms: 1.03x faster                                                   |
| html5lib       | 45.3 ms                                                            | 44.8 ms: 1.01x faster                                                  |
| tornado_http   | 101 ms                                                             | 102 ms: 1.01x slower                                                   |
| Geometric mean | (ref)                                                              | 1.01x slower                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                    | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_eager_io          | 568 ms                                                             | 491 ms: 1.16x faster                                                   |
| async_tree_eager_io_tg       | 565 ms                                                             | 492 ms: 1.15x faster                                                   |
| async_tree_io                | 549 ms                                                             | 488 ms: 1.12x faster                                                   |
| async_tree_io_tg             | 545 ms                                                             | 486 ms: 1.12x faster                                                   |
| asyncio_tcp                  | 324 ms                                                             | 292 ms: 1.11x faster                                                   |
| async_tree_none              | 233 ms                                                             | 215 ms: 1.08x faster                                                   |
| async_tree_memoization       | 285 ms                                                             | 264 ms: 1.08x faster                                                   |
| async_tree_none_tg           | 224 ms                                                             | 208 ms: 1.07x faster                                                   |
| async_tree_eager_tg          | 182 ms                                                             | 172 ms: 1.06x faster                                                   |
| async_tree_memoization_tg    | 279 ms                                                             | 265 ms: 1.05x faster                                                   |
| async_tree_cpu_io_mixed_tg   | 427 ms                                                             | 406 ms: 1.05x faster                                                   |
| async_tree_cpu_io_mixed      | 429 ms                                                             | 414 ms: 1.04x faster                                                   |
| async_tree_eager_memoization | 183 ms                                                             | 178 ms: 1.02x faster                                                   |
| asyncio_websockets           | 305 ms                                                             | 314 ms: 1.03x slower                                                   |
| coroutines                   | 15.1 ms                                                            | 15.6 ms: 1.03x slower                                                  |
| async_generators             | 231 ms                                                             | 244 ms: 1.06x slower                                                   |
| Geometric mean               | (ref)                                                              | 1.05x faster                                                           |

Benchmark hidden because not significant (4): async_tree_eager_cpu_io_mixed_tg, asyncio_tcp_ssl, async_tree_eager_cpu_io_mixed, async_tree_eager

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 17.6 ns: 1.09x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 209 ms                                                             | 200 ms: 1.05x faster                                                   |
| decimal_factorial | 174 ms                                                             | 172 ms: 1.01x faster                                                   |
| Geometric mean    | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| float          | 51.2 ms                                                            | 42.4 ms: 1.21x faster                                                  |
| nbody          | 74.2 ms                                                            | 65.3 ms: 1.14x faster                                                  |
| pidigits       | 216 ms                                                             | 216 ms: 1.00x faster                                                   |
| Geometric mean | (ref)                                                              | 1.11x faster                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_compile  | 97.0 ms                                                            | 92.2 ms: 1.05x faster                                                  |
| regex_v8       | 15.0 ms                                                            | 14.6 ms: 1.03x faster                                                  |
| regex_effbot   | 1.98 ms                                                            | 2.01 ms: 1.02x slower                                                  |
| regex_dna      | 147 ms                                                             | 150 ms: 1.02x slower                                                   |
| Geometric mean | (ref)                                                              | 1.01x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| urlsafe_base64_small | 340 us                                                             | 260 us: 1.31x faster                                                   |
| base64_small         | 227 us                                                             | 183 us: 1.24x faster                                                   |
| base16_small         | 265 us                                                             | 214 us: 1.24x faster                                                   |
| unpickle_pure_python | 163 us                                                             | 136 us: 1.19x faster                                                   |
| json_dumps           | 7.52 ms                                                            | 6.43 ms: 1.17x faster                                                  |
| ascii85_large        | 681 ms                                                             | 590 ms: 1.15x faster                                                   |
| xml_etree_process    | 50.0 ms                                                            | 43.4 ms: 1.15x faster                                                  |
| xml_etree_generate   | 68.1 ms                                                            | 59.2 ms: 1.15x faster                                                  |
| xml_etree_iterparse  | 85.5 ms                                                            | 75.2 ms: 1.14x faster                                                  |
| ascii85_small        | 13.0 ms                                                            | 11.5 ms: 1.13x faster                                                  |
| pickle_pure_python   | 251 us                                                             | 229 us: 1.09x faster                                                   |
| base85_small         | 4.66 ms                                                            | 4.38 ms: 1.06x faster                                                  |
| json_loads           | 18.6 us                                                            | 17.6 us: 1.06x faster                                                  |
| base85_large         | 249 ms                                                             | 237 ms: 1.05x faster                                                   |
| pickle_dict          | 20.0 us                                                            | 19.1 us: 1.04x faster                                                  |
| base16_large         | 6.35 ms                                                            | 6.11 ms: 1.04x faster                                                  |
| xml_etree_parse      | 118 ms                                                             | 114 ms: 1.03x faster                                                   |
| base32_large         | 289 ms                                                             | 281 ms: 1.03x faster                                                   |
| tomli_loads          | 1.49 sec                                                           | 1.45 sec: 1.03x faster                                                 |
| unpickle_list        | 3.03 us                                                            | 2.96 us: 1.03x faster                                                  |
| unpickle             | 10.5 us                                                            | 10.3 us: 1.01x faster                                                  |
| pickle_list          | 3.03 us                                                            | 3.00 us: 1.01x faster                                                  |
| base64_large         | 5.70 ms                                                            | 5.66 ms: 1.01x faster                                                  |
| pickle               | 8.04 us                                                            | 8.01 us: 1.00x faster                                                  |
| base32_small         | 5.71 ms                                                            | 5.73 ms: 1.00x slower                                                  |
| Geometric mean       | (ref)                                                              | 1.09x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 9.59 ms: 1.04x faster                                                  |
| python_startup_no_site | 6.52 ms                                                            | 6.40 ms: 1.02x faster                                                  |
| Geometric mean         | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| mako            | 8.69 ms                                                            | 7.18 ms: 1.21x faster                                                  |
| genshi_text     | 18.0 ms                                                            | 17.7 ms: 1.02x faster                                                  |
| django_template | 30.5 ms                                                            | 31.1 ms: 1.02x slower                                                  |
| genshi_xml      | 43.2 ms                                                            | 47.1 ms: 1.09x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 12.4 ms                                                            | 8.95 ms: 1.39x faster                                                  |
| thread_mandelbrot_naive     | 207 ms                                                             | 170 ms: 1.22x faster                                                   |
| thread_mandelbrot_optimized | 205 ms                                                             | 170 ms: 1.21x faster                                                   |
| thread_pipeline_naive       | 34.9 ms                                                            | 33.4 ms: 1.04x faster                                                  |
| thread_pipeline_optimized   | 25.8 ms                                                            | 24.8 ms: 1.04x faster                                                  |
| thread_memo_optimized       | 17.5 ms                                                            | 16.8 ms: 1.04x faster                                                  |
| thread_accumulate_naive     | 40.4 ms                                                            | 39.0 ms: 1.03x faster                                                  |
| thread_accumulate_optimized | 39.5 ms                                                            | 38.6 ms: 1.02x faster                                                  |
| thread_counter_naive        | 21.2 ms                                                            | 21.4 ms: 1.01x slower                                                  |
| thread_counter_optimized    | 18.3 ms                                                            | 18.6 ms: 1.02x slower                                                  |
| thread_montecarlo_optimized | 12.9 ms                                                            | 13.7 ms: 1.06x slower                                                  |
| thread_montecarlo_naive     | 14.3 ms                                                            | 17.2 ms: 1.20x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.05x faster                                                           |

All benchmarks:
===============

| Benchmark                    | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| richards                     | 34.7 ms                                                            | 19.4 ms: 1.79x faster                                                  |
| richards_super               | 40.3 ms                                                            | 24.3 ms: 1.66x faster                                                  |
| thread_memo_naive            | 12.4 ms                                                            | 8.95 ms: 1.39x faster                                                  |
| scimark_fft                  | 211 ms                                                             | 156 ms: 1.35x faster                                                   |
| urlsafe_base64_small         | 340 us                                                             | 260 us: 1.31x faster                                                   |
| base64_small                 | 227 us                                                             | 183 us: 1.24x faster                                                   |
| base16_small                 | 265 us                                                             | 214 us: 1.24x faster                                                   |
| deepcopy_memo                | 19.1 us                                                            | 15.5 us: 1.24x faster                                                  |
| thread_mandelbrot_naive      | 207 ms                                                             | 170 ms: 1.22x faster                                                   |
| deltablue                    | 2.76 ms                                                            | 2.26 ms: 1.22x faster                                                  |
| mako                         | 8.69 ms                                                            | 7.18 ms: 1.21x faster                                                  |
| float                        | 51.2 ms                                                            | 42.4 ms: 1.21x faster                                                  |
| thread_mandelbrot_optimized  | 205 ms                                                             | 170 ms: 1.21x faster                                                   |
| spectral_norm                | 64.1 ms                                                            | 53.7 ms: 1.19x faster                                                  |
| unpickle_pure_python         | 163 us                                                             | 136 us: 1.19x faster                                                   |
| scimark_monte_carlo          | 42.3 ms                                                            | 35.9 ms: 1.18x faster                                                  |
| json_dumps                   | 7.52 ms                                                            | 6.43 ms: 1.17x faster                                                  |
| pathlib                      | 12.7 ms                                                            | 10.9 ms: 1.16x faster                                                  |
| async_tree_eager_io          | 568 ms                                                             | 491 ms: 1.16x faster                                                   |
| telco                        | 5.39 ms                                                            | 4.67 ms: 1.15x faster                                                  |
| ascii85_large                | 681 ms                                                             | 590 ms: 1.15x faster                                                   |
| xml_etree_process            | 50.0 ms                                                            | 43.4 ms: 1.15x faster                                                  |
| xml_etree_generate           | 68.1 ms                                                            | 59.2 ms: 1.15x faster                                                  |
| async_tree_eager_io_tg       | 565 ms                                                             | 492 ms: 1.15x faster                                                   |
| scimark_lu                   | 74.7 ms                                                            | 65.2 ms: 1.15x faster                                                  |
| logging_silent               | 59.2 ns                                                            | 52.1 ns: 1.14x faster                                                  |
| nbody                        | 74.2 ms                                                            | 65.3 ms: 1.14x faster                                                  |
| xml_etree_iterparse          | 85.5 ms                                                            | 75.2 ms: 1.14x faster                                                  |
| ascii85_small                | 13.0 ms                                                            | 11.5 ms: 1.13x faster                                                  |
| async_tree_io                | 549 ms                                                             | 488 ms: 1.12x faster                                                   |
| scimark_sor                  | 78.2 ms                                                            | 69.5 ms: 1.12x faster                                                  |
| async_tree_io_tg             | 545 ms                                                             | 486 ms: 1.12x faster                                                   |
| asyncio_tcp                  | 324 ms                                                             | 292 ms: 1.11x faster                                                   |
| pyflate                      | 309 ms                                                             | 281 ms: 1.10x faster                                                   |
| scimark_sparse_mat_mult      | 2.89 ms                                                            | 2.64 ms: 1.10x faster                                                  |
| logging_format               | 6.00 us                                                            | 5.48 us: 1.10x faster                                                  |
| pickle_pure_python           | 251 us                                                             | 229 us: 1.09x faster                                                   |
| noop                         | 19.2 ns                                                            | 17.6 ns: 1.09x faster                                                  |
| bpe_tokeniser                | 3.11 sec                                                           | 2.86 sec: 1.09x faster                                                 |
| async_tree_none              | 233 ms                                                             | 215 ms: 1.08x faster                                                   |
| async_tree_memoization       | 285 ms                                                             | 264 ms: 1.08x faster                                                   |
| fannkuch                     | 246 ms                                                             | 228 ms: 1.08x faster                                                   |
| async_tree_none_tg           | 224 ms                                                             | 208 ms: 1.07x faster                                                   |
| crypto_pyaes                 | 56.7 ms                                                            | 52.8 ms: 1.07x faster                                                  |
| meteor_contest               | 85.4 ms                                                            | 79.9 ms: 1.07x faster                                                  |
| json                         | 3.46 ms                                                            | 3.25 ms: 1.07x faster                                                  |
| base85_small                 | 4.66 ms                                                            | 4.38 ms: 1.06x faster                                                  |
| json_loads                   | 18.6 us                                                            | 17.6 us: 1.06x faster                                                  |
| async_tree_eager_tg          | 182 ms                                                             | 172 ms: 1.06x faster                                                   |
| go                           | 91.1 ms                                                            | 85.9 ms: 1.06x faster                                                  |
| async_tree_memoization_tg    | 279 ms                                                             | 265 ms: 1.05x faster                                                   |
| async_tree_cpu_io_mixed_tg   | 427 ms                                                             | 406 ms: 1.05x faster                                                   |
| base85_large                 | 249 ms                                                             | 237 ms: 1.05x faster                                                   |
| regex_compile                | 97.0 ms                                                            | 92.2 ms: 1.05x faster                                                  |
| decimal_pi                   | 209 ms                                                             | 200 ms: 1.05x faster                                                   |
| thread_pipeline_naive        | 34.9 ms                                                            | 33.4 ms: 1.04x faster                                                  |
| pickle_dict                  | 20.0 us                                                            | 19.1 us: 1.04x faster                                                  |
| thread_pipeline_optimized    | 25.8 ms                                                            | 24.8 ms: 1.04x faster                                                  |
| thread_memo_optimized        | 17.5 ms                                                            | 16.8 ms: 1.04x faster                                                  |
| base16_large                 | 6.35 ms                                                            | 6.11 ms: 1.04x faster                                                  |
| async_tree_cpu_io_mixed      | 429 ms                                                             | 414 ms: 1.04x faster                                                   |
| python_startup               | 9.93 ms                                                            | 9.59 ms: 1.04x faster                                                  |
| thread_accumulate_naive      | 40.4 ms                                                            | 39.0 ms: 1.03x faster                                                  |
| xml_etree_parse              | 118 ms                                                             | 114 ms: 1.03x faster                                                   |
| fastapi_http                 | 222 ms                                                             | 215 ms: 1.03x faster                                                   |
| regex_v8                     | 15.0 ms                                                            | 14.6 ms: 1.03x faster                                                  |
| base32_large                 | 289 ms                                                             | 281 ms: 1.03x faster                                                   |
| tomli_loads                  | 1.49 sec                                                           | 1.45 sec: 1.03x faster                                                 |
| unpickle_list                | 3.03 us                                                            | 2.96 us: 1.03x faster                                                  |
| async_tree_eager_memoization | 183 ms                                                             | 178 ms: 1.02x faster                                                   |
| thread_accumulate_optimized  | 39.5 ms                                                            | 38.6 ms: 1.02x faster                                                  |
| python_startup_no_site       | 6.52 ms                                                            | 6.40 ms: 1.02x faster                                                  |
| genshi_text                  | 18.0 ms                                                            | 17.7 ms: 1.02x faster                                                  |
| generators                   | 24.2 ms                                                            | 23.8 ms: 1.01x faster                                                  |
| unpickle                     | 10.5 us                                                            | 10.3 us: 1.01x faster                                                  |
| logging_simple               | 5.02 us                                                            | 4.96 us: 1.01x faster                                                  |
| decimal_factorial            | 174 ms                                                             | 172 ms: 1.01x faster                                                   |
| html5lib                     | 45.3 ms                                                            | 44.8 ms: 1.01x faster                                                  |
| pickle_list                  | 3.03 us                                                            | 3.00 us: 1.01x faster                                                  |
| base64_large                 | 5.70 ms                                                            | 5.66 ms: 1.01x faster                                                  |
| gc_traversal                 | 3.36 ms                                                            | 3.34 ms: 1.01x faster                                                  |
| pickle                       | 8.04 us                                                            | 8.01 us: 1.00x faster                                                  |
| pidigits                     | 216 ms                                                             | 216 ms: 1.00x faster                                                   |
| base32_small                 | 5.71 ms                                                            | 5.73 ms: 1.00x slower                                                  |
| tornado_http                 | 101 ms                                                             | 102 ms: 1.01x slower                                                   |
| thread_counter_naive         | 21.2 ms                                                            | 21.4 ms: 1.01x slower                                                  |
| sqlglot_v2_parse             | 954 us                                                             | 968 us: 1.01x slower                                                   |
| thread_counter_optimized     | 18.3 ms                                                            | 18.6 ms: 1.02x slower                                                  |
| regex_effbot                 | 1.98 ms                                                            | 2.01 ms: 1.02x slower                                                  |
| django_template              | 30.5 ms                                                            | 31.1 ms: 1.02x slower                                                  |
| regex_dna                    | 147 ms                                                             | 150 ms: 1.02x slower                                                   |
| typing_runtime_protocols     | 115 us                                                             | 118 us: 1.03x slower                                                   |
| thrift                       | 2.00 ms                                                            | 2.06 ms: 1.03x slower                                                  |
| coverage                     | 54.5 ms                                                            | 56.1 ms: 1.03x slower                                                  |
| asyncio_websockets           | 305 ms                                                             | 314 ms: 1.03x slower                                                   |
| coroutines                   | 15.1 ms                                                            | 15.6 ms: 1.03x slower                                                  |
| pycparser                    | 878 ms                                                             | 911 ms: 1.04x slower                                                   |
| argparse_many_optionals      | 34.5 ms                                                            | 36.0 ms: 1.04x slower                                                  |
| nqueens                      | 59.8 ms                                                            | 63.0 ms: 1.05x slower                                                  |
| pprint_safe_repr             | 534 ms                                                             | 563 ms: 1.05x slower                                                   |
| sqlglot_v2_transpile         | 1.21 ms                                                            | 1.28 ms: 1.05x slower                                                  |
| async_generators             | 231 ms                                                             | 244 ms: 1.06x slower                                                   |
| argparse_subparsers          | 687 us                                                             | 728 us: 1.06x slower                                                   |
| thread_montecarlo_optimized  | 12.9 ms                                                            | 13.7 ms: 1.06x slower                                                  |
| raytrace                     | 201 ms                                                             | 214 ms: 1.07x slower                                                   |
| sqlalchemy_imperative        | 14.8 ms                                                            | 15.8 ms: 1.07x slower                                                  |
| pprint_pformat               | 1.10 sec                                                           | 1.18 sec: 1.07x slower                                                 |
| xdsl_constant_fold           | 36.0 ms                                                            | 38.6 ms: 1.07x slower                                                  |
| chameleon                    | 10.3 ms                                                            | 11.1 ms: 1.08x slower                                                  |
| hexiom                       | 4.50 ms                                                            | 4.89 ms: 1.09x slower                                                  |
| genshi_xml                   | 43.2 ms                                                            | 47.1 ms: 1.09x slower                                                  |
| sympy_expand                 | 344 ms                                                             | 376 ms: 1.09x slower                                                   |
| deepcopy                     | 198 us                                                             | 218 us: 1.10x slower                                                   |
| deepcopy_reduce              | 2.02 us                                                            | 2.24 us: 1.11x slower                                                  |
| chaos                        | 42.9 ms                                                            | 47.7 ms: 1.11x slower                                                  |
| sympy_sum                    | 109 ms                                                             | 127 ms: 1.17x slower                                                   |
| sympy_integrate              | 15.1 ms                                                            | 17.7 ms: 1.17x slower                                                  |
| mypy2                        | 780 ms                                                             | 918 ms: 1.18x slower                                                   |
| sqlglot_v2_normalize         | 84.9 ms                                                            | 101 ms: 1.19x slower                                                   |
| mdp                          | 971 ms                                                             | 1.16 sec: 1.19x slower                                                 |
| sqlglot_v2_optimize          | 41.8 ms                                                            | 49.8 ms: 1.19x slower                                                  |
| thread_montecarlo_naive      | 14.3 ms                                                            | 17.2 ms: 1.20x slower                                                  |
| pylint                       | 222 ms                                                             | 272 ms: 1.23x slower                                                   |
| sympy_str                    | 200 ms                                                             | 247 ms: 1.23x slower                                                   |
| unpack_sequence              | 35.6 ns                                                            | 54.2 ns: 1.52x slower                                                  |
| Geometric mean               | (ref)                                                              | 1.04x faster                                                           |

Benchmark hidden because not significant (6): async_tree_eager_cpu_io_mixed_tg, asyncio_tcp_ssl, async_tree_eager_cpu_io_mixed, comprehensions, create_gc_cycles, async_tree_eager
Ignored benchmarks (6) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json: async_tree_eager_memoization_tg, docutils, networkx_connected_components, networkx_k_core, networkx_shortest_path, quadtree_nbody

- Geometric mean (including insignificant results): 1.039x faster

# HPT report

- Reliability score: 99.87% likely to be faster
- 90% likely to have a speedup of 1.01x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.02x