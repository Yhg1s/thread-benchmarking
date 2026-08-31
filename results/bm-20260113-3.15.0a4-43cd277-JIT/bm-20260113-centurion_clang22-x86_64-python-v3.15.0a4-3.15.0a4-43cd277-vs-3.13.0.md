# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.148x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.04x faster
- Memory change: 1.17x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 10.6 ms: 1.05x faster                                                  |
| docutils       | 1.89 sec                                                           | 2.09 sec: 1.11x slower                                                 |
| fastapi_http   | 215 ms                                                             | 212 ms: 1.01x faster                                                   |
| html5lib       | 50.9 ms                                                            | 44.6 ms: 1.14x faster                                                  |
| tornado_http   | 98.9 ms                                                            | 102 ms: 1.03x slower                                                   |
| Geometric mean | (ref)                                                              | 1.01x faster                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 259 ms: 1.62x faster                                                   |
| async_tree_io_tg                 | 781 ms                                                             | 496 ms: 1.57x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 488 ms: 1.54x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 260 ms: 1.51x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 498 ms: 1.49x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 212 ms: 1.48x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 496 ms: 1.47x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 213 ms: 1.36x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 175 ms: 1.26x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 405 ms: 1.25x faster                                                   |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 399 ms: 1.24x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 15.5 ms: 1.17x faster                                                  |
| asyncio_tcp                      | 316 ms                                                             | 280 ms: 1.13x faster                                                   |
| async_tree_eager                 | 88.3 ms                                                            | 79.9 ms: 1.11x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 324 ms: 1.06x faster                                                   |
| async_generators                 | 251 ms                                                             | 239 ms: 1.05x faster                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.01x faster                                                 |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 382 ms: 1.27x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 235 ms: 1.35x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 172 ms: 3.02x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.14x faster                                                           |

Benchmark hidden because not significant (1): asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 16.8 ns: 1.28x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 203 ms: 1.12x faster                                                   |
| decimal_factorial | 177 ms                                                             | 173 ms: 1.02x faster                                                   |
| Geometric mean    | (ref)                                                              | 1.07x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 38.5 ms: 1.54x faster                                                  |
| nbody          | 75.8 ms                                                            | 49.3 ms: 1.54x faster                                                  |
| quadtree_nbody | 675 ms                                                             | 549 ms: 1.23x faster                                                   |
| pidigits       | 216 ms                                                             | 215 ms: 1.00x faster                                                   |
| Geometric mean | (ref)                                                              | 1.31x faster                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_compile  | 102 ms                                                             | 87.8 ms: 1.17x faster                                                  |
| regex_effbot   | 2.33 ms                                                            | 2.07 ms: 1.13x faster                                                  |
| regex_dna      | 159 ms                                                             | 144 ms: 1.10x faster                                                   |
| regex_v8       | 15.0 ms                                                            | 14.4 ms: 1.04x faster                                                  |
| Geometric mean | (ref)                                                              | 1.11x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.11 ms: 6.98x faster                                                  |
| base16_small         | 836 us                                                             | 213 us: 3.93x faster                                                   |
| ascii85_large        | 824 ms                                                             | 550 ms: 1.50x faster                                                   |
| ascii85_small        | 15.7 ms                                                            | 10.8 ms: 1.46x faster                                                  |
| unpickle_pure_python | 161 us                                                             | 119 us: 1.35x faster                                                   |
| urlsafe_base64_small | 328 us                                                             | 256 us: 1.28x faster                                                   |
| json_dumps           | 7.26 ms                                                            | 5.86 ms: 1.24x faster                                                  |
| base64_small         | 222 us                                                             | 181 us: 1.22x faster                                                   |
| xml_etree_generate   | 70.6 ms                                                            | 58.8 ms: 1.20x faster                                                  |
| xml_etree_iterparse  | 86.8 ms                                                            | 73.6 ms: 1.18x faster                                                  |
| xml_etree_process    | 49.9 ms                                                            | 42.5 ms: 1.17x faster                                                  |
| unpickle_list        | 3.42 us                                                            | 2.93 us: 1.17x faster                                                  |
| base32_small         | 6.46 ms                                                            | 5.65 ms: 1.14x faster                                                  |
| pickle_pure_python   | 245 us                                                             | 216 us: 1.14x faster                                                   |
| base85_large         | 267 ms                                                             | 236 ms: 1.13x faster                                                   |
| base32_large         | 325 ms                                                             | 289 ms: 1.13x faster                                                   |
| base85_small         | 4.85 ms                                                            | 4.32 ms: 1.12x faster                                                  |
| tomli_loads          | 1.77 sec                                                           | 1.63 sec: 1.08x faster                                                 |
| xml_etree_parse      | 121 ms                                                             | 113 ms: 1.06x faster                                                   |
| unpickle             | 10.8 us                                                            | 10.2 us: 1.06x faster                                                  |
| json_loads           | 18.2 us                                                            | 17.5 us: 1.04x faster                                                  |
| pickle_dict          | 19.0 us                                                            | 19.2 us: 1.01x slower                                                  |
| base64_large         | 5.69 ms                                                            | 5.74 ms: 1.01x slower                                                  |
| pickle_list          | 2.66 us                                                            | 2.92 us: 1.10x slower                                                  |
| pickle               | 7.21 us                                                            | 7.98 us: 1.11x slower                                                  |
| Geometric mean       | (ref)                                                              | 1.29x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.37 ms: 1.02x faster                                                  |
| python_startup         | 9.51 ms                                                            | 9.64 ms: 1.01x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.00x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 17.0 ms: 1.24x faster                                                  |
| mako            | 8.30 ms                                                            | 7.28 ms: 1.14x faster                                                  |
| genshi_xml      | 46.3 ms                                                            | 47.1 ms: 1.02x slower                                                  |
| django_template | 28.8 ms                                                            | 30.5 ms: 1.06x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.07x faster                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 8.81 ms: 4.30x faster                                                  |
| thread_pipeline_naive       | 49.8 ms                                                            | 31.5 ms: 1.58x faster                                                  |
| thread_montecarlo_naive     | 18.1 ms                                                            | 14.9 ms: 1.22x faster                                                  |
| thread_counter_naive        | 23.7 ms                                                            | 20.5 ms: 1.16x faster                                                  |
| thread_mandelbrot_naive     | 190 ms                                                             | 173 ms: 1.09x faster                                                   |
| thread_mandelbrot_optimized | 189 ms                                                             | 174 ms: 1.09x faster                                                   |
| thread_counter_optimized    | 19.7 ms                                                            | 18.9 ms: 1.05x faster                                                  |
| thread_montecarlo_optimized | 14.2 ms                                                            | 13.9 ms: 1.02x faster                                                  |
| thread_memo_optimized       | 16.8 ms                                                            | 16.6 ms: 1.01x faster                                                  |
| thread_accumulate_naive     | 36.5 ms                                                            | 38.3 ms: 1.05x slower                                                  |
| thread_pipeline_optimized   | 22.8 ms                                                            | 24.5 ms: 1.08x slower                                                  |
| thread_accumulate_optimized | 35.3 ms                                                            | 38.0 ms: 1.08x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.21x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.11 ms: 6.98x faster                                                  |
| thread_memo_naive                | 37.9 ms                                                            | 8.81 ms: 4.30x faster                                                  |
| base16_small                     | 836 us                                                             | 213 us: 3.93x faster                                                   |
| richards                         | 38.2 ms                                                            | 15.8 ms: 2.41x faster                                                  |
| richards_super                   | 43.8 ms                                                            | 19.4 ms: 2.25x faster                                                  |
| mdp                              | 2.05 sec                                                           | 1.13 sec: 1.81x faster                                                 |
| go                               | 129 ms                                                             | 73.4 ms: 1.76x faster                                                  |
| deepcopy_memo                    | 27.8 us                                                            | 16.1 us: 1.72x faster                                                  |
| async_tree_memoization_tg        | 421 ms                                                             | 259 ms: 1.62x faster                                                   |
| argparse_many_optionals          | 12.9 ms                                                            | 8.17 ms: 1.58x faster                                                  |
| thread_pipeline_naive            | 49.8 ms                                                            | 31.5 ms: 1.58x faster                                                  |
| async_tree_io_tg                 | 781 ms                                                             | 496 ms: 1.57x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 488 ms: 1.54x faster                                                   |
| float                            | 59.2 ms                                                            | 38.5 ms: 1.54x faster                                                  |
| nbody                            | 75.8 ms                                                            | 49.3 ms: 1.54x faster                                                  |
| async_tree_memoization           | 392 ms                                                             | 260 ms: 1.51x faster                                                   |
| ascii85_large                    | 824 ms                                                             | 550 ms: 1.50x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 498 ms: 1.49x faster                                                   |
| pyflate                          | 374 ms                                                             | 253 ms: 1.48x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 212 ms: 1.48x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 496 ms: 1.47x faster                                                   |
| ascii85_small                    | 15.7 ms                                                            | 10.8 ms: 1.46x faster                                                  |
| scimark_monte_carlo              | 47.2 ms                                                            | 32.4 ms: 1.46x faster                                                  |
| scimark_sor                      | 96.2 ms                                                            | 66.9 ms: 1.44x faster                                                  |
| fannkuch                         | 287 ms                                                             | 211 ms: 1.36x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 213 ms: 1.36x faster                                                   |
| unpickle_pure_python             | 161 us                                                             | 119 us: 1.35x faster                                                   |
| scimark_fft                      | 216 ms                                                             | 161 ms: 1.35x faster                                                   |
| urlsafe_base64_small             | 328 us                                                             | 256 us: 1.28x faster                                                   |
| noop                             | 21.4 ns                                                            | 16.8 ns: 1.28x faster                                                  |
| logging_silent                   | 60.1 ns                                                            | 47.5 ns: 1.27x faster                                                  |
| async_tree_eager_memoization     | 221 ms                                                             | 175 ms: 1.26x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 405 ms: 1.25x faster                                                   |
| deltablue                        | 2.59 ms                                                            | 2.08 ms: 1.24x faster                                                  |
| genshi_text                      | 21.1 ms                                                            | 17.0 ms: 1.24x faster                                                  |
| json_dumps                       | 7.26 ms                                                            | 5.86 ms: 1.24x faster                                                  |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 399 ms: 1.24x faster                                                   |
| quadtree_nbody                   | 675 ms                                                             | 549 ms: 1.23x faster                                                   |
| spectral_norm                    | 68.6 ms                                                            | 55.8 ms: 1.23x faster                                                  |
| deepcopy                         | 267 us                                                             | 218 us: 1.22x faster                                                   |
| base64_small                     | 222 us                                                             | 181 us: 1.22x faster                                                   |
| thread_montecarlo_naive          | 18.1 ms                                                            | 14.9 ms: 1.22x faster                                                  |
| xml_etree_generate               | 70.6 ms                                                            | 58.8 ms: 1.20x faster                                                  |
| bpe_tokeniser                    | 3.37 sec                                                           | 2.86 sec: 1.18x faster                                                 |
| xml_etree_iterparse              | 86.8 ms                                                            | 73.6 ms: 1.18x faster                                                  |
| telco                            | 5.37 ms                                                            | 4.56 ms: 1.18x faster                                                  |
| xml_etree_process                | 49.9 ms                                                            | 42.5 ms: 1.17x faster                                                  |
| coroutines                       | 18.2 ms                                                            | 15.5 ms: 1.17x faster                                                  |
| unpickle_list                    | 3.42 us                                                            | 2.93 us: 1.17x faster                                                  |
| regex_compile                    | 102 ms                                                             | 87.8 ms: 1.17x faster                                                  |
| thread_counter_naive             | 23.7 ms                                                            | 20.5 ms: 1.16x faster                                                  |
| base32_small                     | 6.46 ms                                                            | 5.65 ms: 1.14x faster                                                  |
| html5lib                         | 50.9 ms                                                            | 44.6 ms: 1.14x faster                                                  |
| mako                             | 8.30 ms                                                            | 7.28 ms: 1.14x faster                                                  |
| pickle_pure_python               | 245 us                                                             | 216 us: 1.14x faster                                                   |
| base85_large                     | 267 ms                                                             | 236 ms: 1.13x faster                                                   |
| pathlib                          | 12.2 ms                                                            | 10.8 ms: 1.13x faster                                                  |
| asyncio_tcp                      | 316 ms                                                             | 280 ms: 1.13x faster                                                   |
| base32_large                     | 325 ms                                                             | 289 ms: 1.13x faster                                                   |
| regex_effbot                     | 2.33 ms                                                            | 2.07 ms: 1.13x faster                                                  |
| decimal_pi                       | 228 ms                                                             | 203 ms: 1.12x faster                                                   |
| base85_small                     | 4.85 ms                                                            | 4.32 ms: 1.12x faster                                                  |
| crypto_pyaes                     | 55.6 ms                                                            | 50.3 ms: 1.11x faster                                                  |
| async_tree_eager                 | 88.3 ms                                                            | 79.9 ms: 1.11x faster                                                  |
| networkx_k_core                  | 2.16 sec                                                           | 1.96 sec: 1.10x faster                                                 |
| scimark_lu                       | 70.2 ms                                                            | 63.8 ms: 1.10x faster                                                  |
| regex_dna                        | 159 ms                                                             | 144 ms: 1.10x faster                                                   |
| thread_mandelbrot_naive          | 190 ms                                                             | 173 ms: 1.09x faster                                                   |
| json                             | 3.50 ms                                                            | 3.21 ms: 1.09x faster                                                  |
| thread_mandelbrot_optimized      | 189 ms                                                             | 174 ms: 1.09x faster                                                   |
| tomli_loads                      | 1.77 sec                                                           | 1.63 sec: 1.08x faster                                                 |
| thrift                           | 2.07 ms                                                            | 1.91 ms: 1.08x faster                                                  |
| meteor_contest                   | 85.7 ms                                                            | 79.5 ms: 1.08x faster                                                  |
| comprehensions                   | 11.4 us                                                            | 10.7 us: 1.07x faster                                                  |
| xml_etree_parse                  | 121 ms                                                             | 113 ms: 1.06x faster                                                   |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 324 ms: 1.06x faster                                                   |
| unpickle                         | 10.8 us                                                            | 10.2 us: 1.06x faster                                                  |
| async_generators                 | 251 ms                                                             | 239 ms: 1.05x faster                                                   |
| sqlglot_v2_parse                 | 979 us                                                             | 933 us: 1.05x faster                                                   |
| chameleon                        | 11.1 ms                                                            | 10.6 ms: 1.05x faster                                                  |
| thread_counter_optimized         | 19.7 ms                                                            | 18.9 ms: 1.05x faster                                                  |
| json_loads                       | 18.2 us                                                            | 17.5 us: 1.04x faster                                                  |
| chaos                            | 43.6 ms                                                            | 41.8 ms: 1.04x faster                                                  |
| regex_v8                         | 15.0 ms                                                            | 14.4 ms: 1.04x faster                                                  |
| logging_simple                   | 5.06 us                                                            | 4.87 us: 1.04x faster                                                  |
| logging_format                   | 5.62 us                                                            | 5.45 us: 1.03x faster                                                  |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.77 ms: 1.03x faster                                                  |
| deepcopy_reduce                  | 2.36 us                                                            | 2.29 us: 1.03x faster                                                  |
| hexiom                           | 4.75 ms                                                            | 4.65 ms: 1.02x faster                                                  |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 13.9 ms: 1.02x faster                                                  |
| decimal_factorial                | 177 ms                                                             | 173 ms: 1.02x faster                                                   |
| python_startup_no_site           | 6.49 ms                                                            | 6.37 ms: 1.02x faster                                                  |
| fastapi_http                     | 215 ms                                                             | 212 ms: 1.01x faster                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.01x faster                                                 |
| thread_memo_optimized            | 16.8 ms                                                            | 16.6 ms: 1.01x faster                                                  |
| raytrace                         | 197 ms                                                             | 195 ms: 1.01x faster                                                   |
| nqueens                          | 58.3 ms                                                            | 58.0 ms: 1.01x faster                                                  |
| networkx_shortest_path           | 454 ms                                                             | 451 ms: 1.01x faster                                                   |
| networkx_connected_components    | 443 ms                                                             | 440 ms: 1.00x faster                                                   |
| pidigits                         | 216 ms                                                             | 215 ms: 1.00x faster                                                   |
| pickle_dict                      | 19.0 us                                                            | 19.2 us: 1.01x slower                                                  |
| base64_large                     | 5.69 ms                                                            | 5.74 ms: 1.01x slower                                                  |
| coverage                         | 55.0 ms                                                            | 55.6 ms: 1.01x slower                                                  |
| python_startup                   | 9.51 ms                                                            | 9.64 ms: 1.01x slower                                                  |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.24 ms: 1.01x slower                                                  |
| pycparser                        | 901 ms                                                             | 915 ms: 1.02x slower                                                   |
| genshi_xml                       | 46.3 ms                                                            | 47.1 ms: 1.02x slower                                                  |
| tornado_http                     | 98.9 ms                                                            | 102 ms: 1.03x slower                                                   |
| xdsl_constant_fold               | 36.4 ms                                                            | 37.7 ms: 1.04x slower                                                  |
| gc_traversal                     | 3.20 ms                                                            | 3.36 ms: 1.05x slower                                                  |
| thread_accumulate_naive          | 36.5 ms                                                            | 38.3 ms: 1.05x slower                                                  |
| django_template                  | 28.8 ms                                                            | 30.5 ms: 1.06x slower                                                  |
| typing_runtime_protocols         | 112 us                                                             | 120 us: 1.07x slower                                                   |
| thread_pipeline_optimized        | 22.8 ms                                                            | 24.5 ms: 1.08x slower                                                  |
| thread_accumulate_optimized      | 35.3 ms                                                            | 38.0 ms: 1.08x slower                                                  |
| generators                       | 22.2 ms                                                            | 24.3 ms: 1.09x slower                                                  |
| pickle_list                      | 2.66 us                                                            | 2.92 us: 1.10x slower                                                  |
| pickle                           | 7.21 us                                                            | 7.98 us: 1.11x slower                                                  |
| docutils                         | 1.89 sec                                                           | 2.09 sec: 1.11x slower                                                 |
| sympy_integrate                  | 15.4 ms                                                            | 17.2 ms: 1.12x slower                                                  |
| argparse_subparsers              | 449 us                                                             | 505 us: 1.12x slower                                                   |
| sympy_expand                     | 331 ms                                                             | 373 ms: 1.12x slower                                                   |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.6 ms: 1.13x slower                                                  |
| create_gc_cycles                 | 1.77 ms                                                            | 2.02 ms: 1.14x slower                                                  |
| sympy_sum                        | 104 ms                                                             | 124 ms: 1.19x slower                                                   |
| pylint                           | 226 ms                                                             | 271 ms: 1.20x slower                                                   |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 50.4 ms: 1.20x slower                                                  |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 102 ms: 1.22x slower                                                   |
| mypy2                            | 741 ms                                                             | 911 ms: 1.23x slower                                                   |
| sympy_str                        | 193 ms                                                             | 239 ms: 1.24x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 382 ms: 1.27x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 235 ms: 1.35x slower                                                   |
| unpack_sequence                  | 26.4 ns                                                            | 64.4 ns: 2.44x slower                                                  |
| async_tree_eager_tg              | 56.8 ms                                                            | 172 ms: 3.02x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.14x faster                                                           |

Benchmark hidden because not significant (3): pprint_safe_repr, pprint_pformat, asyncio_websockets

- Geometric mean (including insignificant results): 1.148x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.07x
- 95% likely to have a speedup of 1.06x
- 99% likely to have a speedup of 1.04x

# Memory
- memory change: 1.17x