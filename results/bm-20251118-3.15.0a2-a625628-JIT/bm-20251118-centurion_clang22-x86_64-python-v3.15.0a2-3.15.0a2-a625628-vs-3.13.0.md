# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.113x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.03x faster
- Memory change: 1.11x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| html5lib       | 50.9 ms                                                            | 44.8 ms: 1.14x faster                                                  |
| tornado_http   | 98.9 ms                                                            | 102 ms: 1.03x slower                                                   |
| Geometric mean | (ref)                                                              | 1.03x faster                                                           |

Benchmark hidden because not significant (2): chameleon, fastapi_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_io_tg                 | 781 ms                                                             | 486 ms: 1.61x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 265 ms: 1.59x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 491 ms: 1.53x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 488 ms: 1.52x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 492 ms: 1.49x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 264 ms: 1.49x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 215 ms: 1.45x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 208 ms: 1.39x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 406 ms: 1.25x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 178 ms: 1.24x faster                                                   |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 414 ms: 1.19x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 15.6 ms: 1.16x faster                                                  |
| asyncio_tcp                      | 316 ms                                                             | 292 ms: 1.08x faster                                                   |
| async_tree_eager                 | 88.3 ms                                                            | 83.2 ms: 1.06x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 327 ms: 1.05x faster                                                   |
| async_generators                 | 251 ms                                                             | 244 ms: 1.03x faster                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.28 sec: 1.01x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 373 ms: 1.24x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 172 ms: 3.02x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.16x faster                                                           |

Benchmark hidden because not significant (1): asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 17.6 ns: 1.22x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 200 ms: 1.14x faster                                                   |
| decimal_factorial | 177 ms                                                             | 172 ms: 1.02x faster                                                   |
| Geometric mean    | (ref)                                                              | 1.08x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 42.4 ms: 1.40x faster                                                  |
| nbody          | 75.8 ms                                                            | 65.3 ms: 1.16x faster                                                  |
| Geometric mean | (ref)                                                              | 1.17x faster                                                           |

Benchmark hidden because not significant (1): pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 2.01 ms: 1.16x faster                                                  |
| regex_compile  | 102 ms                                                             | 92.2 ms: 1.11x faster                                                  |
| regex_dna      | 159 ms                                                             | 150 ms: 1.06x faster                                                   |
| regex_v8       | 15.0 ms                                                            | 14.6 ms: 1.03x faster                                                  |
| Geometric mean | (ref)                                                              | 1.09x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.11 ms: 6.98x faster                                                  |
| base16_small         | 836 us                                                             | 214 us: 3.91x faster                                                   |
| ascii85_large        | 824 ms                                                             | 590 ms: 1.40x faster                                                   |
| ascii85_small        | 15.7 ms                                                            | 11.5 ms: 1.36x faster                                                  |
| urlsafe_base64_small | 328 us                                                             | 260 us: 1.26x faster                                                   |
| tomli_loads          | 1.77 sec                                                           | 1.45 sec: 1.22x faster                                                 |
| base64_small         | 222 us                                                             | 183 us: 1.21x faster                                                   |
| xml_etree_generate   | 70.6 ms                                                            | 59.2 ms: 1.19x faster                                                  |
| unpickle_pure_python | 161 us                                                             | 136 us: 1.18x faster                                                   |
| unpickle_list        | 3.42 us                                                            | 2.96 us: 1.16x faster                                                  |
| base32_large         | 325 ms                                                             | 281 ms: 1.15x faster                                                   |
| xml_etree_iterparse  | 86.8 ms                                                            | 75.2 ms: 1.15x faster                                                  |
| xml_etree_process    | 49.9 ms                                                            | 43.4 ms: 1.15x faster                                                  |
| json_dumps           | 7.26 ms                                                            | 6.43 ms: 1.13x faster                                                  |
| base32_small         | 6.46 ms                                                            | 5.73 ms: 1.13x faster                                                  |
| base85_large         | 267 ms                                                             | 237 ms: 1.13x faster                                                   |
| base85_small         | 4.85 ms                                                            | 4.38 ms: 1.11x faster                                                  |
| pickle_pure_python   | 245 us                                                             | 229 us: 1.07x faster                                                   |
| xml_etree_parse      | 121 ms                                                             | 114 ms: 1.06x faster                                                   |
| unpickle             | 10.8 us                                                            | 10.3 us: 1.05x faster                                                  |
| json_loads           | 18.2 us                                                            | 17.6 us: 1.04x faster                                                  |
| base64_large         | 5.69 ms                                                            | 5.66 ms: 1.01x faster                                                  |
| pickle_dict          | 19.0 us                                                            | 19.1 us: 1.00x slower                                                  |
| pickle               | 7.21 us                                                            | 8.01 us: 1.11x slower                                                  |
| pickle_list          | 2.66 us                                                            | 3.00 us: 1.13x slower                                                  |
| Geometric mean       | (ref)                                                              | 1.27x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.40 ms: 1.02x faster                                                  |
| python_startup         | 9.51 ms                                                            | 9.59 ms: 1.01x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.00x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 17.7 ms: 1.19x faster                                                  |
| mako            | 8.30 ms                                                            | 7.18 ms: 1.16x faster                                                  |
| genshi_xml      | 46.3 ms                                                            | 47.1 ms: 1.02x slower                                                  |
| django_template | 28.8 ms                                                            | 31.1 ms: 1.08x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.06x faster                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 8.95 ms: 4.23x faster                                                  |
| thread_pipeline_naive       | 49.8 ms                                                            | 33.4 ms: 1.49x faster                                                  |
| thread_mandelbrot_naive     | 190 ms                                                             | 170 ms: 1.12x faster                                                   |
| thread_mandelbrot_optimized | 189 ms                                                             | 170 ms: 1.11x faster                                                   |
| thread_counter_naive        | 23.7 ms                                                            | 21.4 ms: 1.11x faster                                                  |
| thread_counter_optimized    | 19.7 ms                                                            | 18.6 ms: 1.06x faster                                                  |
| thread_montecarlo_naive     | 18.1 ms                                                            | 17.2 ms: 1.06x faster                                                  |
| thread_montecarlo_optimized | 14.2 ms                                                            | 13.7 ms: 1.04x faster                                                  |
| thread_accumulate_naive     | 36.5 ms                                                            | 39.0 ms: 1.07x slower                                                  |
| thread_pipeline_optimized   | 22.8 ms                                                            | 24.8 ms: 1.09x slower                                                  |
| thread_accumulate_optimized | 35.3 ms                                                            | 38.6 ms: 1.09x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.19x faster                                                           |

Benchmark hidden because not significant (1): thread_memo_optimized

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.11 ms: 6.98x faster                                                  |
| thread_memo_naive                | 37.9 ms                                                            | 8.95 ms: 4.23x faster                                                  |
| base16_small                     | 836 us                                                             | 214 us: 3.91x faster                                                   |
| richards                         | 38.2 ms                                                            | 19.4 ms: 1.96x faster                                                  |
| richards_super                   | 43.8 ms                                                            | 24.3 ms: 1.80x faster                                                  |
| deepcopy_memo                    | 27.8 us                                                            | 15.5 us: 1.79x faster                                                  |
| mdp                              | 2.05 sec                                                           | 1.16 sec: 1.78x faster                                                 |
| async_tree_io_tg                 | 781 ms                                                             | 486 ms: 1.61x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 265 ms: 1.59x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 491 ms: 1.53x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 488 ms: 1.52x faster                                                   |
| go                               | 129 ms                                                             | 85.9 ms: 1.51x faster                                                  |
| thread_pipeline_naive            | 49.8 ms                                                            | 33.4 ms: 1.49x faster                                                  |
| async_tree_eager_io_tg           | 731 ms                                                             | 492 ms: 1.49x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 264 ms: 1.49x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 215 ms: 1.45x faster                                                   |
| float                            | 59.2 ms                                                            | 42.4 ms: 1.40x faster                                                  |
| ascii85_large                    | 824 ms                                                             | 590 ms: 1.40x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 208 ms: 1.39x faster                                                   |
| scimark_fft                      | 216 ms                                                             | 156 ms: 1.38x faster                                                   |
| scimark_sor                      | 96.2 ms                                                            | 69.5 ms: 1.38x faster                                                  |
| ascii85_small                    | 15.7 ms                                                            | 11.5 ms: 1.36x faster                                                  |
| pyflate                          | 374 ms                                                             | 281 ms: 1.33x faster                                                   |
| scimark_monte_carlo              | 47.2 ms                                                            | 35.9 ms: 1.31x faster                                                  |
| spectral_norm                    | 68.6 ms                                                            | 53.7 ms: 1.28x faster                                                  |
| urlsafe_base64_small             | 328 us                                                             | 260 us: 1.26x faster                                                   |
| fannkuch                         | 287 ms                                                             | 228 ms: 1.26x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 406 ms: 1.25x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 178 ms: 1.24x faster                                                   |
| deepcopy                         | 267 us                                                             | 218 us: 1.23x faster                                                   |
| tomli_loads                      | 1.77 sec                                                           | 1.45 sec: 1.22x faster                                                 |
| noop                             | 21.4 ns                                                            | 17.6 ns: 1.22x faster                                                  |
| base64_small                     | 222 us                                                             | 183 us: 1.21x faster                                                   |
| xml_etree_generate               | 70.6 ms                                                            | 59.2 ms: 1.19x faster                                                  |
| genshi_text                      | 21.1 ms                                                            | 17.7 ms: 1.19x faster                                                  |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 414 ms: 1.19x faster                                                   |
| unpickle_pure_python             | 161 us                                                             | 136 us: 1.18x faster                                                   |
| bpe_tokeniser                    | 3.37 sec                                                           | 2.86 sec: 1.18x faster                                                 |
| coroutines                       | 18.2 ms                                                            | 15.6 ms: 1.16x faster                                                  |
| nbody                            | 75.8 ms                                                            | 65.3 ms: 1.16x faster                                                  |
| regex_effbot                     | 2.33 ms                                                            | 2.01 ms: 1.16x faster                                                  |
| unpickle_list                    | 3.42 us                                                            | 2.96 us: 1.16x faster                                                  |
| mako                             | 8.30 ms                                                            | 7.18 ms: 1.16x faster                                                  |
| base32_large                     | 325 ms                                                             | 281 ms: 1.15x faster                                                   |
| logging_silent                   | 60.1 ns                                                            | 52.1 ns: 1.15x faster                                                  |
| xml_etree_iterparse              | 86.8 ms                                                            | 75.2 ms: 1.15x faster                                                  |
| xml_etree_process                | 49.9 ms                                                            | 43.4 ms: 1.15x faster                                                  |
| telco                            | 5.37 ms                                                            | 4.67 ms: 1.15x faster                                                  |
| deltablue                        | 2.59 ms                                                            | 2.26 ms: 1.14x faster                                                  |
| decimal_pi                       | 228 ms                                                             | 200 ms: 1.14x faster                                                   |
| html5lib                         | 50.9 ms                                                            | 44.8 ms: 1.14x faster                                                  |
| json_dumps                       | 7.26 ms                                                            | 6.43 ms: 1.13x faster                                                  |
| base32_small                     | 6.46 ms                                                            | 5.73 ms: 1.13x faster                                                  |
| base85_large                     | 267 ms                                                             | 237 ms: 1.13x faster                                                   |
| pathlib                          | 12.2 ms                                                            | 10.9 ms: 1.12x faster                                                  |
| thread_mandelbrot_naive          | 190 ms                                                             | 170 ms: 1.12x faster                                                   |
| thread_mandelbrot_optimized      | 189 ms                                                             | 170 ms: 1.11x faster                                                   |
| regex_compile                    | 102 ms                                                             | 92.2 ms: 1.11x faster                                                  |
| thread_counter_naive             | 23.7 ms                                                            | 21.4 ms: 1.11x faster                                                  |
| base85_small                     | 4.85 ms                                                            | 4.38 ms: 1.11x faster                                                  |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.64 ms: 1.08x faster                                                  |
| asyncio_tcp                      | 316 ms                                                             | 292 ms: 1.08x faster                                                   |
| json                             | 3.50 ms                                                            | 3.25 ms: 1.08x faster                                                  |
| scimark_lu                       | 70.2 ms                                                            | 65.2 ms: 1.08x faster                                                  |
| meteor_contest                   | 85.7 ms                                                            | 79.9 ms: 1.07x faster                                                  |
| pickle_pure_python               | 245 us                                                             | 229 us: 1.07x faster                                                   |
| async_tree_eager                 | 88.3 ms                                                            | 83.2 ms: 1.06x faster                                                  |
| xml_etree_parse                  | 121 ms                                                             | 114 ms: 1.06x faster                                                   |
| thread_counter_optimized         | 19.7 ms                                                            | 18.6 ms: 1.06x faster                                                  |
| thread_montecarlo_naive          | 18.1 ms                                                            | 17.2 ms: 1.06x faster                                                  |
| regex_dna                        | 159 ms                                                             | 150 ms: 1.06x faster                                                   |
| crypto_pyaes                     | 55.6 ms                                                            | 52.8 ms: 1.05x faster                                                  |
| deepcopy_reduce                  | 2.36 us                                                            | 2.24 us: 1.05x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 327 ms: 1.05x faster                                                   |
| unpickle                         | 10.8 us                                                            | 10.3 us: 1.05x faster                                                  |
| json_loads                       | 18.2 us                                                            | 17.6 us: 1.04x faster                                                  |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 13.7 ms: 1.04x faster                                                  |
| regex_v8                         | 15.0 ms                                                            | 14.6 ms: 1.03x faster                                                  |
| async_generators                 | 251 ms                                                             | 244 ms: 1.03x faster                                                   |
| logging_format                   | 5.62 us                                                            | 5.48 us: 1.03x faster                                                  |
| decimal_factorial                | 177 ms                                                             | 172 ms: 1.02x faster                                                   |
| logging_simple                   | 5.06 us                                                            | 4.96 us: 1.02x faster                                                  |
| python_startup_no_site           | 6.49 ms                                                            | 6.40 ms: 1.02x faster                                                  |
| sqlglot_v2_parse                 | 979 us                                                             | 968 us: 1.01x faster                                                   |
| thrift                           | 2.07 ms                                                            | 2.06 ms: 1.01x faster                                                  |
| base64_large                     | 5.69 ms                                                            | 5.66 ms: 1.01x faster                                                  |
| comprehensions                   | 11.4 us                                                            | 11.4 us: 1.00x faster                                                  |
| pickle_dict                      | 19.0 us                                                            | 19.1 us: 1.00x slower                                                  |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.28 sec: 1.01x slower                                                 |
| python_startup                   | 9.51 ms                                                            | 9.59 ms: 1.01x slower                                                  |
| pycparser                        | 901 ms                                                             | 911 ms: 1.01x slower                                                   |
| genshi_xml                       | 46.3 ms                                                            | 47.1 ms: 1.02x slower                                                  |
| coverage                         | 55.0 ms                                                            | 56.1 ms: 1.02x slower                                                  |
| tornado_http                     | 98.9 ms                                                            | 102 ms: 1.03x slower                                                   |
| hexiom                           | 4.75 ms                                                            | 4.89 ms: 1.03x slower                                                  |
| pprint_safe_repr                 | 546 ms                                                             | 563 ms: 1.03x slower                                                   |
| gc_traversal                     | 3.20 ms                                                            | 3.34 ms: 1.04x slower                                                  |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.28 ms: 1.05x slower                                                  |
| pprint_pformat                   | 1.13 sec                                                           | 1.18 sec: 1.05x slower                                                 |
| typing_runtime_protocols         | 112 us                                                             | 118 us: 1.05x slower                                                   |
| xdsl_constant_fold               | 36.4 ms                                                            | 38.6 ms: 1.06x slower                                                  |
| thread_accumulate_naive          | 36.5 ms                                                            | 39.0 ms: 1.07x slower                                                  |
| generators                       | 22.2 ms                                                            | 23.8 ms: 1.07x slower                                                  |
| nqueens                          | 58.3 ms                                                            | 63.0 ms: 1.08x slower                                                  |
| django_template                  | 28.8 ms                                                            | 31.1 ms: 1.08x slower                                                  |
| raytrace                         | 197 ms                                                             | 214 ms: 1.09x slower                                                   |
| thread_pipeline_optimized        | 22.8 ms                                                            | 24.8 ms: 1.09x slower                                                  |
| thread_accumulate_optimized      | 35.3 ms                                                            | 38.6 ms: 1.09x slower                                                  |
| chaos                            | 43.6 ms                                                            | 47.7 ms: 1.09x slower                                                  |
| pickle                           | 7.21 us                                                            | 8.01 us: 1.11x slower                                                  |
| pickle_list                      | 2.66 us                                                            | 3.00 us: 1.13x slower                                                  |
| sympy_expand                     | 331 ms                                                             | 376 ms: 1.13x slower                                                   |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.8 ms: 1.14x slower                                                  |
| create_gc_cycles                 | 1.77 ms                                                            | 2.02 ms: 1.14x slower                                                  |
| sympy_integrate                  | 15.4 ms                                                            | 17.7 ms: 1.15x slower                                                  |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 49.8 ms: 1.18x slower                                                  |
| pylint                           | 226 ms                                                             | 272 ms: 1.20x slower                                                   |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 101 ms: 1.21x slower                                                   |
| sympy_sum                        | 104 ms                                                             | 127 ms: 1.22x slower                                                   |
| mypy2                            | 741 ms                                                             | 918 ms: 1.24x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 373 ms: 1.24x slower                                                   |
| sympy_str                        | 193 ms                                                             | 247 ms: 1.28x slower                                                   |
| argparse_subparsers              | 449 us                                                             | 728 us: 1.62x slower                                                   |
| unpack_sequence                  | 26.4 ns                                                            | 54.2 ns: 2.05x slower                                                  |
| argparse_many_optionals          | 12.9 ms                                                            | 36.0 ms: 2.78x slower                                                  |
| async_tree_eager_tg              | 56.8 ms                                                            | 172 ms: 3.02x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.11x faster                                                           |

Benchmark hidden because not significant (5): chameleon, fastapi_http, pidigits, thread_memo_optimized, asyncio_websockets
Ignored benchmarks (6) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json: async_tree_eager_memoization_tg, docutils, networkx_connected_components, networkx_k_core, networkx_shortest_path, quadtree_nbody

- Geometric mean (including insignificant results): 1.113x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.06x
- 95% likely to have a speedup of 1.05x
- 99% likely to have a speedup of 1.03x

# Memory
- memory change: 1.11x