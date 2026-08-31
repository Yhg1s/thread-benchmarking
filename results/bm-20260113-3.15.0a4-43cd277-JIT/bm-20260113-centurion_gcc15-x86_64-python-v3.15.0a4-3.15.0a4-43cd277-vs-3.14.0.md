# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.059x faster
- HPT reliability: 99.99%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.02x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| docutils       | 2.02 sec                                                         | 2.10 sec: 1.04x slower                                               |
| fastapi_http   | 215 ms                                                           | 200 ms: 1.08x faster                                                 |
| html5lib       | 45.5 ms                                                          | 43.2 ms: 1.05x faster                                                |
| tornado_http   | 101 ms                                                           | 99.3 ms: 1.01x faster                                                |
| Geometric mean | (ref)                                                            | 1.02x faster                                                         |

Benchmark hidden because not significant (1): chameleon

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| asyncio_tcp                      | 332 ms                                                           | 273 ms: 1.22x faster                                                 |
| async_tree_eager_io_tg           | 549 ms                                                           | 469 ms: 1.17x faster                                                 |
| async_tree_eager_io              | 548 ms                                                           | 468 ms: 1.17x faster                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 471 ms: 1.12x faster                                                 |
| async_tree_io                    | 527 ms                                                           | 476 ms: 1.11x faster                                                 |
| async_tree_memoization_tg        | 275 ms                                                           | 253 ms: 1.09x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 206 ms: 1.09x faster                                                 |
| async_tree_memoization           | 274 ms                                                           | 254 ms: 1.08x faster                                                 |
| async_tree_none_tg               | 221 ms                                                           | 207 ms: 1.07x faster                                                 |
| async_tree_eager_tg              | 179 ms                                                           | 170 ms: 1.05x faster                                                 |
| async_tree_eager_memoization     | 175 ms                                                           | 170 ms: 1.03x faster                                                 |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 229 ms: 1.03x faster                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.27 sec: 1.01x faster                                               |
| coroutines                       | 15.4 ms                                                          | 15.2 ms: 1.01x faster                                                |
| async_tree_eager                 | 78.8 ms                                                          | 78.3 ms: 1.01x faster                                                |
| asyncio_websockets               | 305 ms                                                           | 310 ms: 1.02x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 407 ms: 1.06x slower                                                 |
| async_generators                 | 243 ms                                                           | 258 ms: 1.06x slower                                                 |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 363 ms: 1.09x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.05x faster                                                         |

Benchmark hidden because not significant (2): async_tree_cpu_io_mixed, async_tree_cpu_io_mixed_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 16.7 ns: 1.12x faster                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_pi        | 201 ms                                                           | 191 ms: 1.05x faster                                                 |
| decimal_factorial | 170 ms                                                           | 171 ms: 1.00x slower                                                 |
| Geometric mean    | (ref)                                                            | 1.02x faster                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| nbody          | 67.2 ms                                                          | 49.0 ms: 1.37x faster                                                |
| float          | 48.1 ms                                                          | 38.7 ms: 1.24x faster                                                |
| quadtree_nbody | 602 ms                                                           | 517 ms: 1.16x faster                                                 |
| pidigits       | 181 ms                                                           | 181 ms: 1.00x faster                                                 |
| Geometric mean | (ref)                                                            | 1.19x faster                                                         |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_compile  | 91.6 ms                                                          | 81.2 ms: 1.13x faster                                                |
| regex_dna      | 141 ms                                                           | 139 ms: 1.01x faster                                                 |
| regex_v8       | 15.0 ms                                                          | 15.3 ms: 1.02x slower                                                |
| Geometric mean | (ref)                                                            | 1.03x faster                                                         |

Benchmark hidden because not significant (1): regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| unpickle_pure_python | 153 us                                                           | 116 us: 1.32x faster                                                 |
| urlsafe_base64_small | 383 us                                                           | 306 us: 1.25x faster                                                 |
| ascii85_large        | 651 ms                                                           | 536 ms: 1.21x faster                                                 |
| base64_small         | 230 us                                                           | 190 us: 1.21x faster                                                 |
| json_dumps           | 7.37 ms                                                          | 6.17 ms: 1.19x faster                                                |
| ascii85_small        | 12.5 ms                                                          | 10.6 ms: 1.18x faster                                                |
| xml_etree_generate   | 71.1 ms                                                          | 63.2 ms: 1.13x faster                                                |
| xml_etree_iterparse  | 76.5 ms                                                          | 68.0 ms: 1.12x faster                                                |
| pickle_pure_python   | 234 us                                                           | 208 us: 1.12x faster                                                 |
| xml_etree_process    | 50.0 ms                                                          | 45.1 ms: 1.11x faster                                                |
| base16_small         | 298 us                                                           | 269 us: 1.11x faster                                                 |
| base85_small         | 4.44 ms                                                          | 4.12 ms: 1.08x faster                                                |
| base64_large         | 6.31 ms                                                          | 5.86 ms: 1.08x faster                                                |
| base16_large         | 5.41 ms                                                          | 5.09 ms: 1.06x faster                                                |
| base85_large         | 233 ms                                                           | 225 ms: 1.04x faster                                                 |
| xml_etree_parse      | 102 ms                                                           | 99.4 ms: 1.03x faster                                                |
| unpickle_list        | 3.64 us                                                          | 3.55 us: 1.03x faster                                                |
| pickle               | 9.23 us                                                          | 9.19 us: 1.00x faster                                                |
| pickle_dict          | 21.3 us                                                          | 21.4 us: 1.01x slower                                                |
| tomli_loads          | 1.41 sec                                                         | 1.43 sec: 1.01x slower                                               |
| unpickle             | 10.3 us                                                          | 10.5 us: 1.01x slower                                                |
| json_loads           | 17.3 us                                                          | 17.6 us: 1.01x slower                                                |
| base32_small         | 5.43 ms                                                          | 5.53 ms: 1.02x slower                                                |
| base32_large         | 276 ms                                                           | 281 ms: 1.02x slower                                                 |
| Geometric mean       | (ref)                                                            | 1.08x faster                                                         |

Benchmark hidden because not significant (1): pickle_list

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 9.36 ms: 1.03x faster                                                |
| python_startup_no_site | 6.29 ms                                                          | 6.15 ms: 1.02x faster                                                |
| Geometric mean         | (ref)                                                            | 1.03x faster                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| mako            | 7.66 ms                                                          | 6.56 ms: 1.17x faster                                                |
| django_template | 28.4 ms                                                          | 28.8 ms: 1.01x slower                                                |
| genshi_text     | 16.4 ms                                                          | 16.9 ms: 1.03x slower                                                |
| genshi_xml      | 38.4 ms                                                          | 44.8 ms: 1.17x slower                                                |
| Geometric mean  | (ref)                                                            | 1.01x slower                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_memo_naive           | 11.8 ms                                                          | 8.90 ms: 1.33x faster                                                |
| thread_mandelbrot_naive     | 217 ms                                                           | 190 ms: 1.14x faster                                                 |
| thread_mandelbrot_optimized | 215 ms                                                           | 193 ms: 1.12x faster                                                 |
| thread_pipeline_naive       | 35.4 ms                                                          | 33.1 ms: 1.07x faster                                                |
| thread_counter_naive        | 21.4 ms                                                          | 20.6 ms: 1.04x faster                                                |
| thread_memo_optimized       | 17.9 ms                                                          | 17.5 ms: 1.03x faster                                                |
| thread_accumulate_naive     | 41.6 ms                                                          | 41.1 ms: 1.01x faster                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 18.9 ms: 1.01x slower                                                |
| thread_montecarlo_optimized | 12.6 ms                                                          | 13.3 ms: 1.05x slower                                                |
| thread_montecarlo_naive     | 14.6 ms                                                          | 16.4 ms: 1.12x slower                                                |
| Geometric mean              | (ref)                                                            | 1.04x faster                                                         |

Benchmark hidden because not significant (2): thread_pipeline_optimized, thread_accumulate_optimized

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| argparse_many_optionals          | 33.3 ms                                                          | 7.37 ms: 4.51x faster                                                |
| richards                         | 32.5 ms                                                          | 16.0 ms: 2.04x faster                                                |
| richards_super                   | 37.2 ms                                                          | 19.5 ms: 1.91x faster                                                |
| argparse_subparsers              | 665 us                                                           | 477 us: 1.40x faster                                                 |
| nbody                            | 67.2 ms                                                          | 49.0 ms: 1.37x faster                                                |
| thread_memo_naive                | 11.8 ms                                                          | 8.90 ms: 1.33x faster                                                |
| unpickle_pure_python             | 153 us                                                           | 116 us: 1.32x faster                                                 |
| scimark_fft                      | 197 ms                                                           | 153 ms: 1.28x faster                                                 |
| urlsafe_base64_small             | 383 us                                                           | 306 us: 1.25x faster                                                 |
| logging_silent                   | 59.7 ns                                                          | 47.9 ns: 1.25x faster                                                |
| float                            | 48.1 ms                                                          | 38.7 ms: 1.24x faster                                                |
| asyncio_tcp                      | 332 ms                                                           | 273 ms: 1.22x faster                                                 |
| ascii85_large                    | 651 ms                                                           | 536 ms: 1.21x faster                                                 |
| base64_small                     | 230 us                                                           | 190 us: 1.21x faster                                                 |
| scimark_monte_carlo              | 37.5 ms                                                          | 31.2 ms: 1.20x faster                                                |
| json_dumps                       | 7.37 ms                                                          | 6.17 ms: 1.19x faster                                                |
| pathlib                          | 12.5 ms                                                          | 10.6 ms: 1.18x faster                                                |
| ascii85_small                    | 12.5 ms                                                          | 10.6 ms: 1.18x faster                                                |
| pyflate                          | 300 ms                                                           | 254 ms: 1.18x faster                                                 |
| fannkuch                         | 234 ms                                                           | 199 ms: 1.18x faster                                                 |
| deepcopy_memo                    | 18.2 us                                                          | 15.5 us: 1.17x faster                                                |
| async_tree_eager_io_tg           | 549 ms                                                           | 469 ms: 1.17x faster                                                 |
| async_tree_eager_io              | 548 ms                                                           | 468 ms: 1.17x faster                                                 |
| mako                             | 7.66 ms                                                          | 6.56 ms: 1.17x faster                                                |
| deltablue                        | 2.24 ms                                                          | 1.92 ms: 1.17x faster                                                |
| telco                            | 5.26 ms                                                          | 4.51 ms: 1.17x faster                                                |
| quadtree_nbody                   | 602 ms                                                           | 517 ms: 1.16x faster                                                 |
| scimark_lu                       | 66.7 ms                                                          | 57.7 ms: 1.16x faster                                                |
| go                               | 82.6 ms                                                          | 71.7 ms: 1.15x faster                                                |
| thread_mandelbrot_naive          | 217 ms                                                           | 190 ms: 1.14x faster                                                 |
| spectral_norm                    | 59.6 ms                                                          | 52.4 ms: 1.14x faster                                                |
| regex_compile                    | 91.6 ms                                                          | 81.2 ms: 1.13x faster                                                |
| xml_etree_generate               | 71.1 ms                                                          | 63.2 ms: 1.13x faster                                                |
| xml_etree_iterparse              | 76.5 ms                                                          | 68.0 ms: 1.12x faster                                                |
| pickle_pure_python               | 234 us                                                           | 208 us: 1.12x faster                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 471 ms: 1.12x faster                                                 |
| noop                             | 18.7 ns                                                          | 16.7 ns: 1.12x faster                                                |
| thread_mandelbrot_optimized      | 215 ms                                                           | 193 ms: 1.12x faster                                                 |
| xml_etree_process                | 50.0 ms                                                          | 45.1 ms: 1.11x faster                                                |
| async_tree_io                    | 527 ms                                                           | 476 ms: 1.11x faster                                                 |
| base16_small                     | 298 us                                                           | 269 us: 1.11x faster                                                 |
| crypto_pyaes                     | 51.5 ms                                                          | 46.8 ms: 1.10x faster                                                |
| scimark_sor                      | 72.8 ms                                                          | 66.8 ms: 1.09x faster                                                |
| async_tree_memoization_tg        | 275 ms                                                           | 253 ms: 1.09x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 206 ms: 1.09x faster                                                 |
| networkx_k_core                  | 2.07 sec                                                         | 1.91 sec: 1.08x faster                                               |
| async_tree_memoization           | 274 ms                                                           | 254 ms: 1.08x faster                                                 |
| base85_small                     | 4.44 ms                                                          | 4.12 ms: 1.08x faster                                                |
| base64_large                     | 6.31 ms                                                          | 5.86 ms: 1.08x faster                                                |
| fastapi_http                     | 215 ms                                                           | 200 ms: 1.08x faster                                                 |
| bpe_tokeniser                    | 3.10 sec                                                         | 2.88 sec: 1.07x faster                                               |
| thread_pipeline_naive            | 35.4 ms                                                          | 33.1 ms: 1.07x faster                                                |
| async_tree_none_tg               | 221 ms                                                           | 207 ms: 1.07x faster                                                 |
| base16_large                     | 5.41 ms                                                          | 5.09 ms: 1.06x faster                                                |
| coverage                         | 55.4 ms                                                          | 52.7 ms: 1.05x faster                                                |
| html5lib                         | 45.5 ms                                                          | 43.2 ms: 1.05x faster                                                |
| async_tree_eager_tg              | 179 ms                                                           | 170 ms: 1.05x faster                                                 |
| decimal_pi                       | 201 ms                                                           | 191 ms: 1.05x faster                                                 |
| logging_simple                   | 4.72 us                                                          | 4.50 us: 1.05x faster                                                |
| json                             | 3.42 ms                                                          | 3.27 ms: 1.05x faster                                                |
| thread_counter_naive             | 21.4 ms                                                          | 20.6 ms: 1.04x faster                                                |
| chaos                            | 41.9 ms                                                          | 40.3 ms: 1.04x faster                                                |
| base85_large                     | 233 ms                                                           | 225 ms: 1.04x faster                                                 |
| sqlglot_v2_parse                 | 909 us                                                           | 881 us: 1.03x faster                                                 |
| meteor_contest                   | 83.9 ms                                                          | 81.4 ms: 1.03x faster                                                |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 2.51 ms: 1.03x faster                                                |
| python_startup                   | 9.62 ms                                                          | 9.36 ms: 1.03x faster                                                |
| xml_etree_parse                  | 102 ms                                                           | 99.4 ms: 1.03x faster                                                |
| async_tree_eager_memoization     | 175 ms                                                           | 170 ms: 1.03x faster                                                 |
| unpickle_list                    | 3.64 us                                                          | 3.55 us: 1.03x faster                                                |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 229 ms: 1.03x faster                                                 |
| thread_memo_optimized            | 17.9 ms                                                          | 17.5 ms: 1.03x faster                                                |
| python_startup_no_site           | 6.29 ms                                                          | 6.15 ms: 1.02x faster                                                |
| thrift                           | 1.84 ms                                                          | 1.81 ms: 1.02x faster                                                |
| raytrace                         | 194 ms                                                           | 191 ms: 1.02x faster                                                 |
| logging_format                   | 5.24 us                                                          | 5.17 us: 1.01x faster                                                |
| tornado_http                     | 101 ms                                                           | 99.3 ms: 1.01x faster                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.27 sec: 1.01x faster                                               |
| regex_dna                        | 141 ms                                                           | 139 ms: 1.01x faster                                                 |
| thread_accumulate_naive          | 41.6 ms                                                          | 41.1 ms: 1.01x faster                                                |
| pycparser                        | 837 ms                                                           | 828 ms: 1.01x faster                                                 |
| coroutines                       | 15.4 ms                                                          | 15.2 ms: 1.01x faster                                                |
| gc_traversal                     | 3.33 ms                                                          | 3.30 ms: 1.01x faster                                                |
| networkx_shortest_path           | 445 ms                                                           | 441 ms: 1.01x faster                                                 |
| networkx_connected_components    | 435 ms                                                           | 432 ms: 1.01x faster                                                 |
| async_tree_eager                 | 78.8 ms                                                          | 78.3 ms: 1.01x faster                                                |
| pickle                           | 9.23 us                                                          | 9.19 us: 1.00x faster                                                |
| pidigits                         | 181 ms                                                           | 181 ms: 1.00x faster                                                 |
| decimal_factorial                | 170 ms                                                           | 171 ms: 1.00x slower                                                 |
| pickle_dict                      | 21.3 us                                                          | 21.4 us: 1.01x slower                                                |
| create_gc_cycles                 | 1.93 ms                                                          | 1.94 ms: 1.01x slower                                                |
| tomli_loads                      | 1.41 sec                                                         | 1.43 sec: 1.01x slower                                               |
| thread_counter_optimized         | 18.7 ms                                                          | 18.9 ms: 1.01x slower                                                |
| unpickle                         | 10.3 us                                                          | 10.5 us: 1.01x slower                                                |
| json_loads                       | 17.3 us                                                          | 17.6 us: 1.01x slower                                                |
| django_template                  | 28.4 ms                                                          | 28.8 ms: 1.01x slower                                                |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.17 ms: 1.02x slower                                                |
| regex_v8                         | 15.0 ms                                                          | 15.3 ms: 1.02x slower                                                |
| base32_small                     | 5.43 ms                                                          | 5.53 ms: 1.02x slower                                                |
| asyncio_websockets               | 305 ms                                                           | 310 ms: 1.02x slower                                                 |
| comprehensions                   | 11.2 us                                                          | 11.4 us: 1.02x slower                                                |
| xdsl_constant_fold               | 35.1 ms                                                          | 35.8 ms: 1.02x slower                                                |
| base32_large                     | 276 ms                                                           | 281 ms: 1.02x slower                                                 |
| typing_runtime_protocols         | 106 us                                                           | 108 us: 1.02x slower                                                 |
| genshi_text                      | 16.4 ms                                                          | 16.9 ms: 1.03x slower                                                |
| deepcopy_reduce                  | 2.05 us                                                          | 2.11 us: 1.03x slower                                                |
| sqlalchemy_imperative            | 14.3 ms                                                          | 14.8 ms: 1.04x slower                                                |
| nqueens                          | 56.3 ms                                                          | 58.6 ms: 1.04x slower                                                |
| docutils                         | 2.02 sec                                                         | 2.10 sec: 1.04x slower                                               |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 13.3 ms: 1.05x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 407 ms: 1.06x slower                                                 |
| async_generators                 | 243 ms                                                           | 258 ms: 1.06x slower                                                 |
| pprint_safe_repr                 | 484 ms                                                           | 513 ms: 1.06x slower                                                 |
| sympy_expand                     | 330 ms                                                           | 350 ms: 1.06x slower                                                 |
| deepcopy                         | 195 us                                                           | 208 us: 1.07x slower                                                 |
| hexiom                           | 4.00 ms                                                          | 4.34 ms: 1.08x slower                                                |
| pprint_pformat                   | 982 ms                                                           | 1.07 sec: 1.09x slower                                               |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 363 ms: 1.09x slower                                                 |
| sympy_integrate                  | 14.7 ms                                                          | 16.2 ms: 1.10x slower                                                |
| thread_montecarlo_naive          | 14.6 ms                                                          | 16.4 ms: 1.12x slower                                                |
| sympy_sum                        | 104 ms                                                           | 117 ms: 1.13x slower                                                 |
| mypy2                            | 756 ms                                                           | 866 ms: 1.15x slower                                                 |
| sympy_str                        | 192 ms                                                           | 222 ms: 1.16x slower                                                 |
| genshi_xml                       | 38.4 ms                                                          | 44.8 ms: 1.17x slower                                                |
| mdp                              | 935 ms                                                           | 1.10 sec: 1.18x slower                                               |
| pylint                           | 215 ms                                                           | 261 ms: 1.21x slower                                                 |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 94.5 ms: 1.21x slower                                                |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 47.4 ms: 1.22x slower                                                |
| unpack_sequence                  | 24.1 ns                                                          | 63.5 ns: 2.64x slower                                                |
| Geometric mean                   | (ref)                                                            | 1.06x faster                                                         |

Benchmark hidden because not significant (8): async_tree_cpu_io_mixed, thread_pipeline_optimized, thread_accumulate_optimized, regex_effbot, pickle_list, chameleon, async_tree_cpu_io_mixed_tg, generators

- Geometric mean (including insignificant results): 1.059x faster

# HPT report

- Reliability score: 99.99% likely to be faster
- 90% likely to have a speedup of 1.01x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.02x