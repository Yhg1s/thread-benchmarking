# Results vs. 3.14.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.202x faster
- HPT reliability: 82.36%
- HPT 99th percentile: 1.00x slower
- Memory change: 0.94x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 11.0 ms: 1.03x slower                                                  |
| docutils       | 2.02 sec                                                         | 1.89 sec: 1.07x faster                                                 |
| fastapi_http   | 215 ms                                                           | 212 ms: 1.02x faster                                                   |
| tornado_http   | 101 ms                                                           | 97.7 ms: 1.03x faster                                                  |
| Geometric mean | (ref)                                                            | 1.01x faster                                                           |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| asyncio_tcp                      | 332 ms                                                           | 291 ms: 1.14x faster                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.26 sec: 1.02x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 337 ms: 1.01x slower                                                   |
| coroutines                       | 15.4 ms                                                          | 15.5 ms: 1.01x slower                                                  |
| asyncio_websockets               | 305 ms                                                           | 310 ms: 1.02x slower                                                   |
| async_tree_eager_memoization     | 175 ms                                                           | 180 ms: 1.03x slower                                                   |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 460 ms: 1.07x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 419 ms: 1.09x slower                                                   |
| async_generators                 | 243 ms                                                           | 266 ms: 1.10x slower                                                   |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 481 ms: 1.10x slower                                                   |
| async_tree_none                  | 223 ms                                                           | 249 ms: 1.11x slower                                                   |
| async_tree_eager_tg              | 179 ms                                                           | 205 ms: 1.15x slower                                                   |
| async_tree_eager_io              | 548 ms                                                           | 629 ms: 1.15x slower                                                   |
| async_tree_none_tg               | 221 ms                                                           | 256 ms: 1.16x slower                                                   |
| async_tree_memoization_tg        | 275 ms                                                           | 323 ms: 1.18x slower                                                   |
| async_tree_memoization           | 274 ms                                                           | 324 ms: 1.18x slower                                                   |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 279 ms: 1.18x slower                                                   |
| async_tree_io                    | 527 ms                                                           | 632 ms: 1.20x slower                                                   |
| async_tree_eager_io_tg           | 549 ms                                                           | 668 ms: 1.22x slower                                                   |
| async_tree_io_tg                 | 529 ms                                                           | 668 ms: 1.26x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.09x slower                                                           |

Benchmark hidden because not significant (1): async_tree_eager

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 19.0 ns: 1.02x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 201 ms                                                           | 202 ms: 1.00x slower                                                   |
| decimal_factorial | 170 ms                                                           | 172 ms: 1.01x slower                                                   |
| Geometric mean    | (ref)                                                            | 1.01x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| quadtree_nbody | 602 ms                                                           | 573 ms: 1.05x faster                                                   |
| pidigits       | 181 ms                                                           | 182 ms: 1.00x slower                                                   |
| float          | 48.1 ms                                                          | 51.9 ms: 1.08x slower                                                  |
| Geometric mean | (ref)                                                            | 1.00x slower                                                           |

Benchmark hidden because not significant (1): nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_compile  | 91.6 ms                                                          | 92.2 ms: 1.01x slower                                                  |
| regex_effbot   | 1.80 ms                                                          | 1.81 ms: 1.01x slower                                                  |
| regex_v8       | 15.0 ms                                                          | 15.2 ms: 1.01x slower                                                  |
| regex_dna      | 141 ms                                                           | 145 ms: 1.03x slower                                                   |
| Geometric mean | (ref)                                                            | 1.01x slower                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 276 ms                                                           | 2.09 ms: 132.08x faster                                                |
| base85_large         | 233 ms                                                           | 3.31 ms: 70.30x faster                                                 |
| ascii85_large        | 651 ms                                                           | 10.2 ms: 64.16x faster                                                 |
| ascii85_small        | 12.5 ms                                                          | 519 us: 24.06x faster                                                  |
| base32_small         | 5.43 ms                                                          | 229 us: 23.75x faster                                                  |
| base85_small         | 4.44 ms                                                          | 200 us: 22.18x faster                                                  |
| base64_large         | 6.31 ms                                                          | 1.55 ms: 4.08x faster                                                  |
| urlsafe_base64_small | 383 us                                                           | 271 us: 1.41x faster                                                   |
| json_dumps           | 7.37 ms                                                          | 6.57 ms: 1.12x faster                                                  |
| tomli_loads          | 1.41 sec                                                         | 1.33 sec: 1.06x faster                                                 |
| unpickle_list        | 3.64 us                                                          | 3.58 us: 1.02x faster                                                  |
| xml_etree_iterparse  | 76.5 ms                                                          | 75.5 ms: 1.01x faster                                                  |
| pickle_pure_python   | 234 us                                                           | 231 us: 1.01x faster                                                   |
| xml_etree_generate   | 71.1 ms                                                          | 70.2 ms: 1.01x faster                                                  |
| xml_etree_process    | 50.0 ms                                                          | 49.4 ms: 1.01x faster                                                  |
| unpickle_pure_python | 153 us                                                           | 153 us: 1.00x slower                                                   |
| unpickle             | 10.3 us                                                          | 10.5 us: 1.01x slower                                                  |
| pickle               | 9.23 us                                                          | 9.43 us: 1.02x slower                                                  |
| json_loads           | 17.3 us                                                          | 17.7 us: 1.02x slower                                                  |
| base64_small         | 230 us                                                           | 236 us: 1.03x slower                                                   |
| xml_etree_parse      | 102 ms                                                           | 107 ms: 1.05x slower                                                   |
| pickle_dict          | 21.3 us                                                          | 22.6 us: 1.06x slower                                                  |
| pickle_list          | 3.26 us                                                          | 3.71 us: 1.14x slower                                                  |
| base16_large         | 5.41 ms                                                          | 7.09 ms: 1.31x slower                                                  |
| base16_small         | 298 us                                                           | 427 us: 1.43x slower                                                   |
| Geometric mean       | (ref)                                                            | 2.59x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.29 ms                                                          | 5.85 ms: 1.07x faster                                                  |
| python_startup         | 9.62 ms                                                          | 9.44 ms: 1.02x faster                                                  |
| Geometric mean         | (ref)                                                            | 1.05x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 28.4 ms                                                          | 29.2 ms: 1.03x slower                                                  |
| mako            | 7.66 ms                                                          | 8.55 ms: 1.12x slower                                                  |
| Geometric mean  | (ref)                                                            | 1.07x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 11.8 ms                                                          | 9.84 ms: 1.20x faster                                                  |
| thread_mandelbrot_naive     | 217 ms                                                           | 206 ms: 1.05x faster                                                   |
| thread_mandelbrot_optimized | 215 ms                                                           | 206 ms: 1.05x faster                                                   |
| thread_pipeline_naive       | 35.4 ms                                                          | 37.2 ms: 1.05x slower                                                  |
| thread_montecarlo_naive     | 14.6 ms                                                          | 15.4 ms: 1.05x slower                                                  |
| thread_montecarlo_optimized | 12.6 ms                                                          | 13.3 ms: 1.05x slower                                                  |
| thread_memo_optimized       | 17.9 ms                                                          | 19.3 ms: 1.07x slower                                                  |
| thread_counter_naive        | 21.4 ms                                                          | 23.0 ms: 1.08x slower                                                  |
| thread_accumulate_naive     | 41.6 ms                                                          | 45.4 ms: 1.09x slower                                                  |
| thread_pipeline_optimized   | 26.3 ms                                                          | 29.0 ms: 1.10x slower                                                  |
| thread_accumulate_optimized | 40.8 ms                                                          | 45.2 ms: 1.11x slower                                                  |
| thread_counter_optimized    | 18.7 ms                                                          | 21.1 ms: 1.13x slower                                                  |
| Geometric mean              | (ref)                                                            | 1.04x slower                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 276 ms                                                           | 2.09 ms: 132.08x faster                                                |
| base85_large                     | 233 ms                                                           | 3.31 ms: 70.30x faster                                                 |
| ascii85_large                    | 651 ms                                                           | 10.2 ms: 64.16x faster                                                 |
| ascii85_small                    | 12.5 ms                                                          | 519 us: 24.06x faster                                                  |
| base32_small                     | 5.43 ms                                                          | 229 us: 23.75x faster                                                  |
| base85_small                     | 4.44 ms                                                          | 200 us: 22.18x faster                                                  |
| argparse_many_optionals          | 33.3 ms                                                          | 7.57 ms: 4.39x faster                                                  |
| base64_large                     | 6.31 ms                                                          | 1.55 ms: 4.08x faster                                                  |
| pylint                           | 215 ms                                                           | 97.8 ms: 2.20x faster                                                  |
| argparse_subparsers              | 665 us                                                           | 448 us: 1.48x faster                                                   |
| urlsafe_base64_small             | 383 us                                                           | 271 us: 1.41x faster                                                   |
| thread_memo_naive                | 11.8 ms                                                          | 9.84 ms: 1.20x faster                                                  |
| create_gc_cycles                 | 1.93 ms                                                          | 1.62 ms: 1.19x faster                                                  |
| pathlib                          | 12.5 ms                                                          | 10.6 ms: 1.19x faster                                                  |
| asyncio_tcp                      | 332 ms                                                           | 291 ms: 1.14x faster                                                   |
| gc_traversal                     | 3.33 ms                                                          | 2.94 ms: 1.13x faster                                                  |
| json_dumps                       | 7.37 ms                                                          | 6.57 ms: 1.12x faster                                                  |
| deepcopy                         | 195 us                                                           | 178 us: 1.09x faster                                                   |
| python_startup_no_site           | 6.29 ms                                                          | 5.85 ms: 1.07x faster                                                  |
| sqlglot_v2_parse                 | 909 us                                                           | 848 us: 1.07x faster                                                   |
| deepcopy_memo                    | 18.2 us                                                          | 17.1 us: 1.07x faster                                                  |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.08 ms: 1.07x faster                                                  |
| docutils                         | 2.02 sec                                                         | 1.89 sec: 1.07x faster                                                 |
| tomli_loads                      | 1.41 sec                                                         | 1.33 sec: 1.06x faster                                                 |
| logging_simple                   | 4.72 us                                                          | 4.46 us: 1.06x faster                                                  |
| thread_mandelbrot_naive          | 217 ms                                                           | 206 ms: 1.05x faster                                                   |
| quadtree_nbody                   | 602 ms                                                           | 573 ms: 1.05x faster                                                   |
| chaos                            | 41.9 ms                                                          | 39.9 ms: 1.05x faster                                                  |
| nqueens                          | 56.3 ms                                                          | 53.7 ms: 1.05x faster                                                  |
| thread_mandelbrot_optimized      | 215 ms                                                           | 206 ms: 1.05x faster                                                   |
| mypy2                            | 756 ms                                                           | 731 ms: 1.04x faster                                                   |
| tornado_http                     | 101 ms                                                           | 97.7 ms: 1.03x faster                                                  |
| logging_format                   | 5.24 us                                                          | 5.10 us: 1.03x faster                                                  |
| raytrace                         | 194 ms                                                           | 189 ms: 1.03x faster                                                   |
| hexiom                           | 4.00 ms                                                          | 3.90 ms: 1.03x faster                                                  |
| pyflate                          | 300 ms                                                           | 293 ms: 1.02x faster                                                   |
| fannkuch                         | 234 ms                                                           | 228 ms: 1.02x faster                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.26 sec: 1.02x faster                                                 |
| spectral_norm                    | 59.6 ms                                                          | 58.3 ms: 1.02x faster                                                  |
| mdp                              | 935 ms                                                           | 916 ms: 1.02x faster                                                   |
| comprehensions                   | 11.2 us                                                          | 10.9 us: 1.02x faster                                                  |
| python_startup                   | 9.62 ms                                                          | 9.44 ms: 1.02x faster                                                  |
| scimark_fft                      | 197 ms                                                           | 193 ms: 1.02x faster                                                   |
| unpickle_list                    | 3.64 us                                                          | 3.58 us: 1.02x faster                                                  |
| telco                            | 5.26 ms                                                          | 5.17 ms: 1.02x faster                                                  |
| fastapi_http                     | 215 ms                                                           | 212 ms: 1.02x faster                                                   |
| xml_etree_iterparse              | 76.5 ms                                                          | 75.5 ms: 1.01x faster                                                  |
| pickle_pure_python               | 234 us                                                           | 231 us: 1.01x faster                                                   |
| scimark_sor                      | 72.8 ms                                                          | 71.8 ms: 1.01x faster                                                  |
| xml_etree_generate               | 71.1 ms                                                          | 70.2 ms: 1.01x faster                                                  |
| xml_etree_process                | 50.0 ms                                                          | 49.4 ms: 1.01x faster                                                  |
| go                               | 82.6 ms                                                          | 82.0 ms: 1.01x faster                                                  |
| sqlalchemy_imperative            | 14.3 ms                                                          | 14.2 ms: 1.01x faster                                                  |
| deepcopy_reduce                  | 2.05 us                                                          | 2.04 us: 1.00x faster                                                  |
| decimal_pi                       | 201 ms                                                           | 202 ms: 1.00x slower                                                   |
| unpickle_pure_python             | 153 us                                                           | 153 us: 1.00x slower                                                   |
| pidigits                         | 181 ms                                                           | 182 ms: 1.00x slower                                                   |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 78.2 ms: 1.00x slower                                                  |
| sympy_str                        | 192 ms                                                           | 193 ms: 1.01x slower                                                   |
| regex_compile                    | 91.6 ms                                                          | 92.2 ms: 1.01x slower                                                  |
| sympy_expand                     | 330 ms                                                           | 333 ms: 1.01x slower                                                   |
| regex_effbot                     | 1.80 ms                                                          | 1.81 ms: 1.01x slower                                                  |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 337 ms: 1.01x slower                                                   |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 2.61 ms: 1.01x slower                                                  |
| regex_v8                         | 15.0 ms                                                          | 15.2 ms: 1.01x slower                                                  |
| decimal_factorial                | 170 ms                                                           | 172 ms: 1.01x slower                                                   |
| meteor_contest                   | 83.9 ms                                                          | 84.9 ms: 1.01x slower                                                  |
| coroutines                       | 15.4 ms                                                          | 15.5 ms: 1.01x slower                                                  |
| logging_silent                   | 59.7 ns                                                          | 60.5 ns: 1.01x slower                                                  |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                                   |
| unpickle                         | 10.3 us                                                          | 10.5 us: 1.01x slower                                                  |
| scimark_monte_carlo              | 37.5 ms                                                          | 38.0 ms: 1.01x slower                                                  |
| thrift                           | 1.84 ms                                                          | 1.87 ms: 1.02x slower                                                  |
| networkx_shortest_path           | 445 ms                                                           | 452 ms: 1.02x slower                                                   |
| noop                             | 18.7 ns                                                          | 19.0 ns: 1.02x slower                                                  |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.15 sec: 1.02x slower                                                 |
| scimark_lu                       | 66.7 ms                                                          | 67.9 ms: 1.02x slower                                                  |
| asyncio_websockets               | 305 ms                                                           | 310 ms: 1.02x slower                                                   |
| deltablue                        | 2.24 ms                                                          | 2.29 ms: 1.02x slower                                                  |
| json                             | 3.42 ms                                                          | 3.49 ms: 1.02x slower                                                  |
| pickle                           | 9.23 us                                                          | 9.43 us: 1.02x slower                                                  |
| typing_runtime_protocols         | 106 us                                                           | 108 us: 1.02x slower                                                   |
| json_loads                       | 17.3 us                                                          | 17.7 us: 1.02x slower                                                  |
| crypto_pyaes                     | 51.5 ms                                                          | 52.8 ms: 1.02x slower                                                  |
| base64_small                     | 230 us                                                           | 236 us: 1.03x slower                                                   |
| richards                         | 32.5 ms                                                          | 33.4 ms: 1.03x slower                                                  |
| django_template                  | 28.4 ms                                                          | 29.2 ms: 1.03x slower                                                  |
| networkx_connected_components    | 435 ms                                                           | 448 ms: 1.03x slower                                                   |
| pprint_safe_repr                 | 484 ms                                                           | 498 ms: 1.03x slower                                                   |
| regex_dna                        | 141 ms                                                           | 145 ms: 1.03x slower                                                   |
| pycparser                        | 837 ms                                                           | 863 ms: 1.03x slower                                                   |
| async_tree_eager_memoization     | 175 ms                                                           | 180 ms: 1.03x slower                                                   |
| chameleon                        | 10.6 ms                                                          | 11.0 ms: 1.03x slower                                                  |
| pprint_pformat                   | 982 ms                                                           | 1.02 sec: 1.03x slower                                                 |
| generators                       | 20.7 ms                                                          | 21.6 ms: 1.04x slower                                                  |
| xml_etree_parse                  | 102 ms                                                           | 107 ms: 1.05x slower                                                   |
| networkx_k_core                  | 2.07 sec                                                         | 2.17 sec: 1.05x slower                                                 |
| thread_pipeline_naive            | 35.4 ms                                                          | 37.2 ms: 1.05x slower                                                  |
| thread_montecarlo_naive          | 14.6 ms                                                          | 15.4 ms: 1.05x slower                                                  |
| unpack_sequence                  | 24.1 ns                                                          | 25.3 ns: 1.05x slower                                                  |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 13.3 ms: 1.05x slower                                                  |
| xdsl_constant_fold               | 35.1 ms                                                          | 37.3 ms: 1.06x slower                                                  |
| pickle_dict                      | 21.3 us                                                          | 22.6 us: 1.06x slower                                                  |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 460 ms: 1.07x slower                                                   |
| thread_memo_optimized            | 17.9 ms                                                          | 19.3 ms: 1.07x slower                                                  |
| thread_counter_naive             | 21.4 ms                                                          | 23.0 ms: 1.08x slower                                                  |
| float                            | 48.1 ms                                                          | 51.9 ms: 1.08x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 419 ms: 1.09x slower                                                   |
| thread_accumulate_naive          | 41.6 ms                                                          | 45.4 ms: 1.09x slower                                                  |
| async_generators                 | 243 ms                                                           | 266 ms: 1.10x slower                                                   |
| thread_pipeline_optimized        | 26.3 ms                                                          | 29.0 ms: 1.10x slower                                                  |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 481 ms: 1.10x slower                                                   |
| thread_accumulate_optimized      | 40.8 ms                                                          | 45.2 ms: 1.11x slower                                                  |
| async_tree_none                  | 223 ms                                                           | 249 ms: 1.11x slower                                                   |
| mako                             | 7.66 ms                                                          | 8.55 ms: 1.12x slower                                                  |
| thread_counter_optimized         | 18.7 ms                                                          | 21.1 ms: 1.13x slower                                                  |
| pickle_list                      | 3.26 us                                                          | 3.71 us: 1.14x slower                                                  |
| async_tree_eager_tg              | 179 ms                                                           | 205 ms: 1.15x slower                                                   |
| async_tree_eager_io              | 548 ms                                                           | 629 ms: 1.15x slower                                                   |
| async_tree_none_tg               | 221 ms                                                           | 256 ms: 1.16x slower                                                   |
| async_tree_memoization_tg        | 275 ms                                                           | 323 ms: 1.18x slower                                                   |
| async_tree_memoization           | 274 ms                                                           | 324 ms: 1.18x slower                                                   |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 279 ms: 1.18x slower                                                   |
| async_tree_io                    | 527 ms                                                           | 632 ms: 1.20x slower                                                   |
| async_tree_eager_io_tg           | 549 ms                                                           | 668 ms: 1.22x slower                                                   |
| async_tree_io_tg                 | 529 ms                                                           | 668 ms: 1.26x slower                                                   |
| base16_large                     | 5.41 ms                                                          | 7.09 ms: 1.31x slower                                                  |
| base16_small                     | 298 us                                                           | 427 us: 1.43x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.20x faster                                                           |

Benchmark hidden because not significant (7): nbody, coverage, sqlglot_v2_optimize, richards_super, async_tree_eager, sympy_integrate, html5lib
Ignored benchmarks (2) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.202x faster

# HPT report

- Reliability score: 82.36% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 0.94x