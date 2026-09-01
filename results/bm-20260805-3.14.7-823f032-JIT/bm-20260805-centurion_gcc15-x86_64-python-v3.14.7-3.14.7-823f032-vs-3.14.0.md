# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.007x slower
- HPT reliability: 52.87%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 10.8 ms: 1.02x slower                                            |
| docutils       | 2.02 sec                                                         | 1.99 sec: 1.01x faster                                           |
| fastapi_http   | 215 ms                                                           | 205 ms: 1.05x faster                                             |
| Geometric mean | (ref)                                                            | 1.01x faster                                                     |

Benchmark hidden because not significant (2): html5lib, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| asyncio_tcp                      | 332 ms                                                           | 304 ms: 1.09x faster                                             |
| coroutines                       | 15.4 ms                                                          | 14.8 ms: 1.04x faster                                            |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 340 ms: 1.02x slower                                             |
| async_tree_eager                 | 78.8 ms                                                          | 84.4 ms: 1.07x slower                                            |
| async_tree_eager_memoization     | 175 ms                                                           | 189 ms: 1.08x slower                                             |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 464 ms: 1.08x slower                                             |
| async_generators                 | 243 ms                                                           | 264 ms: 1.09x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 419 ms: 1.09x slower                                             |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 476 ms: 1.09x slower                                             |
| async_tree_none                  | 223 ms                                                           | 255 ms: 1.14x slower                                             |
| async_tree_eager_tg              | 179 ms                                                           | 206 ms: 1.15x slower                                             |
| async_tree_eager_io              | 548 ms                                                           | 638 ms: 1.16x slower                                             |
| async_tree_memoization           | 274 ms                                                           | 321 ms: 1.17x slower                                             |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 278 ms: 1.18x slower                                             |
| async_tree_none_tg               | 221 ms                                                           | 263 ms: 1.19x slower                                             |
| async_tree_eager_io_tg           | 549 ms                                                           | 662 ms: 1.21x slower                                             |
| async_tree_memoization_tg        | 275 ms                                                           | 336 ms: 1.22x slower                                             |
| async_tree_io                    | 527 ms                                                           | 665 ms: 1.26x slower                                             |
| async_tree_io_tg                 | 529 ms                                                           | 681 ms: 1.29x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.11x slower                                                     |

Benchmark hidden because not significant (2): asyncio_tcp_ssl, asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 15.7 ns: 1.19x faster                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_pi     | 201 ms                                                           | 198 ms: 1.01x faster                                             |
| Geometric mean | (ref)                                                            | 1.01x faster                                                     |

Benchmark hidden because not significant (1): decimal_factorial

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| float          | 48.1 ms                                                          | 42.2 ms: 1.14x faster                                            |
| quadtree_nbody | 602 ms                                                           | 557 ms: 1.08x faster                                             |
| nbody          | 67.2 ms                                                          | 62.7 ms: 1.07x faster                                            |
| pidigits       | 181 ms                                                           | 181 ms: 1.00x faster                                             |
| Geometric mean | (ref)                                                            | 1.07x faster                                                     |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_effbot   | 1.80 ms                                                          | 1.77 ms: 1.01x faster                                            |
| regex_dna      | 141 ms                                                           | 139 ms: 1.01x faster                                             |
| regex_compile  | 91.6 ms                                                          | 92.1 ms: 1.00x slower                                            |
| regex_v8       | 15.0 ms                                                          | 15.4 ms: 1.03x slower                                            |
| Geometric mean | (ref)                                                            | 1.00x slower                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base64_large         | 6.31 ms                                                          | 5.04 ms: 1.25x faster                                            |
| unpickle_pure_python | 153 us                                                           | 131 us: 1.17x faster                                             |
| xml_etree_generate   | 71.1 ms                                                          | 65.0 ms: 1.09x faster                                            |
| base64_small         | 230 us                                                           | 213 us: 1.08x faster                                             |
| ascii85_small        | 12.5 ms                                                          | 11.6 ms: 1.08x faster                                            |
| xml_etree_process    | 50.0 ms                                                          | 46.7 ms: 1.07x faster                                            |
| urlsafe_base64_small | 383 us                                                           | 358 us: 1.07x faster                                             |
| base85_small         | 4.44 ms                                                          | 4.17 ms: 1.07x faster                                            |
| base85_large         | 233 ms                                                           | 220 ms: 1.06x faster                                             |
| tomli_loads          | 1.41 sec                                                         | 1.34 sec: 1.05x faster                                           |
| xml_etree_iterparse  | 76.5 ms                                                          | 74.1 ms: 1.03x faster                                            |
| ascii85_large        | 651 ms                                                           | 647 ms: 1.01x faster                                             |
| pickle_dict          | 21.3 us                                                          | 21.2 us: 1.00x faster                                            |
| unpickle_list        | 3.64 us                                                          | 3.66 us: 1.00x slower                                            |
| pickle               | 9.23 us                                                          | 9.29 us: 1.01x slower                                            |
| base32_large         | 276 ms                                                           | 278 ms: 1.01x slower                                             |
| json_dumps           | 7.37 ms                                                          | 7.48 ms: 1.01x slower                                            |
| unpickle             | 10.3 us                                                          | 10.5 us: 1.02x slower                                            |
| base32_small         | 5.43 ms                                                          | 5.56 ms: 1.02x slower                                            |
| xml_etree_parse      | 102 ms                                                           | 107 ms: 1.05x slower                                             |
| json_loads           | 17.3 us                                                          | 18.8 us: 1.09x slower                                            |
| base16_small         | 298 us                                                           | 334 us: 1.12x slower                                             |
| pickle_list          | 3.26 us                                                          | 3.87 us: 1.19x slower                                            |
| base16_large         | 5.41 ms                                                          | 7.44 ms: 1.38x slower                                            |
| Geometric mean       | (ref)                                                            | 1.01x faster                                                     |

Benchmark hidden because not significant (1): pickle_pure_python

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup_no_site | 6.29 ms                                                          | 6.35 ms: 1.01x slower                                            |
| python_startup         | 9.62 ms                                                          | 9.77 ms: 1.02x slower                                            |
| Geometric mean         | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| mako            | 7.66 ms                                                          | 7.44 ms: 1.03x faster                                            |
| genshi_text     | 16.4 ms                                                          | 16.2 ms: 1.01x faster                                            |
| django_template | 28.4 ms                                                          | 28.5 ms: 1.01x slower                                            |
| genshi_xml      | 38.4 ms                                                          | 39.2 ms: 1.02x slower                                            |
| Geometric mean  | (ref)                                                            | 1.00x faster                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_memo_naive           | 11.8 ms                                                          | 11.0 ms: 1.08x faster                                            |
| thread_counter_optimized    | 18.7 ms                                                          | 17.5 ms: 1.07x faster                                            |
| thread_counter_naive        | 21.4 ms                                                          | 20.3 ms: 1.05x faster                                            |
| thread_pipeline_optimized   | 26.3 ms                                                          | 25.0 ms: 1.05x faster                                            |
| thread_memo_optimized       | 17.9 ms                                                          | 17.1 ms: 1.05x faster                                            |
| thread_mandelbrot_naive     | 217 ms                                                           | 208 ms: 1.04x faster                                             |
| thread_accumulate_optimized | 40.8 ms                                                          | 39.2 ms: 1.04x faster                                            |
| thread_accumulate_naive     | 41.6 ms                                                          | 40.1 ms: 1.04x faster                                            |
| thread_mandelbrot_optimized | 215 ms                                                           | 209 ms: 1.03x faster                                             |
| thread_pipeline_naive       | 35.4 ms                                                          | 34.6 ms: 1.02x faster                                            |
| thread_montecarlo_optimized | 12.6 ms                                                          | 13.5 ms: 1.08x slower                                            |
| thread_montecarlo_naive     | 14.6 ms                                                          | 18.2 ms: 1.25x slower                                            |
| Geometric mean              | (ref)                                                            | 1.01x faster                                                     |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| argparse_many_optionals          | 33.3 ms                                                          | 7.47 ms: 4.45x faster                                            |
| argparse_subparsers              | 665 us                                                           | 505 us: 1.32x faster                                             |
| base64_large                     | 6.31 ms                                                          | 5.04 ms: 1.25x faster                                            |
| noop                             | 18.7 ns                                                          | 15.7 ns: 1.19x faster                                            |
| richards                         | 32.5 ms                                                          | 27.7 ms: 1.18x faster                                            |
| scimark_fft                      | 197 ms                                                           | 168 ms: 1.17x faster                                             |
| unpickle_pure_python             | 153 us                                                           | 131 us: 1.17x faster                                             |
| richards_super                   | 37.2 ms                                                          | 32.0 ms: 1.16x faster                                            |
| float                            | 48.1 ms                                                          | 42.2 ms: 1.14x faster                                            |
| deltablue                        | 2.24 ms                                                          | 1.97 ms: 1.14x faster                                            |
| xml_etree_generate               | 71.1 ms                                                          | 65.0 ms: 1.09x faster                                            |
| asyncio_tcp                      | 332 ms                                                           | 304 ms: 1.09x faster                                             |
| base64_small                     | 230 us                                                           | 213 us: 1.08x faster                                             |
| quadtree_nbody                   | 602 ms                                                           | 557 ms: 1.08x faster                                             |
| ascii85_small                    | 12.5 ms                                                          | 11.6 ms: 1.08x faster                                            |
| thread_memo_naive                | 11.8 ms                                                          | 11.0 ms: 1.08x faster                                            |
| spectral_norm                    | 59.6 ms                                                          | 55.5 ms: 1.07x faster                                            |
| nbody                            | 67.2 ms                                                          | 62.7 ms: 1.07x faster                                            |
| xml_etree_process                | 50.0 ms                                                          | 46.7 ms: 1.07x faster                                            |
| gc_traversal                     | 3.33 ms                                                          | 3.11 ms: 1.07x faster                                            |
| urlsafe_base64_small             | 383 us                                                           | 358 us: 1.07x faster                                             |
| thread_counter_optimized         | 18.7 ms                                                          | 17.5 ms: 1.07x faster                                            |
| base85_small                     | 4.44 ms                                                          | 4.17 ms: 1.07x faster                                            |
| create_gc_cycles                 | 1.93 ms                                                          | 1.82 ms: 1.06x faster                                            |
| base85_large                     | 233 ms                                                           | 220 ms: 1.06x faster                                             |
| deepcopy_reduce                  | 2.05 us                                                          | 1.93 us: 1.06x faster                                            |
| thread_counter_naive             | 21.4 ms                                                          | 20.3 ms: 1.05x faster                                            |
| thread_pipeline_optimized        | 26.3 ms                                                          | 25.0 ms: 1.05x faster                                            |
| fastapi_http                     | 215 ms                                                           | 205 ms: 1.05x faster                                             |
| tomli_loads                      | 1.41 sec                                                         | 1.34 sec: 1.05x faster                                           |
| thread_memo_optimized            | 17.9 ms                                                          | 17.1 ms: 1.05x faster                                            |
| thread_mandelbrot_naive          | 217 ms                                                           | 208 ms: 1.04x faster                                             |
| logging_simple                   | 4.72 us                                                          | 4.53 us: 1.04x faster                                            |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 2.48 ms: 1.04x faster                                            |
| thread_accumulate_optimized      | 40.8 ms                                                          | 39.2 ms: 1.04x faster                                            |
| thread_accumulate_naive          | 41.6 ms                                                          | 40.1 ms: 1.04x faster                                            |
| coroutines                       | 15.4 ms                                                          | 14.8 ms: 1.04x faster                                            |
| xml_etree_iterparse              | 76.5 ms                                                          | 74.1 ms: 1.03x faster                                            |
| scimark_sor                      | 72.8 ms                                                          | 70.4 ms: 1.03x faster                                            |
| fannkuch                         | 234 ms                                                           | 227 ms: 1.03x faster                                             |
| mako                             | 7.66 ms                                                          | 7.44 ms: 1.03x faster                                            |
| deepcopy                         | 195 us                                                           | 189 us: 1.03x faster                                             |
| coverage                         | 55.4 ms                                                          | 53.9 ms: 1.03x faster                                            |
| nqueens                          | 56.3 ms                                                          | 54.7 ms: 1.03x faster                                            |
| thread_mandelbrot_optimized      | 215 ms                                                           | 209 ms: 1.03x faster                                             |
| networkx_shortest_path           | 445 ms                                                           | 433 ms: 1.03x faster                                             |
| generators                       | 20.7 ms                                                          | 20.2 ms: 1.03x faster                                            |
| thread_pipeline_naive            | 35.4 ms                                                          | 34.6 ms: 1.02x faster                                            |
| networkx_connected_components    | 435 ms                                                           | 427 ms: 1.02x faster                                             |
| chaos                            | 41.9 ms                                                          | 41.1 ms: 1.02x faster                                            |
| logging_format                   | 5.24 us                                                          | 5.15 us: 1.02x faster                                            |
| genshi_text                      | 16.4 ms                                                          | 16.2 ms: 1.01x faster                                            |
| decimal_pi                       | 201 ms                                                           | 198 ms: 1.01x faster                                             |
| docutils                         | 2.02 sec                                                         | 1.99 sec: 1.01x faster                                           |
| regex_effbot                     | 1.80 ms                                                          | 1.77 ms: 1.01x faster                                            |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.05 sec: 1.01x faster                                           |
| regex_dna                        | 141 ms                                                           | 139 ms: 1.01x faster                                             |
| deepcopy_memo                    | 18.2 us                                                          | 18.1 us: 1.01x faster                                            |
| pyflate                          | 300 ms                                                           | 298 ms: 1.01x faster                                             |
| ascii85_large                    | 651 ms                                                           | 647 ms: 1.01x faster                                             |
| scimark_lu                       | 66.7 ms                                                          | 66.3 ms: 1.01x faster                                            |
| pickle_dict                      | 21.3 us                                                          | 21.2 us: 1.00x faster                                            |
| pidigits                         | 181 ms                                                           | 181 ms: 1.00x faster                                             |
| sympy_str                        | 192 ms                                                           | 192 ms: 1.00x slower                                             |
| unpickle_list                    | 3.64 us                                                          | 3.66 us: 1.00x slower                                            |
| raytrace                         | 194 ms                                                           | 195 ms: 1.00x slower                                             |
| regex_compile                    | 91.6 ms                                                          | 92.1 ms: 1.00x slower                                            |
| django_template                  | 28.4 ms                                                          | 28.5 ms: 1.01x slower                                            |
| scimark_monte_carlo              | 37.5 ms                                                          | 37.7 ms: 1.01x slower                                            |
| pathlib                          | 12.5 ms                                                          | 12.6 ms: 1.01x slower                                            |
| logging_silent                   | 59.7 ns                                                          | 60.1 ns: 1.01x slower                                            |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                             |
| pickle                           | 9.23 us                                                          | 9.29 us: 1.01x slower                                            |
| base32_large                     | 276 ms                                                           | 278 ms: 1.01x slower                                             |
| python_startup_no_site           | 6.29 ms                                                          | 6.35 ms: 1.01x slower                                            |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 78.8 ms: 1.01x slower                                            |
| sympy_integrate                  | 14.7 ms                                                          | 14.9 ms: 1.01x slower                                            |
| thrift                           | 1.84 ms                                                          | 1.86 ms: 1.01x slower                                            |
| json_dumps                       | 7.37 ms                                                          | 7.48 ms: 1.01x slower                                            |
| python_startup                   | 9.62 ms                                                          | 9.77 ms: 1.02x slower                                            |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 39.4 ms: 1.02x slower                                            |
| networkx_k_core                  | 2.07 sec                                                         | 2.10 sec: 1.02x slower                                           |
| telco                            | 5.26 ms                                                          | 5.35 ms: 1.02x slower                                            |
| unpickle                         | 10.3 us                                                          | 10.5 us: 1.02x slower                                            |
| chameleon                        | 10.6 ms                                                          | 10.8 ms: 1.02x slower                                            |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 340 ms: 1.02x slower                                             |
| genshi_xml                       | 38.4 ms                                                          | 39.2 ms: 1.02x slower                                            |
| meteor_contest                   | 83.9 ms                                                          | 85.8 ms: 1.02x slower                                            |
| sympy_expand                     | 330 ms                                                           | 338 ms: 1.02x slower                                             |
| base32_small                     | 5.43 ms                                                          | 5.56 ms: 1.02x slower                                            |
| typing_runtime_protocols         | 106 us                                                           | 109 us: 1.03x slower                                             |
| sqlglot_v2_parse                 | 909 us                                                           | 933 us: 1.03x slower                                             |
| regex_v8                         | 15.0 ms                                                          | 15.4 ms: 1.03x slower                                            |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.18 ms: 1.03x slower                                            |
| sqlalchemy_imperative            | 14.3 ms                                                          | 14.7 ms: 1.03x slower                                            |
| xdsl_constant_fold               | 35.1 ms                                                          | 36.5 ms: 1.04x slower                                            |
| json                             | 3.42 ms                                                          | 3.56 ms: 1.04x slower                                            |
| xml_etree_parse                  | 102 ms                                                           | 107 ms: 1.05x slower                                             |
| pylint                           | 215 ms                                                           | 227 ms: 1.06x slower                                             |
| crypto_pyaes                     | 51.5 ms                                                          | 54.4 ms: 1.06x slower                                            |
| pycparser                        | 837 ms                                                           | 890 ms: 1.06x slower                                             |
| async_tree_eager                 | 78.8 ms                                                          | 84.4 ms: 1.07x slower                                            |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 13.5 ms: 1.08x slower                                            |
| async_tree_eager_memoization     | 175 ms                                                           | 189 ms: 1.08x slower                                             |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 464 ms: 1.08x slower                                             |
| comprehensions                   | 11.2 us                                                          | 12.0 us: 1.08x slower                                            |
| json_loads                       | 17.3 us                                                          | 18.8 us: 1.09x slower                                            |
| async_generators                 | 243 ms                                                           | 264 ms: 1.09x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 419 ms: 1.09x slower                                             |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 476 ms: 1.09x slower                                             |
| hexiom                           | 4.00 ms                                                          | 4.40 ms: 1.10x slower                                            |
| base16_small                     | 298 us                                                           | 334 us: 1.12x slower                                             |
| async_tree_none                  | 223 ms                                                           | 255 ms: 1.14x slower                                             |
| async_tree_eager_tg              | 179 ms                                                           | 206 ms: 1.15x slower                                             |
| async_tree_eager_io              | 548 ms                                                           | 638 ms: 1.16x slower                                             |
| go                               | 82.6 ms                                                          | 96.6 ms: 1.17x slower                                            |
| async_tree_memoization           | 274 ms                                                           | 321 ms: 1.17x slower                                             |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 278 ms: 1.18x slower                                             |
| pickle_list                      | 3.26 us                                                          | 3.87 us: 1.19x slower                                            |
| async_tree_none_tg               | 221 ms                                                           | 263 ms: 1.19x slower                                             |
| async_tree_eager_io_tg           | 549 ms                                                           | 662 ms: 1.21x slower                                             |
| async_tree_memoization_tg        | 275 ms                                                           | 336 ms: 1.22x slower                                             |
| thread_montecarlo_naive          | 14.6 ms                                                          | 18.2 ms: 1.25x slower                                            |
| async_tree_io                    | 527 ms                                                           | 665 ms: 1.26x slower                                             |
| pprint_safe_repr                 | 484 ms                                                           | 620 ms: 1.28x slower                                             |
| async_tree_io_tg                 | 529 ms                                                           | 681 ms: 1.29x slower                                             |
| pprint_pformat                   | 982 ms                                                           | 1.27 sec: 1.30x slower                                           |
| base16_large                     | 5.41 ms                                                          | 7.44 ms: 1.38x slower                                            |
| mypy2                            | 756 ms                                                           | 1.04 sec: 1.38x slower                                           |
| unpack_sequence                  | 24.1 ns                                                          | 102 ns: 4.23x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.01x slower                                                     |

Benchmark hidden because not significant (7): html5lib, mdp, tornado_http, asyncio_tcp_ssl, decimal_factorial, pickle_pure_python, asyncio_websockets

- Geometric mean (including insignificant results): 1.007x slower

# HPT report

- Reliability score: 52.87% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.01x