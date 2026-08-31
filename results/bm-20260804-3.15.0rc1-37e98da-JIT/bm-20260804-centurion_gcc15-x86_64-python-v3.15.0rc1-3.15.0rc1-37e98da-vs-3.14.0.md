# Results vs. 3.14.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.281x faster
- HPT reliability: 99.89%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.04x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 10.3 ms: 1.03x faster                                                  |
| docutils       | 2.02 sec                                                         | 1.94 sec: 1.04x faster                                                 |
| fastapi_http   | 215 ms                                                           | 198 ms: 1.09x faster                                                   |
| tornado_http   | 101 ms                                                           | 96.9 ms: 1.04x faster                                                  |
| Geometric mean | (ref)                                                            | 1.04x faster                                                           |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| asyncio_tcp                      | 332 ms                                                           | 274 ms: 1.21x faster                                                   |
| async_tree_eager                 | 78.8 ms                                                          | 74.3 ms: 1.06x faster                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.26 sec: 1.02x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 228 ms: 1.02x slower                                                   |
| asyncio_websockets               | 305 ms                                                           | 311 ms: 1.02x slower                                                   |
| async_tree_eager_memoization     | 175 ms                                                           | 180 ms: 1.03x slower                                                   |
| async_tree_eager_tg              | 179 ms                                                           | 188 ms: 1.05x slower                                                   |
| async_tree_none_tg               | 221 ms                                                           | 234 ms: 1.06x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 354 ms: 1.06x slower                                                   |
| async_tree_memoization           | 274 ms                                                           | 292 ms: 1.07x slower                                                   |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 459 ms: 1.07x slower                                                   |
| async_tree_eager_io              | 548 ms                                                           | 590 ms: 1.08x slower                                                   |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 471 ms: 1.08x slower                                                   |
| async_tree_io                    | 527 ms                                                           | 581 ms: 1.10x slower                                                   |
| async_generators                 | 243 ms                                                           | 268 ms: 1.10x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 428 ms: 1.11x slower                                                   |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 261 ms: 1.11x slower                                                   |
| async_tree_memoization_tg        | 275 ms                                                           | 306 ms: 1.11x slower                                                   |
| async_tree_eager_io_tg           | 549 ms                                                           | 624 ms: 1.14x slower                                                   |
| async_tree_io_tg                 | 529 ms                                                           | 622 ms: 1.18x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.05x slower                                                           |

Benchmark hidden because not significant (1): coroutines

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 16.4 ns: 1.14x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 201 ms                                                           | 191 ms: 1.06x faster                                                   |
| decimal_factorial | 170 ms                                                           | 168 ms: 1.01x faster                                                   |
| Geometric mean    | (ref)                                                            | 1.03x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| nbody          | 67.2 ms                                                          | 42.0 ms: 1.60x faster                                                  |
| float          | 48.1 ms                                                          | 37.7 ms: 1.28x faster                                                  |
| quadtree_nbody | 602 ms                                                           | 526 ms: 1.15x faster                                                   |
| pidigits       | 181 ms                                                           | 181 ms: 1.00x faster                                                   |
| Geometric mean | (ref)                                                            | 1.24x faster                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_compile  | 91.6 ms                                                          | 82.1 ms: 1.12x faster                                                  |
| regex_v8       | 15.0 ms                                                          | 14.6 ms: 1.03x faster                                                  |
| regex_dna      | 141 ms                                                           | 145 ms: 1.03x slower                                                   |
| regex_effbot   | 1.80 ms                                                          | 1.96 ms: 1.09x slower                                                  |
| Geometric mean | (ref)                                                            | 1.01x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 276 ms                                                           | 2.09 ms: 132.01x faster                                                |
| base85_large         | 233 ms                                                           | 3.24 ms: 71.76x faster                                                 |
| ascii85_large        | 651 ms                                                           | 10.1 ms: 64.42x faster                                                 |
| base32_small         | 5.43 ms                                                          | 203 us: 26.75x faster                                                  |
| ascii85_small        | 12.5 ms                                                          | 485 us: 25.73x faster                                                  |
| base85_small         | 4.44 ms                                                          | 184 us: 24.14x faster                                                  |
| base64_large         | 6.31 ms                                                          | 1.53 ms: 4.12x faster                                                  |
| urlsafe_base64_small | 383 us                                                           | 248 us: 1.55x faster                                                   |
| json_dumps           | 7.37 ms                                                          | 5.96 ms: 1.24x faster                                                  |
| unpickle_pure_python | 153 us                                                           | 125 us: 1.23x faster                                                   |
| base64_small         | 230 us                                                           | 198 us: 1.16x faster                                                   |
| tomli_loads          | 1.41 sec                                                         | 1.23 sec: 1.14x faster                                                 |
| pickle_pure_python   | 234 us                                                           | 206 us: 1.14x faster                                                   |
| xml_etree_process    | 50.0 ms                                                          | 44.8 ms: 1.12x faster                                                  |
| xml_etree_generate   | 71.1 ms                                                          | 65.0 ms: 1.09x faster                                                  |
| xml_etree_iterparse  | 76.5 ms                                                          | 72.4 ms: 1.06x faster                                                  |
| unpickle_list        | 3.64 us                                                          | 3.58 us: 1.02x faster                                                  |
| json_loads           | 17.3 us                                                          | 17.6 us: 1.02x slower                                                  |
| unpickle             | 10.3 us                                                          | 10.6 us: 1.02x slower                                                  |
| pickle               | 9.23 us                                                          | 9.55 us: 1.03x slower                                                  |
| xml_etree_parse      | 102 ms                                                           | 107 ms: 1.05x slower                                                   |
| pickle_dict          | 21.3 us                                                          | 22.5 us: 1.06x slower                                                  |
| pickle_list          | 3.26 us                                                          | 3.73 us: 1.15x slower                                                  |
| base16_large         | 5.41 ms                                                          | 7.10 ms: 1.31x slower                                                  |
| base16_small         | 298 us                                                           | 391 us: 1.31x slower                                                   |
| Geometric mean       | (ref)                                                            | 2.73x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.29 ms                                                          | 5.95 ms: 1.06x faster                                                  |
| python_startup         | 9.62 ms                                                          | 9.54 ms: 1.01x faster                                                  |
| Geometric mean         | (ref)                                                            | 1.03x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| mako            | 7.66 ms                                                          | 7.10 ms: 1.08x faster                                                  |
| django_template | 28.4 ms                                                          | 31.8 ms: 1.12x slower                                                  |
| Geometric mean  | (ref)                                                            | 1.02x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 11.8 ms                                                          | 8.42 ms: 1.41x faster                                                  |
| thread_mandelbrot_naive     | 217 ms                                                           | 194 ms: 1.12x faster                                                   |
| thread_pipeline_naive       | 35.4 ms                                                          | 32.3 ms: 1.10x faster                                                  |
| thread_counter_naive        | 21.4 ms                                                          | 19.6 ms: 1.09x faster                                                  |
| thread_mandelbrot_optimized | 215 ms                                                           | 198 ms: 1.09x faster                                                   |
| thread_montecarlo_optimized | 12.6 ms                                                          | 12.3 ms: 1.02x faster                                                  |
| thread_counter_optimized    | 18.7 ms                                                          | 18.3 ms: 1.02x faster                                                  |
| thread_memo_optimized       | 17.9 ms                                                          | 17.8 ms: 1.01x faster                                                  |
| thread_accumulate_naive     | 41.6 ms                                                          | 42.3 ms: 1.02x slower                                                  |
| thread_pipeline_optimized   | 26.3 ms                                                          | 27.0 ms: 1.03x slower                                                  |
| thread_accumulate_optimized | 40.8 ms                                                          | 42.4 ms: 1.04x slower                                                  |
| thread_montecarlo_naive     | 14.6 ms                                                          | 16.1 ms: 1.10x slower                                                  |
| Geometric mean              | (ref)                                                            | 1.05x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 276 ms                                                           | 2.09 ms: 132.01x faster                                                |
| base85_large                     | 233 ms                                                           | 3.24 ms: 71.76x faster                                                 |
| ascii85_large                    | 651 ms                                                           | 10.1 ms: 64.42x faster                                                 |
| base32_small                     | 5.43 ms                                                          | 203 us: 26.75x faster                                                  |
| ascii85_small                    | 12.5 ms                                                          | 485 us: 25.73x faster                                                  |
| base85_small                     | 4.44 ms                                                          | 184 us: 24.14x faster                                                  |
| argparse_many_optionals          | 33.3 ms                                                          | 7.17 ms: 4.64x faster                                                  |
| base64_large                     | 6.31 ms                                                          | 1.53 ms: 4.12x faster                                                  |
| pylint                           | 215 ms                                                           | 99.1 ms: 2.17x faster                                                  |
| richards_super                   | 37.2 ms                                                          | 18.2 ms: 2.04x faster                                                  |
| richards                         | 32.5 ms                                                          | 16.1 ms: 2.03x faster                                                  |
| nbody                            | 67.2 ms                                                          | 42.0 ms: 1.60x faster                                                  |
| scimark_lu                       | 66.7 ms                                                          | 42.2 ms: 1.58x faster                                                  |
| argparse_subparsers              | 665 us                                                           | 429 us: 1.55x faster                                                   |
| urlsafe_base64_small             | 383 us                                                           | 248 us: 1.55x faster                                                   |
| scimark_sor                      | 72.8 ms                                                          | 50.6 ms: 1.44x faster                                                  |
| spectral_norm                    | 59.6 ms                                                          | 42.2 ms: 1.41x faster                                                  |
| thread_memo_naive                | 11.8 ms                                                          | 8.42 ms: 1.41x faster                                                  |
| scimark_fft                      | 197 ms                                                           | 151 ms: 1.31x faster                                                   |
| float                            | 48.1 ms                                                          | 37.7 ms: 1.28x faster                                                  |
| deepcopy_memo                    | 18.2 us                                                          | 14.6 us: 1.25x faster                                                  |
| json_dumps                       | 7.37 ms                                                          | 5.96 ms: 1.24x faster                                                  |
| fannkuch                         | 234 ms                                                           | 190 ms: 1.23x faster                                                   |
| unpickle_pure_python             | 153 us                                                           | 125 us: 1.23x faster                                                   |
| nqueens                          | 56.3 ms                                                          | 46.0 ms: 1.22x faster                                                  |
| asyncio_tcp                      | 332 ms                                                           | 274 ms: 1.21x faster                                                   |
| pathlib                          | 12.5 ms                                                          | 10.4 ms: 1.21x faster                                                  |
| deltablue                        | 2.24 ms                                                          | 1.89 ms: 1.19x faster                                                  |
| create_gc_cycles                 | 1.93 ms                                                          | 1.63 ms: 1.18x faster                                                  |
| sqlglot_v2_parse                 | 909 us                                                           | 776 us: 1.17x faster                                                   |
| base64_small                     | 230 us                                                           | 198 us: 1.16x faster                                                   |
| pyflate                          | 300 ms                                                           | 261 ms: 1.15x faster                                                   |
| quadtree_nbody                   | 602 ms                                                           | 526 ms: 1.15x faster                                                   |
| tomli_loads                      | 1.41 sec                                                         | 1.23 sec: 1.14x faster                                                 |
| noop                             | 18.7 ns                                                          | 16.4 ns: 1.14x faster                                                  |
| pickle_pure_python               | 234 us                                                           | 206 us: 1.14x faster                                                   |
| gc_traversal                     | 3.33 ms                                                          | 2.94 ms: 1.13x faster                                                  |
| telco                            | 5.26 ms                                                          | 4.66 ms: 1.13x faster                                                  |
| logging_format                   | 5.24 us                                                          | 4.68 us: 1.12x faster                                                  |
| thread_mandelbrot_naive          | 217 ms                                                           | 194 ms: 1.12x faster                                                   |
| logging_simple                   | 4.72 us                                                          | 4.23 us: 1.12x faster                                                  |
| xml_etree_process                | 50.0 ms                                                          | 44.8 ms: 1.12x faster                                                  |
| regex_compile                    | 91.6 ms                                                          | 82.1 ms: 1.12x faster                                                  |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.05 ms: 1.10x faster                                                  |
| comprehensions                   | 11.2 us                                                          | 10.2 us: 1.10x faster                                                  |
| thread_pipeline_naive            | 35.4 ms                                                          | 32.3 ms: 1.10x faster                                                  |
| sympy_expand                     | 330 ms                                                           | 301 ms: 1.10x faster                                                   |
| xml_etree_generate               | 71.1 ms                                                          | 65.0 ms: 1.09x faster                                                  |
| sqlalchemy_imperative            | 14.3 ms                                                          | 13.1 ms: 1.09x faster                                                  |
| thread_counter_naive             | 21.4 ms                                                          | 19.6 ms: 1.09x faster                                                  |
| fastapi_http                     | 215 ms                                                           | 198 ms: 1.09x faster                                                   |
| thread_mandelbrot_optimized      | 215 ms                                                           | 198 ms: 1.09x faster                                                   |
| mako                             | 7.66 ms                                                          | 7.10 ms: 1.08x faster                                                  |
| async_tree_eager                 | 78.8 ms                                                          | 74.3 ms: 1.06x faster                                                  |
| crypto_pyaes                     | 51.5 ms                                                          | 48.7 ms: 1.06x faster                                                  |
| xml_etree_iterparse              | 76.5 ms                                                          | 72.4 ms: 1.06x faster                                                  |
| python_startup_no_site           | 6.29 ms                                                          | 5.95 ms: 1.06x faster                                                  |
| decimal_pi                       | 201 ms                                                           | 191 ms: 1.06x faster                                                   |
| chaos                            | 41.9 ms                                                          | 39.8 ms: 1.05x faster                                                  |
| xdsl_constant_fold               | 35.1 ms                                                          | 33.4 ms: 1.05x faster                                                  |
| bpe_tokeniser                    | 3.10 sec                                                         | 2.95 sec: 1.05x faster                                                 |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 2.46 ms: 1.05x faster                                                  |
| hexiom                           | 4.00 ms                                                          | 3.82 ms: 1.05x faster                                                  |
| go                               | 82.6 ms                                                          | 79.4 ms: 1.04x faster                                                  |
| meteor_contest                   | 83.9 ms                                                          | 80.7 ms: 1.04x faster                                                  |
| docutils                         | 2.02 sec                                                         | 1.94 sec: 1.04x faster                                                 |
| tornado_http                     | 101 ms                                                           | 96.9 ms: 1.04x faster                                                  |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 37.3 ms: 1.04x faster                                                  |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 75.4 ms: 1.03x faster                                                  |
| chameleon                        | 10.6 ms                                                          | 10.3 ms: 1.03x faster                                                  |
| regex_v8                         | 15.0 ms                                                          | 14.6 ms: 1.03x faster                                                  |
| sympy_str                        | 192 ms                                                           | 186 ms: 1.03x faster                                                   |
| scimark_monte_carlo              | 37.5 ms                                                          | 36.5 ms: 1.03x faster                                                  |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 12.3 ms: 1.02x faster                                                  |
| raytrace                         | 194 ms                                                           | 190 ms: 1.02x faster                                                   |
| thread_counter_optimized         | 18.7 ms                                                          | 18.3 ms: 1.02x faster                                                  |
| networkx_shortest_path           | 445 ms                                                           | 435 ms: 1.02x faster                                                   |
| networkx_connected_components    | 435 ms                                                           | 427 ms: 1.02x faster                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.26 sec: 1.02x faster                                                 |
| unpickle_list                    | 3.64 us                                                          | 3.58 us: 1.02x faster                                                  |
| json                             | 3.42 ms                                                          | 3.37 ms: 1.02x faster                                                  |
| typing_runtime_protocols         | 106 us                                                           | 104 us: 1.01x faster                                                   |
| decimal_factorial                | 170 ms                                                           | 168 ms: 1.01x faster                                                   |
| thrift                           | 1.84 ms                                                          | 1.82 ms: 1.01x faster                                                  |
| python_startup                   | 9.62 ms                                                          | 9.54 ms: 1.01x faster                                                  |
| thread_memo_optimized            | 17.9 ms                                                          | 17.8 ms: 1.01x faster                                                  |
| pidigits                         | 181 ms                                                           | 181 ms: 1.00x faster                                                   |
| logging_silent                   | 59.7 ns                                                          | 60.1 ns: 1.01x slower                                                  |
| thread_accumulate_naive          | 41.6 ms                                                          | 42.3 ms: 1.02x slower                                                  |
| json_loads                       | 17.3 us                                                          | 17.6 us: 1.02x slower                                                  |
| async_tree_none                  | 223 ms                                                           | 228 ms: 1.02x slower                                                   |
| unpickle                         | 10.3 us                                                          | 10.6 us: 1.02x slower                                                  |
| asyncio_websockets               | 305 ms                                                           | 311 ms: 1.02x slower                                                   |
| sympy_sum                        | 104 ms                                                           | 106 ms: 1.02x slower                                                   |
| generators                       | 20.7 ms                                                          | 21.2 ms: 1.02x slower                                                  |
| coverage                         | 55.4 ms                                                          | 56.8 ms: 1.02x slower                                                  |
| thread_pipeline_optimized        | 26.3 ms                                                          | 27.0 ms: 1.03x slower                                                  |
| async_tree_eager_memoization     | 175 ms                                                           | 180 ms: 1.03x slower                                                   |
| mdp                              | 935 ms                                                           | 964 ms: 1.03x slower                                                   |
| pprint_safe_repr                 | 484 ms                                                           | 499 ms: 1.03x slower                                                   |
| sympy_integrate                  | 14.7 ms                                                          | 15.2 ms: 1.03x slower                                                  |
| regex_dna                        | 141 ms                                                           | 145 ms: 1.03x slower                                                   |
| pickle                           | 9.23 us                                                          | 9.55 us: 1.03x slower                                                  |
| thread_accumulate_optimized      | 40.8 ms                                                          | 42.4 ms: 1.04x slower                                                  |
| pprint_pformat                   | 982 ms                                                           | 1.02 sec: 1.04x slower                                                 |
| pycparser                        | 837 ms                                                           | 869 ms: 1.04x slower                                                   |
| xml_etree_parse                  | 102 ms                                                           | 107 ms: 1.05x slower                                                   |
| async_tree_eager_tg              | 179 ms                                                           | 188 ms: 1.05x slower                                                   |
| pickle_dict                      | 21.3 us                                                          | 22.5 us: 1.06x slower                                                  |
| async_tree_none_tg               | 221 ms                                                           | 234 ms: 1.06x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 354 ms: 1.06x slower                                                   |
| async_tree_memoization           | 274 ms                                                           | 292 ms: 1.07x slower                                                   |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 459 ms: 1.07x slower                                                   |
| async_tree_eager_io              | 548 ms                                                           | 590 ms: 1.08x slower                                                   |
| networkx_k_core                  | 2.07 sec                                                         | 2.23 sec: 1.08x slower                                                 |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 471 ms: 1.08x slower                                                   |
| regex_effbot                     | 1.80 ms                                                          | 1.96 ms: 1.09x slower                                                  |
| thread_montecarlo_naive          | 14.6 ms                                                          | 16.1 ms: 1.10x slower                                                  |
| async_tree_io                    | 527 ms                                                           | 581 ms: 1.10x slower                                                   |
| async_generators                 | 243 ms                                                           | 268 ms: 1.10x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 428 ms: 1.11x slower                                                   |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 261 ms: 1.11x slower                                                   |
| async_tree_memoization_tg        | 275 ms                                                           | 306 ms: 1.11x slower                                                   |
| django_template                  | 28.4 ms                                                          | 31.8 ms: 1.12x slower                                                  |
| async_tree_eager_io_tg           | 549 ms                                                           | 624 ms: 1.14x slower                                                   |
| pickle_list                      | 3.26 us                                                          | 3.73 us: 1.15x slower                                                  |
| async_tree_io_tg                 | 529 ms                                                           | 622 ms: 1.18x slower                                                   |
| base16_large                     | 5.41 ms                                                          | 7.10 ms: 1.31x slower                                                  |
| base16_small                     | 298 us                                                           | 391 us: 1.31x slower                                                   |
| mypy2                            | 756 ms                                                           | 1.10 sec: 1.45x slower                                                 |
| unpack_sequence                  | 24.1 ns                                                          | 80.8 ns: 3.36x slower                                                  |
| Geometric mean                   | (ref)                                                            | 1.27x faster                                                           |

Benchmark hidden because not significant (4): html5lib, deepcopy, coroutines, deepcopy_reduce
Ignored benchmarks (2) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.281x faster

# HPT report

- Reliability score: 99.89% likely to be faster
- 90% likely to have a speedup of 1.02x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.04x