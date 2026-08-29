# Results vs. 3.13.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.268x faster
- HPT reliability: 61.23%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.64x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 11.1 ms: 1.12x slower                                                 |
| docutils       | 1.89 sec                                                        | 2.20 sec: 1.16x slower                                                |
| fastapi_http   | 218 ms                                                          | 193 ms: 1.13x faster                                                  |
| html5lib       | 51.7 ms                                                         | 49.2 ms: 1.05x faster                                                 |
| tornado_http   | 101 ms                                                          | 93.7 ms: 1.08x faster                                                 |
| Geometric mean | (ref)                                                           | 1.00x slower                                                          |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| async_tree_io_tg                 | 778 ms                                                          | 552 ms: 1.41x faster                                                  |
| async_tree_eager_io_tg           | 728 ms                                                          | 550 ms: 1.32x faster                                                  |
| async_tree_eager_io              | 749 ms                                                          | 580 ms: 1.29x faster                                                  |
| async_tree_io                    | 741 ms                                                          | 575 ms: 1.29x faster                                                  |
| async_tree_memoization_tg        | 419 ms                                                          | 340 ms: 1.23x faster                                                  |
| asyncio_tcp                      | 318 ms                                                          | 268 ms: 1.19x faster                                                  |
| async_tree_none                  | 308 ms                                                          | 279 ms: 1.10x faster                                                  |
| async_tree_none_tg               | 291 ms                                                          | 267 ms: 1.09x faster                                                  |
| async_tree_memoization           | 388 ms                                                          | 361 ms: 1.07x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 463 ms: 1.06x faster                                                  |
| async_tree_eager_memoization     | 219 ms                                                          | 209 ms: 1.05x faster                                                  |
| asyncio_websockets               | 303 ms                                                          | 292 ms: 1.04x faster                                                  |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 490 ms: 1.03x slower                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.33 sec: 1.03x slower                                                |
| coroutines                       | 15.4 ms                                                         | 16.0 ms: 1.04x slower                                                 |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 337 ms: 1.04x slower                                                  |
| async_tree_eager                 | 89.6 ms                                                         | 96.7 ms: 1.08x slower                                                 |
| async_generators                 | 240 ms                                                          | 270 ms: 1.13x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 453 ms: 1.59x slower                                                  |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 325 ms: 1.86x slower                                                  |
| async_tree_eager_tg              | 58.6 ms                                                         | 237 ms: 4.04x slower                                                  |
| Geometric mean                   | (ref)                                                           | 1.04x slower                                                          |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 22.9 ns: 1.12x slower                                                 |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                          | 191 ms: 1.08x slower                                                  |
| decimal_pi        | 222 ms                                                          | 247 ms: 1.11x slower                                                  |
| Geometric mean    | (ref)                                                           | 1.10x slower                                                          |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 190 ms: 1.00x slower                                                  |
| quadtree_nbody | 626 ms                                                          | 653 ms: 1.04x slower                                                  |
| float          | 57.0 ms                                                         | 67.1 ms: 1.18x slower                                                 |
| nbody          | 65.9 ms                                                         | 88.4 ms: 1.34x slower                                                 |
| Geometric mean | (ref)                                                           | 1.13x slower                                                          |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 2.05 ms: 1.12x faster                                                 |
| regex_v8       | 15.2 ms                                                         | 14.8 ms: 1.03x faster                                                 |
| regex_dna      | 162 ms                                                          | 159 ms: 1.02x faster                                                  |
| regex_compile  | 98.5 ms                                                         | 104 ms: 1.05x slower                                                  |
| Geometric mean | (ref)                                                           | 1.03x faster                                                          |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| base32_large         | 296 ms                                                          | 1.93 ms: 153.26x faster                                               |
| ascii85_large        | 717 ms                                                          | 9.50 ms: 75.41x faster                                                |
| base85_large         | 252 ms                                                          | 3.53 ms: 71.28x faster                                                |
| ascii85_small        | 13.6 ms                                                         | 436 us: 31.15x faster                                                 |
| base32_small         | 5.79 ms                                                         | 186 us: 31.12x faster                                                 |
| base85_small         | 4.59 ms                                                         | 171 us: 26.89x faster                                                 |
| base16_large         | 37.0 ms                                                         | 6.29 ms: 5.88x faster                                                 |
| base64_large         | 3.33 ms                                                         | 1.86 ms: 1.79x faster                                                 |
| base16_small         | 740 us                                                          | 422 us: 1.75x faster                                                  |
| urlsafe_base64_small | 325 us                                                          | 253 us: 1.29x faster                                                  |
| xml_etree_iterparse  | 79.9 ms                                                         | 71.6 ms: 1.12x faster                                                 |
| tomli_loads          | 1.62 sec                                                        | 1.50 sec: 1.08x faster                                                |
| json_dumps           | 6.95 ms                                                         | 7.21 ms: 1.04x slower                                                 |
| xml_etree_generate   | 64.2 ms                                                         | 69.8 ms: 1.09x slower                                                 |
| pickle_dict          | 22.0 us                                                         | 24.1 us: 1.09x slower                                                 |
| unpickle_pure_python | 151 us                                                          | 169 us: 1.12x slower                                                  |
| xml_etree_process    | 46.6 ms                                                         | 52.5 ms: 1.13x slower                                                 |
| pickle_pure_python   | 223 us                                                          | 260 us: 1.16x slower                                                  |
| unpickle             | 10.5 us                                                         | 12.3 us: 1.16x slower                                                 |
| base64_small         | 177 us                                                          | 209 us: 1.18x slower                                                  |
| pickle               | 7.44 us                                                         | 8.87 us: 1.19x slower                                                 |
| unpickle_list        | 3.33 us                                                         | 3.99 us: 1.20x slower                                                 |
| json_loads           | 16.2 us                                                         | 20.3 us: 1.25x slower                                                 |
| pickle_list          | 3.14 us                                                         | 4.00 us: 1.27x slower                                                 |
| Geometric mean       | (ref)                                                           | 2.76x faster                                                          |

Benchmark hidden because not significant (1): xml_etree_parse

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 7.94 ms: 1.23x slower                                                 |
| python_startup         | 9.51 ms                                                         | 11.7 ms: 1.23x slower                                                 |
| Geometric mean         | (ref)                                                           | 1.23x slower                                                          |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| django_template | 27.6 ms                                                         | 31.5 ms: 1.14x slower                                                 |
| mako            | 7.16 ms                                                         | 11.8 ms: 1.65x slower                                                 |
| Geometric mean  | (ref)                                                           | 1.37x slower                                                          |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 210 ms                                                          | 59.9 ms: 3.51x faster                                                 |
| thread_mandelbrot_optimized | 208 ms                                                          | 59.8 ms: 3.47x faster                                                 |
| thread_pipeline_optimized   | 20.9 ms                                                         | 6.55 ms: 3.18x faster                                                 |
| thread_accumulate_optimized | 32.3 ms                                                         | 10.6 ms: 3.05x faster                                                 |
| thread_montecarlo_optimized | 14.5 ms                                                         | 4.80 ms: 3.02x faster                                                 |
| thread_counter_optimized    | 16.5 ms                                                         | 5.55 ms: 2.98x faster                                                 |
| thread_accumulate_naive     | 33.4 ms                                                         | 11.4 ms: 2.94x faster                                                 |
| thread_memo_optimized       | 15.3 ms                                                         | 5.61 ms: 2.72x faster                                                 |
| thread_pipeline_naive       | 47.3 ms                                                         | 21.3 ms: 2.22x faster                                                 |
| thread_counter_naive        | 20.6 ms                                                         | 13.0 ms: 1.59x faster                                                 |
| thread_memo_naive           | 36.1 ms                                                         | 23.7 ms: 1.53x faster                                                 |
| thread_montecarlo_naive     | 19.0 ms                                                         | 39.5 ms: 2.08x slower                                                 |
| Geometric mean              | (ref)                                                           | 2.30x faster                                                          |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| base32_large                     | 296 ms                                                          | 1.93 ms: 153.26x faster                                               |
| ascii85_large                    | 717 ms                                                          | 9.50 ms: 75.41x faster                                                |
| base85_large                     | 252 ms                                                          | 3.53 ms: 71.28x faster                                                |
| ascii85_small                    | 13.6 ms                                                         | 436 us: 31.15x faster                                                 |
| base32_small                     | 5.79 ms                                                         | 186 us: 31.12x faster                                                 |
| base85_small                     | 4.59 ms                                                         | 171 us: 26.89x faster                                                 |
| base16_large                     | 37.0 ms                                                         | 6.29 ms: 5.88x faster                                                 |
| thread_mandelbrot_naive          | 210 ms                                                          | 59.9 ms: 3.51x faster                                                 |
| thread_mandelbrot_optimized      | 208 ms                                                          | 59.8 ms: 3.47x faster                                                 |
| thread_pipeline_optimized        | 20.9 ms                                                         | 6.55 ms: 3.18x faster                                                 |
| thread_accumulate_optimized      | 32.3 ms                                                         | 10.6 ms: 3.05x faster                                                 |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 4.80 ms: 3.02x faster                                                 |
| thread_counter_optimized         | 16.5 ms                                                         | 5.55 ms: 2.98x faster                                                 |
| thread_accumulate_naive          | 33.4 ms                                                         | 11.4 ms: 2.94x faster                                                 |
| thread_memo_optimized            | 15.3 ms                                                         | 5.61 ms: 2.72x faster                                                 |
| pylint                           | 227 ms                                                          | 92.6 ms: 2.45x faster                                                 |
| thread_pipeline_naive            | 47.3 ms                                                         | 21.3 ms: 2.22x faster                                                 |
| mdp                              | 2.15 sec                                                        | 1.01 sec: 2.13x faster                                                |
| gc_traversal                     | 3.07 ms                                                         | 1.58 ms: 1.94x faster                                                 |
| base64_large                     | 3.33 ms                                                         | 1.86 ms: 1.79x faster                                                 |
| base16_small                     | 740 us                                                          | 422 us: 1.75x faster                                                  |
| thread_counter_naive             | 20.6 ms                                                         | 13.0 ms: 1.59x faster                                                 |
| thread_memo_naive                | 36.1 ms                                                         | 23.7 ms: 1.53x faster                                                 |
| argparse_many_optionals          | 12.8 ms                                                         | 8.43 ms: 1.52x faster                                                 |
| async_tree_io_tg                 | 778 ms                                                          | 552 ms: 1.41x faster                                                  |
| create_gc_cycles                 | 1.75 ms                                                         | 1.26 ms: 1.39x faster                                                 |
| deepcopy_memo                    | 26.5 us                                                         | 19.8 us: 1.34x faster                                                 |
| deepcopy                         | 269 us                                                          | 203 us: 1.33x faster                                                  |
| async_tree_eager_io_tg           | 728 ms                                                          | 550 ms: 1.32x faster                                                  |
| async_tree_eager_io              | 749 ms                                                          | 580 ms: 1.29x faster                                                  |
| async_tree_io                    | 741 ms                                                          | 575 ms: 1.29x faster                                                  |
| urlsafe_base64_small             | 325 us                                                          | 253 us: 1.29x faster                                                  |
| async_tree_memoization_tg        | 419 ms                                                          | 340 ms: 1.23x faster                                                  |
| go                               | 117 ms                                                          | 97.5 ms: 1.20x faster                                                 |
| asyncio_tcp                      | 318 ms                                                          | 268 ms: 1.19x faster                                                  |
| fastapi_http                     | 218 ms                                                          | 193 ms: 1.13x faster                                                  |
| regex_effbot                     | 2.30 ms                                                         | 2.05 ms: 1.12x faster                                                 |
| xml_etree_iterparse              | 79.9 ms                                                         | 71.6 ms: 1.12x faster                                                 |
| async_tree_none                  | 308 ms                                                          | 279 ms: 1.10x faster                                                  |
| pathlib                          | 12.8 ms                                                         | 11.6 ms: 1.10x faster                                                 |
| async_tree_none_tg               | 291 ms                                                          | 267 ms: 1.09x faster                                                  |
| tomli_loads                      | 1.62 sec                                                        | 1.50 sec: 1.08x faster                                                |
| tornado_http                     | 101 ms                                                          | 93.7 ms: 1.08x faster                                                 |
| async_tree_memoization           | 388 ms                                                          | 361 ms: 1.07x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 463 ms: 1.06x faster                                                  |
| richards                         | 37.8 ms                                                         | 35.9 ms: 1.05x faster                                                 |
| html5lib                         | 51.7 ms                                                         | 49.2 ms: 1.05x faster                                                 |
| async_tree_eager_memoization     | 219 ms                                                          | 209 ms: 1.05x faster                                                  |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.17 sec: 1.04x faster                                                |
| deepcopy_reduce                  | 2.40 us                                                         | 2.31 us: 1.04x faster                                                 |
| asyncio_websockets               | 303 ms                                                          | 292 ms: 1.04x faster                                                  |
| richards_super                   | 42.8 ms                                                         | 41.6 ms: 1.03x faster                                                 |
| regex_v8                         | 15.2 ms                                                         | 14.8 ms: 1.03x faster                                                 |
| pycparser                        | 860 ms                                                          | 841 ms: 1.02x faster                                                  |
| regex_dna                        | 162 ms                                                          | 159 ms: 1.02x faster                                                  |
| pidigits                         | 189 ms                                                          | 190 ms: 1.00x slower                                                  |
| telco                            | 5.83 ms                                                         | 5.86 ms: 1.00x slower                                                 |
| thrift                           | 2.02 ms                                                         | 2.04 ms: 1.01x slower                                                 |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 490 ms: 1.03x slower                                                  |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.24 ms: 1.03x slower                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.33 sec: 1.03x slower                                                |
| json_dumps                       | 6.95 ms                                                         | 7.21 ms: 1.04x slower                                                 |
| pyflate                          | 342 ms                                                          | 355 ms: 1.04x slower                                                  |
| coroutines                       | 15.4 ms                                                         | 16.0 ms: 1.04x slower                                                 |
| json                             | 3.51 ms                                                         | 3.65 ms: 1.04x slower                                                 |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 337 ms: 1.04x slower                                                  |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 41.8 ms: 1.04x slower                                                 |
| quadtree_nbody                   | 626 ms                                                          | 653 ms: 1.04x slower                                                  |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 84.2 ms: 1.05x slower                                                 |
| sqlglot_v2_parse                 | 958 us                                                          | 1.00 ms: 1.05x slower                                                 |
| regex_compile                    | 98.5 ms                                                         | 104 ms: 1.05x slower                                                  |
| pprint_safe_repr                 | 530 ms                                                          | 563 ms: 1.06x slower                                                  |
| sympy_integrate                  | 15.8 ms                                                         | 16.9 ms: 1.07x slower                                                 |
| chaos                            | 45.1 ms                                                         | 48.2 ms: 1.07x slower                                                 |
| logging_simple                   | 4.71 us                                                         | 5.05 us: 1.07x slower                                                 |
| scimark_sor                      | 78.9 ms                                                         | 84.6 ms: 1.07x slower                                                 |
| hexiom                           | 4.30 ms                                                         | 4.62 ms: 1.07x slower                                                 |
| decimal_factorial                | 177 ms                                                          | 191 ms: 1.08x slower                                                  |
| async_tree_eager                 | 89.6 ms                                                         | 96.7 ms: 1.08x slower                                                 |
| pprint_pformat                   | 1.09 sec                                                        | 1.18 sec: 1.08x slower                                                |
| sympy_sum                        | 106 ms                                                          | 116 ms: 1.09x slower                                                  |
| xml_etree_generate               | 64.2 ms                                                         | 69.8 ms: 1.09x slower                                                 |
| sympy_expand                     | 336 ms                                                          | 368 ms: 1.09x slower                                                  |
| pickle_dict                      | 22.0 us                                                         | 24.1 us: 1.09x slower                                                 |
| xdsl_constant_fold               | 36.7 ms                                                         | 40.2 ms: 1.09x slower                                                 |
| sympy_str                        | 197 ms                                                          | 216 ms: 1.09x slower                                                  |
| scimark_fft                      | 226 ms                                                          | 249 ms: 1.10x slower                                                  |
| comprehensions                   | 10.9 us                                                         | 12.0 us: 1.10x slower                                                 |
| logging_format                   | 5.25 us                                                         | 5.78 us: 1.10x slower                                                 |
| generators                       | 21.2 ms                                                         | 23.4 ms: 1.10x slower                                                 |
| decimal_pi                       | 222 ms                                                          | 247 ms: 1.11x slower                                                  |
| noop                             | 20.5 ns                                                         | 22.9 ns: 1.12x slower                                                 |
| chameleon                        | 9.95 ms                                                         | 11.1 ms: 1.12x slower                                                 |
| unpickle_pure_python             | 151 us                                                          | 169 us: 1.12x slower                                                  |
| xml_etree_process                | 46.6 ms                                                         | 52.5 ms: 1.13x slower                                                 |
| argparse_subparsers              | 452 us                                                          | 509 us: 1.13x slower                                                  |
| async_generators                 | 240 ms                                                          | 270 ms: 1.13x slower                                                  |
| logging_silent                   | 61.0 ns                                                         | 69.1 ns: 1.13x slower                                                 |
| scimark_monte_carlo              | 46.5 ms                                                         | 53.0 ms: 1.14x slower                                                 |
| django_template                  | 27.6 ms                                                         | 31.5 ms: 1.14x slower                                                 |
| pickle_pure_python               | 223 us                                                          | 260 us: 1.16x slower                                                  |
| docutils                         | 1.89 sec                                                        | 2.20 sec: 1.16x slower                                                |
| unpickle                         | 10.5 us                                                         | 12.3 us: 1.16x slower                                                 |
| unpack_sequence                  | 27.1 ns                                                         | 31.6 ns: 1.17x slower                                                 |
| raytrace                         | 195 ms                                                          | 230 ms: 1.18x slower                                                  |
| float                            | 57.0 ms                                                         | 67.1 ms: 1.18x slower                                                 |
| base64_small                     | 177 us                                                          | 209 us: 1.18x slower                                                  |
| scimark_lu                       | 74.5 ms                                                         | 87.9 ms: 1.18x slower                                                 |
| deltablue                        | 2.41 ms                                                         | 2.84 ms: 1.18x slower                                                 |
| spectral_norm                    | 65.9 ms                                                         | 77.8 ms: 1.18x slower                                                 |
| pickle                           | 7.44 us                                                         | 8.87 us: 1.19x slower                                                 |
| mypy2                            | 724 ms                                                          | 865 ms: 1.19x slower                                                  |
| networkx_shortest_path           | 437 ms                                                          | 522 ms: 1.19x slower                                                  |
| unpickle_list                    | 3.33 us                                                         | 3.99 us: 1.20x slower                                                 |
| meteor_contest                   | 84.4 ms                                                         | 101 ms: 1.20x slower                                                  |
| python_startup_no_site           | 6.46 ms                                                         | 7.94 ms: 1.23x slower                                                 |
| python_startup                   | 9.51 ms                                                         | 11.7 ms: 1.23x slower                                                 |
| fannkuch                         | 246 ms                                                          | 306 ms: 1.24x slower                                                  |
| json_loads                       | 16.2 us                                                         | 20.3 us: 1.25x slower                                                 |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.93 ms: 1.25x slower                                                 |
| typing_runtime_protocols         | 113 us                                                          | 143 us: 1.27x slower                                                  |
| pickle_list                      | 3.14 us                                                         | 4.00 us: 1.27x slower                                                 |
| nqueens                          | 53.6 ms                                                         | 68.8 ms: 1.28x slower                                                 |
| crypto_pyaes                     | 50.9 ms                                                         | 66.0 ms: 1.30x slower                                                 |
| nbody                            | 65.9 ms                                                         | 88.4 ms: 1.34x slower                                                 |
| networkx_connected_components    | 425 ms                                                          | 610 ms: 1.43x slower                                                  |
| coverage                         | 55.8 ms                                                         | 81.3 ms: 1.46x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 453 ms: 1.59x slower                                                  |
| mako                             | 7.16 ms                                                         | 11.8 ms: 1.65x slower                                                 |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 325 ms: 1.86x slower                                                  |
| thread_montecarlo_naive          | 19.0 ms                                                         | 39.5 ms: 2.08x slower                                                 |
| async_tree_eager_tg              | 58.6 ms                                                         | 237 ms: 4.04x slower                                                  |
| Geometric mean                   | (ref)                                                           | 1.27x faster                                                          |

Benchmark hidden because not significant (2): networkx_k_core, xml_etree_parse
Ignored benchmarks (3) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.268x faster

# HPT report

- Reliability score: 61.23% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.64x