# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.114x faster
- HPT reliability: 90.73%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.57x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 11.5 ms: 1.03x slower                                              |
| docutils       | 1.89 sec                                                           | 2.01 sec: 1.06x slower                                             |
| fastapi_http   | 215 ms                                                             | 195 ms: 1.11x faster                                               |
| html5lib       | 50.9 ms                                                            | 46.0 ms: 1.11x faster                                              |
| tornado_http   | 98.9 ms                                                            | 96.7 ms: 1.02x faster                                              |
| Geometric mean | (ref)                                                              | 1.03x faster                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_io_tg                 | 781 ms                                                             | 497 ms: 1.57x faster                                               |
| async_tree_memoization_tg        | 421 ms                                                             | 271 ms: 1.55x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 479 ms: 1.52x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 509 ms: 1.48x faster                                               |
| async_tree_io                    | 743 ms                                                             | 530 ms: 1.40x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 209 ms: 1.39x faster                                               |
| async_tree_none                  | 312 ms                                                             | 236 ms: 1.33x faster                                               |
| async_tree_memoization           | 392 ms                                                             | 304 ms: 1.29x faster                                               |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 413 ms: 1.23x faster                                               |
| coroutines                       | 18.2 ms                                                            | 15.4 ms: 1.18x faster                                              |
| async_tree_eager_memoization     | 221 ms                                                             | 192 ms: 1.15x faster                                               |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 445 ms: 1.11x faster                                               |
| asyncio_websockets               | 313 ms                                                             | 289 ms: 1.08x faster                                               |
| asyncio_tcp                      | 316 ms                                                             | 303 ms: 1.04x faster                                               |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 338 ms: 1.01x faster                                               |
| async_generators                 | 251 ms                                                             | 248 ms: 1.01x faster                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.39 sec: 1.09x slower                                             |
| async_tree_eager                 | 88.3 ms                                                            | 97.3 ms: 1.10x slower                                              |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 397 ms: 1.32x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 251 ms: 1.44x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 183 ms: 3.21x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.08x faster                                                       |

Benchmarks with tag 'baseline':
===============================

Benchmark hidden because not significant (1): noop

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                             | 188 ms: 1.06x slower                                               |
| decimal_pi        | 228 ms                                                             | 247 ms: 1.08x slower                                               |
| Geometric mean    | (ref)                                                              | 1.07x slower                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 55.0 ms: 1.08x faster                                              |
| pidigits       | 216 ms                                                             | 215 ms: 1.01x faster                                               |
| quadtree_nbody | 675 ms                                                             | 684 ms: 1.01x slower                                               |
| nbody          | 75.8 ms                                                            | 83.3 ms: 1.10x slower                                              |
| Geometric mean | (ref)                                                              | 1.01x slower                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 2.04 ms: 1.14x faster                                              |
| regex_v8       | 15.0 ms                                                            | 14.1 ms: 1.07x faster                                              |
| regex_dna      | 159 ms                                                             | 149 ms: 1.07x faster                                               |
| regex_compile  | 102 ms                                                             | 107 ms: 1.04x slower                                               |
| Geometric mean | (ref)                                                              | 1.06x faster                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.09 ms: 7.01x faster                                              |
| base16_small         | 836 us                                                             | 245 us: 3.42x faster                                               |
| xml_etree_iterparse  | 86.8 ms                                                            | 68.6 ms: 1.26x faster                                              |
| tomli_loads          | 1.77 sec                                                           | 1.53 sec: 1.15x faster                                             |
| ascii85_small        | 15.7 ms                                                            | 14.4 ms: 1.10x faster                                              |
| ascii85_large        | 824 ms                                                             | 753 ms: 1.09x faster                                               |
| xml_etree_parse      | 121 ms                                                             | 112 ms: 1.08x faster                                               |
| base32_small         | 6.46 ms                                                            | 6.05 ms: 1.07x faster                                              |
| base32_large         | 325 ms                                                             | 306 ms: 1.06x faster                                               |
| unpickle_list        | 3.42 us                                                            | 3.30 us: 1.04x faster                                              |
| base85_large         | 267 ms                                                             | 259 ms: 1.03x faster                                               |
| base64_small         | 222 us                                                             | 216 us: 1.03x faster                                               |
| xml_etree_generate   | 70.6 ms                                                            | 69.7 ms: 1.01x faster                                              |
| unpickle             | 10.8 us                                                            | 10.7 us: 1.01x faster                                              |
| base64_large         | 5.69 ms                                                            | 5.69 ms: 1.00x faster                                              |
| urlsafe_base64_small | 328 us                                                             | 331 us: 1.01x slower                                               |
| base85_small         | 4.85 ms                                                            | 4.93 ms: 1.02x slower                                              |
| xml_etree_process    | 49.9 ms                                                            | 51.0 ms: 1.02x slower                                              |
| unpickle_pure_python | 161 us                                                             | 165 us: 1.02x slower                                               |
| json_dumps           | 7.26 ms                                                            | 7.47 ms: 1.03x slower                                              |
| pickle_dict          | 19.0 us                                                            | 19.6 us: 1.03x slower                                              |
| pickle_pure_python   | 245 us                                                             | 259 us: 1.06x slower                                               |
| pickle               | 7.21 us                                                            | 7.76 us: 1.08x slower                                              |
| json_loads           | 18.2 us                                                            | 20.7 us: 1.14x slower                                              |
| pickle_list          | 2.66 us                                                            | 3.27 us: 1.23x slower                                              |
| Geometric mean       | (ref)                                                              | 1.15x faster                                                       |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                            | 11.7 ms: 1.23x slower                                              |
| python_startup_no_site | 6.49 ms                                                            | 8.20 ms: 1.26x slower                                              |
| Geometric mean         | (ref)                                                              | 1.24x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 20.2 ms: 1.04x faster                                              |
| genshi_xml      | 46.3 ms                                                            | 45.7 ms: 1.01x faster                                              |
| django_template | 28.8 ms                                                            | 33.3 ms: 1.16x slower                                              |
| mako            | 8.30 ms                                                            | 11.2 ms: 1.36x slower                                              |
| Geometric mean  | (ref)                                                              | 1.10x slower                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_counter_optimized    | 19.7 ms                                                            | 5.05 ms: 3.91x faster                                              |
| thread_pipeline_optimized   | 22.8 ms                                                            | 6.45 ms: 3.53x faster                                              |
| thread_mandelbrot_naive     | 190 ms                                                             | 54.1 ms: 3.50x faster                                              |
| thread_mandelbrot_optimized | 189 ms                                                             | 54.5 ms: 3.47x faster                                              |
| thread_accumulate_optimized | 35.3 ms                                                            | 10.2 ms: 3.46x faster                                              |
| thread_montecarlo_optimized | 14.2 ms                                                            | 4.36 ms: 3.25x faster                                              |
| thread_memo_optimized       | 16.8 ms                                                            | 5.53 ms: 3.04x faster                                              |
| thread_accumulate_naive     | 36.5 ms                                                            | 12.9 ms: 2.84x faster                                              |
| thread_pipeline_naive       | 49.8 ms                                                            | 26.3 ms: 1.90x faster                                              |
| thread_memo_naive           | 37.9 ms                                                            | 22.9 ms: 1.65x faster                                              |
| thread_counter_naive        | 23.7 ms                                                            | 20.3 ms: 1.17x faster                                              |
| thread_montecarlo_naive     | 18.1 ms                                                            | 25.5 ms: 1.41x slower                                              |
| Geometric mean              | (ref)                                                              | 2.43x faster                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.09 ms: 7.01x faster                                              |
| thread_counter_optimized         | 19.7 ms                                                            | 5.05 ms: 3.91x faster                                              |
| thread_pipeline_optimized        | 22.8 ms                                                            | 6.45 ms: 3.53x faster                                              |
| thread_mandelbrot_naive          | 190 ms                                                             | 54.1 ms: 3.50x faster                                              |
| thread_mandelbrot_optimized      | 189 ms                                                             | 54.5 ms: 3.47x faster                                              |
| thread_accumulate_optimized      | 35.3 ms                                                            | 10.2 ms: 3.46x faster                                              |
| base16_small                     | 836 us                                                             | 245 us: 3.42x faster                                               |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 4.36 ms: 3.25x faster                                              |
| thread_memo_optimized            | 16.8 ms                                                            | 5.53 ms: 3.04x faster                                              |
| thread_accumulate_naive          | 36.5 ms                                                            | 12.9 ms: 2.84x faster                                              |
| gc_traversal                     | 3.20 ms                                                            | 1.55 ms: 2.06x faster                                              |
| mdp                              | 2.05 sec                                                           | 1.03 sec: 2.00x faster                                             |
| thread_pipeline_naive            | 49.8 ms                                                            | 26.3 ms: 1.90x faster                                              |
| thread_memo_naive                | 37.9 ms                                                            | 22.9 ms: 1.65x faster                                              |
| async_tree_io_tg                 | 781 ms                                                             | 497 ms: 1.57x faster                                               |
| async_tree_memoization_tg        | 421 ms                                                             | 271 ms: 1.55x faster                                               |
| argparse_many_optionals          | 12.9 ms                                                            | 8.45 ms: 1.53x faster                                              |
| async_tree_eager_io_tg           | 731 ms                                                             | 479 ms: 1.52x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 509 ms: 1.48x faster                                               |
| create_gc_cycles                 | 1.77 ms                                                            | 1.23 ms: 1.44x faster                                              |
| async_tree_io                    | 743 ms                                                             | 530 ms: 1.40x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 209 ms: 1.39x faster                                               |
| async_tree_none                  | 312 ms                                                             | 236 ms: 1.33x faster                                               |
| go                               | 129 ms                                                             | 97.7 ms: 1.32x faster                                              |
| async_tree_memoization           | 392 ms                                                             | 304 ms: 1.29x faster                                               |
| xml_etree_iterparse              | 86.8 ms                                                            | 68.6 ms: 1.26x faster                                              |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 413 ms: 1.23x faster                                               |
| deepcopy_memo                    | 27.8 us                                                            | 23.3 us: 1.19x faster                                              |
| deepcopy                         | 267 us                                                             | 225 us: 1.18x faster                                               |
| coroutines                       | 18.2 ms                                                            | 15.4 ms: 1.18x faster                                              |
| thread_counter_naive             | 23.7 ms                                                            | 20.3 ms: 1.17x faster                                              |
| tomli_loads                      | 1.77 sec                                                           | 1.53 sec: 1.15x faster                                             |
| scimark_sor                      | 96.2 ms                                                            | 83.5 ms: 1.15x faster                                              |
| async_tree_eager_memoization     | 221 ms                                                             | 192 ms: 1.15x faster                                               |
| regex_effbot                     | 2.33 ms                                                            | 2.04 ms: 1.14x faster                                              |
| pyflate                          | 374 ms                                                             | 337 ms: 1.11x faster                                               |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 445 ms: 1.11x faster                                               |
| html5lib                         | 50.9 ms                                                            | 46.0 ms: 1.11x faster                                              |
| fastapi_http                     | 215 ms                                                             | 195 ms: 1.11x faster                                               |
| ascii85_small                    | 15.7 ms                                                            | 14.4 ms: 1.10x faster                                              |
| ascii85_large                    | 824 ms                                                             | 753 ms: 1.09x faster                                               |
| asyncio_websockets               | 313 ms                                                             | 289 ms: 1.08x faster                                               |
| xml_etree_parse                  | 121 ms                                                             | 112 ms: 1.08x faster                                               |
| float                            | 59.2 ms                                                            | 55.0 ms: 1.08x faster                                              |
| regex_v8                         | 15.0 ms                                                            | 14.1 ms: 1.07x faster                                              |
| base32_small                     | 6.46 ms                                                            | 6.05 ms: 1.07x faster                                              |
| regex_dna                        | 159 ms                                                             | 149 ms: 1.07x faster                                               |
| base32_large                     | 325 ms                                                             | 306 ms: 1.06x faster                                               |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.19 sec: 1.06x faster                                             |
| genshi_text                      | 21.1 ms                                                            | 20.2 ms: 1.04x faster                                              |
| asyncio_tcp                      | 316 ms                                                             | 303 ms: 1.04x faster                                               |
| unpickle_list                    | 3.42 us                                                            | 3.30 us: 1.04x faster                                              |
| base85_large                     | 267 ms                                                             | 259 ms: 1.03x faster                                               |
| pycparser                        | 901 ms                                                             | 875 ms: 1.03x faster                                               |
| base64_small                     | 222 us                                                             | 216 us: 1.03x faster                                               |
| tornado_http                     | 98.9 ms                                                            | 96.7 ms: 1.02x faster                                              |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 338 ms: 1.01x faster                                               |
| xml_etree_generate               | 70.6 ms                                                            | 69.7 ms: 1.01x faster                                              |
| deepcopy_reduce                  | 2.36 us                                                            | 2.33 us: 1.01x faster                                              |
| unpickle                         | 10.8 us                                                            | 10.7 us: 1.01x faster                                              |
| genshi_xml                       | 46.3 ms                                                            | 45.7 ms: 1.01x faster                                              |
| async_generators                 | 251 ms                                                             | 248 ms: 1.01x faster                                               |
| pidigits                         | 216 ms                                                             | 215 ms: 1.01x faster                                               |
| base64_large                     | 5.69 ms                                                            | 5.69 ms: 1.00x faster                                              |
| urlsafe_base64_small             | 328 us                                                             | 331 us: 1.01x slower                                               |
| thrift                           | 2.07 ms                                                            | 2.10 ms: 1.01x slower                                              |
| scimark_monte_carlo              | 47.2 ms                                                            | 47.8 ms: 1.01x slower                                              |
| quadtree_nbody                   | 675 ms                                                             | 684 ms: 1.01x slower                                               |
| networkx_connected_components    | 443 ms                                                             | 449 ms: 1.01x slower                                               |
| base85_small                     | 4.85 ms                                                            | 4.93 ms: 1.02x slower                                              |
| xml_etree_process                | 49.9 ms                                                            | 51.0 ms: 1.02x slower                                              |
| unpickle_pure_python             | 161 us                                                             | 165 us: 1.02x slower                                               |
| scimark_fft                      | 216 ms                                                             | 222 ms: 1.03x slower                                               |
| json_dumps                       | 7.26 ms                                                            | 7.47 ms: 1.03x slower                                              |
| richards                         | 38.2 ms                                                            | 39.3 ms: 1.03x slower                                              |
| pickle_dict                      | 19.0 us                                                            | 19.6 us: 1.03x slower                                              |
| chameleon                        | 11.1 ms                                                            | 11.5 ms: 1.03x slower                                              |
| json                             | 3.50 ms                                                            | 3.62 ms: 1.03x slower                                              |
| richards_super                   | 43.8 ms                                                            | 45.4 ms: 1.04x slower                                              |
| pathlib                          | 12.2 ms                                                            | 12.7 ms: 1.04x slower                                              |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 87.0 ms: 1.04x slower                                              |
| regex_compile                    | 102 ms                                                             | 107 ms: 1.04x slower                                               |
| networkx_shortest_path           | 454 ms                                                             | 473 ms: 1.04x slower                                               |
| hexiom                           | 4.75 ms                                                            | 4.96 ms: 1.05x slower                                              |
| chaos                            | 43.6 ms                                                            | 45.8 ms: 1.05x slower                                              |
| pickle_pure_python               | 245 us                                                             | 259 us: 1.06x slower                                               |
| sympy_integrate                  | 15.4 ms                                                            | 16.4 ms: 1.06x slower                                              |
| generators                       | 22.2 ms                                                            | 23.6 ms: 1.06x slower                                              |
| docutils                         | 1.89 sec                                                           | 2.01 sec: 1.06x slower                                             |
| decimal_factorial                | 177 ms                                                             | 188 ms: 1.06x slower                                               |
| pprint_safe_repr                 | 546 ms                                                             | 583 ms: 1.07x slower                                               |
| logging_simple                   | 5.06 us                                                            | 5.44 us: 1.08x slower                                              |
| pickle                           | 7.21 us                                                            | 7.76 us: 1.08x slower                                              |
| telco                            | 5.37 ms                                                            | 5.79 ms: 1.08x slower                                              |
| decimal_pi                       | 228 ms                                                             | 247 ms: 1.08x slower                                               |
| nqueens                          | 58.3 ms                                                            | 63.4 ms: 1.09x slower                                              |
| pprint_pformat                   | 1.13 sec                                                           | 1.22 sec: 1.09x slower                                             |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.39 sec: 1.09x slower                                             |
| mypy2                            | 741 ms                                                             | 808 ms: 1.09x slower                                               |
| xdsl_constant_fold               | 36.4 ms                                                            | 39.7 ms: 1.09x slower                                              |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.33 ms: 1.09x slower                                              |
| logging_silent                   | 60.1 ns                                                            | 65.7 ns: 1.09x slower                                              |
| logging_format                   | 5.62 us                                                            | 6.15 us: 1.09x slower                                              |
| nbody                            | 75.8 ms                                                            | 83.3 ms: 1.10x slower                                              |
| sympy_sum                        | 104 ms                                                             | 115 ms: 1.10x slower                                               |
| async_tree_eager                 | 88.3 ms                                                            | 97.3 ms: 1.10x slower                                              |
| comprehensions                   | 11.4 us                                                            | 12.7 us: 1.11x slower                                              |
| sympy_str                        | 193 ms                                                             | 215 ms: 1.11x slower                                               |
| sympy_expand                     | 331 ms                                                             | 372 ms: 1.12x slower                                               |
| raytrace                         | 197 ms                                                             | 222 ms: 1.13x slower                                               |
| meteor_contest                   | 85.7 ms                                                            | 96.6 ms: 1.13x slower                                              |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 3.22 ms: 1.13x slower                                              |
| sqlglot_v2_parse                 | 979 us                                                             | 1.11 ms: 1.13x slower                                              |
| crypto_pyaes                     | 55.6 ms                                                            | 63.1 ms: 1.13x slower                                              |
| json_loads                       | 18.2 us                                                            | 20.7 us: 1.14x slower                                              |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.9 ms: 1.15x slower                                              |
| deltablue                        | 2.59 ms                                                            | 2.97 ms: 1.15x slower                                              |
| django_template                  | 28.8 ms                                                            | 33.3 ms: 1.16x slower                                              |
| typing_runtime_protocols         | 112 us                                                             | 130 us: 1.16x slower                                               |
| argparse_subparsers              | 449 us                                                             | 528 us: 1.17x slower                                               |
| scimark_lu                       | 70.2 ms                                                            | 85.9 ms: 1.22x slower                                              |
| python_startup                   | 9.51 ms                                                            | 11.7 ms: 1.23x slower                                              |
| pickle_list                      | 2.66 us                                                            | 3.27 us: 1.23x slower                                              |
| python_startup_no_site           | 6.49 ms                                                            | 8.20 ms: 1.26x slower                                              |
| coverage                         | 55.0 ms                                                            | 69.8 ms: 1.27x slower                                              |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 397 ms: 1.32x slower                                               |
| unpack_sequence                  | 26.4 ns                                                            | 34.9 ns: 1.32x slower                                              |
| mako                             | 8.30 ms                                                            | 11.2 ms: 1.36x slower                                              |
| thread_montecarlo_naive          | 18.1 ms                                                            | 25.5 ms: 1.41x slower                                              |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 251 ms: 1.44x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 183 ms: 3.21x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.11x faster                                                       |

Benchmark hidden because not significant (6): pylint, networkx_k_core, fannkuch, sqlglot_v2_optimize, noop, spectral_norm

- Geometric mean (including insignificant results): 1.114x faster

# HPT report

- Reliability score: 90.73% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.57x