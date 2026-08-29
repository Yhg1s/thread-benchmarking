# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.080x faster
- HPT reliability: 99.95%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.10x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 10.1 ms: 1.01x slower                                               |
| docutils       | 1.89 sec                                                        | 1.96 sec: 1.04x slower                                              |
| html5lib       | 51.7 ms                                                         | 44.7 ms: 1.16x faster                                               |
| Geometric mean | (ref)                                                           | 1.02x faster                                                        |

Benchmark hidden because not significant (2): fastapi_http, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_memoization_tg        | 419 ms                                                          | 264 ms: 1.59x faster                                                |
| async_tree_io_tg                 | 778 ms                                                          | 490 ms: 1.59x faster                                                |
| async_tree_eager_io_tg           | 728 ms                                                          | 467 ms: 1.56x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 484 ms: 1.55x faster                                                |
| async_tree_io                    | 741 ms                                                          | 497 ms: 1.49x faster                                                |
| async_tree_none_tg               | 291 ms                                                          | 202 ms: 1.44x faster                                                |
| async_tree_memoization           | 388 ms                                                          | 274 ms: 1.41x faster                                                |
| async_tree_none                  | 308 ms                                                          | 220 ms: 1.40x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 381 ms: 1.28x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 173 ms: 1.27x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 388 ms: 1.22x faster                                                |
| asyncio_tcp                      | 318 ms                                                          | 265 ms: 1.20x faster                                                |
| async_tree_eager                 | 89.6 ms                                                         | 80.9 ms: 1.11x faster                                               |
| async_generators                 | 240 ms                                                          | 223 ms: 1.08x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 302 ms: 1.07x faster                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.26 sec: 1.02x faster                                              |
| asyncio_websockets               | 303 ms                                                          | 312 ms: 1.03x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 344 ms: 1.20x slower                                                |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 228 ms: 1.30x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                         | 179 ms: 3.06x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.14x faster                                                        |

Benchmark hidden because not significant (1): coroutines

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 21.3 ns: 1.04x slower                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                          | 210 ms: 1.06x faster                                                |
| decimal_factorial | 177 ms                                                          | 173 ms: 1.02x faster                                                |
| Geometric mean    | (ref)                                                           | 1.04x faster                                                        |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 49.1 ms: 1.16x faster                                               |
| quadtree_nbody | 626 ms                                                          | 587 ms: 1.07x faster                                                |
| pidigits       | 189 ms                                                          | 188 ms: 1.00x faster                                                |
| nbody          | 65.9 ms                                                         | 67.0 ms: 1.02x slower                                               |
| Geometric mean | (ref)                                                           | 1.05x faster                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 2.01 ms: 1.14x faster                                               |
| regex_compile  | 98.5 ms                                                         | 94.2 ms: 1.05x faster                                               |
| regex_dna      | 162 ms                                                          | 157 ms: 1.03x faster                                                |
| regex_v8       | 15.2 ms                                                         | 14.9 ms: 1.02x faster                                               |
| Geometric mean | (ref)                                                           | 1.06x faster                                                        |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 4.91 ms: 7.53x faster                                               |
| base16_small         | 740 us                                                          | 302 us: 2.45x faster                                                |
| xml_etree_iterparse  | 79.9 ms                                                         | 69.6 ms: 1.15x faster                                               |
| xml_etree_parse      | 104 ms                                                          | 93.5 ms: 1.12x faster                                               |
| json_dumps           | 6.95 ms                                                         | 6.41 ms: 1.08x faster                                               |
| ascii85_large        | 717 ms                                                          | 671 ms: 1.07x faster                                                |
| ascii85_small        | 13.6 ms                                                         | 12.8 ms: 1.06x faster                                               |
| pickle_dict          | 22.0 us                                                         | 21.2 us: 1.04x faster                                               |
| xml_etree_generate   | 64.2 ms                                                         | 62.3 ms: 1.03x faster                                               |
| xml_etree_process    | 46.6 ms                                                         | 45.7 ms: 1.02x faster                                               |
| urlsafe_base64_small | 325 us                                                          | 328 us: 1.01x slower                                                |
| unpickle             | 10.5 us                                                         | 10.6 us: 1.01x slower                                               |
| base85_large         | 252 ms                                                          | 254 ms: 1.01x slower                                                |
| unpickle_pure_python | 151 us                                                          | 153 us: 1.01x slower                                                |
| base32_large         | 296 ms                                                          | 303 ms: 1.03x slower                                                |
| base32_small         | 5.79 ms                                                         | 5.96 ms: 1.03x slower                                               |
| base85_small         | 4.59 ms                                                         | 4.74 ms: 1.03x slower                                               |
| json_loads           | 16.2 us                                                         | 16.8 us: 1.03x slower                                               |
| tomli_loads          | 1.62 sec                                                        | 1.68 sec: 1.03x slower                                              |
| base64_large         | 3.33 ms                                                         | 3.45 ms: 1.04x slower                                               |
| unpickle_list        | 3.33 us                                                         | 3.49 us: 1.05x slower                                               |
| pickle_list          | 3.14 us                                                         | 3.33 us: 1.06x slower                                               |
| pickle_pure_python   | 223 us                                                          | 242 us: 1.08x slower                                                |
| pickle               | 7.44 us                                                         | 8.38 us: 1.13x slower                                               |
| Geometric mean       | (ref)                                                           | 1.12x faster                                                        |

Benchmark hidden because not significant (1): base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 6.19 ms: 1.04x faster                                               |
| python_startup         | 9.51 ms                                                         | 9.39 ms: 1.01x faster                                               |
| Geometric mean         | (ref)                                                           | 1.03x faster                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| genshi_text     | 17.8 ms                                                         | 17.1 ms: 1.05x faster                                               |
| genshi_xml      | 41.3 ms                                                         | 41.0 ms: 1.01x faster                                               |
| mako            | 7.16 ms                                                         | 7.70 ms: 1.08x slower                                               |
| django_template | 27.6 ms                                                         | 29.8 ms: 1.08x slower                                               |
| Geometric mean  | (ref)                                                           | 1.03x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_memo_naive           | 36.1 ms                                                         | 10.5 ms: 3.43x faster                                               |
| thread_pipeline_naive       | 47.3 ms                                                         | 33.7 ms: 1.40x faster                                               |
| thread_montecarlo_naive     | 19.0 ms                                                         | 16.8 ms: 1.13x faster                                               |
| thread_montecarlo_optimized | 14.5 ms                                                         | 14.2 ms: 1.02x faster                                               |
| thread_mandelbrot_naive     | 210 ms                                                          | 221 ms: 1.05x slower                                                |
| thread_counter_naive        | 20.6 ms                                                         | 22.1 ms: 1.07x slower                                               |
| thread_mandelbrot_optimized | 208 ms                                                          | 228 ms: 1.10x slower                                                |
| thread_memo_optimized       | 15.3 ms                                                         | 17.7 ms: 1.16x slower                                               |
| thread_accumulate_naive     | 33.4 ms                                                         | 39.2 ms: 1.17x slower                                               |
| thread_counter_optimized    | 16.5 ms                                                         | 20.0 ms: 1.21x slower                                               |
| thread_accumulate_optimized | 32.3 ms                                                         | 39.1 ms: 1.21x slower                                               |
| thread_pipeline_optimized   | 20.9 ms                                                         | 25.5 ms: 1.22x slower                                               |
| Geometric mean              | (ref)                                                           | 1.05x faster                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 4.91 ms: 7.53x faster                                               |
| thread_memo_naive                | 36.1 ms                                                         | 10.5 ms: 3.43x faster                                               |
| base16_small                     | 740 us                                                          | 302 us: 2.45x faster                                                |
| mdp                              | 2.15 sec                                                        | 964 ms: 2.23x faster                                                |
| argparse_many_optionals          | 12.8 ms                                                         | 7.59 ms: 1.69x faster                                               |
| async_tree_memoization_tg        | 419 ms                                                          | 264 ms: 1.59x faster                                                |
| async_tree_io_tg                 | 778 ms                                                          | 490 ms: 1.59x faster                                                |
| async_tree_eager_io_tg           | 728 ms                                                          | 467 ms: 1.56x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 484 ms: 1.55x faster                                                |
| deepcopy_memo                    | 26.5 us                                                         | 17.3 us: 1.53x faster                                               |
| async_tree_io                    | 741 ms                                                          | 497 ms: 1.49x faster                                                |
| deepcopy                         | 269 us                                                          | 186 us: 1.44x faster                                                |
| async_tree_none_tg               | 291 ms                                                          | 202 ms: 1.44x faster                                                |
| async_tree_memoization           | 388 ms                                                          | 274 ms: 1.41x faster                                                |
| thread_pipeline_naive            | 47.3 ms                                                         | 33.7 ms: 1.40x faster                                               |
| async_tree_none                  | 308 ms                                                          | 220 ms: 1.40x faster                                                |
| go                               | 117 ms                                                          | 85.5 ms: 1.37x faster                                               |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 381 ms: 1.28x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 173 ms: 1.27x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 388 ms: 1.22x faster                                                |
| richards                         | 37.8 ms                                                         | 31.0 ms: 1.22x faster                                               |
| deepcopy_reduce                  | 2.40 us                                                         | 2.00 us: 1.20x faster                                               |
| asyncio_tcp                      | 318 ms                                                          | 265 ms: 1.20x faster                                                |
| richards_super                   | 42.8 ms                                                         | 36.2 ms: 1.18x faster                                               |
| float                            | 57.0 ms                                                         | 49.1 ms: 1.16x faster                                               |
| html5lib                         | 51.7 ms                                                         | 44.7 ms: 1.16x faster                                               |
| xml_etree_iterparse              | 79.9 ms                                                         | 69.6 ms: 1.15x faster                                               |
| telco                            | 5.83 ms                                                         | 5.11 ms: 1.14x faster                                               |
| regex_effbot                     | 2.30 ms                                                         | 2.01 ms: 1.14x faster                                               |
| thread_montecarlo_naive          | 19.0 ms                                                         | 16.8 ms: 1.13x faster                                               |
| networkx_k_core                  | 2.16 sec                                                        | 1.91 sec: 1.13x faster                                              |
| xml_etree_parse                  | 104 ms                                                          | 93.5 ms: 1.12x faster                                               |
| scimark_monte_carlo              | 46.5 ms                                                         | 41.9 ms: 1.11x faster                                               |
| async_tree_eager                 | 89.6 ms                                                         | 80.9 ms: 1.11x faster                                               |
| pathlib                          | 12.8 ms                                                         | 11.6 ms: 1.11x faster                                               |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.00 sec: 1.10x faster                                              |
| pyflate                          | 342 ms                                                          | 315 ms: 1.08x faster                                                |
| json_dumps                       | 6.95 ms                                                         | 6.41 ms: 1.08x faster                                               |
| scimark_sor                      | 78.9 ms                                                         | 72.9 ms: 1.08x faster                                               |
| unpack_sequence                  | 27.1 ns                                                         | 25.1 ns: 1.08x faster                                               |
| chaos                            | 45.1 ms                                                         | 41.9 ms: 1.08x faster                                               |
| async_generators                 | 240 ms                                                          | 223 ms: 1.08x faster                                                |
| pprint_pformat                   | 1.09 sec                                                        | 1.01 sec: 1.07x faster                                              |
| xdsl_constant_fold               | 36.7 ms                                                         | 34.2 ms: 1.07x faster                                               |
| ascii85_large                    | 717 ms                                                          | 671 ms: 1.07x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 302 ms: 1.07x faster                                                |
| quadtree_nbody                   | 626 ms                                                          | 587 ms: 1.07x faster                                                |
| pylint                           | 227 ms                                                          | 213 ms: 1.07x faster                                                |
| ascii85_small                    | 13.6 ms                                                         | 12.8 ms: 1.06x faster                                               |
| decimal_pi                       | 222 ms                                                          | 210 ms: 1.06x faster                                                |
| scimark_fft                      | 226 ms                                                          | 214 ms: 1.06x faster                                                |
| hexiom                           | 4.30 ms                                                         | 4.08 ms: 1.06x faster                                               |
| thrift                           | 2.02 ms                                                         | 1.91 ms: 1.06x faster                                               |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.15 ms: 1.05x faster                                               |
| regex_compile                    | 98.5 ms                                                         | 94.2 ms: 1.05x faster                                               |
| genshi_text                      | 17.8 ms                                                         | 17.1 ms: 1.05x faster                                               |
| pprint_safe_repr                 | 530 ms                                                          | 507 ms: 1.04x faster                                                |
| python_startup_no_site           | 6.46 ms                                                         | 6.19 ms: 1.04x faster                                               |
| sqlglot_v2_parse                 | 958 us                                                          | 922 us: 1.04x faster                                                |
| json                             | 3.51 ms                                                         | 3.38 ms: 1.04x faster                                               |
| pickle_dict                      | 22.0 us                                                         | 21.2 us: 1.04x faster                                               |
| regex_dna                        | 162 ms                                                          | 157 ms: 1.03x faster                                                |
| xml_etree_generate               | 64.2 ms                                                         | 62.3 ms: 1.03x faster                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.26 sec: 1.02x faster                                              |
| regex_v8                         | 15.2 ms                                                         | 14.9 ms: 1.02x faster                                               |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 14.2 ms: 1.02x faster                                               |
| decimal_factorial                | 177 ms                                                          | 173 ms: 1.02x faster                                                |
| pycparser                        | 860 ms                                                          | 841 ms: 1.02x faster                                                |
| fannkuch                         | 246 ms                                                          | 241 ms: 1.02x faster                                                |
| xml_etree_process                | 46.6 ms                                                         | 45.7 ms: 1.02x faster                                               |
| spectral_norm                    | 65.9 ms                                                         | 64.6 ms: 1.02x faster                                               |
| sympy_integrate                  | 15.8 ms                                                         | 15.6 ms: 1.01x faster                                               |
| python_startup                   | 9.51 ms                                                         | 9.39 ms: 1.01x faster                                               |
| logging_simple                   | 4.71 us                                                         | 4.67 us: 1.01x faster                                               |
| genshi_xml                       | 41.3 ms                                                         | 41.0 ms: 1.01x faster                                               |
| raytrace                         | 195 ms                                                          | 194 ms: 1.01x faster                                                |
| pidigits                         | 189 ms                                                          | 188 ms: 1.00x faster                                                |
| urlsafe_base64_small             | 325 us                                                          | 328 us: 1.01x slower                                                |
| logging_format                   | 5.25 us                                                         | 5.29 us: 1.01x slower                                               |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 81.2 ms: 1.01x slower                                               |
| unpickle                         | 10.5 us                                                         | 10.6 us: 1.01x slower                                               |
| base85_large                     | 252 ms                                                          | 254 ms: 1.01x slower                                                |
| sympy_expand                     | 336 ms                                                          | 340 ms: 1.01x slower                                                |
| chameleon                        | 9.95 ms                                                         | 10.1 ms: 1.01x slower                                               |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.19 ms: 1.01x slower                                               |
| logging_silent                   | 61.0 ns                                                         | 61.8 ns: 1.01x slower                                               |
| unpickle_pure_python             | 151 us                                                          | 153 us: 1.01x slower                                                |
| scimark_lu                       | 74.5 ms                                                         | 75.6 ms: 1.01x slower                                               |
| nbody                            | 65.9 ms                                                         | 67.0 ms: 1.02x slower                                               |
| sympy_str                        | 197 ms                                                          | 200 ms: 1.02x slower                                                |
| generators                       | 21.2 ms                                                         | 21.6 ms: 1.02x slower                                               |
| sympy_sum                        | 106 ms                                                          | 109 ms: 1.02x slower                                                |
| base32_large                     | 296 ms                                                          | 303 ms: 1.03x slower                                                |
| deltablue                        | 2.41 ms                                                         | 2.47 ms: 1.03x slower                                               |
| base32_small                     | 5.79 ms                                                         | 5.96 ms: 1.03x slower                                               |
| asyncio_websockets               | 303 ms                                                          | 312 ms: 1.03x slower                                                |
| coverage                         | 55.8 ms                                                         | 57.5 ms: 1.03x slower                                               |
| base85_small                     | 4.59 ms                                                         | 4.74 ms: 1.03x slower                                               |
| networkx_shortest_path           | 437 ms                                                          | 451 ms: 1.03x slower                                                |
| json_loads                       | 16.2 us                                                         | 16.8 us: 1.03x slower                                               |
| meteor_contest                   | 84.4 ms                                                         | 87.3 ms: 1.03x slower                                               |
| tomli_loads                      | 1.62 sec                                                        | 1.68 sec: 1.03x slower                                              |
| docutils                         | 1.89 sec                                                        | 1.96 sec: 1.04x slower                                              |
| base64_large                     | 3.33 ms                                                         | 3.45 ms: 1.04x slower                                               |
| mypy2                            | 724 ms                                                          | 752 ms: 1.04x slower                                                |
| noop                             | 20.5 ns                                                         | 21.3 ns: 1.04x slower                                               |
| gc_traversal                     | 3.07 ms                                                         | 3.20 ms: 1.04x slower                                               |
| unpickle_list                    | 3.33 us                                                         | 3.49 us: 1.05x slower                                               |
| thread_mandelbrot_naive          | 210 ms                                                          | 221 ms: 1.05x slower                                                |
| crypto_pyaes                     | 50.9 ms                                                         | 54.0 ms: 1.06x slower                                               |
| pickle_list                      | 3.14 us                                                         | 3.33 us: 1.06x slower                                               |
| thread_counter_naive             | 20.6 ms                                                         | 22.1 ms: 1.07x slower                                               |
| mako                             | 7.16 ms                                                         | 7.70 ms: 1.08x slower                                               |
| argparse_subparsers              | 452 us                                                          | 486 us: 1.08x slower                                                |
| django_template                  | 27.6 ms                                                         | 29.8 ms: 1.08x slower                                               |
| pickle_pure_python               | 223 us                                                          | 242 us: 1.08x slower                                                |
| thread_mandelbrot_optimized      | 208 ms                                                          | 228 ms: 1.10x slower                                                |
| nqueens                          | 53.6 ms                                                         | 59.2 ms: 1.10x slower                                               |
| create_gc_cycles                 | 1.75 ms                                                         | 1.96 ms: 1.12x slower                                               |
| pickle                           | 7.44 us                                                         | 8.38 us: 1.13x slower                                               |
| thread_memo_optimized            | 15.3 ms                                                         | 17.7 ms: 1.16x slower                                               |
| thread_accumulate_naive          | 33.4 ms                                                         | 39.2 ms: 1.17x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 344 ms: 1.20x slower                                                |
| thread_counter_optimized         | 16.5 ms                                                         | 20.0 ms: 1.21x slower                                               |
| thread_accumulate_optimized      | 32.3 ms                                                         | 39.1 ms: 1.21x slower                                               |
| thread_pipeline_optimized        | 20.9 ms                                                         | 25.5 ms: 1.22x slower                                               |
| networkx_connected_components    | 425 ms                                                          | 542 ms: 1.27x slower                                                |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 228 ms: 1.30x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                         | 179 ms: 3.06x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.08x faster                                                        |

Benchmark hidden because not significant (7): fastapi_http, coroutines, tornado_http, comprehensions, sqlglot_v2_optimize, base64_small, typing_runtime_protocols
Ignored benchmarks (1) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.080x faster

# HPT report

- Reliability score: 99.95% likely to be faster
- 90% likely to have a speedup of 1.02x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.10x