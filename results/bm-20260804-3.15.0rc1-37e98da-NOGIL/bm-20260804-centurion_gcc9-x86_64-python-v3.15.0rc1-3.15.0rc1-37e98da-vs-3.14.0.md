# Results vs. 3.14.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.192x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.05x slower
- Memory change: 1.48x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 11.1 ms: 1.17x slower                                                 |
| docutils       | 1.95 sec                                                        | 2.20 sec: 1.13x slower                                                |
| fastapi_http   | 216 ms                                                          | 193 ms: 1.12x faster                                                  |
| html5lib       | 46.9 ms                                                         | 49.2 ms: 1.05x slower                                                 |
| tornado_http   | 101 ms                                                          | 93.7 ms: 1.08x faster                                                 |
| Geometric mean | (ref)                                                           | 1.03x slower                                                          |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| asyncio_tcp                      | 325 ms                                                          | 268 ms: 1.21x faster                                                  |
| asyncio_websockets               | 296 ms                                                          | 292 ms: 1.01x faster                                                  |
| async_tree_io_tg                 | 539 ms                                                          | 552 ms: 1.02x slower                                                  |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.33 sec: 1.04x slower                                                |
| async_tree_eager_io              | 552 ms                                                          | 580 ms: 1.05x slower                                                  |
| coroutines                       | 15.1 ms                                                         | 16.0 ms: 1.06x slower                                                 |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 337 ms: 1.07x slower                                                  |
| async_tree_io                    | 531 ms                                                          | 575 ms: 1.08x slower                                                  |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 463 ms: 1.13x slower                                                  |
| async_tree_eager_memoization     | 180 ms                                                          | 209 ms: 1.16x slower                                                  |
| async_generators                 | 228 ms                                                          | 270 ms: 1.19x slower                                                  |
| async_tree_eager                 | 81.3 ms                                                         | 96.7 ms: 1.19x slower                                                 |
| async_tree_none_tg               | 223 ms                                                          | 267 ms: 1.19x slower                                                  |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 490 ms: 1.20x slower                                                  |
| async_tree_memoization_tg        | 277 ms                                                          | 340 ms: 1.23x slower                                                  |
| async_tree_none                  | 228 ms                                                          | 279 ms: 1.23x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 453 ms: 1.25x slower                                                  |
| async_tree_memoization           | 281 ms                                                          | 361 ms: 1.29x slower                                                  |
| async_tree_eager_tg              | 182 ms                                                          | 237 ms: 1.30x slower                                                  |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 325 ms: 1.38x slower                                                  |
| Geometric mean                   | (ref)                                                           | 1.13x slower                                                          |

Benchmark hidden because not significant (1): async_tree_eager_io_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 22.9 ns: 1.18x slower                                                 |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 191 ms: 1.10x slower                                                  |
| decimal_pi        | 208 ms                                                          | 247 ms: 1.19x slower                                                  |
| Geometric mean    | (ref)                                                           | 1.15x slower                                                          |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 190 ms: 1.00x slower                                                  |
| quadtree_nbody | 596 ms                                                          | 653 ms: 1.10x slower                                                  |
| nbody          | 67.9 ms                                                         | 88.4 ms: 1.30x slower                                                 |
| float          | 47.3 ms                                                         | 67.1 ms: 1.42x slower                                                 |
| Geometric mean | (ref)                                                           | 1.19x slower                                                          |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| regex_effbot   | 1.95 ms                                                         | 2.05 ms: 1.05x slower                                                 |
| regex_dna      | 150 ms                                                          | 159 ms: 1.06x slower                                                  |
| regex_compile  | 93.9 ms                                                         | 104 ms: 1.10x slower                                                  |
| Geometric mean | (ref)                                                           | 1.05x slower                                                          |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| base32_large         | 292 ms                                                          | 1.93 ms: 151.63x faster                                               |
| ascii85_large        | 667 ms                                                          | 9.50 ms: 70.22x faster                                                |
| base85_large         | 248 ms                                                          | 3.53 ms: 70.14x faster                                                |
| base32_small         | 5.71 ms                                                         | 186 us: 30.64x faster                                                 |
| ascii85_small        | 12.7 ms                                                         | 436 us: 29.10x faster                                                 |
| base85_small         | 4.69 ms                                                         | 171 us: 27.48x faster                                                 |
| base64_large         | 3.63 ms                                                         | 1.86 ms: 1.95x faster                                                 |
| urlsafe_base64_small | 329 us                                                          | 253 us: 1.30x faster                                                  |
| xml_etree_iterparse  | 76.2 ms                                                         | 71.6 ms: 1.06x faster                                                 |
| json_dumps           | 6.95 ms                                                         | 7.21 ms: 1.04x slower                                                 |
| tomli_loads          | 1.44 sec                                                        | 1.50 sec: 1.04x slower                                                |
| pickle_pure_python   | 240 us                                                          | 260 us: 1.08x slower                                                  |
| pickle               | 8.20 us                                                         | 8.87 us: 1.08x slower                                                 |
| unpickle_pure_python | 152 us                                                          | 169 us: 1.11x slower                                                  |
| xml_etree_parse      | 94.3 ms                                                         | 105 ms: 1.11x slower                                                  |
| xml_etree_generate   | 62.6 ms                                                         | 69.8 ms: 1.12x slower                                                 |
| pickle_dict          | 21.5 us                                                         | 24.1 us: 1.12x slower                                                 |
| base64_small         | 186 us                                                          | 209 us: 1.13x slower                                                  |
| json_loads           | 17.5 us                                                         | 20.3 us: 1.16x slower                                                 |
| unpickle_list        | 3.43 us                                                         | 3.99 us: 1.16x slower                                                 |
| xml_etree_process    | 44.7 ms                                                         | 52.5 ms: 1.17x slower                                                 |
| base16_large         | 5.33 ms                                                         | 6.29 ms: 1.18x slower                                                 |
| unpickle             | 10.2 us                                                         | 12.3 us: 1.20x slower                                                 |
| pickle_list          | 3.24 us                                                         | 4.00 us: 1.24x slower                                                 |
| base16_small         | 305 us                                                          | 422 us: 1.38x slower                                                  |
| Geometric mean       | (ref)                                                           | 2.46x faster                                                          |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 11.7 ms: 1.20x slower                                                 |
| python_startup_no_site | 6.38 ms                                                         | 7.94 ms: 1.24x slower                                                 |
| Geometric mean         | (ref)                                                           | 1.22x slower                                                          |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| django_template | 27.8 ms                                                         | 31.5 ms: 1.13x slower                                                 |
| mako            | 7.40 ms                                                         | 11.8 ms: 1.60x slower                                                 |
| Geometric mean  | (ref)                                                           | 1.34x slower                                                          |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 233 ms                                                          | 59.9 ms: 3.90x faster                                                 |
| thread_mandelbrot_optimized | 233 ms                                                          | 59.8 ms: 3.90x faster                                                 |
| thread_pipeline_optimized   | 22.5 ms                                                         | 6.55 ms: 3.43x faster                                                 |
| thread_accumulate_optimized | 35.1 ms                                                         | 10.6 ms: 3.31x faster                                                 |
| thread_accumulate_naive     | 35.8 ms                                                         | 11.4 ms: 3.15x faster                                                 |
| thread_counter_optimized    | 17.1 ms                                                         | 5.55 ms: 3.08x faster                                                 |
| thread_montecarlo_optimized | 13.9 ms                                                         | 4.80 ms: 2.90x faster                                                 |
| thread_memo_optimized       | 15.9 ms                                                         | 5.61 ms: 2.84x faster                                                 |
| thread_counter_naive        | 20.2 ms                                                         | 13.0 ms: 1.56x faster                                                 |
| thread_pipeline_naive       | 32.0 ms                                                         | 21.3 ms: 1.50x faster                                                 |
| thread_memo_naive           | 11.5 ms                                                         | 23.7 ms: 2.05x slower                                                 |
| thread_montecarlo_naive     | 15.8 ms                                                         | 39.5 ms: 2.50x slower                                                 |
| Geometric mean              | (ref)                                                           | 2.07x faster                                                          |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| base32_large                     | 292 ms                                                          | 1.93 ms: 151.63x faster                                               |
| ascii85_large                    | 667 ms                                                          | 9.50 ms: 70.22x faster                                                |
| base85_large                     | 248 ms                                                          | 3.53 ms: 70.14x faster                                                |
| base32_small                     | 5.71 ms                                                         | 186 us: 30.64x faster                                                 |
| ascii85_small                    | 12.7 ms                                                         | 436 us: 29.10x faster                                                 |
| base85_small                     | 4.69 ms                                                         | 171 us: 27.48x faster                                                 |
| argparse_many_optionals          | 34.4 ms                                                         | 8.43 ms: 4.08x faster                                                 |
| thread_mandelbrot_naive          | 233 ms                                                          | 59.9 ms: 3.90x faster                                                 |
| thread_mandelbrot_optimized      | 233 ms                                                          | 59.8 ms: 3.90x faster                                                 |
| thread_pipeline_optimized        | 22.5 ms                                                         | 6.55 ms: 3.43x faster                                                 |
| thread_accumulate_optimized      | 35.1 ms                                                         | 10.6 ms: 3.31x faster                                                 |
| thread_accumulate_naive          | 35.8 ms                                                         | 11.4 ms: 3.15x faster                                                 |
| thread_counter_optimized         | 17.1 ms                                                         | 5.55 ms: 3.08x faster                                                 |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 4.80 ms: 2.90x faster                                                 |
| thread_memo_optimized            | 15.9 ms                                                         | 5.61 ms: 2.84x faster                                                 |
| pylint                           | 216 ms                                                          | 92.6 ms: 2.33x faster                                                 |
| gc_traversal                     | 3.26 ms                                                         | 1.58 ms: 2.06x faster                                                 |
| base64_large                     | 3.63 ms                                                         | 1.86 ms: 1.95x faster                                                 |
| create_gc_cycles                 | 1.96 ms                                                         | 1.26 ms: 1.56x faster                                                 |
| thread_counter_naive             | 20.2 ms                                                         | 13.0 ms: 1.56x faster                                                 |
| thread_pipeline_naive            | 32.0 ms                                                         | 21.3 ms: 1.50x faster                                                 |
| argparse_subparsers              | 686 us                                                          | 509 us: 1.35x faster                                                  |
| urlsafe_base64_small             | 329 us                                                          | 253 us: 1.30x faster                                                  |
| asyncio_tcp                      | 325 ms                                                          | 268 ms: 1.21x faster                                                  |
| fastapi_http                     | 216 ms                                                          | 193 ms: 1.12x faster                                                  |
| pathlib                          | 13.0 ms                                                         | 11.6 ms: 1.12x faster                                                 |
| tornado_http                     | 101 ms                                                          | 93.7 ms: 1.08x faster                                                 |
| xml_etree_iterparse              | 76.2 ms                                                         | 71.6 ms: 1.06x faster                                                 |
| asyncio_websockets               | 296 ms                                                          | 292 ms: 1.01x faster                                                  |
| pycparser                        | 851 ms                                                          | 841 ms: 1.01x faster                                                  |
| pidigits                         | 189 ms                                                          | 190 ms: 1.00x slower                                                  |
| async_tree_io_tg                 | 539 ms                                                          | 552 ms: 1.02x slower                                                  |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.33 sec: 1.04x slower                                                |
| networkx_k_core                  | 2.07 sec                                                        | 2.15 sec: 1.04x slower                                                |
| json_dumps                       | 6.95 ms                                                         | 7.21 ms: 1.04x slower                                                 |
| tomli_loads                      | 1.44 sec                                                        | 1.50 sec: 1.04x slower                                                |
| telco                            | 5.59 ms                                                         | 5.86 ms: 1.05x slower                                                 |
| html5lib                         | 46.9 ms                                                         | 49.2 ms: 1.05x slower                                                 |
| async_tree_eager_io              | 552 ms                                                          | 580 ms: 1.05x slower                                                  |
| regex_effbot                     | 1.95 ms                                                         | 2.05 ms: 1.05x slower                                                 |
| deepcopy                         | 193 us                                                          | 203 us: 1.05x slower                                                  |
| logging_simple                   | 4.79 us                                                         | 5.05 us: 1.06x slower                                                 |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.17 sec: 1.06x slower                                                |
| regex_dna                        | 150 ms                                                          | 159 ms: 1.06x slower                                                  |
| coroutines                       | 15.1 ms                                                         | 16.0 ms: 1.06x slower                                                 |
| logging_silent                   | 65.3 ns                                                         | 69.1 ns: 1.06x slower                                                 |
| mdp                              | 946 ms                                                          | 1.01 sec: 1.06x slower                                                |
| json                             | 3.42 ms                                                         | 3.65 ms: 1.07x slower                                                 |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 41.8 ms: 1.07x slower                                                 |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 337 ms: 1.07x slower                                                  |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 84.2 ms: 1.08x slower                                                 |
| logging_format                   | 5.35 us                                                         | 5.78 us: 1.08x slower                                                 |
| pickle_pure_python               | 240 us                                                          | 260 us: 1.08x slower                                                  |
| pickle                           | 8.20 us                                                         | 8.87 us: 1.08x slower                                                 |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.24 ms: 1.08x slower                                                 |
| async_tree_io                    | 531 ms                                                          | 575 ms: 1.08x slower                                                  |
| sympy_sum                        | 106 ms                                                          | 116 ms: 1.09x slower                                                  |
| thrift                           | 1.86 ms                                                         | 2.04 ms: 1.09x slower                                                 |
| quadtree_nbody                   | 596 ms                                                          | 653 ms: 1.10x slower                                                  |
| sympy_integrate                  | 15.4 ms                                                         | 16.9 ms: 1.10x slower                                                 |
| scimark_fft                      | 226 ms                                                          | 249 ms: 1.10x slower                                                  |
| deepcopy_memo                    | 18.0 us                                                         | 19.8 us: 1.10x slower                                                 |
| richards                         | 32.6 ms                                                         | 35.9 ms: 1.10x slower                                                 |
| chaos                            | 43.8 ms                                                         | 48.2 ms: 1.10x slower                                                 |
| decimal_factorial                | 173 ms                                                          | 191 ms: 1.10x slower                                                  |
| regex_compile                    | 93.9 ms                                                         | 104 ms: 1.10x slower                                                  |
| sqlglot_v2_parse                 | 911 us                                                          | 1.00 ms: 1.10x slower                                                 |
| sympy_expand                     | 332 ms                                                          | 368 ms: 1.11x slower                                                  |
| unpickle_pure_python             | 152 us                                                          | 169 us: 1.11x slower                                                  |
| sympy_str                        | 194 ms                                                          | 216 ms: 1.11x slower                                                  |
| richards_super                   | 37.4 ms                                                         | 41.6 ms: 1.11x slower                                                 |
| xml_etree_parse                  | 94.3 ms                                                         | 105 ms: 1.11x slower                                                  |
| xml_etree_generate               | 62.6 ms                                                         | 69.8 ms: 1.12x slower                                                 |
| comprehensions                   | 10.8 us                                                         | 12.0 us: 1.12x slower                                                 |
| pickle_dict                      | 21.5 us                                                         | 24.1 us: 1.12x slower                                                 |
| scimark_sor                      | 75.7 ms                                                         | 84.6 ms: 1.12x slower                                                 |
| hexiom                           | 4.11 ms                                                         | 4.62 ms: 1.12x slower                                                 |
| base64_small                     | 186 us                                                          | 209 us: 1.13x slower                                                  |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 463 ms: 1.13x slower                                                  |
| docutils                         | 1.95 sec                                                        | 2.20 sec: 1.13x slower                                                |
| django_template                  | 27.8 ms                                                         | 31.5 ms: 1.13x slower                                                 |
| mypy2                            | 753 ms                                                          | 865 ms: 1.15x slower                                                  |
| go                               | 84.7 ms                                                         | 97.5 ms: 1.15x slower                                                 |
| generators                       | 20.3 ms                                                         | 23.4 ms: 1.15x slower                                                 |
| xdsl_constant_fold               | 34.7 ms                                                         | 40.2 ms: 1.16x slower                                                 |
| deepcopy_reduce                  | 2.00 us                                                         | 2.31 us: 1.16x slower                                                 |
| json_loads                       | 17.5 us                                                         | 20.3 us: 1.16x slower                                                 |
| async_tree_eager_memoization     | 180 ms                                                          | 209 ms: 1.16x slower                                                  |
| unpickle_list                    | 3.43 us                                                         | 3.99 us: 1.16x slower                                                 |
| chameleon                        | 9.52 ms                                                         | 11.1 ms: 1.17x slower                                                 |
| xml_etree_process                | 44.7 ms                                                         | 52.5 ms: 1.17x slower                                                 |
| networkx_shortest_path           | 444 ms                                                          | 522 ms: 1.17x slower                                                  |
| base16_large                     | 5.33 ms                                                         | 6.29 ms: 1.18x slower                                                 |
| noop                             | 19.4 ns                                                         | 22.9 ns: 1.18x slower                                                 |
| raytrace                         | 194 ms                                                          | 230 ms: 1.18x slower                                                  |
| async_generators                 | 228 ms                                                          | 270 ms: 1.19x slower                                                  |
| pyflate                          | 299 ms                                                          | 355 ms: 1.19x slower                                                  |
| spectral_norm                    | 65.6 ms                                                         | 77.8 ms: 1.19x slower                                                 |
| pprint_safe_repr                 | 474 ms                                                          | 563 ms: 1.19x slower                                                  |
| async_tree_eager                 | 81.3 ms                                                         | 96.7 ms: 1.19x slower                                                 |
| scimark_lu                       | 73.8 ms                                                         | 87.9 ms: 1.19x slower                                                 |
| decimal_pi                       | 208 ms                                                          | 247 ms: 1.19x slower                                                  |
| pprint_pformat                   | 989 ms                                                          | 1.18 sec: 1.19x slower                                                |
| async_tree_none_tg               | 223 ms                                                          | 267 ms: 1.19x slower                                                  |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 490 ms: 1.20x slower                                                  |
| python_startup                   | 9.73 ms                                                         | 11.7 ms: 1.20x slower                                                 |
| unpickle                         | 10.2 us                                                         | 12.3 us: 1.20x slower                                                 |
| meteor_contest                   | 84.1 ms                                                         | 101 ms: 1.21x slower                                                  |
| nqueens                          | 56.8 ms                                                         | 68.8 ms: 1.21x slower                                                 |
| crypto_pyaes                     | 54.5 ms                                                         | 66.0 ms: 1.21x slower                                                 |
| deltablue                        | 2.34 ms                                                         | 2.84 ms: 1.22x slower                                                 |
| async_tree_memoization_tg        | 277 ms                                                          | 340 ms: 1.23x slower                                                  |
| async_tree_none                  | 228 ms                                                          | 279 ms: 1.23x slower                                                  |
| unpack_sequence                  | 25.8 ns                                                         | 31.6 ns: 1.23x slower                                                 |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 3.93 ms: 1.23x slower                                                 |
| pickle_list                      | 3.24 us                                                         | 4.00 us: 1.24x slower                                                 |
| python_startup_no_site           | 6.38 ms                                                         | 7.94 ms: 1.24x slower                                                 |
| fannkuch                         | 245 ms                                                          | 306 ms: 1.25x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 453 ms: 1.25x slower                                                  |
| typing_runtime_protocols         | 112 us                                                          | 143 us: 1.28x slower                                                  |
| async_tree_memoization           | 281 ms                                                          | 361 ms: 1.29x slower                                                  |
| async_tree_eager_tg              | 182 ms                                                          | 237 ms: 1.30x slower                                                  |
| nbody                            | 67.9 ms                                                         | 88.4 ms: 1.30x slower                                                 |
| scimark_monte_carlo              | 40.7 ms                                                         | 53.0 ms: 1.30x slower                                                 |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 325 ms: 1.38x slower                                                  |
| base16_small                     | 305 us                                                          | 422 us: 1.38x slower                                                  |
| networkx_connected_components    | 438 ms                                                          | 610 ms: 1.39x slower                                                  |
| coverage                         | 57.4 ms                                                         | 81.3 ms: 1.41x slower                                                 |
| float                            | 47.3 ms                                                         | 67.1 ms: 1.42x slower                                                 |
| mako                             | 7.40 ms                                                         | 11.8 ms: 1.60x slower                                                 |
| thread_memo_naive                | 11.5 ms                                                         | 23.7 ms: 2.05x slower                                                 |
| thread_montecarlo_naive          | 15.8 ms                                                         | 39.5 ms: 2.50x slower                                                 |
| Geometric mean                   | (ref)                                                           | 1.19x faster                                                          |

Benchmark hidden because not significant (2): regex_v8, async_tree_eager_io_tg
Ignored benchmarks (3) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.192x faster

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.07x
- 95% likely to have a slowdown of 1.06x
- 99% likely to have a slowdown of 1.05x

# Memory
- memory change: 1.48x