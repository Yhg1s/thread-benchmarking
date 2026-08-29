# Results vs. 3.14.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.164x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.01x slower
- Memory change: 0.95x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 10.1 ms: 1.07x slower                                                 |
| docutils       | 1.95 sec                                                        | 1.86 sec: 1.04x faster                                                |
| fastapi_http   | 216 ms                                                          | 223 ms: 1.04x slower                                                  |
| html5lib       | 46.9 ms                                                         | 48.2 ms: 1.03x slower                                                 |
| tornado_http   | 101 ms                                                          | 99.4 ms: 1.02x faster                                                 |
| Geometric mean | (ref)                                                           | 1.01x slower                                                          |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| asyncio_tcp                      | 325 ms                                                          | 268 ms: 1.21x faster                                                  |
| async_tree_eager                 | 81.3 ms                                                         | 79.2 ms: 1.03x faster                                                 |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.26 sec: 1.02x faster                                                |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 319 ms: 1.02x slower                                                  |
| async_tree_eager_memoization     | 180 ms                                                          | 183 ms: 1.02x slower                                                  |
| coroutines                       | 15.1 ms                                                         | 16.0 ms: 1.06x slower                                                 |
| asyncio_websockets               | 296 ms                                                          | 313 ms: 1.06x slower                                                  |
| async_generators                 | 228 ms                                                          | 244 ms: 1.07x slower                                                  |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 450 ms: 1.10x slower                                                  |
| async_tree_none                  | 228 ms                                                          | 252 ms: 1.10x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 403 ms: 1.11x slower                                                  |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 466 ms: 1.14x slower                                                  |
| async_tree_eager_io              | 552 ms                                                          | 631 ms: 1.14x slower                                                  |
| async_tree_eager_tg              | 182 ms                                                          | 209 ms: 1.14x slower                                                  |
| async_tree_none_tg               | 223 ms                                                          | 262 ms: 1.17x slower                                                  |
| async_tree_memoization           | 281 ms                                                          | 332 ms: 1.18x slower                                                  |
| async_tree_memoization_tg        | 277 ms                                                          | 328 ms: 1.18x slower                                                  |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 283 ms: 1.20x slower                                                  |
| async_tree_io                    | 531 ms                                                          | 638 ms: 1.20x slower                                                  |
| async_tree_eager_io_tg           | 550 ms                                                          | 669 ms: 1.21x slower                                                  |
| async_tree_io_tg                 | 539 ms                                                          | 678 ms: 1.26x slower                                                  |
| Geometric mean                   | (ref)                                                           | 1.10x slower                                                          |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 21.1 ns: 1.09x slower                                                 |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 176 ms: 1.02x slower                                                  |
| decimal_pi        | 208 ms                                                          | 217 ms: 1.05x slower                                                  |
| Geometric mean    | (ref)                                                           | 1.03x slower                                                          |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 194 ms: 1.03x slower                                                  |
| float          | 47.3 ms                                                         | 55.7 ms: 1.18x slower                                                 |
| Geometric mean | (ref)                                                           | 1.05x slower                                                          |

Benchmark hidden because not significant (2): quadtree_nbody, nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| regex_v8       | 14.8 ms                                                         | 15.1 ms: 1.02x slower                                                 |
| regex_compile  | 93.9 ms                                                         | 95.7 ms: 1.02x slower                                                 |
| regex_effbot   | 1.95 ms                                                         | 2.01 ms: 1.04x slower                                                 |
| regex_dna      | 150 ms                                                          | 156 ms: 1.04x slower                                                  |
| Geometric mean | (ref)                                                           | 1.03x slower                                                          |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| base32_large         | 292 ms                                                          | 1.89 ms: 155.01x faster                                               |
| ascii85_large        | 667 ms                                                          | 9.49 ms: 70.32x faster                                                |
| base85_large         | 248 ms                                                          | 3.53 ms: 70.09x faster                                                |
| ascii85_small        | 12.7 ms                                                         | 510 us: 24.85x faster                                                 |
| base32_small         | 5.71 ms                                                         | 231 us: 24.67x faster                                                 |
| base85_small         | 4.69 ms                                                         | 211 us: 22.27x faster                                                 |
| base64_large         | 3.63 ms                                                         | 1.89 ms: 1.92x faster                                                 |
| urlsafe_base64_small | 329 us                                                          | 289 us: 1.14x faster                                                  |
| json_dumps           | 6.95 ms                                                         | 6.45 ms: 1.08x faster                                                 |
| json_loads           | 17.5 us                                                         | 16.8 us: 1.04x faster                                                 |
| unpickle_pure_python | 152 us                                                          | 154 us: 1.01x slower                                                  |
| tomli_loads          | 1.44 sec                                                        | 1.47 sec: 1.02x slower                                                |
| unpickle             | 10.2 us                                                         | 10.6 us: 1.05x slower                                                 |
| xml_etree_iterparse  | 76.2 ms                                                         | 79.7 ms: 1.05x slower                                                 |
| unpickle_list        | 3.43 us                                                         | 3.62 us: 1.05x slower                                                 |
| xml_etree_generate   | 62.6 ms                                                         | 66.9 ms: 1.07x slower                                                 |
| xml_etree_process    | 44.7 ms                                                         | 48.1 ms: 1.08x slower                                                 |
| pickle_dict          | 21.5 us                                                         | 23.2 us: 1.08x slower                                                 |
| pickle               | 8.20 us                                                         | 8.90 us: 1.09x slower                                                 |
| xml_etree_parse      | 94.3 ms                                                         | 108 ms: 1.15x slower                                                  |
| pickle_list          | 3.24 us                                                         | 3.80 us: 1.17x slower                                                 |
| base16_large         | 5.33 ms                                                         | 7.31 ms: 1.37x slower                                                 |
| base64_small         | 186 us                                                          | 257 us: 1.38x slower                                                  |
| base16_small         | 305 us                                                          | 457 us: 1.49x slower                                                  |
| Geometric mean       | (ref)                                                           | 2.43x faster                                                          |

Benchmark hidden because not significant (1): pickle_pure_python

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| python_startup_no_site | 6.38 ms                                                         | 5.99 ms: 1.06x faster                                                 |
| python_startup         | 9.73 ms                                                         | 9.67 ms: 1.01x faster                                                 |
| Geometric mean         | (ref)                                                           | 1.03x faster                                                          |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| mako            | 7.40 ms                                                         | 7.68 ms: 1.04x slower                                                 |
| django_template | 27.8 ms                                                         | 29.7 ms: 1.07x slower                                                 |
| Geometric mean  | (ref)                                                           | 1.05x slower                                                          |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| thread_memo_naive           | 11.5 ms                                                         | 10.3 ms: 1.12x faster                                                 |
| thread_mandelbrot_naive     | 233 ms                                                          | 225 ms: 1.04x faster                                                  |
| thread_mandelbrot_optimized | 233 ms                                                          | 228 ms: 1.02x faster                                                  |
| thread_montecarlo_optimized | 13.9 ms                                                         | 14.7 ms: 1.06x slower                                                 |
| thread_montecarlo_naive     | 15.8 ms                                                         | 17.2 ms: 1.09x slower                                                 |
| thread_pipeline_naive       | 32.0 ms                                                         | 36.4 ms: 1.14x slower                                                 |
| thread_counter_naive        | 20.2 ms                                                         | 23.1 ms: 1.14x slower                                                 |
| thread_accumulate_naive     | 35.8 ms                                                         | 41.5 ms: 1.16x slower                                                 |
| thread_memo_optimized       | 15.9 ms                                                         | 18.5 ms: 1.16x slower                                                 |
| thread_accumulate_optimized | 35.1 ms                                                         | 41.5 ms: 1.18x slower                                                 |
| thread_pipeline_optimized   | 22.5 ms                                                         | 27.1 ms: 1.21x slower                                                 |
| thread_counter_optimized    | 17.1 ms                                                         | 20.8 ms: 1.22x slower                                                 |
| Geometric mean              | (ref)                                                           | 1.09x slower                                                          |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| base32_large                     | 292 ms                                                          | 1.89 ms: 155.01x faster                                               |
| ascii85_large                    | 667 ms                                                          | 9.49 ms: 70.32x faster                                                |
| base85_large                     | 248 ms                                                          | 3.53 ms: 70.09x faster                                                |
| ascii85_small                    | 12.7 ms                                                         | 510 us: 24.85x faster                                                 |
| base32_small                     | 5.71 ms                                                         | 231 us: 24.67x faster                                                 |
| base85_small                     | 4.69 ms                                                         | 211 us: 22.27x faster                                                 |
| argparse_many_optionals          | 34.4 ms                                                         | 7.58 ms: 4.54x faster                                                 |
| pylint                           | 216 ms                                                          | 99.5 ms: 2.17x faster                                                 |
| base64_large                     | 3.63 ms                                                         | 1.89 ms: 1.92x faster                                                 |
| argparse_subparsers              | 686 us                                                          | 456 us: 1.51x faster                                                  |
| asyncio_tcp                      | 325 ms                                                          | 268 ms: 1.21x faster                                                  |
| create_gc_cycles                 | 1.96 ms                                                         | 1.67 ms: 1.18x faster                                                 |
| urlsafe_base64_small             | 329 us                                                          | 289 us: 1.14x faster                                                  |
| thread_memo_naive                | 11.5 ms                                                         | 10.3 ms: 1.12x faster                                                 |
| pathlib                          | 13.0 ms                                                         | 11.8 ms: 1.10x faster                                                 |
| json_dumps                       | 6.95 ms                                                         | 6.45 ms: 1.08x faster                                                 |
| deepcopy                         | 193 us                                                          | 179 us: 1.08x faster                                                  |
| python_startup_no_site           | 6.38 ms                                                         | 5.99 ms: 1.06x faster                                                 |
| telco                            | 5.59 ms                                                         | 5.28 ms: 1.06x faster                                                 |
| logging_silent                   | 65.3 ns                                                         | 62.1 ns: 1.05x faster                                                 |
| docutils                         | 1.95 sec                                                        | 1.86 sec: 1.04x faster                                                |
| mypy2                            | 753 ms                                                          | 723 ms: 1.04x faster                                                  |
| json_loads                       | 17.5 us                                                         | 16.8 us: 1.04x faster                                                 |
| thread_mandelbrot_naive          | 233 ms                                                          | 225 ms: 1.04x faster                                                  |
| sqlglot_v2_parse                 | 911 us                                                          | 880 us: 1.04x faster                                                  |
| deepcopy_memo                    | 18.0 us                                                         | 17.5 us: 1.03x faster                                                 |
| async_tree_eager                 | 81.3 ms                                                         | 79.2 ms: 1.03x faster                                                 |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.12 ms: 1.03x faster                                                 |
| chaos                            | 43.8 ms                                                         | 42.7 ms: 1.03x faster                                                 |
| logging_simple                   | 4.79 us                                                         | 4.67 us: 1.02x faster                                                 |
| thread_mandelbrot_optimized      | 233 ms                                                          | 228 ms: 1.02x faster                                                  |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.26 sec: 1.02x faster                                                |
| tornado_http                     | 101 ms                                                          | 99.4 ms: 1.02x faster                                                 |
| json                             | 3.42 ms                                                         | 3.38 ms: 1.01x faster                                                 |
| unpack_sequence                  | 25.8 ns                                                         | 25.5 ns: 1.01x faster                                                 |
| deepcopy_reduce                  | 2.00 us                                                         | 1.98 us: 1.01x faster                                                 |
| spectral_norm                    | 65.6 ms                                                         | 65.1 ms: 1.01x faster                                                 |
| python_startup                   | 9.73 ms                                                         | 9.67 ms: 1.01x faster                                                 |
| scimark_sor                      | 75.7 ms                                                         | 75.2 ms: 1.01x faster                                                 |
| richards                         | 32.6 ms                                                         | 33.0 ms: 1.01x slower                                                 |
| comprehensions                   | 10.8 us                                                         | 10.9 us: 1.01x slower                                                 |
| unpickle_pure_python             | 152 us                                                          | 154 us: 1.01x slower                                                  |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 319 ms: 1.02x slower                                                  |
| tomli_loads                      | 1.44 sec                                                        | 1.47 sec: 1.02x slower                                                |
| regex_v8                         | 14.8 ms                                                         | 15.1 ms: 1.02x slower                                                 |
| async_tree_eager_memoization     | 180 ms                                                          | 183 ms: 1.02x slower                                                  |
| sympy_integrate                  | 15.4 ms                                                         | 15.6 ms: 1.02x slower                                                 |
| regex_compile                    | 93.9 ms                                                         | 95.7 ms: 1.02x slower                                                 |
| decimal_factorial                | 173 ms                                                          | 176 ms: 1.02x slower                                                  |
| go                               | 84.7 ms                                                         | 86.4 ms: 1.02x slower                                                 |
| richards_super                   | 37.4 ms                                                         | 38.2 ms: 1.02x slower                                                 |
| scimark_fft                      | 226 ms                                                          | 231 ms: 1.02x slower                                                  |
| pidigits                         | 189 ms                                                          | 194 ms: 1.03x slower                                                  |
| sympy_expand                     | 332 ms                                                          | 341 ms: 1.03x slower                                                  |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 80.4 ms: 1.03x slower                                                 |
| html5lib                         | 46.9 ms                                                         | 48.2 ms: 1.03x slower                                                 |
| sympy_sum                        | 106 ms                                                          | 109 ms: 1.03x slower                                                  |
| pycparser                        | 851 ms                                                          | 877 ms: 1.03x slower                                                  |
| gc_traversal                     | 3.26 ms                                                         | 3.36 ms: 1.03x slower                                                 |
| regex_effbot                     | 1.95 ms                                                         | 2.01 ms: 1.04x slower                                                 |
| sympy_str                        | 194 ms                                                          | 201 ms: 1.04x slower                                                  |
| fastapi_http                     | 216 ms                                                          | 223 ms: 1.04x slower                                                  |
| mako                             | 7.40 ms                                                         | 7.68 ms: 1.04x slower                                                 |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 40.6 ms: 1.04x slower                                                 |
| regex_dna                        | 150 ms                                                          | 156 ms: 1.04x slower                                                  |
| networkx_k_core                  | 2.07 sec                                                        | 2.16 sec: 1.04x slower                                                |
| crypto_pyaes                     | 54.5 ms                                                         | 56.9 ms: 1.04x slower                                                 |
| hexiom                           | 4.11 ms                                                         | 4.29 ms: 1.04x slower                                                 |
| unpickle                         | 10.2 us                                                         | 10.6 us: 1.05x slower                                                 |
| decimal_pi                       | 208 ms                                                          | 217 ms: 1.05x slower                                                  |
| pyflate                          | 299 ms                                                          | 313 ms: 1.05x slower                                                  |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.14 sec: 1.05x slower                                                |
| xml_etree_iterparse              | 76.2 ms                                                         | 79.7 ms: 1.05x slower                                                 |
| pprint_pformat                   | 989 ms                                                          | 1.04 sec: 1.05x slower                                                |
| meteor_contest                   | 84.1 ms                                                         | 88.2 ms: 1.05x slower                                                 |
| unpickle_list                    | 3.43 us                                                         | 3.62 us: 1.05x slower                                                 |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 14.7 ms: 1.06x slower                                                 |
| coroutines                       | 15.1 ms                                                         | 16.0 ms: 1.06x slower                                                 |
| asyncio_websockets               | 296 ms                                                          | 313 ms: 1.06x slower                                                  |
| thrift                           | 1.86 ms                                                         | 1.97 ms: 1.06x slower                                                 |
| networkx_shortest_path           | 444 ms                                                          | 471 ms: 1.06x slower                                                  |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 3.38 ms: 1.06x slower                                                 |
| deltablue                        | 2.34 ms                                                         | 2.48 ms: 1.06x slower                                                 |
| coverage                         | 57.4 ms                                                         | 61.1 ms: 1.06x slower                                                 |
| django_template                  | 27.8 ms                                                         | 29.7 ms: 1.07x slower                                                 |
| chameleon                        | 9.52 ms                                                         | 10.1 ms: 1.07x slower                                                 |
| xml_etree_generate               | 62.6 ms                                                         | 66.9 ms: 1.07x slower                                                 |
| async_generators                 | 228 ms                                                          | 244 ms: 1.07x slower                                                  |
| pprint_safe_repr                 | 474 ms                                                          | 509 ms: 1.07x slower                                                  |
| scimark_monte_carlo              | 40.7 ms                                                         | 43.8 ms: 1.08x slower                                                 |
| xml_etree_process                | 44.7 ms                                                         | 48.1 ms: 1.08x slower                                                 |
| pickle_dict                      | 21.5 us                                                         | 23.2 us: 1.08x slower                                                 |
| scimark_lu                       | 73.8 ms                                                         | 80.0 ms: 1.08x slower                                                 |
| xdsl_constant_fold               | 34.7 ms                                                         | 37.7 ms: 1.09x slower                                                 |
| pickle                           | 8.20 us                                                         | 8.90 us: 1.09x slower                                                 |
| typing_runtime_protocols         | 112 us                                                          | 122 us: 1.09x slower                                                  |
| thread_montecarlo_naive          | 15.8 ms                                                         | 17.2 ms: 1.09x slower                                                 |
| noop                             | 19.4 ns                                                         | 21.1 ns: 1.09x slower                                                 |
| generators                       | 20.3 ms                                                         | 22.3 ms: 1.10x slower                                                 |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 450 ms: 1.10x slower                                                  |
| async_tree_none                  | 228 ms                                                          | 252 ms: 1.10x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 403 ms: 1.11x slower                                                  |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 466 ms: 1.14x slower                                                  |
| thread_pipeline_naive            | 32.0 ms                                                         | 36.4 ms: 1.14x slower                                                 |
| thread_counter_naive             | 20.2 ms                                                         | 23.1 ms: 1.14x slower                                                 |
| async_tree_eager_io              | 552 ms                                                          | 631 ms: 1.14x slower                                                  |
| async_tree_eager_tg              | 182 ms                                                          | 209 ms: 1.14x slower                                                  |
| xml_etree_parse                  | 94.3 ms                                                         | 108 ms: 1.15x slower                                                  |
| thread_accumulate_naive          | 35.8 ms                                                         | 41.5 ms: 1.16x slower                                                 |
| thread_memo_optimized            | 15.9 ms                                                         | 18.5 ms: 1.16x slower                                                 |
| pickle_list                      | 3.24 us                                                         | 3.80 us: 1.17x slower                                                 |
| async_tree_none_tg               | 223 ms                                                          | 262 ms: 1.17x slower                                                  |
| float                            | 47.3 ms                                                         | 55.7 ms: 1.18x slower                                                 |
| thread_accumulate_optimized      | 35.1 ms                                                         | 41.5 ms: 1.18x slower                                                 |
| async_tree_memoization           | 281 ms                                                          | 332 ms: 1.18x slower                                                  |
| async_tree_memoization_tg        | 277 ms                                                          | 328 ms: 1.18x slower                                                  |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 283 ms: 1.20x slower                                                  |
| async_tree_io                    | 531 ms                                                          | 638 ms: 1.20x slower                                                  |
| thread_pipeline_optimized        | 22.5 ms                                                         | 27.1 ms: 1.21x slower                                                 |
| async_tree_eager_io_tg           | 550 ms                                                          | 669 ms: 1.21x slower                                                  |
| thread_counter_optimized         | 17.1 ms                                                         | 20.8 ms: 1.22x slower                                                 |
| async_tree_io_tg                 | 539 ms                                                          | 678 ms: 1.26x slower                                                  |
| networkx_connected_components    | 438 ms                                                          | 560 ms: 1.28x slower                                                  |
| base16_large                     | 5.33 ms                                                         | 7.31 ms: 1.37x slower                                                 |
| base64_small                     | 186 us                                                          | 257 us: 1.38x slower                                                  |
| base16_small                     | 305 us                                                          | 457 us: 1.49x slower                                                  |
| Geometric mean                   | (ref)                                                           | 1.16x faster                                                          |

Benchmark hidden because not significant (8): logging_format, fannkuch, raytrace, nqueens, pickle_pure_python, quadtree_nbody, mdp, nbody
Ignored benchmarks (3) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.164x faster

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.02x
- 95% likely to have a slowdown of 1.02x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 0.95x