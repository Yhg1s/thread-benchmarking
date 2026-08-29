# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.117x faster
- HPT reliability: 90.77%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.59x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 11.7 ms: 1.07x slower                                                |
| docutils       | 1.98 sec                                                         | 2.11 sec: 1.07x slower                                               |
| fastapi_http   | 215 ms                                                           | 180 ms: 1.19x faster                                                 |
| html5lib       | 49.1 ms                                                          | 44.9 ms: 1.09x faster                                                |
| tornado_http   | 99.2 ms                                                          | 93.4 ms: 1.06x faster                                                |
| Geometric mean | (ref)                                                            | 1.04x faster                                                         |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| async_tree_io_tg                 | 777 ms                                                           | 465 ms: 1.67x faster                                                 |
| async_tree_eager_io_tg           | 724 ms                                                           | 458 ms: 1.58x faster                                                 |
| async_tree_memoization_tg        | 417 ms                                                           | 269 ms: 1.55x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 498 ms: 1.50x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 502 ms: 1.48x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 208 ms: 1.39x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 227 ms: 1.37x faster                                                 |
| async_tree_memoization           | 389 ms                                                           | 292 ms: 1.33x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 416 ms: 1.27x faster                                                 |
| asyncio_tcp                      | 326 ms                                                           | 269 ms: 1.21x faster                                                 |
| async_tree_eager_memoization     | 215 ms                                                           | 183 ms: 1.18x faster                                                 |
| coroutines                       | 17.6 ms                                                          | 15.0 ms: 1.17x faster                                                |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 441 ms: 1.17x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 335 ms: 1.07x faster                                                 |
| asyncio_websockets               | 304 ms                                                           | 285 ms: 1.07x faster                                                 |
| async_generators                 | 262 ms                                                           | 269 ms: 1.03x slower                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.35 sec: 1.05x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 401 ms: 1.25x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 249 ms: 1.44x slower                                                 |
| async_tree_eager_tg              | 58.6 ms                                                          | 183 ms: 3.12x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.12x faster                                                         |

Benchmark hidden because not significant (1): async_tree_eager

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 20.0 ns: 1.02x faster                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                           | 184 ms: 1.07x slower                                                 |
| decimal_pi        | 210 ms                                                           | 230 ms: 1.09x slower                                                 |
| Geometric mean    | (ref)                                                            | 1.08x slower                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 52.5 ms: 1.08x faster                                                |
| pidigits       | 181 ms                                                           | 178 ms: 1.02x faster                                                 |
| nbody          | 66.8 ms                                                          | 82.2 ms: 1.23x slower                                                |
| Geometric mean | (ref)                                                            | 1.03x slower                                                         |

Benchmark hidden because not significant (1): quadtree_nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_dna      | 144 ms                                                           | 145 ms: 1.01x slower                                                 |
| regex_compile  | 97.7 ms                                                          | 99.2 ms: 1.02x slower                                                |
| regex_effbot   | 1.99 ms                                                          | 2.03 ms: 1.02x slower                                                |
| regex_v8       | 14.7 ms                                                          | 15.3 ms: 1.04x slower                                                |
| Geometric mean | (ref)                                                            | 1.02x slower                                                         |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.09 ms: 6.21x faster                                                |
| base16_small         | 656 us                                                           | 300 us: 2.19x faster                                                 |
| base64_large         | 6.32 ms                                                          | 5.62 ms: 1.12x faster                                                |
| ascii85_small        | 15.5 ms                                                          | 14.1 ms: 1.10x faster                                                |
| ascii85_large        | 814 ms                                                           | 741 ms: 1.10x faster                                                 |
| xml_etree_parse      | 107 ms                                                           | 99.2 ms: 1.08x faster                                                |
| tomli_loads          | 1.63 sec                                                         | 1.51 sec: 1.08x faster                                               |
| base64_small         | 228 us                                                           | 212 us: 1.08x faster                                                 |
| xml_etree_iterparse  | 69.6 ms                                                          | 65.3 ms: 1.07x faster                                                |
| json_dumps           | 7.49 ms                                                          | 7.26 ms: 1.03x faster                                                |
| urlsafe_base64_small | 379 us                                                           | 369 us: 1.03x faster                                                 |
| pickle_dict          | 21.9 us                                                          | 21.4 us: 1.02x faster                                                |
| pickle_pure_python   | 223 us                                                           | 230 us: 1.03x slower                                                 |
| base32_small         | 5.69 ms                                                          | 5.90 ms: 1.04x slower                                                |
| base32_large         | 286 ms                                                           | 299 ms: 1.05x slower                                                 |
| pickle_list          | 3.03 us                                                          | 3.23 us: 1.07x slower                                                |
| unpickle_pure_python | 149 us                                                           | 159 us: 1.07x slower                                                 |
| base85_large         | 243 ms                                                           | 261 ms: 1.07x slower                                                 |
| pickle               | 8.22 us                                                          | 9.04 us: 1.10x slower                                                |
| base85_small         | 4.41 ms                                                          | 4.92 ms: 1.12x slower                                                |
| unpickle             | 10.3 us                                                          | 11.5 us: 1.12x slower                                                |
| xml_etree_process    | 48.1 ms                                                          | 53.9 ms: 1.12x slower                                                |
| xml_etree_generate   | 66.3 ms                                                          | 74.4 ms: 1.12x slower                                                |
| json_loads           | 16.7 us                                                          | 19.5 us: 1.17x slower                                                |
| unpickle_list        | 3.45 us                                                          | 4.71 us: 1.37x slower                                                |
| Geometric mean       | (ref)                                                            | 1.08x faster                                                         |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup         | 9.38 ms                                                          | 11.4 ms: 1.22x slower                                                |
| python_startup_no_site | 6.36 ms                                                          | 7.98 ms: 1.26x slower                                                |
| Geometric mean         | (ref)                                                            | 1.24x slower                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| genshi_xml      | 39.7 ms                                                          | 42.6 ms: 1.07x slower                                                |
| django_template | 27.3 ms                                                          | 30.0 ms: 1.10x slower                                                |
| genshi_text     | 17.6 ms                                                          | 19.7 ms: 1.12x slower                                                |
| mako            | 7.43 ms                                                          | 11.9 ms: 1.61x slower                                                |
| Geometric mean  | (ref)                                                            | 1.21x slower                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 220 ms                                                           | 58.9 ms: 3.74x faster                                                |
| thread_mandelbrot_optimized | 218 ms                                                           | 59.2 ms: 3.68x faster                                                |
| thread_pipeline_optimized   | 25.6 ms                                                          | 7.24 ms: 3.54x faster                                                |
| thread_accumulate_optimized | 39.8 ms                                                          | 11.7 ms: 3.39x faster                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 5.77 ms: 3.24x faster                                                |
| thread_memo_optimized       | 18.2 ms                                                          | 6.15 ms: 2.96x faster                                                |
| thread_accumulate_naive     | 40.9 ms                                                          | 13.9 ms: 2.94x faster                                                |
| thread_montecarlo_optimized | 13.3 ms                                                          | 4.66 ms: 2.86x faster                                                |
| thread_pipeline_naive       | 52.1 ms                                                          | 23.6 ms: 2.21x faster                                                |
| thread_memo_naive           | 39.0 ms                                                          | 21.0 ms: 1.86x faster                                                |
| thread_counter_naive        | 22.6 ms                                                          | 20.8 ms: 1.09x faster                                                |
| thread_montecarlo_naive     | 17.8 ms                                                          | 25.7 ms: 1.44x slower                                                |
| Geometric mean              | (ref)                                                            | 2.42x faster                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.09 ms: 6.21x faster                                                |
| thread_mandelbrot_naive          | 220 ms                                                           | 58.9 ms: 3.74x faster                                                |
| thread_mandelbrot_optimized      | 218 ms                                                           | 59.2 ms: 3.68x faster                                                |
| thread_pipeline_optimized        | 25.6 ms                                                          | 7.24 ms: 3.54x faster                                                |
| thread_accumulate_optimized      | 39.8 ms                                                          | 11.7 ms: 3.39x faster                                                |
| thread_counter_optimized         | 18.7 ms                                                          | 5.77 ms: 3.24x faster                                                |
| thread_memo_optimized            | 18.2 ms                                                          | 6.15 ms: 2.96x faster                                                |
| thread_accumulate_naive          | 40.9 ms                                                          | 13.9 ms: 2.94x faster                                                |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 4.66 ms: 2.86x faster                                                |
| thread_pipeline_naive            | 52.1 ms                                                          | 23.6 ms: 2.21x faster                                                |
| base16_small                     | 656 us                                                           | 300 us: 2.19x faster                                                 |
| mdp                              | 2.11 sec                                                         | 976 ms: 2.16x faster                                                 |
| gc_traversal                     | 3.16 ms                                                          | 1.47 ms: 2.14x faster                                                |
| thread_memo_naive                | 39.0 ms                                                          | 21.0 ms: 1.86x faster                                                |
| async_tree_io_tg                 | 777 ms                                                           | 465 ms: 1.67x faster                                                 |
| argparse_many_optionals          | 12.6 ms                                                          | 7.61 ms: 1.65x faster                                                |
| async_tree_eager_io_tg           | 724 ms                                                           | 458 ms: 1.58x faster                                                 |
| async_tree_memoization_tg        | 417 ms                                                           | 269 ms: 1.55x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 498 ms: 1.50x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 502 ms: 1.48x faster                                                 |
| deepcopy_memo                    | 26.6 us                                                          | 19.0 us: 1.40x faster                                                |
| async_tree_none_tg               | 289 ms                                                           | 208 ms: 1.39x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 227 ms: 1.37x faster                                                 |
| deepcopy                         | 267 us                                                           | 196 us: 1.36x faster                                                 |
| go                               | 121 ms                                                           | 89.4 ms: 1.36x faster                                                |
| async_tree_memoization           | 389 ms                                                           | 292 ms: 1.33x faster                                                 |
| create_gc_cycles                 | 1.70 ms                                                          | 1.29 ms: 1.32x faster                                                |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 416 ms: 1.27x faster                                                 |
| scimark_sor                      | 97.0 ms                                                          | 77.8 ms: 1.25x faster                                                |
| asyncio_tcp                      | 326 ms                                                           | 269 ms: 1.21x faster                                                 |
| fastapi_http                     | 215 ms                                                           | 180 ms: 1.19x faster                                                 |
| async_tree_eager_memoization     | 215 ms                                                           | 183 ms: 1.18x faster                                                 |
| coroutines                       | 17.6 ms                                                          | 15.0 ms: 1.17x faster                                                |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 441 ms: 1.17x faster                                                 |
| pathlib                          | 12.4 ms                                                          | 10.7 ms: 1.16x faster                                                |
| pyflate                          | 358 ms                                                           | 317 ms: 1.13x faster                                                 |
| base64_large                     | 6.32 ms                                                          | 5.62 ms: 1.12x faster                                                |
| pycparser                        | 884 ms                                                           | 802 ms: 1.10x faster                                                 |
| ascii85_small                    | 15.5 ms                                                          | 14.1 ms: 1.10x faster                                                |
| ascii85_large                    | 814 ms                                                           | 741 ms: 1.10x faster                                                 |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.11 sec: 1.09x faster                                               |
| html5lib                         | 49.1 ms                                                          | 44.9 ms: 1.09x faster                                                |
| thrift                           | 2.07 ms                                                          | 1.90 ms: 1.09x faster                                                |
| thread_counter_naive             | 22.6 ms                                                          | 20.8 ms: 1.09x faster                                                |
| xml_etree_parse                  | 107 ms                                                           | 99.2 ms: 1.08x faster                                                |
| float                            | 56.6 ms                                                          | 52.5 ms: 1.08x faster                                                |
| tomli_loads                      | 1.63 sec                                                         | 1.51 sec: 1.08x faster                                               |
| base64_small                     | 228 us                                                           | 212 us: 1.08x faster                                                 |
| pprint_safe_repr                 | 541 ms                                                           | 504 ms: 1.08x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 335 ms: 1.07x faster                                                 |
| deepcopy_reduce                  | 2.37 us                                                          | 2.22 us: 1.07x faster                                                |
| xml_etree_iterparse              | 69.6 ms                                                          | 65.3 ms: 1.07x faster                                                |
| asyncio_websockets               | 304 ms                                                           | 285 ms: 1.07x faster                                                 |
| tornado_http                     | 99.2 ms                                                          | 93.4 ms: 1.06x faster                                                |
| pprint_pformat                   | 1.11 sec                                                         | 1.06 sec: 1.04x faster                                               |
| telco                            | 5.50 ms                                                          | 5.29 ms: 1.04x faster                                                |
| pylint                           | 226 ms                                                           | 218 ms: 1.04x faster                                                 |
| json_dumps                       | 7.49 ms                                                          | 7.26 ms: 1.03x faster                                                |
| hexiom                           | 4.42 ms                                                          | 4.30 ms: 1.03x faster                                                |
| generators                       | 22.0 ms                                                          | 21.4 ms: 1.03x faster                                                |
| chaos                            | 45.0 ms                                                          | 43.9 ms: 1.03x faster                                                |
| urlsafe_base64_small             | 379 us                                                           | 369 us: 1.03x faster                                                 |
| logging_silent                   | 60.6 ns                                                          | 59.3 ns: 1.02x faster                                                |
| pickle_dict                      | 21.9 us                                                          | 21.4 us: 1.02x faster                                                |
| noop                             | 20.4 ns                                                          | 20.0 ns: 1.02x faster                                                |
| pidigits                         | 181 ms                                                           | 178 ms: 1.02x faster                                                 |
| comprehensions                   | 11.6 us                                                          | 11.6 us: 1.00x faster                                                |
| richards                         | 36.8 ms                                                          | 37.3 ms: 1.01x slower                                                |
| regex_dna                        | 144 ms                                                           | 145 ms: 1.01x slower                                                 |
| regex_compile                    | 97.7 ms                                                          | 99.2 ms: 1.02x slower                                                |
| regex_effbot                     | 1.99 ms                                                          | 2.03 ms: 1.02x slower                                                |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.22 ms: 1.02x slower                                                |
| sympy_integrate                  | 15.4 ms                                                          | 15.8 ms: 1.02x slower                                                |
| networkx_k_core                  | 2.15 sec                                                         | 2.20 sec: 1.02x slower                                               |
| async_generators                 | 262 ms                                                           | 269 ms: 1.03x slower                                                 |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 41.2 ms: 1.03x slower                                                |
| pickle_pure_python               | 223 us                                                           | 230 us: 1.03x slower                                                 |
| xdsl_constant_fold               | 36.7 ms                                                          | 37.8 ms: 1.03x slower                                                |
| sqlglot_v2_parse                 | 953 us                                                           | 985 us: 1.03x slower                                                 |
| scimark_monte_carlo              | 44.3 ms                                                          | 45.7 ms: 1.03x slower                                                |
| base32_small                     | 5.69 ms                                                          | 5.90 ms: 1.04x slower                                                |
| regex_v8                         | 14.7 ms                                                          | 15.3 ms: 1.04x slower                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.35 sec: 1.05x slower                                               |
| base32_large                     | 286 ms                                                           | 299 ms: 1.05x slower                                                 |
| sympy_sum                        | 104 ms                                                           | 109 ms: 1.05x slower                                                 |
| richards_super                   | 41.3 ms                                                          | 43.5 ms: 1.05x slower                                                |
| meteor_contest                   | 89.9 ms                                                          | 94.6 ms: 1.05x slower                                                |
| json                             | 3.49 ms                                                          | 3.69 ms: 1.06x slower                                                |
| sympy_str                        | 193 ms                                                           | 205 ms: 1.06x slower                                                 |
| scimark_lu                       | 70.2 ms                                                          | 74.5 ms: 1.06x slower                                                |
| logging_format                   | 5.23 us                                                          | 5.57 us: 1.06x slower                                                |
| decimal_factorial                | 173 ms                                                           | 184 ms: 1.07x slower                                                 |
| pickle_list                      | 3.03 us                                                          | 3.23 us: 1.07x slower                                                |
| docutils                         | 1.98 sec                                                         | 2.11 sec: 1.07x slower                                               |
| chameleon                        | 10.9 ms                                                          | 11.7 ms: 1.07x slower                                                |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.8 ms: 1.07x slower                                                |
| genshi_xml                       | 39.7 ms                                                          | 42.6 ms: 1.07x slower                                                |
| unpickle_pure_python             | 149 us                                                           | 159 us: 1.07x slower                                                 |
| base85_large                     | 243 ms                                                           | 261 ms: 1.07x slower                                                 |
| sympy_expand                     | 330 ms                                                           | 355 ms: 1.08x slower                                                 |
| logging_simple                   | 4.60 us                                                          | 4.96 us: 1.08x slower                                                |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 85.9 ms: 1.09x slower                                                |
| nqueens                          | 57.3 ms                                                          | 62.7 ms: 1.09x slower                                                |
| decimal_pi                       | 210 ms                                                           | 230 ms: 1.09x slower                                                 |
| raytrace                         | 199 ms                                                           | 218 ms: 1.09x slower                                                 |
| argparse_subparsers              | 446 us                                                           | 490 us: 1.10x slower                                                 |
| pickle                           | 8.22 us                                                          | 9.04 us: 1.10x slower                                                |
| django_template                  | 27.3 ms                                                          | 30.0 ms: 1.10x slower                                                |
| spectral_norm                    | 64.1 ms                                                          | 70.9 ms: 1.11x slower                                                |
| fannkuch                         | 265 ms                                                           | 295 ms: 1.11x slower                                                 |
| base85_small                     | 4.41 ms                                                          | 4.92 ms: 1.12x slower                                                |
| unpickle                         | 10.3 us                                                          | 11.5 us: 1.12x slower                                                |
| xml_etree_process                | 48.1 ms                                                          | 53.9 ms: 1.12x slower                                                |
| xml_etree_generate               | 66.3 ms                                                          | 74.4 ms: 1.12x slower                                                |
| genshi_text                      | 17.6 ms                                                          | 19.7 ms: 1.12x slower                                                |
| mypy2                            | 726 ms                                                           | 825 ms: 1.14x slower                                                 |
| networkx_connected_components    | 460 ms                                                           | 523 ms: 1.14x slower                                                 |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 3.04 ms: 1.15x slower                                                |
| networkx_shortest_path           | 464 ms                                                           | 539 ms: 1.16x slower                                                 |
| json_loads                       | 16.7 us                                                          | 19.5 us: 1.17x slower                                                |
| typing_runtime_protocols         | 106 us                                                           | 127 us: 1.20x slower                                                 |
| unpack_sequence                  | 26.2 ns                                                          | 31.5 ns: 1.20x slower                                                |
| python_startup                   | 9.38 ms                                                          | 11.4 ms: 1.22x slower                                                |
| nbody                            | 66.8 ms                                                          | 82.2 ms: 1.23x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 401 ms: 1.25x slower                                                 |
| python_startup_no_site           | 6.36 ms                                                          | 7.98 ms: 1.26x slower                                                |
| crypto_pyaes                     | 50.0 ms                                                          | 62.8 ms: 1.26x slower                                                |
| unpickle_list                    | 3.45 us                                                          | 4.71 us: 1.37x slower                                                |
| coverage                         | 52.2 ms                                                          | 74.4 ms: 1.43x slower                                                |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 249 ms: 1.44x slower                                                 |
| thread_montecarlo_naive          | 17.8 ms                                                          | 25.7 ms: 1.44x slower                                                |
| mako                             | 7.43 ms                                                          | 11.9 ms: 1.61x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                          | 183 ms: 3.12x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.12x faster                                                         |

Benchmark hidden because not significant (4): deltablue, scimark_fft, async_tree_eager, quadtree_nbody

- Geometric mean (including insignificant results): 1.117x faster

# HPT report

- Reliability score: 90.77% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.59x