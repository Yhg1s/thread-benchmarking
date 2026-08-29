# Results vs. 3.13.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.296x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.03x faster
- Memory change: 1.03x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 11.0 ms: 1.00x slower                                                  |
| docutils       | 1.98 sec                                                         | 1.89 sec: 1.05x faster                                                 |
| fastapi_http   | 215 ms                                                           | 212 ms: 1.01x faster                                                   |
| html5lib       | 49.1 ms                                                          | 46.5 ms: 1.06x faster                                                  |
| tornado_http   | 99.2 ms                                                          | 97.7 ms: 1.02x faster                                                  |
| Geometric mean | (ref)                                                            | 1.03x faster                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_memoization_tg        | 417 ms                                                           | 323 ms: 1.29x faster                                                   |
| async_tree_none                  | 310 ms                                                           | 249 ms: 1.25x faster                                                   |
| async_tree_memoization           | 389 ms                                                           | 324 ms: 1.20x faster                                                   |
| async_tree_eager_io              | 749 ms                                                           | 629 ms: 1.19x faster                                                   |
| async_tree_eager_memoization     | 215 ms                                                           | 180 ms: 1.19x faster                                                   |
| async_tree_io                    | 741 ms                                                           | 632 ms: 1.17x faster                                                   |
| async_tree_io_tg                 | 777 ms                                                           | 668 ms: 1.16x faster                                                   |
| async_tree_eager                 | 90.0 ms                                                          | 78.9 ms: 1.14x faster                                                  |
| coroutines                       | 17.6 ms                                                          | 15.5 ms: 1.13x faster                                                  |
| async_tree_none_tg               | 289 ms                                                           | 256 ms: 1.13x faster                                                   |
| asyncio_tcp                      | 326 ms                                                           | 291 ms: 1.12x faster                                                   |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 460 ms: 1.12x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 481 ms: 1.10x faster                                                   |
| async_tree_eager_io_tg           | 724 ms                                                           | 668 ms: 1.08x faster                                                   |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 337 ms: 1.07x faster                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.26 sec: 1.02x faster                                                 |
| asyncio_websockets               | 304 ms                                                           | 310 ms: 1.02x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 419 ms: 1.30x slower                                                   |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 279 ms: 1.61x slower                                                   |
| async_tree_eager_tg              | 58.6 ms                                                          | 205 ms: 3.50x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.01x faster                                                           |

Benchmark hidden because not significant (1): async_generators

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 19.0 ns: 1.07x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 202 ms: 1.04x faster                                                   |
| decimal_factorial | 173 ms                                                           | 172 ms: 1.00x faster                                                   |
| Geometric mean    | (ref)                                                            | 1.02x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 51.9 ms: 1.09x faster                                                  |
| quadtree_nbody | 620 ms                                                           | 573 ms: 1.08x faster                                                   |
| pidigits       | 181 ms                                                           | 182 ms: 1.00x slower                                                   |
| Geometric mean | (ref)                                                            | 1.04x faster                                                           |

Benchmark hidden because not significant (1): nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.81 ms: 1.10x faster                                                  |
| regex_compile  | 97.7 ms                                                          | 92.2 ms: 1.06x faster                                                  |
| regex_dna      | 144 ms                                                           | 145 ms: 1.01x slower                                                   |
| regex_v8       | 14.7 ms                                                          | 15.2 ms: 1.03x slower                                                  |
| Geometric mean | (ref)                                                            | 1.03x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 286 ms                                                           | 2.09 ms: 136.68x faster                                                |
| ascii85_large        | 814 ms                                                           | 10.2 ms: 80.17x faster                                                 |
| base85_large         | 243 ms                                                           | 3.31 ms: 73.42x faster                                                 |
| ascii85_small        | 15.5 ms                                                          | 519 us: 29.84x faster                                                  |
| base32_small         | 5.69 ms                                                          | 229 us: 24.87x faster                                                  |
| base85_small         | 4.41 ms                                                          | 200 us: 22.00x faster                                                  |
| base16_large         | 31.6 ms                                                          | 7.09 ms: 4.45x faster                                                  |
| base64_large         | 6.32 ms                                                          | 1.55 ms: 4.09x faster                                                  |
| base16_small         | 656 us                                                           | 427 us: 1.54x faster                                                   |
| urlsafe_base64_small | 379 us                                                           | 271 us: 1.39x faster                                                   |
| tomli_loads          | 1.63 sec                                                         | 1.33 sec: 1.23x faster                                                 |
| json_dumps           | 7.49 ms                                                          | 6.57 ms: 1.14x faster                                                  |
| xml_etree_parse      | 107 ms                                                           | 107 ms: 1.01x faster                                                   |
| unpickle             | 10.3 us                                                          | 10.5 us: 1.02x slower                                                  |
| xml_etree_process    | 48.1 ms                                                          | 49.4 ms: 1.03x slower                                                  |
| unpickle_pure_python | 149 us                                                           | 153 us: 1.03x slower                                                   |
| base64_small         | 228 us                                                           | 236 us: 1.03x slower                                                   |
| pickle_dict          | 21.9 us                                                          | 22.6 us: 1.03x slower                                                  |
| pickle_pure_python   | 223 us                                                           | 231 us: 1.04x slower                                                   |
| unpickle_list        | 3.45 us                                                          | 3.58 us: 1.04x slower                                                  |
| xml_etree_generate   | 66.3 ms                                                          | 70.2 ms: 1.06x slower                                                  |
| json_loads           | 16.7 us                                                          | 17.7 us: 1.06x slower                                                  |
| xml_etree_iterparse  | 69.6 ms                                                          | 75.5 ms: 1.08x slower                                                  |
| pickle               | 8.22 us                                                          | 9.43 us: 1.15x slower                                                  |
| pickle_list          | 3.03 us                                                          | 3.71 us: 1.22x slower                                                  |
| Geometric mean       | (ref)                                                            | 2.89x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 5.85 ms: 1.09x faster                                                  |
| python_startup         | 9.38 ms                                                          | 9.44 ms: 1.01x slower                                                  |
| Geometric mean         | (ref)                                                            | 1.04x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 27.3 ms                                                          | 29.2 ms: 1.07x slower                                                  |
| mako            | 7.43 ms                                                          | 8.55 ms: 1.15x slower                                                  |
| Geometric mean  | (ref)                                                            | 1.11x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 9.84 ms: 3.96x faster                                                  |
| thread_pipeline_naive       | 52.1 ms                                                          | 37.2 ms: 1.40x faster                                                  |
| thread_montecarlo_naive     | 17.8 ms                                                          | 15.4 ms: 1.16x faster                                                  |
| thread_mandelbrot_naive     | 220 ms                                                           | 206 ms: 1.07x faster                                                   |
| thread_mandelbrot_optimized | 218 ms                                                           | 206 ms: 1.06x faster                                                   |
| thread_montecarlo_optimized | 13.3 ms                                                          | 13.3 ms: 1.00x faster                                                  |
| thread_counter_naive        | 22.6 ms                                                          | 23.0 ms: 1.02x slower                                                  |
| thread_memo_optimized       | 18.2 ms                                                          | 19.3 ms: 1.06x slower                                                  |
| thread_accumulate_naive     | 40.9 ms                                                          | 45.4 ms: 1.11x slower                                                  |
| thread_counter_optimized    | 18.7 ms                                                          | 21.1 ms: 1.13x slower                                                  |
| thread_pipeline_optimized   | 25.6 ms                                                          | 29.0 ms: 1.13x slower                                                  |
| thread_accumulate_optimized | 39.8 ms                                                          | 45.2 ms: 1.14x slower                                                  |
| Geometric mean              | (ref)                                                            | 1.13x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 286 ms                                                           | 2.09 ms: 136.68x faster                                                |
| ascii85_large                    | 814 ms                                                           | 10.2 ms: 80.17x faster                                                 |
| base85_large                     | 243 ms                                                           | 3.31 ms: 73.42x faster                                                 |
| ascii85_small                    | 15.5 ms                                                          | 519 us: 29.84x faster                                                  |
| base32_small                     | 5.69 ms                                                          | 229 us: 24.87x faster                                                  |
| base85_small                     | 4.41 ms                                                          | 200 us: 22.00x faster                                                  |
| base16_large                     | 31.6 ms                                                          | 7.09 ms: 4.45x faster                                                  |
| base64_large                     | 6.32 ms                                                          | 1.55 ms: 4.09x faster                                                  |
| thread_memo_naive                | 39.0 ms                                                          | 9.84 ms: 3.96x faster                                                  |
| pylint                           | 226 ms                                                           | 97.8 ms: 2.31x faster                                                  |
| mdp                              | 2.11 sec                                                         | 916 ms: 2.30x faster                                                   |
| argparse_many_optionals          | 12.6 ms                                                          | 7.57 ms: 1.66x faster                                                  |
| deepcopy_memo                    | 26.6 us                                                          | 17.1 us: 1.56x faster                                                  |
| base16_small                     | 656 us                                                           | 427 us: 1.54x faster                                                   |
| deepcopy                         | 267 us                                                           | 178 us: 1.50x faster                                                   |
| go                               | 121 ms                                                           | 82.0 ms: 1.48x faster                                                  |
| thread_pipeline_naive            | 52.1 ms                                                          | 37.2 ms: 1.40x faster                                                  |
| urlsafe_base64_small             | 379 us                                                           | 271 us: 1.39x faster                                                   |
| scimark_sor                      | 97.0 ms                                                          | 71.8 ms: 1.35x faster                                                  |
| async_tree_memoization_tg        | 417 ms                                                           | 323 ms: 1.29x faster                                                   |
| async_tree_none                  | 310 ms                                                           | 249 ms: 1.25x faster                                                   |
| tomli_loads                      | 1.63 sec                                                         | 1.33 sec: 1.23x faster                                                 |
| pyflate                          | 358 ms                                                           | 293 ms: 1.22x faster                                                   |
| async_tree_memoization           | 389 ms                                                           | 324 ms: 1.20x faster                                                   |
| async_tree_eager_io              | 749 ms                                                           | 629 ms: 1.19x faster                                                   |
| async_tree_eager_memoization     | 215 ms                                                           | 180 ms: 1.19x faster                                                   |
| pathlib                          | 12.4 ms                                                          | 10.6 ms: 1.18x faster                                                  |
| async_tree_io                    | 741 ms                                                           | 632 ms: 1.17x faster                                                   |
| deepcopy_reduce                  | 2.37 us                                                          | 2.04 us: 1.17x faster                                                  |
| scimark_monte_carlo              | 44.3 ms                                                          | 38.0 ms: 1.16x faster                                                  |
| async_tree_io_tg                 | 777 ms                                                           | 668 ms: 1.16x faster                                                   |
| fannkuch                         | 265 ms                                                           | 228 ms: 1.16x faster                                                   |
| thread_montecarlo_naive          | 17.8 ms                                                          | 15.4 ms: 1.16x faster                                                  |
| async_tree_eager                 | 90.0 ms                                                          | 78.9 ms: 1.14x faster                                                  |
| json_dumps                       | 7.49 ms                                                          | 6.57 ms: 1.14x faster                                                  |
| hexiom                           | 4.42 ms                                                          | 3.90 ms: 1.13x faster                                                  |
| coroutines                       | 17.6 ms                                                          | 15.5 ms: 1.13x faster                                                  |
| async_tree_none_tg               | 289 ms                                                           | 256 ms: 1.13x faster                                                   |
| chaos                            | 45.0 ms                                                          | 39.9 ms: 1.13x faster                                                  |
| sqlglot_v2_parse                 | 953 us                                                           | 848 us: 1.12x faster                                                   |
| asyncio_tcp                      | 326 ms                                                           | 291 ms: 1.12x faster                                                   |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 460 ms: 1.12x faster                                                   |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.08 ms: 1.11x faster                                                  |
| richards_super                   | 41.3 ms                                                          | 37.2 ms: 1.11x faster                                                  |
| thrift                           | 2.07 ms                                                          | 1.87 ms: 1.11x faster                                                  |
| richards                         | 36.8 ms                                                          | 33.4 ms: 1.10x faster                                                  |
| deltablue                        | 2.52 ms                                                          | 2.29 ms: 1.10x faster                                                  |
| regex_effbot                     | 1.99 ms                                                          | 1.81 ms: 1.10x faster                                                  |
| spectral_norm                    | 64.1 ms                                                          | 58.3 ms: 1.10x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 481 ms: 1.10x faster                                                   |
| float                            | 56.6 ms                                                          | 51.9 ms: 1.09x faster                                                  |
| pprint_pformat                   | 1.11 sec                                                         | 1.02 sec: 1.09x faster                                                 |
| scimark_fft                      | 211 ms                                                           | 193 ms: 1.09x faster                                                   |
| pprint_safe_repr                 | 541 ms                                                           | 498 ms: 1.09x faster                                                   |
| python_startup_no_site           | 6.36 ms                                                          | 5.85 ms: 1.09x faster                                                  |
| async_tree_eager_io_tg           | 724 ms                                                           | 668 ms: 1.08x faster                                                   |
| quadtree_nbody                   | 620 ms                                                           | 573 ms: 1.08x faster                                                   |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.15 sec: 1.08x faster                                                 |
| gc_traversal                     | 3.16 ms                                                          | 2.94 ms: 1.07x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 337 ms: 1.07x faster                                                   |
| noop                             | 20.4 ns                                                          | 19.0 ns: 1.07x faster                                                  |
| thread_mandelbrot_naive          | 220 ms                                                           | 206 ms: 1.07x faster                                                   |
| nqueens                          | 57.3 ms                                                          | 53.7 ms: 1.07x faster                                                  |
| telco                            | 5.50 ms                                                          | 5.17 ms: 1.06x faster                                                  |
| comprehensions                   | 11.6 us                                                          | 10.9 us: 1.06x faster                                                  |
| regex_compile                    | 97.7 ms                                                          | 92.2 ms: 1.06x faster                                                  |
| meteor_contest                   | 89.9 ms                                                          | 84.9 ms: 1.06x faster                                                  |
| thread_mandelbrot_optimized      | 218 ms                                                           | 206 ms: 1.06x faster                                                   |
| html5lib                         | 49.1 ms                                                          | 46.5 ms: 1.06x faster                                                  |
| create_gc_cycles                 | 1.70 ms                                                          | 1.62 ms: 1.05x faster                                                  |
| raytrace                         | 199 ms                                                           | 189 ms: 1.05x faster                                                   |
| docutils                         | 1.98 sec                                                         | 1.89 sec: 1.05x faster                                                 |
| sympy_integrate                  | 15.4 ms                                                          | 14.8 ms: 1.05x faster                                                  |
| decimal_pi                       | 210 ms                                                           | 202 ms: 1.04x faster                                                   |
| unpack_sequence                  | 26.2 ns                                                          | 25.3 ns: 1.04x faster                                                  |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 38.7 ms: 1.03x faster                                                  |
| scimark_lu                       | 70.2 ms                                                          | 67.9 ms: 1.03x faster                                                  |
| logging_simple                   | 4.60 us                                                          | 4.46 us: 1.03x faster                                                  |
| networkx_shortest_path           | 464 ms                                                           | 452 ms: 1.03x faster                                                   |
| logging_format                   | 5.23 us                                                          | 5.10 us: 1.03x faster                                                  |
| networkx_connected_components    | 460 ms                                                           | 448 ms: 1.03x faster                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.26 sec: 1.02x faster                                                 |
| pycparser                        | 884 ms                                                           | 863 ms: 1.02x faster                                                   |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.61 ms: 1.02x faster                                                  |
| tornado_http                     | 99.2 ms                                                          | 97.7 ms: 1.02x faster                                                  |
| fastapi_http                     | 215 ms                                                           | 212 ms: 1.01x faster                                                   |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 78.2 ms: 1.01x faster                                                  |
| xml_etree_parse                  | 107 ms                                                           | 107 ms: 1.01x faster                                                   |
| decimal_factorial                | 173 ms                                                           | 172 ms: 1.00x faster                                                   |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 13.3 ms: 1.00x faster                                                  |
| sympy_str                        | 193 ms                                                           | 193 ms: 1.00x faster                                                   |
| pidigits                         | 181 ms                                                           | 182 ms: 1.00x slower                                                   |
| chameleon                        | 10.9 ms                                                          | 11.0 ms: 1.00x slower                                                  |
| argparse_subparsers              | 446 us                                                           | 448 us: 1.00x slower                                                   |
| python_startup                   | 9.38 ms                                                          | 9.44 ms: 1.01x slower                                                  |
| sympy_expand                     | 330 ms                                                           | 333 ms: 1.01x slower                                                   |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                                   |
| regex_dna                        | 144 ms                                                           | 145 ms: 1.01x slower                                                   |
| thread_counter_naive             | 22.6 ms                                                          | 23.0 ms: 1.02x slower                                                  |
| unpickle                         | 10.3 us                                                          | 10.5 us: 1.02x slower                                                  |
| asyncio_websockets               | 304 ms                                                           | 310 ms: 1.02x slower                                                   |
| typing_runtime_protocols         | 106 us                                                           | 108 us: 1.02x slower                                                   |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.2 ms: 1.03x slower                                                  |
| xml_etree_process                | 48.1 ms                                                          | 49.4 ms: 1.03x slower                                                  |
| unpickle_pure_python             | 149 us                                                           | 153 us: 1.03x slower                                                   |
| base64_small                     | 228 us                                                           | 236 us: 1.03x slower                                                   |
| regex_v8                         | 14.7 ms                                                          | 15.2 ms: 1.03x slower                                                  |
| pickle_dict                      | 21.9 us                                                          | 22.6 us: 1.03x slower                                                  |
| pickle_pure_python               | 223 us                                                           | 231 us: 1.04x slower                                                   |
| unpickle_list                    | 3.45 us                                                          | 3.58 us: 1.04x slower                                                  |
| coverage                         | 52.2 ms                                                          | 55.0 ms: 1.05x slower                                                  |
| crypto_pyaes                     | 50.0 ms                                                          | 52.8 ms: 1.06x slower                                                  |
| thread_memo_optimized            | 18.2 ms                                                          | 19.3 ms: 1.06x slower                                                  |
| xml_etree_generate               | 66.3 ms                                                          | 70.2 ms: 1.06x slower                                                  |
| json_loads                       | 16.7 us                                                          | 17.7 us: 1.06x slower                                                  |
| django_template                  | 27.3 ms                                                          | 29.2 ms: 1.07x slower                                                  |
| xml_etree_iterparse              | 69.6 ms                                                          | 75.5 ms: 1.08x slower                                                  |
| thread_accumulate_naive          | 40.9 ms                                                          | 45.4 ms: 1.11x slower                                                  |
| thread_counter_optimized         | 18.7 ms                                                          | 21.1 ms: 1.13x slower                                                  |
| thread_pipeline_optimized        | 25.6 ms                                                          | 29.0 ms: 1.13x slower                                                  |
| thread_accumulate_optimized      | 39.8 ms                                                          | 45.2 ms: 1.14x slower                                                  |
| pickle                           | 8.22 us                                                          | 9.43 us: 1.15x slower                                                  |
| mako                             | 7.43 ms                                                          | 8.55 ms: 1.15x slower                                                  |
| pickle_list                      | 3.03 us                                                          | 3.71 us: 1.22x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 419 ms: 1.30x slower                                                   |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 279 ms: 1.61x slower                                                   |
| async_tree_eager_tg              | 58.6 ms                                                          | 205 ms: 3.50x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.29x faster                                                           |

Benchmark hidden because not significant (8): generators, nbody, logging_silent, json, mypy2, networkx_k_core, xdsl_constant_fold, async_generators
Ignored benchmarks (2) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.296x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.05x
- 95% likely to have a speedup of 1.04x
- 99% likely to have a speedup of 1.03x

# Memory
- memory change: 1.03x