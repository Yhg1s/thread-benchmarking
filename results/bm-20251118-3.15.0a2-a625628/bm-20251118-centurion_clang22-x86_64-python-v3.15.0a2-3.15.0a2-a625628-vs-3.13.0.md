# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.057x faster
- HPT reliability: 97.30%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.11x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| docutils       | 1.89 sec                                                           | 1.99 sec: 1.05x slower                                                 |
| fastapi_http   | 215 ms                                                             | 222 ms: 1.03x slower                                                   |
| html5lib       | 50.9 ms                                                            | 46.5 ms: 1.10x faster                                                  |
| Geometric mean | (ref)                                                              | 1.00x faster                                                           |

Benchmark hidden because not significant (2): chameleon, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 274 ms: 1.54x faster                                                   |
| async_tree_io_tg                 | 781 ms                                                             | 509 ms: 1.54x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 482 ms: 1.52x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 513 ms: 1.47x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 510 ms: 1.46x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 217 ms: 1.44x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 279 ms: 1.41x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 208 ms: 1.39x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 401 ms: 1.26x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 178 ms: 1.24x faster                                                   |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 412 ms: 1.20x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 15.3 ms: 1.19x faster                                                  |
| async_generators                 | 251 ms                                                             | 225 ms: 1.11x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 301 ms: 1.05x faster                                                   |
| async_tree_eager                 | 88.3 ms                                                            | 85.0 ms: 1.04x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 333 ms: 1.03x faster                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.29 sec: 1.01x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 379 ms: 1.26x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 237 ms: 1.35x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 181 ms: 3.19x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.12x faster                                                           |

Benchmark hidden because not significant (1): asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 20.2 ns: 1.06x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 207 ms: 1.10x faster                                                   |
| decimal_factorial | 177 ms                                                             | 172 ms: 1.03x faster                                                   |
| Geometric mean    | (ref)                                                              | 1.06x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 54.9 ms: 1.08x faster                                                  |
| quadtree_nbody | 675 ms                                                             | 630 ms: 1.07x faster                                                   |
| pidigits       | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| Geometric mean | (ref)                                                              | 1.03x faster                                                           |

Benchmark hidden because not significant (1): nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 1.97 ms: 1.19x faster                                                  |
| regex_dna      | 159 ms                                                             | 146 ms: 1.09x faster                                                   |
| regex_compile  | 102 ms                                                             | 104 ms: 1.02x slower                                                   |
| Geometric mean | (ref)                                                              | 1.06x faster                                                           |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.11 ms: 6.99x faster                                                  |
| base16_small         | 836 us                                                             | 270 us: 3.10x faster                                                   |
| unpickle_list        | 3.42 us                                                            | 3.01 us: 1.14x faster                                                  |
| xml_etree_iterparse  | 86.8 ms                                                            | 77.2 ms: 1.12x faster                                                  |
| json_dumps           | 7.26 ms                                                            | 6.58 ms: 1.10x faster                                                  |
| base32_large         | 325 ms                                                             | 295 ms: 1.10x faster                                                   |
| base32_small         | 6.46 ms                                                            | 5.94 ms: 1.09x faster                                                  |
| ascii85_large        | 824 ms                                                             | 768 ms: 1.07x faster                                                   |
| ascii85_small        | 15.7 ms                                                            | 14.7 ms: 1.07x faster                                                  |
| tomli_loads          | 1.77 sec                                                           | 1.67 sec: 1.06x faster                                                 |
| json_loads           | 18.2 us                                                            | 17.4 us: 1.05x faster                                                  |
| unpickle             | 10.8 us                                                            | 10.4 us: 1.04x faster                                                  |
| xml_etree_parse      | 121 ms                                                             | 116 ms: 1.04x faster                                                   |
| xml_etree_generate   | 70.6 ms                                                            | 69.0 ms: 1.02x faster                                                  |
| base85_large         | 267 ms                                                             | 268 ms: 1.00x slower                                                   |
| pickle_dict          | 19.0 us                                                            | 19.2 us: 1.01x slower                                                  |
| base64_large         | 5.69 ms                                                            | 5.75 ms: 1.01x slower                                                  |
| xml_etree_process    | 49.9 ms                                                            | 50.4 ms: 1.01x slower                                                  |
| base85_small         | 4.85 ms                                                            | 4.94 ms: 1.02x slower                                                  |
| base64_small         | 222 us                                                             | 230 us: 1.04x slower                                                   |
| urlsafe_base64_small | 328 us                                                             | 350 us: 1.07x slower                                                   |
| pickle_pure_python   | 245 us                                                             | 263 us: 1.07x slower                                                   |
| unpickle_pure_python | 161 us                                                             | 174 us: 1.08x slower                                                   |
| pickle_list          | 2.66 us                                                            | 2.92 us: 1.10x slower                                                  |
| pickle               | 7.21 us                                                            | 8.00 us: 1.11x slower                                                  |
| Geometric mean       | (ref)                                                              | 1.15x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.37 ms: 1.02x faster                                                  |
| python_startup         | 9.51 ms                                                            | 9.60 ms: 1.01x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.01x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 19.2 ms: 1.10x faster                                                  |
| django_template | 28.8 ms                                                            | 31.6 ms: 1.10x slower                                                  |
| mako            | 8.30 ms                                                            | 9.41 ms: 1.13x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.03x slower                                                           |

Benchmark hidden because not significant (1): genshi_xml

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 10.9 ms: 3.46x faster                                                  |
| thread_pipeline_naive       | 49.8 ms                                                            | 36.6 ms: 1.36x faster                                                  |
| thread_montecarlo_naive     | 18.1 ms                                                            | 14.6 ms: 1.24x faster                                                  |
| thread_montecarlo_optimized | 14.2 ms                                                            | 12.8 ms: 1.11x faster                                                  |
| thread_mandelbrot_naive     | 190 ms                                                             | 189 ms: 1.01x faster                                                   |
| thread_counter_naive        | 23.7 ms                                                            | 23.8 ms: 1.00x slower                                                  |
| thread_counter_optimized    | 19.7 ms                                                            | 21.1 ms: 1.07x slower                                                  |
| thread_memo_optimized       | 16.8 ms                                                            | 18.4 ms: 1.09x slower                                                  |
| thread_accumulate_naive     | 36.5 ms                                                            | 42.2 ms: 1.16x slower                                                  |
| thread_accumulate_optimized | 35.3 ms                                                            | 41.2 ms: 1.17x slower                                                  |
| thread_pipeline_optimized   | 22.8 ms                                                            | 27.3 ms: 1.20x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.11x faster                                                           |

Benchmark hidden because not significant (1): thread_mandelbrot_optimized

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.11 ms: 6.99x faster                                                  |
| thread_memo_naive                | 37.9 ms                                                            | 10.9 ms: 3.46x faster                                                  |
| base16_small                     | 836 us                                                             | 270 us: 3.10x faster                                                   |
| mdp                              | 2.05 sec                                                           | 978 ms: 2.10x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 274 ms: 1.54x faster                                                   |
| async_tree_io_tg                 | 781 ms                                                             | 509 ms: 1.54x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 482 ms: 1.52x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 513 ms: 1.47x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 510 ms: 1.46x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 217 ms: 1.44x faster                                                   |
| deepcopy_memo                    | 27.8 us                                                            | 19.5 us: 1.43x faster                                                  |
| async_tree_memoization           | 392 ms                                                             | 279 ms: 1.41x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 208 ms: 1.39x faster                                                   |
| thread_pipeline_naive            | 49.8 ms                                                            | 36.6 ms: 1.36x faster                                                  |
| go                               | 129 ms                                                             | 96.5 ms: 1.34x faster                                                  |
| deepcopy                         | 267 us                                                             | 203 us: 1.31x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 401 ms: 1.26x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 178 ms: 1.24x faster                                                   |
| thread_montecarlo_naive          | 18.1 ms                                                            | 14.6 ms: 1.24x faster                                                  |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 412 ms: 1.20x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 15.3 ms: 1.19x faster                                                  |
| regex_effbot                     | 2.33 ms                                                            | 1.97 ms: 1.19x faster                                                  |
| pyflate                          | 374 ms                                                             | 324 ms: 1.15x faster                                                   |
| unpickle_list                    | 3.42 us                                                            | 3.01 us: 1.14x faster                                                  |
| pathlib                          | 12.2 ms                                                            | 10.8 ms: 1.13x faster                                                  |
| xml_etree_iterparse              | 86.8 ms                                                            | 77.2 ms: 1.12x faster                                                  |
| async_generators                 | 251 ms                                                             | 225 ms: 1.11x faster                                                   |
| deepcopy_reduce                  | 2.36 us                                                            | 2.13 us: 1.11x faster                                                  |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 12.8 ms: 1.11x faster                                                  |
| fannkuch                         | 287 ms                                                             | 260 ms: 1.10x faster                                                   |
| json_dumps                       | 7.26 ms                                                            | 6.58 ms: 1.10x faster                                                  |
| decimal_pi                       | 228 ms                                                             | 207 ms: 1.10x faster                                                   |
| genshi_text                      | 21.1 ms                                                            | 19.2 ms: 1.10x faster                                                  |
| base32_large                     | 325 ms                                                             | 295 ms: 1.10x faster                                                   |
| html5lib                         | 50.9 ms                                                            | 46.5 ms: 1.10x faster                                                  |
| regex_dna                        | 159 ms                                                             | 146 ms: 1.09x faster                                                   |
| richards_super                   | 43.8 ms                                                            | 40.3 ms: 1.09x faster                                                  |
| base32_small                     | 6.46 ms                                                            | 5.94 ms: 1.09x faster                                                  |
| telco                            | 5.37 ms                                                            | 4.96 ms: 1.08x faster                                                  |
| richards                         | 38.2 ms                                                            | 35.3 ms: 1.08x faster                                                  |
| spectral_norm                    | 68.6 ms                                                            | 63.5 ms: 1.08x faster                                                  |
| float                            | 59.2 ms                                                            | 54.9 ms: 1.08x faster                                                  |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.14 sec: 1.07x faster                                                 |
| ascii85_large                    | 824 ms                                                             | 768 ms: 1.07x faster                                                   |
| ascii85_small                    | 15.7 ms                                                            | 14.7 ms: 1.07x faster                                                  |
| quadtree_nbody                   | 675 ms                                                             | 630 ms: 1.07x faster                                                   |
| noop                             | 21.4 ns                                                            | 20.2 ns: 1.06x faster                                                  |
| tomli_loads                      | 1.77 sec                                                           | 1.67 sec: 1.06x faster                                                 |
| scimark_sor                      | 96.2 ms                                                            | 91.1 ms: 1.06x faster                                                  |
| scimark_monte_carlo              | 47.2 ms                                                            | 44.7 ms: 1.06x faster                                                  |
| scimark_fft                      | 216 ms                                                             | 206 ms: 1.05x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 301 ms: 1.05x faster                                                   |
| json_loads                       | 18.2 us                                                            | 17.4 us: 1.05x faster                                                  |
| unpickle                         | 10.8 us                                                            | 10.4 us: 1.04x faster                                                  |
| json                             | 3.50 ms                                                            | 3.36 ms: 1.04x faster                                                  |
| async_tree_eager                 | 88.3 ms                                                            | 85.0 ms: 1.04x faster                                                  |
| xml_etree_parse                  | 121 ms                                                             | 116 ms: 1.04x faster                                                   |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.75 ms: 1.04x faster                                                  |
| pylint                           | 226 ms                                                             | 219 ms: 1.03x faster                                                   |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 333 ms: 1.03x faster                                                   |
| decimal_factorial                | 177 ms                                                             | 172 ms: 1.03x faster                                                   |
| xml_etree_generate               | 70.6 ms                                                            | 69.0 ms: 1.02x faster                                                  |
| python_startup_no_site           | 6.49 ms                                                            | 6.37 ms: 1.02x faster                                                  |
| meteor_contest                   | 85.7 ms                                                            | 84.4 ms: 1.02x faster                                                  |
| thrift                           | 2.07 ms                                                            | 2.04 ms: 1.01x faster                                                  |
| comprehensions                   | 11.4 us                                                            | 11.3 us: 1.01x faster                                                  |
| thread_mandelbrot_naive          | 190 ms                                                             | 189 ms: 1.01x faster                                                   |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 42.0 ms: 1.00x faster                                                  |
| base85_large                     | 267 ms                                                             | 268 ms: 1.00x slower                                                   |
| pidigits                         | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| thread_counter_naive             | 23.7 ms                                                            | 23.8 ms: 1.00x slower                                                  |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.23 ms: 1.01x slower                                                  |
| pickle_dict                      | 19.0 us                                                            | 19.2 us: 1.01x slower                                                  |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.29 sec: 1.01x slower                                                 |
| python_startup                   | 9.51 ms                                                            | 9.60 ms: 1.01x slower                                                  |
| base64_large                     | 5.69 ms                                                            | 5.75 ms: 1.01x slower                                                  |
| xml_etree_process                | 49.9 ms                                                            | 50.4 ms: 1.01x slower                                                  |
| sqlglot_v2_parse                 | 979 us                                                             | 991 us: 1.01x slower                                                   |
| chaos                            | 43.6 ms                                                            | 44.2 ms: 1.01x slower                                                  |
| regex_compile                    | 102 ms                                                             | 104 ms: 1.02x slower                                                   |
| base85_small                     | 4.85 ms                                                            | 4.94 ms: 1.02x slower                                                  |
| pprint_pformat                   | 1.13 sec                                                           | 1.15 sec: 1.02x slower                                                 |
| logging_simple                   | 5.06 us                                                            | 5.17 us: 1.02x slower                                                  |
| crypto_pyaes                     | 55.6 ms                                                            | 57.0 ms: 1.02x slower                                                  |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 85.9 ms: 1.03x slower                                                  |
| pprint_safe_repr                 | 546 ms                                                             | 561 ms: 1.03x slower                                                   |
| pycparser                        | 901 ms                                                             | 930 ms: 1.03x slower                                                   |
| fastapi_http                     | 215 ms                                                             | 222 ms: 1.03x slower                                                   |
| raytrace                         | 197 ms                                                             | 204 ms: 1.03x slower                                                   |
| base64_small                     | 222 us                                                             | 230 us: 1.04x slower                                                   |
| logging_format                   | 5.62 us                                                            | 5.83 us: 1.04x slower                                                  |
| typing_runtime_protocols         | 112 us                                                             | 117 us: 1.04x slower                                                   |
| gc_traversal                     | 3.20 ms                                                            | 3.34 ms: 1.04x slower                                                  |
| docutils                         | 1.89 sec                                                           | 1.99 sec: 1.05x slower                                                 |
| mypy2                            | 741 ms                                                             | 782 ms: 1.05x slower                                                   |
| sympy_sum                        | 104 ms                                                             | 111 ms: 1.06x slower                                                   |
| nqueens                          | 58.3 ms                                                            | 62.2 ms: 1.07x slower                                                  |
| urlsafe_base64_small             | 328 us                                                             | 350 us: 1.07x slower                                                   |
| generators                       | 22.2 ms                                                            | 23.8 ms: 1.07x slower                                                  |
| thread_counter_optimized         | 19.7 ms                                                            | 21.1 ms: 1.07x slower                                                  |
| sympy_str                        | 193 ms                                                             | 207 ms: 1.07x slower                                                   |
| pickle_pure_python               | 245 us                                                             | 263 us: 1.07x slower                                                   |
| sympy_expand                     | 331 ms                                                             | 356 ms: 1.07x slower                                                   |
| unpickle_pure_python             | 161 us                                                             | 174 us: 1.08x slower                                                   |
| scimark_lu                       | 70.2 ms                                                            | 76.4 ms: 1.09x slower                                                  |
| logging_silent                   | 60.1 ns                                                            | 65.5 ns: 1.09x slower                                                  |
| thread_memo_optimized            | 16.8 ms                                                            | 18.4 ms: 1.09x slower                                                  |
| django_template                  | 28.8 ms                                                            | 31.6 ms: 1.10x slower                                                  |
| pickle_list                      | 2.66 us                                                            | 2.92 us: 1.10x slower                                                  |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.3 ms: 1.10x slower                                                  |
| pickle                           | 7.21 us                                                            | 8.00 us: 1.11x slower                                                  |
| deltablue                        | 2.59 ms                                                            | 2.90 ms: 1.12x slower                                                  |
| mako                             | 8.30 ms                                                            | 9.41 ms: 1.13x slower                                                  |
| create_gc_cycles                 | 1.77 ms                                                            | 2.02 ms: 1.14x slower                                                  |
| thread_accumulate_naive          | 36.5 ms                                                            | 42.2 ms: 1.16x slower                                                  |
| thread_accumulate_optimized      | 35.3 ms                                                            | 41.2 ms: 1.17x slower                                                  |
| thread_pipeline_optimized        | 22.8 ms                                                            | 27.3 ms: 1.20x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 379 ms: 1.26x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 237 ms: 1.35x slower                                                   |
| unpack_sequence                  | 26.4 ns                                                            | 36.2 ns: 1.37x slower                                                  |
| argparse_subparsers              | 449 us                                                             | 714 us: 1.59x slower                                                   |
| argparse_many_optionals          | 12.9 ms                                                            | 36.8 ms: 2.85x slower                                                  |
| async_tree_eager_tg              | 56.8 ms                                                            | 181 ms: 3.19x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.06x faster                                                           |

Benchmark hidden because not significant (11): hexiom, sympy_integrate, coverage, asyncio_websockets, genshi_xml, thread_mandelbrot_optimized, chameleon, regex_v8, tornado_http, xdsl_constant_fold, nbody
Ignored benchmarks (3) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json: networkx_connected_components, networkx_k_core, networkx_shortest_path

- Geometric mean (including insignificant results): 1.057x faster

# HPT report

- Reliability score: 97.30% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.11x