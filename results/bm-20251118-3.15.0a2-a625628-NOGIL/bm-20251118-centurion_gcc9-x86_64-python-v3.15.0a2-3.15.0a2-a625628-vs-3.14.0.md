# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.023x faster
- HPT reliability: 99.11%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.48x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 10.9 ms: 1.14x slower                                               |
| docutils       | 1.95 sec                                                        | 2.00 sec: 1.03x slower                                              |
| fastapi_http   | 216 ms                                                          | 190 ms: 1.14x faster                                                |
| tornado_http   | 101 ms                                                          | 92.7 ms: 1.09x faster                                               |
| Geometric mean | (ref)                                                           | 1.01x faster                                                        |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 550 ms                                                          | 385 ms: 1.43x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 385 ms: 1.40x faster                                                |
| async_tree_none_tg               | 223 ms                                                          | 168 ms: 1.33x faster                                                |
| async_tree_eager_io              | 552 ms                                                          | 420 ms: 1.32x faster                                                |
| async_tree_io                    | 531 ms                                                          | 422 ms: 1.26x faster                                                |
| async_tree_memoization_tg        | 277 ms                                                          | 226 ms: 1.23x faster                                                |
| async_tree_eager_tg              | 182 ms                                                          | 152 ms: 1.20x faster                                                |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 347 ms: 1.18x faster                                                |
| async_tree_none                  | 228 ms                                                          | 201 ms: 1.13x faster                                                |
| async_tree_memoization           | 281 ms                                                          | 250 ms: 1.12x faster                                                |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 211 ms: 1.12x faster                                                |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 372 ms: 1.09x faster                                                |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 332 ms: 1.09x faster                                                |
| asyncio_tcp                      | 325 ms                                                          | 299 ms: 1.08x faster                                                |
| async_tree_eager_memoization     | 180 ms                                                          | 172 ms: 1.05x faster                                                |
| asyncio_websockets               | 296 ms                                                          | 288 ms: 1.03x faster                                                |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 308 ms: 1.02x faster                                                |
| coroutines                       | 15.1 ms                                                         | 15.7 ms: 1.03x slower                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.37 sec: 1.07x slower                                              |
| async_generators                 | 228 ms                                                          | 248 ms: 1.09x slower                                                |
| async_tree_eager                 | 81.3 ms                                                         | 93.6 ms: 1.15x slower                                               |
| Geometric mean                   | (ref)                                                           | 1.12x faster                                                        |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 23.1 ns: 1.19x slower                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 189 ms: 1.09x slower                                                |
| decimal_pi        | 208 ms                                                          | 243 ms: 1.17x slower                                                |
| Geometric mean    | (ref)                                                           | 1.13x slower                                                        |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| float          | 47.3 ms                                                         | 51.1 ms: 1.08x slower                                               |
| quadtree_nbody | 596 ms                                                          | 652 ms: 1.09x slower                                                |
| nbody          | 67.9 ms                                                         | 82.2 ms: 1.21x slower                                               |
| Geometric mean | (ref)                                                           | 1.09x slower                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_dna      | 150 ms                                                          | 151 ms: 1.01x slower                                                |
| regex_effbot   | 1.95 ms                                                         | 2.01 ms: 1.03x slower                                               |
| regex_compile  | 93.9 ms                                                         | 105 ms: 1.12x slower                                                |
| Geometric mean | (ref)                                                           | 1.04x slower                                                        |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| xml_etree_iterparse  | 76.2 ms                                                         | 65.6 ms: 1.16x faster                                               |
| base16_large         | 5.33 ms                                                         | 4.76 ms: 1.12x faster                                               |
| base64_large         | 3.63 ms                                                         | 3.39 ms: 1.07x faster                                               |
| base64_small         | 186 us                                                          | 176 us: 1.05x faster                                                |
| base16_small         | 305 us                                                          | 295 us: 1.04x faster                                                |
| pickle_list          | 3.24 us                                                         | 3.14 us: 1.03x faster                                               |
| xml_etree_parse      | 94.3 ms                                                         | 92.7 ms: 1.02x faster                                               |
| urlsafe_base64_small | 329 us                                                          | 334 us: 1.02x slower                                                |
| pickle_dict          | 21.5 us                                                         | 22.2 us: 1.03x slower                                               |
| pickle               | 8.20 us                                                         | 8.54 us: 1.04x slower                                               |
| json_dumps           | 6.95 ms                                                         | 7.43 ms: 1.07x slower                                               |
| pickle_pure_python   | 240 us                                                          | 257 us: 1.07x slower                                                |
| unpickle_pure_python | 152 us                                                          | 163 us: 1.07x slower                                                |
| xml_etree_generate   | 62.6 ms                                                         | 67.8 ms: 1.08x slower                                               |
| base85_small         | 4.69 ms                                                         | 5.10 ms: 1.09x slower                                               |
| tomli_loads          | 1.44 sec                                                        | 1.58 sec: 1.10x slower                                              |
| json_loads           | 17.5 us                                                         | 19.2 us: 1.10x slower                                               |
| base32_large         | 292 ms                                                          | 325 ms: 1.11x slower                                                |
| xml_etree_process    | 44.7 ms                                                         | 49.9 ms: 1.12x slower                                               |
| base85_large         | 248 ms                                                          | 279 ms: 1.13x slower                                                |
| ascii85_small        | 12.7 ms                                                         | 14.3 ms: 1.13x slower                                               |
| ascii85_large        | 667 ms                                                          | 760 ms: 1.14x slower                                                |
| unpickle_list        | 3.43 us                                                         | 3.93 us: 1.15x slower                                               |
| base32_small         | 5.71 ms                                                         | 6.56 ms: 1.15x slower                                               |
| unpickle             | 10.2 us                                                         | 11.9 us: 1.17x slower                                               |
| Geometric mean       | (ref)                                                           | 1.05x slower                                                        |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 11.7 ms: 1.20x slower                                               |
| python_startup_no_site | 6.38 ms                                                         | 8.22 ms: 1.29x slower                                               |
| Geometric mean         | (ref)                                                           | 1.25x slower                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| genshi_xml      | 39.5 ms                                                         | 42.7 ms: 1.08x slower                                               |
| django_template | 27.8 ms                                                         | 31.0 ms: 1.11x slower                                               |
| genshi_text     | 16.8 ms                                                         | 19.3 ms: 1.15x slower                                               |
| mako            | 7.40 ms                                                         | 11.6 ms: 1.57x slower                                               |
| Geometric mean  | (ref)                                                           | 1.21x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 233 ms                                                          | 61.6 ms: 3.78x faster                                               |
| thread_mandelbrot_optimized | 233 ms                                                          | 63.1 ms: 3.69x faster                                               |
| thread_pipeline_optimized   | 22.5 ms                                                         | 6.58 ms: 3.41x faster                                               |
| thread_accumulate_optimized | 35.1 ms                                                         | 10.7 ms: 3.27x faster                                               |
| thread_counter_optimized    | 17.1 ms                                                         | 5.58 ms: 3.07x faster                                               |
| thread_accumulate_naive     | 35.8 ms                                                         | 12.8 ms: 2.80x faster                                               |
| thread_memo_optimized       | 15.9 ms                                                         | 5.70 ms: 2.79x faster                                               |
| thread_montecarlo_optimized | 13.9 ms                                                         | 5.02 ms: 2.77x faster                                               |
| thread_pipeline_naive       | 32.0 ms                                                         | 24.2 ms: 1.32x faster                                               |
| thread_counter_naive        | 20.2 ms                                                         | 20.5 ms: 1.01x slower                                               |
| thread_montecarlo_naive     | 15.8 ms                                                         | 30.1 ms: 1.90x slower                                               |
| thread_memo_naive           | 11.5 ms                                                         | 22.3 ms: 1.93x slower                                               |
| Geometric mean              | (ref)                                                           | 1.98x faster                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_mandelbrot_naive          | 233 ms                                                          | 61.6 ms: 3.78x faster                                               |
| thread_mandelbrot_optimized      | 233 ms                                                          | 63.1 ms: 3.69x faster                                               |
| thread_pipeline_optimized        | 22.5 ms                                                         | 6.58 ms: 3.41x faster                                               |
| thread_accumulate_optimized      | 35.1 ms                                                         | 10.7 ms: 3.27x faster                                               |
| thread_counter_optimized         | 17.1 ms                                                         | 5.58 ms: 3.07x faster                                               |
| thread_accumulate_naive          | 35.8 ms                                                         | 12.8 ms: 2.80x faster                                               |
| thread_memo_optimized            | 15.9 ms                                                         | 5.70 ms: 2.79x faster                                               |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 5.02 ms: 2.77x faster                                               |
| gc_traversal                     | 3.26 ms                                                         | 1.66 ms: 1.97x faster                                               |
| create_gc_cycles                 | 1.96 ms                                                         | 1.36 ms: 1.45x faster                                               |
| async_tree_eager_io_tg           | 550 ms                                                          | 385 ms: 1.43x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 385 ms: 1.40x faster                                                |
| async_tree_none_tg               | 223 ms                                                          | 168 ms: 1.33x faster                                                |
| thread_pipeline_naive            | 32.0 ms                                                         | 24.2 ms: 1.32x faster                                               |
| async_tree_eager_io              | 552 ms                                                          | 420 ms: 1.32x faster                                                |
| async_tree_io                    | 531 ms                                                          | 422 ms: 1.26x faster                                                |
| async_tree_memoization_tg        | 277 ms                                                          | 226 ms: 1.23x faster                                                |
| async_tree_eager_tg              | 182 ms                                                          | 152 ms: 1.20x faster                                                |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 347 ms: 1.18x faster                                                |
| xml_etree_iterparse              | 76.2 ms                                                         | 65.6 ms: 1.16x faster                                               |
| fastapi_http                     | 216 ms                                                          | 190 ms: 1.14x faster                                                |
| async_tree_none                  | 228 ms                                                          | 201 ms: 1.13x faster                                                |
| pathlib                          | 13.0 ms                                                         | 11.5 ms: 1.13x faster                                               |
| async_tree_memoization           | 281 ms                                                          | 250 ms: 1.12x faster                                                |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 211 ms: 1.12x faster                                                |
| base16_large                     | 5.33 ms                                                         | 4.76 ms: 1.12x faster                                               |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 372 ms: 1.09x faster                                                |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 332 ms: 1.09x faster                                                |
| tornado_http                     | 101 ms                                                          | 92.7 ms: 1.09x faster                                               |
| asyncio_tcp                      | 325 ms                                                          | 299 ms: 1.08x faster                                                |
| base64_large                     | 3.63 ms                                                         | 3.39 ms: 1.07x faster                                               |
| base64_small                     | 186 us                                                          | 176 us: 1.05x faster                                                |
| async_tree_eager_memoization     | 180 ms                                                          | 172 ms: 1.05x faster                                                |
| base16_small                     | 305 us                                                          | 295 us: 1.04x faster                                                |
| pycparser                        | 851 ms                                                          | 824 ms: 1.03x faster                                                |
| pickle_list                      | 3.24 us                                                         | 3.14 us: 1.03x faster                                               |
| asyncio_websockets               | 296 ms                                                          | 288 ms: 1.03x faster                                                |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 308 ms: 1.02x faster                                                |
| xml_etree_parse                  | 94.3 ms                                                         | 92.7 ms: 1.02x faster                                               |
| pidigits                         | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| regex_dna                        | 150 ms                                                          | 151 ms: 1.01x slower                                                |
| thread_counter_naive             | 20.2 ms                                                         | 20.5 ms: 1.01x slower                                               |
| urlsafe_base64_small             | 329 us                                                          | 334 us: 1.02x slower                                                |
| logging_silent                   | 65.3 ns                                                         | 66.4 ns: 1.02x slower                                               |
| telco                            | 5.59 ms                                                         | 5.73 ms: 1.02x slower                                               |
| mypy2                            | 753 ms                                                          | 774 ms: 1.03x slower                                                |
| docutils                         | 1.95 sec                                                        | 2.00 sec: 1.03x slower                                              |
| scimark_fft                      | 226 ms                                                          | 233 ms: 1.03x slower                                                |
| pickle_dict                      | 21.5 us                                                         | 22.2 us: 1.03x slower                                               |
| coroutines                       | 15.1 ms                                                         | 15.7 ms: 1.03x slower                                               |
| regex_effbot                     | 1.95 ms                                                         | 2.01 ms: 1.03x slower                                               |
| pylint                           | 216 ms                                                          | 224 ms: 1.04x slower                                                |
| pickle                           | 8.20 us                                                         | 8.54 us: 1.04x slower                                               |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.14 sec: 1.05x slower                                              |
| argparse_subparsers              | 686 us                                                          | 718 us: 1.05x slower                                                |
| json                             | 3.42 ms                                                         | 3.60 ms: 1.05x slower                                               |
| generators                       | 20.3 ms                                                         | 21.4 ms: 1.05x slower                                               |
| mdp                              | 946 ms                                                          | 999 ms: 1.06x slower                                                |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 83.1 ms: 1.06x slower                                               |
| sympy_sum                        | 106 ms                                                          | 113 ms: 1.07x slower                                                |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 41.7 ms: 1.07x slower                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.37 sec: 1.07x slower                                              |
| json_dumps                       | 6.95 ms                                                         | 7.43 ms: 1.07x slower                                               |
| pickle_pure_python               | 240 us                                                          | 257 us: 1.07x slower                                                |
| thrift                           | 1.86 ms                                                         | 2.00 ms: 1.07x slower                                               |
| unpickle_pure_python             | 152 us                                                          | 163 us: 1.07x slower                                                |
| argparse_many_optionals          | 34.4 ms                                                         | 37.1 ms: 1.08x slower                                               |
| sympy_expand                     | 332 ms                                                          | 358 ms: 1.08x slower                                                |
| float                            | 47.3 ms                                                         | 51.1 ms: 1.08x slower                                               |
| logging_simple                   | 4.79 us                                                         | 5.17 us: 1.08x slower                                               |
| deepcopy                         | 193 us                                                          | 208 us: 1.08x slower                                                |
| genshi_xml                       | 39.5 ms                                                         | 42.7 ms: 1.08x slower                                               |
| xml_etree_generate               | 62.6 ms                                                         | 67.8 ms: 1.08x slower                                               |
| sympy_integrate                  | 15.4 ms                                                         | 16.6 ms: 1.08x slower                                               |
| base85_small                     | 4.69 ms                                                         | 5.10 ms: 1.09x slower                                               |
| async_generators                 | 228 ms                                                          | 248 ms: 1.09x slower                                                |
| sympy_str                        | 194 ms                                                          | 211 ms: 1.09x slower                                                |
| decimal_factorial                | 173 ms                                                          | 189 ms: 1.09x slower                                                |
| deepcopy_memo                    | 18.0 us                                                         | 19.7 us: 1.09x slower                                               |
| quadtree_nbody                   | 596 ms                                                          | 652 ms: 1.09x slower                                                |
| logging_format                   | 5.35 us                                                         | 5.86 us: 1.09x slower                                               |
| tomli_loads                      | 1.44 sec                                                        | 1.58 sec: 1.10x slower                                              |
| json_loads                       | 17.5 us                                                         | 19.2 us: 1.10x slower                                               |
| chaos                            | 43.8 ms                                                         | 48.2 ms: 1.10x slower                                               |
| django_template                  | 27.8 ms                                                         | 31.0 ms: 1.11x slower                                               |
| base32_large                     | 292 ms                                                          | 325 ms: 1.11x slower                                                |
| comprehensions                   | 10.8 us                                                         | 12.0 us: 1.11x slower                                               |
| xml_etree_process                | 44.7 ms                                                         | 49.9 ms: 1.12x slower                                               |
| regex_compile                    | 93.9 ms                                                         | 105 ms: 1.12x slower                                                |
| hexiom                           | 4.11 ms                                                         | 4.60 ms: 1.12x slower                                               |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.29 ms: 1.12x slower                                               |
| xdsl_constant_fold               | 34.7 ms                                                         | 39.0 ms: 1.12x slower                                               |
| base85_large                     | 248 ms                                                          | 279 ms: 1.13x slower                                                |
| pprint_pformat                   | 989 ms                                                          | 1.11 sec: 1.13x slower                                              |
| scimark_sor                      | 75.7 ms                                                         | 85.3 ms: 1.13x slower                                               |
| ascii85_small                    | 12.7 ms                                                         | 14.3 ms: 1.13x slower                                               |
| deepcopy_reduce                  | 2.00 us                                                         | 2.26 us: 1.13x slower                                               |
| deltablue                        | 2.34 ms                                                         | 2.64 ms: 1.13x slower                                               |
| go                               | 84.7 ms                                                         | 96.0 ms: 1.13x slower                                               |
| ascii85_large                    | 667 ms                                                          | 760 ms: 1.14x slower                                                |
| chameleon                        | 9.52 ms                                                         | 10.9 ms: 1.14x slower                                               |
| pprint_safe_repr                 | 474 ms                                                          | 543 ms: 1.14x slower                                                |
| richards                         | 32.6 ms                                                         | 37.4 ms: 1.15x slower                                               |
| unpickle_list                    | 3.43 us                                                         | 3.93 us: 1.15x slower                                               |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 3.65 ms: 1.15x slower                                               |
| base32_small                     | 5.71 ms                                                         | 6.56 ms: 1.15x slower                                               |
| sqlglot_v2_parse                 | 911 us                                                          | 1.05 ms: 1.15x slower                                               |
| async_tree_eager                 | 81.3 ms                                                         | 93.6 ms: 1.15x slower                                               |
| genshi_text                      | 16.8 ms                                                         | 19.3 ms: 1.15x slower                                               |
| scimark_lu                       | 73.8 ms                                                         | 86.0 ms: 1.16x slower                                               |
| spectral_norm                    | 65.6 ms                                                         | 76.4 ms: 1.17x slower                                               |
| decimal_pi                       | 208 ms                                                          | 243 ms: 1.17x slower                                                |
| unpickle                         | 10.2 us                                                         | 11.9 us: 1.17x slower                                               |
| nqueens                          | 56.8 ms                                                         | 66.7 ms: 1.17x slower                                               |
| richards_super                   | 37.4 ms                                                         | 44.0 ms: 1.18x slower                                               |
| crypto_pyaes                     | 54.5 ms                                                         | 64.2 ms: 1.18x slower                                               |
| pyflate                          | 299 ms                                                          | 355 ms: 1.19x slower                                                |
| raytrace                         | 194 ms                                                          | 231 ms: 1.19x slower                                                |
| fannkuch                         | 245 ms                                                          | 292 ms: 1.19x slower                                                |
| noop                             | 19.4 ns                                                         | 23.1 ns: 1.19x slower                                               |
| meteor_contest                   | 84.1 ms                                                         | 101 ms: 1.20x slower                                                |
| python_startup                   | 9.73 ms                                                         | 11.7 ms: 1.20x slower                                               |
| nbody                            | 67.9 ms                                                         | 82.2 ms: 1.21x slower                                               |
| typing_runtime_protocols         | 112 us                                                          | 136 us: 1.22x slower                                                |
| unpack_sequence                  | 25.8 ns                                                         | 32.4 ns: 1.26x slower                                               |
| python_startup_no_site           | 6.38 ms                                                         | 8.22 ms: 1.29x slower                                               |
| scimark_monte_carlo              | 40.7 ms                                                         | 52.8 ms: 1.30x slower                                               |
| coverage                         | 57.4 ms                                                         | 79.5 ms: 1.38x slower                                               |
| mako                             | 7.40 ms                                                         | 11.6 ms: 1.57x slower                                               |
| thread_montecarlo_naive          | 15.8 ms                                                         | 30.1 ms: 1.90x slower                                               |
| thread_memo_naive                | 11.5 ms                                                         | 22.3 ms: 1.93x slower                                               |
| Geometric mean                   | (ref)                                                           | 1.02x faster                                                        |

Benchmark hidden because not significant (2): regex_v8, html5lib
Ignored benchmarks (4) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: networkx_connected_components, networkx_k_core, networkx_shortest_path, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.023x faster

# HPT report

- Reliability score: 99.11% likely to be slow
- 90% likely to have a slowdown of 1.02x
- 95% likely to have a slowdown of 1.01x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.48x