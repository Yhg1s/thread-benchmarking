# Results vs. 3.13.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.384x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.08x faster
- Memory change: 1.12x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 10.3 ms: 1.06x faster                                                  |
| docutils       | 1.98 sec                                                         | 1.94 sec: 1.02x faster                                                 |
| fastapi_http   | 215 ms                                                           | 198 ms: 1.08x faster                                                   |
| html5lib       | 49.1 ms                                                          | 44.7 ms: 1.10x faster                                                  |
| tornado_http   | 99.2 ms                                                          | 96.9 ms: 1.02x faster                                                  |
| Geometric mean | (ref)                                                            | 1.06x faster                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_memoization_tg        | 417 ms                                                           | 306 ms: 1.37x faster                                                   |
| async_tree_none                  | 310 ms                                                           | 228 ms: 1.36x faster                                                   |
| async_tree_memoization           | 389 ms                                                           | 292 ms: 1.33x faster                                                   |
| async_tree_io                    | 741 ms                                                           | 581 ms: 1.27x faster                                                   |
| async_tree_eager_io              | 749 ms                                                           | 590 ms: 1.27x faster                                                   |
| async_tree_io_tg                 | 777 ms                                                           | 622 ms: 1.25x faster                                                   |
| async_tree_none_tg               | 289 ms                                                           | 234 ms: 1.24x faster                                                   |
| async_tree_eager                 | 90.0 ms                                                          | 74.3 ms: 1.21x faster                                                  |
| async_tree_eager_memoization     | 215 ms                                                           | 180 ms: 1.19x faster                                                   |
| asyncio_tcp                      | 326 ms                                                           | 274 ms: 1.19x faster                                                   |
| async_tree_eager_io_tg           | 724 ms                                                           | 624 ms: 1.16x faster                                                   |
| coroutines                       | 17.6 ms                                                          | 15.4 ms: 1.14x faster                                                  |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 459 ms: 1.12x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 471 ms: 1.12x faster                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.26 sec: 1.02x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 354 ms: 1.02x faster                                                   |
| async_generators                 | 262 ms                                                           | 268 ms: 1.03x slower                                                   |
| asyncio_websockets               | 304 ms                                                           | 311 ms: 1.03x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 428 ms: 1.33x slower                                                   |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 261 ms: 1.51x slower                                                   |
| async_tree_eager_tg              | 58.6 ms                                                          | 188 ms: 3.21x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.05x faster                                                           |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 16.4 ns: 1.24x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 191 ms: 1.10x faster                                                   |
| decimal_factorial | 173 ms                                                           | 168 ms: 1.03x faster                                                   |
| Geometric mean    | (ref)                                                            | 1.06x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| nbody          | 66.8 ms                                                          | 42.0 ms: 1.59x faster                                                  |
| float          | 56.6 ms                                                          | 37.7 ms: 1.50x faster                                                  |
| quadtree_nbody | 620 ms                                                           | 526 ms: 1.18x faster                                                   |
| pidigits       | 181 ms                                                           | 181 ms: 1.00x faster                                                   |
| Geometric mean | (ref)                                                            | 1.30x faster                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_compile  | 97.7 ms                                                          | 82.1 ms: 1.19x faster                                                  |
| regex_effbot   | 1.99 ms                                                          | 1.96 ms: 1.02x faster                                                  |
| regex_v8       | 14.7 ms                                                          | 14.6 ms: 1.01x faster                                                  |
| regex_dna      | 144 ms                                                           | 145 ms: 1.01x slower                                                   |
| Geometric mean | (ref)                                                            | 1.05x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 286 ms                                                           | 2.09 ms: 136.61x faster                                                |
| ascii85_large        | 814 ms                                                           | 10.1 ms: 80.49x faster                                                 |
| base85_large         | 243 ms                                                           | 3.24 ms: 74.94x faster                                                 |
| ascii85_small        | 15.5 ms                                                          | 485 us: 31.90x faster                                                  |
| base32_small         | 5.69 ms                                                          | 203 us: 28.01x faster                                                  |
| base85_small         | 4.41 ms                                                          | 184 us: 23.94x faster                                                  |
| base16_large         | 31.6 ms                                                          | 7.10 ms: 4.45x faster                                                  |
| base64_large         | 6.32 ms                                                          | 1.53 ms: 4.12x faster                                                  |
| base16_small         | 656 us                                                           | 391 us: 1.68x faster                                                   |
| urlsafe_base64_small | 379 us                                                           | 248 us: 1.53x faster                                                   |
| tomli_loads          | 1.63 sec                                                         | 1.23 sec: 1.33x faster                                                 |
| json_dumps           | 7.49 ms                                                          | 5.96 ms: 1.26x faster                                                  |
| unpickle_pure_python | 149 us                                                           | 125 us: 1.19x faster                                                   |
| base64_small         | 228 us                                                           | 198 us: 1.15x faster                                                   |
| pickle_pure_python   | 223 us                                                           | 206 us: 1.08x faster                                                   |
| xml_etree_process    | 48.1 ms                                                          | 44.8 ms: 1.07x faster                                                  |
| xml_etree_generate   | 66.3 ms                                                          | 65.0 ms: 1.02x faster                                                  |
| xml_etree_parse      | 107 ms                                                           | 107 ms: 1.01x faster                                                   |
| pickle_dict          | 21.9 us                                                          | 22.5 us: 1.03x slower                                                  |
| unpickle             | 10.3 us                                                          | 10.6 us: 1.03x slower                                                  |
| unpickle_list        | 3.45 us                                                          | 3.58 us: 1.04x slower                                                  |
| xml_etree_iterparse  | 69.6 ms                                                          | 72.4 ms: 1.04x slower                                                  |
| json_loads           | 16.7 us                                                          | 17.6 us: 1.05x slower                                                  |
| pickle               | 8.22 us                                                          | 9.55 us: 1.16x slower                                                  |
| pickle_list          | 3.03 us                                                          | 3.73 us: 1.23x slower                                                  |
| Geometric mean       | (ref)                                                            | 3.05x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 5.95 ms: 1.07x faster                                                  |
| python_startup         | 9.38 ms                                                          | 9.54 ms: 1.02x slower                                                  |
| Geometric mean         | (ref)                                                            | 1.02x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| mako            | 7.43 ms                                                          | 7.10 ms: 1.05x faster                                                  |
| django_template | 27.3 ms                                                          | 31.8 ms: 1.17x slower                                                  |
| Geometric mean  | (ref)                                                            | 1.06x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 8.42 ms: 4.63x faster                                                  |
| thread_pipeline_naive       | 52.1 ms                                                          | 32.3 ms: 1.61x faster                                                  |
| thread_counter_naive        | 22.6 ms                                                          | 19.6 ms: 1.15x faster                                                  |
| thread_mandelbrot_naive     | 220 ms                                                           | 194 ms: 1.13x faster                                                   |
| thread_montecarlo_naive     | 17.8 ms                                                          | 16.1 ms: 1.11x faster                                                  |
| thread_mandelbrot_optimized | 218 ms                                                           | 198 ms: 1.10x faster                                                   |
| thread_montecarlo_optimized | 13.3 ms                                                          | 12.3 ms: 1.08x faster                                                  |
| thread_counter_optimized    | 18.7 ms                                                          | 18.3 ms: 1.02x faster                                                  |
| thread_memo_optimized       | 18.2 ms                                                          | 17.8 ms: 1.02x faster                                                  |
| thread_accumulate_naive     | 40.9 ms                                                          | 42.3 ms: 1.03x slower                                                  |
| thread_pipeline_optimized   | 25.6 ms                                                          | 27.0 ms: 1.05x slower                                                  |
| thread_accumulate_optimized | 39.8 ms                                                          | 42.4 ms: 1.07x slower                                                  |
| Geometric mean              | (ref)                                                            | 1.23x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 286 ms                                                           | 2.09 ms: 136.61x faster                                                |
| ascii85_large                    | 814 ms                                                           | 10.1 ms: 80.49x faster                                                 |
| base85_large                     | 243 ms                                                           | 3.24 ms: 74.94x faster                                                 |
| ascii85_small                    | 15.5 ms                                                          | 485 us: 31.90x faster                                                  |
| base32_small                     | 5.69 ms                                                          | 203 us: 28.01x faster                                                  |
| base85_small                     | 4.41 ms                                                          | 184 us: 23.94x faster                                                  |
| thread_memo_naive                | 39.0 ms                                                          | 8.42 ms: 4.63x faster                                                  |
| base16_large                     | 31.6 ms                                                          | 7.10 ms: 4.45x faster                                                  |
| base64_large                     | 6.32 ms                                                          | 1.53 ms: 4.12x faster                                                  |
| richards                         | 36.8 ms                                                          | 16.1 ms: 2.29x faster                                                  |
| pylint                           | 226 ms                                                           | 99.1 ms: 2.28x faster                                                  |
| richards_super                   | 41.3 ms                                                          | 18.2 ms: 2.27x faster                                                  |
| mdp                              | 2.11 sec                                                         | 964 ms: 2.19x faster                                                   |
| scimark_sor                      | 97.0 ms                                                          | 50.6 ms: 1.92x faster                                                  |
| deepcopy_memo                    | 26.6 us                                                          | 14.6 us: 1.83x faster                                                  |
| argparse_many_optionals          | 12.6 ms                                                          | 7.17 ms: 1.75x faster                                                  |
| base16_small                     | 656 us                                                           | 391 us: 1.68x faster                                                   |
| scimark_lu                       | 70.2 ms                                                          | 42.2 ms: 1.66x faster                                                  |
| thread_pipeline_naive            | 52.1 ms                                                          | 32.3 ms: 1.61x faster                                                  |
| nbody                            | 66.8 ms                                                          | 42.0 ms: 1.59x faster                                                  |
| urlsafe_base64_small             | 379 us                                                           | 248 us: 1.53x faster                                                   |
| go                               | 121 ms                                                           | 79.4 ms: 1.53x faster                                                  |
| spectral_norm                    | 64.1 ms                                                          | 42.2 ms: 1.52x faster                                                  |
| float                            | 56.6 ms                                                          | 37.7 ms: 1.50x faster                                                  |
| scimark_fft                      | 211 ms                                                           | 151 ms: 1.40x faster                                                   |
| fannkuch                         | 265 ms                                                           | 190 ms: 1.40x faster                                                   |
| pyflate                          | 358 ms                                                           | 261 ms: 1.37x faster                                                   |
| deepcopy                         | 267 us                                                           | 195 us: 1.37x faster                                                   |
| async_tree_memoization_tg        | 417 ms                                                           | 306 ms: 1.37x faster                                                   |
| async_tree_none                  | 310 ms                                                           | 228 ms: 1.36x faster                                                   |
| deltablue                        | 2.52 ms                                                          | 1.89 ms: 1.33x faster                                                  |
| async_tree_memoization           | 389 ms                                                           | 292 ms: 1.33x faster                                                   |
| tomli_loads                      | 1.63 sec                                                         | 1.23 sec: 1.33x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 581 ms: 1.27x faster                                                   |
| async_tree_eager_io              | 749 ms                                                           | 590 ms: 1.27x faster                                                   |
| json_dumps                       | 7.49 ms                                                          | 5.96 ms: 1.26x faster                                                  |
| async_tree_io_tg                 | 777 ms                                                           | 622 ms: 1.25x faster                                                   |
| nqueens                          | 57.3 ms                                                          | 46.0 ms: 1.25x faster                                                  |
| noop                             | 20.4 ns                                                          | 16.4 ns: 1.24x faster                                                  |
| async_tree_none_tg               | 289 ms                                                           | 234 ms: 1.24x faster                                                   |
| sqlglot_v2_parse                 | 953 us                                                           | 776 us: 1.23x faster                                                   |
| scimark_monte_carlo              | 44.3 ms                                                          | 36.5 ms: 1.21x faster                                                  |
| async_tree_eager                 | 90.0 ms                                                          | 74.3 ms: 1.21x faster                                                  |
| pathlib                          | 12.4 ms                                                          | 10.4 ms: 1.20x faster                                                  |
| async_tree_eager_memoization     | 215 ms                                                           | 180 ms: 1.19x faster                                                   |
| unpickle_pure_python             | 149 us                                                           | 125 us: 1.19x faster                                                   |
| regex_compile                    | 97.7 ms                                                          | 82.1 ms: 1.19x faster                                                  |
| asyncio_tcp                      | 326 ms                                                           | 274 ms: 1.19x faster                                                   |
| telco                            | 5.50 ms                                                          | 4.66 ms: 1.18x faster                                                  |
| quadtree_nbody                   | 620 ms                                                           | 526 ms: 1.18x faster                                                   |
| async_tree_eager_io_tg           | 724 ms                                                           | 624 ms: 1.16x faster                                                   |
| hexiom                           | 4.42 ms                                                          | 3.82 ms: 1.16x faster                                                  |
| deepcopy_reduce                  | 2.37 us                                                          | 2.05 us: 1.16x faster                                                  |
| bpe_tokeniser                    | 3.40 sec                                                         | 2.95 sec: 1.16x faster                                                 |
| thread_counter_naive             | 22.6 ms                                                          | 19.6 ms: 1.15x faster                                                  |
| base64_small                     | 228 us                                                           | 198 us: 1.15x faster                                                   |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.05 ms: 1.14x faster                                                  |
| comprehensions                   | 11.6 us                                                          | 10.2 us: 1.14x faster                                                  |
| coroutines                       | 17.6 ms                                                          | 15.4 ms: 1.14x faster                                                  |
| thrift                           | 2.07 ms                                                          | 1.82 ms: 1.13x faster                                                  |
| chaos                            | 45.0 ms                                                          | 39.8 ms: 1.13x faster                                                  |
| thread_mandelbrot_naive          | 220 ms                                                           | 194 ms: 1.13x faster                                                   |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 459 ms: 1.12x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 471 ms: 1.12x faster                                                   |
| logging_format                   | 5.23 us                                                          | 4.68 us: 1.12x faster                                                  |
| meteor_contest                   | 89.9 ms                                                          | 80.7 ms: 1.11x faster                                                  |
| thread_montecarlo_naive          | 17.8 ms                                                          | 16.1 ms: 1.11x faster                                                  |
| decimal_pi                       | 210 ms                                                           | 191 ms: 1.10x faster                                                   |
| xdsl_constant_fold               | 36.7 ms                                                          | 33.4 ms: 1.10x faster                                                  |
| thread_mandelbrot_optimized      | 218 ms                                                           | 198 ms: 1.10x faster                                                   |
| html5lib                         | 49.1 ms                                                          | 44.7 ms: 1.10x faster                                                  |
| sympy_expand                     | 330 ms                                                           | 301 ms: 1.10x faster                                                   |
| logging_simple                   | 4.60 us                                                          | 4.23 us: 1.09x faster                                                  |
| pprint_pformat                   | 1.11 sec                                                         | 1.02 sec: 1.09x faster                                                 |
| pprint_safe_repr                 | 541 ms                                                           | 499 ms: 1.09x faster                                                   |
| fastapi_http                     | 215 ms                                                           | 198 ms: 1.08x faster                                                   |
| pickle_pure_python               | 223 us                                                           | 206 us: 1.08x faster                                                   |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 12.3 ms: 1.08x faster                                                  |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.46 ms: 1.08x faster                                                  |
| networkx_connected_components    | 460 ms                                                           | 427 ms: 1.08x faster                                                   |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 37.3 ms: 1.07x faster                                                  |
| gc_traversal                     | 3.16 ms                                                          | 2.94 ms: 1.07x faster                                                  |
| xml_etree_process                | 48.1 ms                                                          | 44.8 ms: 1.07x faster                                                  |
| python_startup_no_site           | 6.36 ms                                                          | 5.95 ms: 1.07x faster                                                  |
| networkx_shortest_path           | 464 ms                                                           | 435 ms: 1.07x faster                                                   |
| chameleon                        | 10.9 ms                                                          | 10.3 ms: 1.06x faster                                                  |
| sqlalchemy_imperative            | 13.8 ms                                                          | 13.1 ms: 1.06x faster                                                  |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 75.4 ms: 1.05x faster                                                  |
| raytrace                         | 199 ms                                                           | 190 ms: 1.05x faster                                                   |
| mako                             | 7.43 ms                                                          | 7.10 ms: 1.05x faster                                                  |
| create_gc_cycles                 | 1.70 ms                                                          | 1.63 ms: 1.04x faster                                                  |
| argparse_subparsers              | 446 us                                                           | 429 us: 1.04x faster                                                   |
| sympy_str                        | 193 ms                                                           | 186 ms: 1.04x faster                                                   |
| json                             | 3.49 ms                                                          | 3.37 ms: 1.04x faster                                                  |
| generators                       | 22.0 ms                                                          | 21.2 ms: 1.04x faster                                                  |
| crypto_pyaes                     | 50.0 ms                                                          | 48.7 ms: 1.03x faster                                                  |
| decimal_factorial                | 173 ms                                                           | 168 ms: 1.03x faster                                                   |
| tornado_http                     | 99.2 ms                                                          | 96.9 ms: 1.02x faster                                                  |
| thread_counter_optimized         | 18.7 ms                                                          | 18.3 ms: 1.02x faster                                                  |
| thread_memo_optimized            | 18.2 ms                                                          | 17.8 ms: 1.02x faster                                                  |
| xml_etree_generate               | 66.3 ms                                                          | 65.0 ms: 1.02x faster                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.26 sec: 1.02x faster                                                 |
| docutils                         | 1.98 sec                                                         | 1.94 sec: 1.02x faster                                                 |
| regex_effbot                     | 1.99 ms                                                          | 1.96 ms: 1.02x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 354 ms: 1.02x faster                                                   |
| pycparser                        | 884 ms                                                           | 869 ms: 1.02x faster                                                   |
| sympy_integrate                  | 15.4 ms                                                          | 15.2 ms: 1.01x faster                                                  |
| typing_runtime_protocols         | 106 us                                                           | 104 us: 1.01x faster                                                   |
| logging_silent                   | 60.6 ns                                                          | 60.1 ns: 1.01x faster                                                  |
| regex_v8                         | 14.7 ms                                                          | 14.6 ms: 1.01x faster                                                  |
| xml_etree_parse                  | 107 ms                                                           | 107 ms: 1.01x faster                                                   |
| pidigits                         | 181 ms                                                           | 181 ms: 1.00x faster                                                   |
| regex_dna                        | 144 ms                                                           | 145 ms: 1.01x slower                                                   |
| python_startup                   | 9.38 ms                                                          | 9.54 ms: 1.02x slower                                                  |
| sympy_sum                        | 104 ms                                                           | 106 ms: 1.02x slower                                                   |
| async_generators                 | 262 ms                                                           | 268 ms: 1.03x slower                                                   |
| asyncio_websockets               | 304 ms                                                           | 311 ms: 1.03x slower                                                   |
| pickle_dict                      | 21.9 us                                                          | 22.5 us: 1.03x slower                                                  |
| unpickle                         | 10.3 us                                                          | 10.6 us: 1.03x slower                                                  |
| thread_accumulate_naive          | 40.9 ms                                                          | 42.3 ms: 1.03x slower                                                  |
| networkx_k_core                  | 2.15 sec                                                         | 2.23 sec: 1.04x slower                                                 |
| unpickle_list                    | 3.45 us                                                          | 3.58 us: 1.04x slower                                                  |
| xml_etree_iterparse              | 69.6 ms                                                          | 72.4 ms: 1.04x slower                                                  |
| thread_pipeline_optimized        | 25.6 ms                                                          | 27.0 ms: 1.05x slower                                                  |
| json_loads                       | 16.7 us                                                          | 17.6 us: 1.05x slower                                                  |
| thread_accumulate_optimized      | 39.8 ms                                                          | 42.4 ms: 1.07x slower                                                  |
| coverage                         | 52.2 ms                                                          | 56.8 ms: 1.09x slower                                                  |
| pickle                           | 8.22 us                                                          | 9.55 us: 1.16x slower                                                  |
| django_template                  | 27.3 ms                                                          | 31.8 ms: 1.17x slower                                                  |
| pickle_list                      | 3.03 us                                                          | 3.73 us: 1.23x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 428 ms: 1.33x slower                                                   |
| mypy2                            | 726 ms                                                           | 1.10 sec: 1.51x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 261 ms: 1.51x slower                                                   |
| unpack_sequence                  | 26.2 ns                                                          | 80.8 ns: 3.08x slower                                                  |
| async_tree_eager_tg              | 58.6 ms                                                          | 188 ms: 3.21x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.37x faster                                                           |
Ignored benchmarks (2) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.384x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.09x
- 95% likely to have a speedup of 1.09x
- 99% likely to have a speedup of 1.08x

# Memory
- memory change: 1.12x