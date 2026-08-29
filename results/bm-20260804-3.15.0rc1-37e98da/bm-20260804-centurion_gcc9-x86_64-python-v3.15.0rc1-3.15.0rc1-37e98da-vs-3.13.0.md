# Results vs. 3.13.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.239x faster
- HPT reliability: 99.06%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.05x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 10.1 ms: 1.02x slower                                                 |
| docutils       | 1.89 sec                                                        | 1.86 sec: 1.01x faster                                                |
| fastapi_http   | 218 ms                                                          | 223 ms: 1.03x slower                                                  |
| html5lib       | 51.7 ms                                                         | 48.2 ms: 1.07x faster                                                 |
| tornado_http   | 101 ms                                                          | 99.4 ms: 1.01x faster                                                 |
| Geometric mean | (ref)                                                           | 1.01x faster                                                          |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| async_tree_memoization_tg        | 419 ms                                                          | 328 ms: 1.28x faster                                                  |
| async_tree_none                  | 308 ms                                                          | 252 ms: 1.22x faster                                                  |
| async_tree_eager_memoization     | 219 ms                                                          | 183 ms: 1.20x faster                                                  |
| async_tree_eager_io              | 749 ms                                                          | 631 ms: 1.19x faster                                                  |
| asyncio_tcp                      | 318 ms                                                          | 268 ms: 1.18x faster                                                  |
| async_tree_memoization           | 388 ms                                                          | 332 ms: 1.17x faster                                                  |
| async_tree_io                    | 741 ms                                                          | 638 ms: 1.16x faster                                                  |
| async_tree_io_tg                 | 778 ms                                                          | 678 ms: 1.15x faster                                                  |
| async_tree_eager                 | 89.6 ms                                                         | 79.2 ms: 1.13x faster                                                 |
| async_tree_none_tg               | 291 ms                                                          | 262 ms: 1.11x faster                                                  |
| async_tree_eager_io_tg           | 728 ms                                                          | 669 ms: 1.09x faster                                                  |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 450 ms: 1.06x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 466 ms: 1.05x faster                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.26 sec: 1.02x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 319 ms: 1.01x faster                                                  |
| async_generators                 | 240 ms                                                          | 244 ms: 1.02x slower                                                  |
| asyncio_websockets               | 303 ms                                                          | 313 ms: 1.03x slower                                                  |
| coroutines                       | 15.4 ms                                                         | 16.0 ms: 1.04x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 403 ms: 1.41x slower                                                  |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 283 ms: 1.62x slower                                                  |
| async_tree_eager_tg              | 58.6 ms                                                         | 209 ms: 3.56x slower                                                  |
| Geometric mean                   | (ref)                                                           | 1.02x slower                                                          |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 21.1 ns: 1.03x slower                                                 |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                          | 217 ms: 1.02x faster                                                  |
| decimal_factorial | 177 ms                                                          | 176 ms: 1.00x faster                                                  |
| Geometric mean    | (ref)                                                           | 1.01x faster                                                          |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| quadtree_nbody | 626 ms                                                          | 598 ms: 1.05x faster                                                  |
| float          | 57.0 ms                                                         | 55.7 ms: 1.02x faster                                                 |
| pidigits       | 189 ms                                                          | 194 ms: 1.03x slower                                                  |
| nbody          | 65.9 ms                                                         | 68.2 ms: 1.03x slower                                                 |
| Geometric mean | (ref)                                                           | 1.00x faster                                                          |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 2.01 ms: 1.14x faster                                                 |
| regex_dna      | 162 ms                                                          | 156 ms: 1.03x faster                                                  |
| regex_compile  | 98.5 ms                                                         | 95.7 ms: 1.03x faster                                                 |
| regex_v8       | 15.2 ms                                                         | 15.1 ms: 1.01x faster                                                 |
| Geometric mean | (ref)                                                           | 1.05x faster                                                          |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| base32_large         | 296 ms                                                          | 1.89 ms: 156.67x faster                                               |
| ascii85_large        | 717 ms                                                          | 9.49 ms: 75.51x faster                                                |
| base85_large         | 252 ms                                                          | 3.53 ms: 71.23x faster                                                |
| ascii85_small        | 13.6 ms                                                         | 510 us: 26.61x faster                                                 |
| base32_small         | 5.79 ms                                                         | 231 us: 25.05x faster                                                 |
| base85_small         | 4.59 ms                                                         | 211 us: 21.79x faster                                                 |
| base16_large         | 37.0 ms                                                         | 7.31 ms: 5.06x faster                                                 |
| base64_large         | 3.33 ms                                                         | 1.89 ms: 1.76x faster                                                 |
| base16_small         | 740 us                                                          | 457 us: 1.62x faster                                                  |
| urlsafe_base64_small | 325 us                                                          | 289 us: 1.13x faster                                                  |
| tomli_loads          | 1.62 sec                                                        | 1.47 sec: 1.10x faster                                                |
| json_dumps           | 6.95 ms                                                         | 6.45 ms: 1.08x faster                                                 |
| unpickle             | 10.5 us                                                         | 10.6 us: 1.01x slower                                                 |
| unpickle_pure_python | 151 us                                                          | 154 us: 1.02x slower                                                  |
| xml_etree_process    | 46.6 ms                                                         | 48.1 ms: 1.03x slower                                                 |
| json_loads           | 16.2 us                                                         | 16.8 us: 1.04x slower                                                 |
| xml_etree_parse      | 104 ms                                                          | 108 ms: 1.04x slower                                                  |
| xml_etree_generate   | 64.2 ms                                                         | 66.9 ms: 1.04x slower                                                 |
| pickle_dict          | 22.0 us                                                         | 23.2 us: 1.05x slower                                                 |
| pickle_pure_python   | 223 us                                                          | 240 us: 1.08x slower                                                  |
| unpickle_list        | 3.33 us                                                         | 3.62 us: 1.09x slower                                                 |
| pickle               | 7.44 us                                                         | 8.90 us: 1.20x slower                                                 |
| pickle_list          | 3.14 us                                                         | 3.80 us: 1.21x slower                                                 |
| base64_small         | 177 us                                                          | 257 us: 1.45x slower                                                  |
| Geometric mean       | (ref)                                                           | 2.73x faster                                                          |

Benchmark hidden because not significant (1): xml_etree_iterparse

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 5.99 ms: 1.08x faster                                                 |
| python_startup         | 9.51 ms                                                         | 9.67 ms: 1.02x slower                                                 |
| Geometric mean         | (ref)                                                           | 1.03x faster                                                          |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| mako            | 7.16 ms                                                         | 7.68 ms: 1.07x slower                                                 |
| django_template | 27.6 ms                                                         | 29.7 ms: 1.08x slower                                                 |
| Geometric mean  | (ref)                                                           | 1.07x slower                                                          |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| thread_memo_naive           | 36.1 ms                                                         | 10.3 ms: 3.50x faster                                                 |
| thread_pipeline_naive       | 47.3 ms                                                         | 36.4 ms: 1.30x faster                                                 |
| thread_montecarlo_naive     | 19.0 ms                                                         | 17.2 ms: 1.11x faster                                                 |
| thread_montecarlo_optimized | 14.5 ms                                                         | 14.7 ms: 1.01x slower                                                 |
| thread_mandelbrot_naive     | 210 ms                                                          | 225 ms: 1.07x slower                                                  |
| thread_mandelbrot_optimized | 208 ms                                                          | 228 ms: 1.10x slower                                                  |
| thread_counter_naive        | 20.6 ms                                                         | 23.1 ms: 1.12x slower                                                 |
| thread_memo_optimized       | 15.3 ms                                                         | 18.5 ms: 1.21x slower                                                 |
| thread_accumulate_naive     | 33.4 ms                                                         | 41.5 ms: 1.24x slower                                                 |
| thread_counter_optimized    | 16.5 ms                                                         | 20.8 ms: 1.26x slower                                                 |
| thread_accumulate_optimized | 32.3 ms                                                         | 41.5 ms: 1.28x slower                                                 |
| thread_pipeline_optimized   | 20.9 ms                                                         | 27.1 ms: 1.30x slower                                                 |
| Geometric mean              | (ref)                                                           | 1.02x faster                                                          |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| base32_large                     | 296 ms                                                          | 1.89 ms: 156.67x faster                                               |
| ascii85_large                    | 717 ms                                                          | 9.49 ms: 75.51x faster                                                |
| base85_large                     | 252 ms                                                          | 3.53 ms: 71.23x faster                                                |
| ascii85_small                    | 13.6 ms                                                         | 510 us: 26.61x faster                                                 |
| base32_small                     | 5.79 ms                                                         | 231 us: 25.05x faster                                                 |
| base85_small                     | 4.59 ms                                                         | 211 us: 21.79x faster                                                 |
| base16_large                     | 37.0 ms                                                         | 7.31 ms: 5.06x faster                                                 |
| thread_memo_naive                | 36.1 ms                                                         | 10.3 ms: 3.50x faster                                                 |
| pylint                           | 227 ms                                                          | 99.5 ms: 2.28x faster                                                 |
| mdp                              | 2.15 sec                                                        | 948 ms: 2.26x faster                                                  |
| base64_large                     | 3.33 ms                                                         | 1.89 ms: 1.76x faster                                                 |
| argparse_many_optionals          | 12.8 ms                                                         | 7.58 ms: 1.69x faster                                                 |
| base16_small                     | 740 us                                                          | 457 us: 1.62x faster                                                  |
| deepcopy_memo                    | 26.5 us                                                         | 17.5 us: 1.52x faster                                                 |
| deepcopy                         | 269 us                                                          | 179 us: 1.50x faster                                                  |
| go                               | 117 ms                                                          | 86.4 ms: 1.35x faster                                                 |
| thread_pipeline_naive            | 47.3 ms                                                         | 36.4 ms: 1.30x faster                                                 |
| async_tree_memoization_tg        | 419 ms                                                          | 328 ms: 1.28x faster                                                  |
| async_tree_none                  | 308 ms                                                          | 252 ms: 1.22x faster                                                  |
| deepcopy_reduce                  | 2.40 us                                                         | 1.98 us: 1.21x faster                                                 |
| async_tree_eager_memoization     | 219 ms                                                          | 183 ms: 1.20x faster                                                  |
| async_tree_eager_io              | 749 ms                                                          | 631 ms: 1.19x faster                                                  |
| asyncio_tcp                      | 318 ms                                                          | 268 ms: 1.18x faster                                                  |
| async_tree_memoization           | 388 ms                                                          | 332 ms: 1.17x faster                                                  |
| async_tree_io                    | 741 ms                                                          | 638 ms: 1.16x faster                                                  |
| async_tree_io_tg                 | 778 ms                                                          | 678 ms: 1.15x faster                                                  |
| richards                         | 37.8 ms                                                         | 33.0 ms: 1.15x faster                                                 |
| regex_effbot                     | 2.30 ms                                                         | 2.01 ms: 1.14x faster                                                 |
| async_tree_eager                 | 89.6 ms                                                         | 79.2 ms: 1.13x faster                                                 |
| urlsafe_base64_small             | 325 us                                                          | 289 us: 1.13x faster                                                  |
| richards_super                   | 42.8 ms                                                         | 38.2 ms: 1.12x faster                                                 |
| async_tree_none_tg               | 291 ms                                                          | 262 ms: 1.11x faster                                                  |
| thread_montecarlo_naive          | 19.0 ms                                                         | 17.2 ms: 1.11x faster                                                 |
| telco                            | 5.83 ms                                                         | 5.28 ms: 1.10x faster                                                 |
| tomli_loads                      | 1.62 sec                                                        | 1.47 sec: 1.10x faster                                                |
| pyflate                          | 342 ms                                                          | 313 ms: 1.09x faster                                                  |
| sqlglot_v2_parse                 | 958 us                                                          | 880 us: 1.09x faster                                                  |
| async_tree_eager_io_tg           | 728 ms                                                          | 669 ms: 1.09x faster                                                  |
| pathlib                          | 12.8 ms                                                         | 11.8 ms: 1.09x faster                                                 |
| python_startup_no_site           | 6.46 ms                                                         | 5.99 ms: 1.08x faster                                                 |
| json_dumps                       | 6.95 ms                                                         | 6.45 ms: 1.08x faster                                                 |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.12 ms: 1.08x faster                                                 |
| html5lib                         | 51.7 ms                                                         | 48.2 ms: 1.07x faster                                                 |
| scimark_monte_carlo              | 46.5 ms                                                         | 43.8 ms: 1.06x faster                                                 |
| unpack_sequence                  | 27.1 ns                                                         | 25.5 ns: 1.06x faster                                                 |
| chaos                            | 45.1 ms                                                         | 42.7 ms: 1.06x faster                                                 |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 450 ms: 1.06x faster                                                  |
| pprint_pformat                   | 1.09 sec                                                        | 1.04 sec: 1.05x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 466 ms: 1.05x faster                                                  |
| create_gc_cycles                 | 1.75 ms                                                         | 1.67 ms: 1.05x faster                                                 |
| scimark_sor                      | 78.9 ms                                                         | 75.2 ms: 1.05x faster                                                 |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.14 sec: 1.05x faster                                                |
| quadtree_nbody                   | 626 ms                                                          | 598 ms: 1.05x faster                                                  |
| pprint_safe_repr                 | 530 ms                                                          | 509 ms: 1.04x faster                                                  |
| json                             | 3.51 ms                                                         | 3.38 ms: 1.04x faster                                                 |
| regex_dna                        | 162 ms                                                          | 156 ms: 1.03x faster                                                  |
| regex_compile                    | 98.5 ms                                                         | 95.7 ms: 1.03x faster                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.26 sec: 1.02x faster                                                |
| float                            | 57.0 ms                                                         | 55.7 ms: 1.02x faster                                                 |
| decimal_pi                       | 222 ms                                                          | 217 ms: 1.02x faster                                                  |
| thrift                           | 2.02 ms                                                         | 1.97 ms: 1.02x faster                                                 |
| tornado_http                     | 101 ms                                                          | 99.4 ms: 1.01x faster                                                 |
| docutils                         | 1.89 sec                                                        | 1.86 sec: 1.01x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 319 ms: 1.01x faster                                                  |
| spectral_norm                    | 65.9 ms                                                         | 65.1 ms: 1.01x faster                                                 |
| sympy_integrate                  | 15.8 ms                                                         | 15.6 ms: 1.01x faster                                                 |
| regex_v8                         | 15.2 ms                                                         | 15.1 ms: 1.01x faster                                                 |
| logging_simple                   | 4.71 us                                                         | 4.67 us: 1.01x faster                                                 |
| raytrace                         | 195 ms                                                          | 194 ms: 1.01x faster                                                  |
| fannkuch                         | 246 ms                                                          | 244 ms: 1.01x faster                                                  |
| decimal_factorial                | 177 ms                                                          | 176 ms: 1.00x faster                                                  |
| argparse_subparsers              | 452 us                                                          | 456 us: 1.01x slower                                                  |
| unpickle                         | 10.5 us                                                         | 10.6 us: 1.01x slower                                                 |
| sympy_expand                     | 336 ms                                                          | 341 ms: 1.01x slower                                                  |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 14.7 ms: 1.01x slower                                                 |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 40.6 ms: 1.01x slower                                                 |
| logging_format                   | 5.25 us                                                         | 5.32 us: 1.01x slower                                                 |
| python_startup                   | 9.51 ms                                                         | 9.67 ms: 1.02x slower                                                 |
| async_generators                 | 240 ms                                                          | 244 ms: 1.02x slower                                                  |
| logging_silent                   | 61.0 ns                                                         | 62.1 ns: 1.02x slower                                                 |
| sympy_str                        | 197 ms                                                          | 201 ms: 1.02x slower                                                  |
| chameleon                        | 9.95 ms                                                         | 10.1 ms: 1.02x slower                                                 |
| pycparser                        | 860 ms                                                          | 877 ms: 1.02x slower                                                  |
| scimark_fft                      | 226 ms                                                          | 231 ms: 1.02x slower                                                  |
| unpickle_pure_python             | 151 us                                                          | 154 us: 1.02x slower                                                  |
| fastapi_http                     | 218 ms                                                          | 223 ms: 1.03x slower                                                  |
| sympy_sum                        | 106 ms                                                          | 109 ms: 1.03x slower                                                  |
| pidigits                         | 189 ms                                                          | 194 ms: 1.03x slower                                                  |
| noop                             | 20.5 ns                                                         | 21.1 ns: 1.03x slower                                                 |
| deltablue                        | 2.41 ms                                                         | 2.48 ms: 1.03x slower                                                 |
| asyncio_websockets               | 303 ms                                                          | 313 ms: 1.03x slower                                                  |
| xml_etree_process                | 46.6 ms                                                         | 48.1 ms: 1.03x slower                                                 |
| nbody                            | 65.9 ms                                                         | 68.2 ms: 1.03x slower                                                 |
| json_loads                       | 16.2 us                                                         | 16.8 us: 1.04x slower                                                 |
| xml_etree_parse                  | 104 ms                                                          | 108 ms: 1.04x slower                                                  |
| coroutines                       | 15.4 ms                                                         | 16.0 ms: 1.04x slower                                                 |
| xml_etree_generate               | 64.2 ms                                                         | 66.9 ms: 1.04x slower                                                 |
| meteor_contest                   | 84.4 ms                                                         | 88.2 ms: 1.05x slower                                                 |
| generators                       | 21.2 ms                                                         | 22.3 ms: 1.05x slower                                                 |
| pickle_dict                      | 22.0 us                                                         | 23.2 us: 1.05x slower                                                 |
| nqueens                          | 53.6 ms                                                         | 56.9 ms: 1.06x slower                                                 |
| thread_mandelbrot_naive          | 210 ms                                                          | 225 ms: 1.07x slower                                                  |
| mako                             | 7.16 ms                                                         | 7.68 ms: 1.07x slower                                                 |
| scimark_lu                       | 74.5 ms                                                         | 80.0 ms: 1.07x slower                                                 |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.38 ms: 1.08x slower                                                 |
| typing_runtime_protocols         | 113 us                                                          | 122 us: 1.08x slower                                                  |
| django_template                  | 27.6 ms                                                         | 29.7 ms: 1.08x slower                                                 |
| pickle_pure_python               | 223 us                                                          | 240 us: 1.08x slower                                                  |
| networkx_shortest_path           | 437 ms                                                          | 471 ms: 1.08x slower                                                  |
| unpickle_list                    | 3.33 us                                                         | 3.62 us: 1.09x slower                                                 |
| coverage                         | 55.8 ms                                                         | 61.1 ms: 1.10x slower                                                 |
| gc_traversal                     | 3.07 ms                                                         | 3.36 ms: 1.10x slower                                                 |
| thread_mandelbrot_optimized      | 208 ms                                                          | 228 ms: 1.10x slower                                                  |
| crypto_pyaes                     | 50.9 ms                                                         | 56.9 ms: 1.12x slower                                                 |
| thread_counter_naive             | 20.6 ms                                                         | 23.1 ms: 1.12x slower                                                 |
| pickle                           | 7.44 us                                                         | 8.90 us: 1.20x slower                                                 |
| pickle_list                      | 3.14 us                                                         | 3.80 us: 1.21x slower                                                 |
| thread_memo_optimized            | 15.3 ms                                                         | 18.5 ms: 1.21x slower                                                 |
| thread_accumulate_naive          | 33.4 ms                                                         | 41.5 ms: 1.24x slower                                                 |
| thread_counter_optimized         | 16.5 ms                                                         | 20.8 ms: 1.26x slower                                                 |
| thread_accumulate_optimized      | 32.3 ms                                                         | 41.5 ms: 1.28x slower                                                 |
| thread_pipeline_optimized        | 20.9 ms                                                         | 27.1 ms: 1.30x slower                                                 |
| networkx_connected_components    | 425 ms                                                          | 560 ms: 1.32x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 403 ms: 1.41x slower                                                  |
| base64_small                     | 177 us                                                          | 257 us: 1.45x slower                                                  |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 283 ms: 1.62x slower                                                  |
| async_tree_eager_tg              | 58.6 ms                                                         | 209 ms: 3.56x slower                                                  |
| Geometric mean                   | (ref)                                                           | 1.24x faster                                                          |

Benchmark hidden because not significant (7): mypy2, xml_etree_iterparse, hexiom, sqlglot_v2_normalize, networkx_k_core, comprehensions, xdsl_constant_fold
Ignored benchmarks (3) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.239x faster

# HPT report

- Reliability score: 99.06% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.05x