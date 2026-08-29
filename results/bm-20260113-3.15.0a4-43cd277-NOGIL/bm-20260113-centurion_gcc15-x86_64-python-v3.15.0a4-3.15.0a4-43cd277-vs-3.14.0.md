# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.037x faster
- HPT reliability: 99.96%
- HPT 99th percentile: 1.01x slower
- Memory change: 1.47x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 11.7 ms: 1.10x slower                                                |
| docutils       | 2.02 sec                                                         | 2.11 sec: 1.05x slower                                               |
| fastapi_http   | 215 ms                                                           | 180 ms: 1.20x faster                                                 |
| tornado_http   | 101 ms                                                           | 93.4 ms: 1.08x faster                                                |
| Geometric mean | (ref)                                                            | 1.03x faster                                                         |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| asyncio_tcp                      | 332 ms                                                           | 269 ms: 1.23x faster                                                 |
| async_tree_eager_io_tg           | 549 ms                                                           | 458 ms: 1.20x faster                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 465 ms: 1.14x faster                                                 |
| async_tree_eager_io              | 548 ms                                                           | 498 ms: 1.10x faster                                                 |
| asyncio_websockets               | 305 ms                                                           | 285 ms: 1.07x faster                                                 |
| async_tree_none_tg               | 221 ms                                                           | 208 ms: 1.06x faster                                                 |
| async_tree_io                    | 527 ms                                                           | 502 ms: 1.05x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 416 ms: 1.05x faster                                                 |
| coroutines                       | 15.4 ms                                                          | 15.0 ms: 1.03x faster                                                |
| async_tree_memoization_tg        | 275 ms                                                           | 269 ms: 1.02x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 335 ms: 1.01x slower                                                 |
| async_tree_none                  | 223 ms                                                           | 227 ms: 1.01x slower                                                 |
| async_tree_eager_tg              | 179 ms                                                           | 183 ms: 1.02x slower                                                 |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 441 ms: 1.03x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 401 ms: 1.04x slower                                                 |
| async_tree_eager_memoization     | 175 ms                                                           | 183 ms: 1.04x slower                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.35 sec: 1.05x slower                                               |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 249 ms: 1.06x slower                                                 |
| async_tree_memoization           | 274 ms                                                           | 292 ms: 1.06x slower                                                 |
| async_generators                 | 243 ms                                                           | 269 ms: 1.11x slower                                                 |
| async_tree_eager                 | 78.8 ms                                                          | 89.9 ms: 1.14x slower                                                |
| Geometric mean                   | (ref)                                                            | 1.02x faster                                                         |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 20.0 ns: 1.07x slower                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 184 ms: 1.08x slower                                                 |
| decimal_pi        | 201 ms                                                           | 230 ms: 1.14x slower                                                 |
| Geometric mean    | (ref)                                                            | 1.11x slower                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| pidigits       | 181 ms                                                           | 178 ms: 1.02x faster                                                 |
| quadtree_nbody | 602 ms                                                           | 623 ms: 1.03x slower                                                 |
| float          | 48.1 ms                                                          | 52.5 ms: 1.09x slower                                                |
| nbody          | 67.2 ms                                                          | 82.2 ms: 1.22x slower                                                |
| Geometric mean | (ref)                                                            | 1.08x slower                                                         |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                          | 15.3 ms: 1.02x slower                                                |
| regex_dna      | 141 ms                                                           | 145 ms: 1.03x slower                                                 |
| regex_compile  | 91.6 ms                                                          | 99.2 ms: 1.08x slower                                                |
| regex_effbot   | 1.80 ms                                                          | 2.03 ms: 1.13x slower                                                |
| Geometric mean | (ref)                                                            | 1.06x slower                                                         |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| xml_etree_iterparse  | 76.5 ms                                                          | 65.3 ms: 1.17x faster                                                |
| base64_large         | 6.31 ms                                                          | 5.62 ms: 1.12x faster                                                |
| base64_small         | 230 us                                                           | 212 us: 1.08x faster                                                 |
| base16_large         | 5.41 ms                                                          | 5.09 ms: 1.06x faster                                                |
| urlsafe_base64_small | 383 us                                                           | 369 us: 1.04x faster                                                 |
| xml_etree_parse      | 102 ms                                                           | 99.2 ms: 1.03x faster                                                |
| pickle               | 9.23 us                                                          | 9.04 us: 1.02x faster                                                |
| pickle_pure_python   | 234 us                                                           | 230 us: 1.02x faster                                                 |
| json_dumps           | 7.37 ms                                                          | 7.26 ms: 1.02x faster                                                |
| pickle_list          | 3.26 us                                                          | 3.23 us: 1.01x faster                                                |
| base16_small         | 298 us                                                           | 300 us: 1.01x slower                                                 |
| pickle_dict          | 21.3 us                                                          | 21.4 us: 1.01x slower                                                |
| unpickle_pure_python | 153 us                                                           | 159 us: 1.04x slower                                                 |
| xml_etree_generate   | 71.1 ms                                                          | 74.4 ms: 1.05x slower                                                |
| tomli_loads          | 1.41 sec                                                         | 1.51 sec: 1.07x slower                                               |
| xml_etree_process    | 50.0 ms                                                          | 53.9 ms: 1.08x slower                                                |
| base32_large         | 276 ms                                                           | 299 ms: 1.08x slower                                                 |
| base32_small         | 5.43 ms                                                          | 5.90 ms: 1.09x slower                                                |
| base85_small         | 4.44 ms                                                          | 4.92 ms: 1.11x slower                                                |
| unpickle             | 10.3 us                                                          | 11.5 us: 1.11x slower                                                |
| base85_large         | 233 ms                                                           | 261 ms: 1.12x slower                                                 |
| json_loads           | 17.3 us                                                          | 19.5 us: 1.13x slower                                                |
| ascii85_small        | 12.5 ms                                                          | 14.1 ms: 1.13x slower                                                |
| ascii85_large        | 651 ms                                                           | 741 ms: 1.14x slower                                                 |
| unpickle_list        | 3.64 us                                                          | 4.71 us: 1.29x slower                                                |
| Geometric mean       | (ref)                                                            | 1.03x slower                                                         |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 11.4 ms: 1.19x slower                                                |
| python_startup_no_site | 6.29 ms                                                          | 7.98 ms: 1.27x slower                                                |
| Geometric mean         | (ref)                                                            | 1.23x slower                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| django_template | 28.4 ms                                                          | 30.0 ms: 1.06x slower                                                |
| genshi_xml      | 38.4 ms                                                          | 42.6 ms: 1.11x slower                                                |
| genshi_text     | 16.4 ms                                                          | 19.7 ms: 1.20x slower                                                |
| mako            | 7.66 ms                                                          | 11.9 ms: 1.56x slower                                                |
| Geometric mean  | (ref)                                                            | 1.22x slower                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 217 ms                                                           | 58.9 ms: 3.69x faster                                                |
| thread_mandelbrot_optimized | 215 ms                                                           | 59.2 ms: 3.64x faster                                                |
| thread_pipeline_optimized   | 26.3 ms                                                          | 7.24 ms: 3.64x faster                                                |
| thread_accumulate_optimized | 40.8 ms                                                          | 11.7 ms: 3.48x faster                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 5.77 ms: 3.24x faster                                                |
| thread_accumulate_naive     | 41.6 ms                                                          | 13.9 ms: 2.99x faster                                                |
| thread_memo_optimized       | 17.9 ms                                                          | 6.15 ms: 2.91x faster                                                |
| thread_montecarlo_optimized | 12.6 ms                                                          | 4.66 ms: 2.70x faster                                                |
| thread_pipeline_naive       | 35.4 ms                                                          | 23.6 ms: 1.50x faster                                                |
| thread_counter_naive        | 21.4 ms                                                          | 20.8 ms: 1.03x faster                                                |
| thread_montecarlo_naive     | 14.6 ms                                                          | 25.7 ms: 1.76x slower                                                |
| thread_memo_naive           | 11.8 ms                                                          | 21.0 ms: 1.77x slower                                                |
| Geometric mean              | (ref)                                                            | 2.08x faster                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| argparse_many_optionals          | 33.3 ms                                                          | 7.61 ms: 4.37x faster                                                |
| thread_mandelbrot_naive          | 217 ms                                                           | 58.9 ms: 3.69x faster                                                |
| thread_mandelbrot_optimized      | 215 ms                                                           | 59.2 ms: 3.64x faster                                                |
| thread_pipeline_optimized        | 26.3 ms                                                          | 7.24 ms: 3.64x faster                                                |
| thread_accumulate_optimized      | 40.8 ms                                                          | 11.7 ms: 3.48x faster                                                |
| thread_counter_optimized         | 18.7 ms                                                          | 5.77 ms: 3.24x faster                                                |
| thread_accumulate_naive          | 41.6 ms                                                          | 13.9 ms: 2.99x faster                                                |
| thread_memo_optimized            | 17.9 ms                                                          | 6.15 ms: 2.91x faster                                                |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 4.66 ms: 2.70x faster                                                |
| gc_traversal                     | 3.33 ms                                                          | 1.47 ms: 2.26x faster                                                |
| thread_pipeline_naive            | 35.4 ms                                                          | 23.6 ms: 1.50x faster                                                |
| create_gc_cycles                 | 1.93 ms                                                          | 1.29 ms: 1.50x faster                                                |
| argparse_subparsers              | 665 us                                                           | 490 us: 1.36x faster                                                 |
| asyncio_tcp                      | 332 ms                                                           | 269 ms: 1.23x faster                                                 |
| async_tree_eager_io_tg           | 549 ms                                                           | 458 ms: 1.20x faster                                                 |
| fastapi_http                     | 215 ms                                                           | 180 ms: 1.20x faster                                                 |
| xml_etree_iterparse              | 76.5 ms                                                          | 65.3 ms: 1.17x faster                                                |
| pathlib                          | 12.5 ms                                                          | 10.7 ms: 1.17x faster                                                |
| async_tree_io_tg                 | 529 ms                                                           | 465 ms: 1.14x faster                                                 |
| base64_large                     | 6.31 ms                                                          | 5.62 ms: 1.12x faster                                                |
| async_tree_eager_io              | 548 ms                                                           | 498 ms: 1.10x faster                                                 |
| base64_small                     | 230 us                                                           | 212 us: 1.08x faster                                                 |
| tornado_http                     | 101 ms                                                           | 93.4 ms: 1.08x faster                                                |
| asyncio_websockets               | 305 ms                                                           | 285 ms: 1.07x faster                                                 |
| base16_large                     | 5.41 ms                                                          | 5.09 ms: 1.06x faster                                                |
| async_tree_none_tg               | 221 ms                                                           | 208 ms: 1.06x faster                                                 |
| async_tree_io                    | 527 ms                                                           | 502 ms: 1.05x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 416 ms: 1.05x faster                                                 |
| pycparser                        | 837 ms                                                           | 802 ms: 1.04x faster                                                 |
| urlsafe_base64_small             | 383 us                                                           | 369 us: 1.04x faster                                                 |
| xml_etree_parse                  | 102 ms                                                           | 99.2 ms: 1.03x faster                                                |
| thread_counter_naive             | 21.4 ms                                                          | 20.8 ms: 1.03x faster                                                |
| coroutines                       | 15.4 ms                                                          | 15.0 ms: 1.03x faster                                                |
| pickle                           | 9.23 us                                                          | 9.04 us: 1.02x faster                                                |
| async_tree_memoization_tg        | 275 ms                                                           | 269 ms: 1.02x faster                                                 |
| pickle_pure_python               | 234 us                                                           | 230 us: 1.02x faster                                                 |
| pidigits                         | 181 ms                                                           | 178 ms: 1.02x faster                                                 |
| json_dumps                       | 7.37 ms                                                          | 7.26 ms: 1.02x faster                                                |
| pickle_list                      | 3.26 us                                                          | 3.23 us: 1.01x faster                                                |
| logging_silent                   | 59.7 ns                                                          | 59.3 ns: 1.01x faster                                                |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.11 sec: 1.01x slower                                               |
| base16_small                     | 298 us                                                           | 300 us: 1.01x slower                                                 |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 335 ms: 1.01x slower                                                 |
| telco                            | 5.26 ms                                                          | 5.29 ms: 1.01x slower                                                |
| deepcopy                         | 195 us                                                           | 196 us: 1.01x slower                                                 |
| pickle_dict                      | 21.3 us                                                          | 21.4 us: 1.01x slower                                                |
| async_tree_none                  | 223 ms                                                           | 227 ms: 1.01x slower                                                 |
| regex_v8                         | 15.0 ms                                                          | 15.3 ms: 1.02x slower                                                |
| async_tree_eager_tg              | 179 ms                                                           | 183 ms: 1.02x slower                                                 |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 441 ms: 1.03x slower                                                 |
| regex_dna                        | 141 ms                                                           | 145 ms: 1.03x slower                                                 |
| generators                       | 20.7 ms                                                          | 21.4 ms: 1.03x slower                                                |
| quadtree_nbody                   | 602 ms                                                           | 623 ms: 1.03x slower                                                 |
| thrift                           | 1.84 ms                                                          | 1.90 ms: 1.03x slower                                                |
| sqlalchemy_imperative            | 14.3 ms                                                          | 14.8 ms: 1.04x slower                                                |
| comprehensions                   | 11.2 us                                                          | 11.6 us: 1.04x slower                                                |
| pprint_safe_repr                 | 484 ms                                                           | 504 ms: 1.04x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 401 ms: 1.04x slower                                                 |
| unpickle_pure_python             | 153 us                                                           | 159 us: 1.04x slower                                                 |
| deepcopy_memo                    | 18.2 us                                                          | 19.0 us: 1.04x slower                                                |
| mdp                              | 935 ms                                                           | 976 ms: 1.04x slower                                                 |
| async_tree_eager_memoization     | 175 ms                                                           | 183 ms: 1.04x slower                                                 |
| xml_etree_generate               | 71.1 ms                                                          | 74.4 ms: 1.05x slower                                                |
| docutils                         | 2.02 sec                                                         | 2.11 sec: 1.05x slower                                               |
| chaos                            | 41.9 ms                                                          | 43.9 ms: 1.05x slower                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.35 sec: 1.05x slower                                               |
| logging_simple                   | 4.72 us                                                          | 4.96 us: 1.05x slower                                                |
| sympy_sum                        | 104 ms                                                           | 109 ms: 1.05x slower                                                 |
| pyflate                          | 300 ms                                                           | 317 ms: 1.06x slower                                                 |
| django_template                  | 28.4 ms                                                          | 30.0 ms: 1.06x slower                                                |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 249 ms: 1.06x slower                                                 |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.22 ms: 1.06x slower                                                |
| logging_format                   | 5.24 us                                                          | 5.57 us: 1.06x slower                                                |
| async_tree_memoization           | 274 ms                                                           | 292 ms: 1.06x slower                                                 |
| scimark_fft                      | 197 ms                                                           | 210 ms: 1.06x slower                                                 |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 41.2 ms: 1.06x slower                                                |
| networkx_k_core                  | 2.07 sec                                                         | 2.20 sec: 1.07x slower                                               |
| scimark_sor                      | 72.8 ms                                                          | 77.8 ms: 1.07x slower                                                |
| sympy_str                        | 192 ms                                                           | 205 ms: 1.07x slower                                                 |
| noop                             | 18.7 ns                                                          | 20.0 ns: 1.07x slower                                                |
| sympy_integrate                  | 14.7 ms                                                          | 15.8 ms: 1.07x slower                                                |
| hexiom                           | 4.00 ms                                                          | 4.30 ms: 1.07x slower                                                |
| tomli_loads                      | 1.41 sec                                                         | 1.51 sec: 1.07x slower                                               |
| sympy_expand                     | 330 ms                                                           | 355 ms: 1.08x slower                                                 |
| xdsl_constant_fold               | 35.1 ms                                                          | 37.8 ms: 1.08x slower                                                |
| json                             | 3.42 ms                                                          | 3.69 ms: 1.08x slower                                                |
| xml_etree_process                | 50.0 ms                                                          | 53.9 ms: 1.08x slower                                                |
| pprint_pformat                   | 982 ms                                                           | 1.06 sec: 1.08x slower                                               |
| go                               | 82.6 ms                                                          | 89.4 ms: 1.08x slower                                                |
| regex_compile                    | 91.6 ms                                                          | 99.2 ms: 1.08x slower                                                |
| sqlglot_v2_parse                 | 909 us                                                           | 985 us: 1.08x slower                                                 |
| decimal_factorial                | 170 ms                                                           | 184 ms: 1.08x slower                                                 |
| deepcopy_reduce                  | 2.05 us                                                          | 2.22 us: 1.08x slower                                                |
| base32_large                     | 276 ms                                                           | 299 ms: 1.08x slower                                                 |
| base32_small                     | 5.43 ms                                                          | 5.90 ms: 1.09x slower                                                |
| mypy2                            | 756 ms                                                           | 825 ms: 1.09x slower                                                 |
| float                            | 48.1 ms                                                          | 52.5 ms: 1.09x slower                                                |
| chameleon                        | 10.6 ms                                                          | 11.7 ms: 1.10x slower                                                |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 85.9 ms: 1.10x slower                                                |
| base85_small                     | 4.44 ms                                                          | 4.92 ms: 1.11x slower                                                |
| async_generators                 | 243 ms                                                           | 269 ms: 1.11x slower                                                 |
| genshi_xml                       | 38.4 ms                                                          | 42.6 ms: 1.11x slower                                                |
| unpickle                         | 10.3 us                                                          | 11.5 us: 1.11x slower                                                |
| nqueens                          | 56.3 ms                                                          | 62.7 ms: 1.11x slower                                                |
| deltablue                        | 2.24 ms                                                          | 2.50 ms: 1.11x slower                                                |
| scimark_lu                       | 66.7 ms                                                          | 74.5 ms: 1.12x slower                                                |
| raytrace                         | 194 ms                                                           | 218 ms: 1.12x slower                                                 |
| base85_large                     | 233 ms                                                           | 261 ms: 1.12x slower                                                 |
| json_loads                       | 17.3 us                                                          | 19.5 us: 1.13x slower                                                |
| meteor_contest                   | 83.9 ms                                                          | 94.6 ms: 1.13x slower                                                |
| regex_effbot                     | 1.80 ms                                                          | 2.03 ms: 1.13x slower                                                |
| ascii85_small                    | 12.5 ms                                                          | 14.1 ms: 1.13x slower                                                |
| ascii85_large                    | 651 ms                                                           | 741 ms: 1.14x slower                                                 |
| decimal_pi                       | 201 ms                                                           | 230 ms: 1.14x slower                                                 |
| async_tree_eager                 | 78.8 ms                                                          | 89.9 ms: 1.14x slower                                                |
| richards                         | 32.5 ms                                                          | 37.3 ms: 1.14x slower                                                |
| richards_super                   | 37.2 ms                                                          | 43.5 ms: 1.17x slower                                                |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 3.04 ms: 1.18x slower                                                |
| spectral_norm                    | 59.6 ms                                                          | 70.9 ms: 1.19x slower                                                |
| python_startup                   | 9.62 ms                                                          | 11.4 ms: 1.19x slower                                                |
| typing_runtime_protocols         | 106 us                                                           | 127 us: 1.20x slower                                                 |
| genshi_text                      | 16.4 ms                                                          | 19.7 ms: 1.20x slower                                                |
| networkx_connected_components    | 435 ms                                                           | 523 ms: 1.20x slower                                                 |
| networkx_shortest_path           | 445 ms                                                           | 539 ms: 1.21x slower                                                 |
| crypto_pyaes                     | 51.5 ms                                                          | 62.8 ms: 1.22x slower                                                |
| scimark_monte_carlo              | 37.5 ms                                                          | 45.7 ms: 1.22x slower                                                |
| nbody                            | 67.2 ms                                                          | 82.2 ms: 1.22x slower                                                |
| fannkuch                         | 234 ms                                                           | 295 ms: 1.26x slower                                                 |
| python_startup_no_site           | 6.29 ms                                                          | 7.98 ms: 1.27x slower                                                |
| unpickle_list                    | 3.64 us                                                          | 4.71 us: 1.29x slower                                                |
| unpack_sequence                  | 24.1 ns                                                          | 31.5 ns: 1.31x slower                                                |
| coverage                         | 55.4 ms                                                          | 74.4 ms: 1.34x slower                                                |
| mako                             | 7.66 ms                                                          | 11.9 ms: 1.56x slower                                                |
| thread_montecarlo_naive          | 14.6 ms                                                          | 25.7 ms: 1.76x slower                                                |
| thread_memo_naive                | 11.8 ms                                                          | 21.0 ms: 1.77x slower                                                |
| Geometric mean                   | (ref)                                                            | 1.04x faster                                                         |

Benchmark hidden because not significant (2): html5lib, pylint

- Geometric mean (including insignificant results): 1.037x faster

# HPT report

- Reliability score: 99.96% likely to be slow
- 90% likely to have a slowdown of 1.03x
- 95% likely to have a slowdown of 1.02x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 1.47x