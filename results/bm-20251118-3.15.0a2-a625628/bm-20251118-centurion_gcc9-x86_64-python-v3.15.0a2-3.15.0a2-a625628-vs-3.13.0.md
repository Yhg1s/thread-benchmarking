# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.073x faster
- HPT reliability: 99.98%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.10x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 9.74 ms: 1.02x faster                                               |
| docutils       | 1.89 sec                                                        | 1.96 sec: 1.04x slower                                              |
| fastapi_http   | 218 ms                                                          | 220 ms: 1.01x slower                                                |
| html5lib       | 51.7 ms                                                         | 45.1 ms: 1.15x faster                                               |
| tornado_http   | 101 ms                                                          | 98.7 ms: 1.02x faster                                               |
| Geometric mean | (ref)                                                           | 1.03x faster                                                        |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_io_tg                 | 778 ms                                                          | 479 ms: 1.62x faster                                                |
| async_tree_memoization_tg        | 419 ms                                                          | 262 ms: 1.60x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 472 ms: 1.59x faster                                                |
| async_tree_io                    | 741 ms                                                          | 472 ms: 1.57x faster                                                |
| async_tree_eager_io_tg           | 728 ms                                                          | 464 ms: 1.57x faster                                                |
| async_tree_none                  | 308 ms                                                          | 200 ms: 1.54x faster                                                |
| async_tree_memoization           | 388 ms                                                          | 259 ms: 1.50x faster                                                |
| async_tree_none_tg               | 291 ms                                                          | 199 ms: 1.46x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 369 ms: 1.33x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 166 ms: 1.32x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 372 ms: 1.28x faster                                                |
| async_tree_eager                 | 89.6 ms                                                         | 79.0 ms: 1.13x faster                                               |
| async_generators                 | 240 ms                                                          | 223 ms: 1.08x faster                                                |
| asyncio_tcp                      | 318 ms                                                          | 298 ms: 1.07x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 304 ms: 1.06x faster                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.28 sec: 1.00x faster                                              |
| asyncio_websockets               | 303 ms                                                          | 309 ms: 1.02x slower                                                |
| coroutines                       | 15.4 ms                                                         | 15.8 ms: 1.03x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 349 ms: 1.22x slower                                                |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 225 ms: 1.28x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                         | 179 ms: 3.06x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.16x faster                                                        |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 21.7 ns: 1.06x slower                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                          | 207 ms: 1.07x faster                                                |
| decimal_factorial | 177 ms                                                          | 174 ms: 1.02x faster                                                |
| Geometric mean    | (ref)                                                           | 1.04x faster                                                        |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 49.5 ms: 1.15x faster                                               |
| quadtree_nbody | 626 ms                                                          | 600 ms: 1.04x faster                                                |
| pidigits       | 189 ms                                                          | 188 ms: 1.00x faster                                                |
| nbody          | 65.9 ms                                                         | 75.3 ms: 1.14x slower                                               |
| Geometric mean | (ref)                                                           | 1.01x faster                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 1.99 ms: 1.15x faster                                               |
| regex_dna      | 162 ms                                                          | 153 ms: 1.06x faster                                                |
| regex_compile  | 98.5 ms                                                         | 95.0 ms: 1.04x faster                                               |
| regex_v8       | 15.2 ms                                                         | 15.4 ms: 1.01x slower                                               |
| Geometric mean | (ref)                                                           | 1.06x faster                                                        |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 4.80 ms: 7.71x faster                                               |
| base16_small         | 740 us                                                          | 299 us: 2.48x faster                                                |
| xml_etree_iterparse  | 79.9 ms                                                         | 70.0 ms: 1.14x faster                                               |
| xml_etree_parse      | 104 ms                                                          | 93.9 ms: 1.11x faster                                               |
| ascii85_large        | 717 ms                                                          | 669 ms: 1.07x faster                                                |
| tomli_loads          | 1.62 sec                                                        | 1.53 sec: 1.06x faster                                              |
| ascii85_small        | 13.6 ms                                                         | 12.9 ms: 1.05x faster                                               |
| xml_etree_process    | 46.6 ms                                                         | 45.1 ms: 1.03x faster                                               |
| xml_etree_generate   | 64.2 ms                                                         | 62.2 ms: 1.03x faster                                               |
| pickle_dict          | 22.0 us                                                         | 21.3 us: 1.03x faster                                               |
| json_dumps           | 6.95 ms                                                         | 6.82 ms: 1.02x faster                                               |
| urlsafe_base64_small | 325 us                                                          | 322 us: 1.01x faster                                                |
| pickle_list          | 3.14 us                                                         | 3.17 us: 1.01x slower                                               |
| base85_large         | 252 ms                                                          | 254 ms: 1.01x slower                                                |
| unpickle_list        | 3.33 us                                                         | 3.42 us: 1.03x slower                                               |
| base32_large         | 296 ms                                                          | 305 ms: 1.03x slower                                                |
| base85_small         | 4.59 ms                                                         | 4.77 ms: 1.04x slower                                               |
| base32_small         | 5.79 ms                                                         | 6.06 ms: 1.05x slower                                               |
| base64_large         | 3.33 ms                                                         | 3.49 ms: 1.05x slower                                               |
| unpickle_pure_python | 151 us                                                          | 159 us: 1.06x slower                                                |
| pickle_pure_python   | 223 us                                                          | 242 us: 1.08x slower                                                |
| pickle               | 7.44 us                                                         | 8.24 us: 1.11x slower                                               |
| Geometric mean       | (ref)                                                           | 1.13x faster                                                        |

Benchmark hidden because not significant (3): base64_small, unpickle, json_loads

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 6.26 ms: 1.03x faster                                               |
| python_startup         | 9.51 ms                                                         | 9.41 ms: 1.01x faster                                               |
| Geometric mean         | (ref)                                                           | 1.02x faster                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| genshi_text     | 17.8 ms                                                         | 16.8 ms: 1.06x faster                                               |
| genshi_xml      | 41.3 ms                                                         | 40.3 ms: 1.03x faster                                               |
| mako            | 7.16 ms                                                         | 7.47 ms: 1.04x slower                                               |
| django_template | 27.6 ms                                                         | 29.1 ms: 1.06x slower                                               |
| Geometric mean  | (ref)                                                           | 1.00x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_memo_naive           | 36.1 ms                                                         | 9.82 ms: 3.68x faster                                               |
| thread_pipeline_naive       | 47.3 ms                                                         | 35.1 ms: 1.35x faster                                               |
| thread_montecarlo_naive     | 19.0 ms                                                         | 15.6 ms: 1.22x faster                                               |
| thread_montecarlo_optimized | 14.5 ms                                                         | 13.6 ms: 1.07x faster                                               |
| thread_counter_naive        | 20.6 ms                                                         | 21.5 ms: 1.04x slower                                               |
| thread_mandelbrot_naive     | 210 ms                                                          | 225 ms: 1.07x slower                                                |
| thread_mandelbrot_optimized | 208 ms                                                          | 232 ms: 1.12x slower                                                |
| thread_memo_optimized       | 15.3 ms                                                         | 17.4 ms: 1.14x slower                                               |
| thread_accumulate_naive     | 33.4 ms                                                         | 38.7 ms: 1.16x slower                                               |
| thread_counter_optimized    | 16.5 ms                                                         | 19.7 ms: 1.19x slower                                               |
| thread_accumulate_optimized | 32.3 ms                                                         | 38.7 ms: 1.20x slower                                               |
| thread_pipeline_optimized   | 20.9 ms                                                         | 26.3 ms: 1.26x slower                                               |
| Geometric mean              | (ref)                                                           | 1.07x faster                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 4.80 ms: 7.71x faster                                               |
| thread_memo_naive                | 36.1 ms                                                         | 9.82 ms: 3.68x faster                                               |
| base16_small                     | 740 us                                                          | 299 us: 2.48x faster                                                |
| mdp                              | 2.15 sec                                                        | 949 ms: 2.26x faster                                                |
| async_tree_io_tg                 | 778 ms                                                          | 479 ms: 1.62x faster                                                |
| async_tree_memoization_tg        | 419 ms                                                          | 262 ms: 1.60x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 472 ms: 1.59x faster                                                |
| async_tree_io                    | 741 ms                                                          | 472 ms: 1.57x faster                                                |
| async_tree_eager_io_tg           | 728 ms                                                          | 464 ms: 1.57x faster                                                |
| deepcopy_memo                    | 26.5 us                                                         | 17.0 us: 1.56x faster                                               |
| async_tree_none                  | 308 ms                                                          | 200 ms: 1.54x faster                                                |
| async_tree_memoization           | 388 ms                                                          | 259 ms: 1.50x faster                                                |
| async_tree_none_tg               | 291 ms                                                          | 199 ms: 1.46x faster                                                |
| deepcopy                         | 269 us                                                          | 185 us: 1.45x faster                                                |
| go                               | 117 ms                                                          | 85.7 ms: 1.36x faster                                               |
| thread_pipeline_naive            | 47.3 ms                                                         | 35.1 ms: 1.35x faster                                               |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 369 ms: 1.33x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 166 ms: 1.32x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 372 ms: 1.28x faster                                                |
| deepcopy_reduce                  | 2.40 us                                                         | 1.96 us: 1.23x faster                                               |
| thread_montecarlo_naive          | 19.0 ms                                                         | 15.6 ms: 1.22x faster                                               |
| richards                         | 37.8 ms                                                         | 32.3 ms: 1.17x faster                                               |
| regex_effbot                     | 2.30 ms                                                         | 1.99 ms: 1.15x faster                                               |
| float                            | 57.0 ms                                                         | 49.5 ms: 1.15x faster                                               |
| html5lib                         | 51.7 ms                                                         | 45.1 ms: 1.15x faster                                               |
| richards_super                   | 42.8 ms                                                         | 37.5 ms: 1.14x faster                                               |
| xml_etree_iterparse              | 79.9 ms                                                         | 70.0 ms: 1.14x faster                                               |
| async_tree_eager                 | 89.6 ms                                                         | 79.0 ms: 1.13x faster                                               |
| pathlib                          | 12.8 ms                                                         | 11.3 ms: 1.13x faster                                               |
| telco                            | 5.83 ms                                                         | 5.18 ms: 1.13x faster                                               |
| scimark_monte_carlo              | 46.5 ms                                                         | 41.7 ms: 1.12x faster                                               |
| pprint_pformat                   | 1.09 sec                                                        | 978 ms: 1.11x faster                                                |
| xml_etree_parse                  | 104 ms                                                          | 93.9 ms: 1.11x faster                                               |
| pyflate                          | 342 ms                                                          | 309 ms: 1.11x faster                                                |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.02 sec: 1.09x faster                                              |
| async_generators                 | 240 ms                                                          | 223 ms: 1.08x faster                                                |
| pprint_safe_repr                 | 530 ms                                                          | 494 ms: 1.07x faster                                                |
| scimark_sor                      | 78.9 ms                                                         | 73.6 ms: 1.07x faster                                               |
| ascii85_large                    | 717 ms                                                          | 669 ms: 1.07x faster                                                |
| decimal_pi                       | 222 ms                                                          | 207 ms: 1.07x faster                                                |
| asyncio_tcp                      | 318 ms                                                          | 298 ms: 1.07x faster                                                |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 13.6 ms: 1.07x faster                                               |
| xdsl_constant_fold               | 36.7 ms                                                         | 34.5 ms: 1.06x faster                                               |
| unpack_sequence                  | 27.1 ns                                                         | 25.5 ns: 1.06x faster                                               |
| pylint                           | 227 ms                                                          | 213 ms: 1.06x faster                                                |
| genshi_text                      | 17.8 ms                                                         | 16.8 ms: 1.06x faster                                               |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 304 ms: 1.06x faster                                                |
| regex_dna                        | 162 ms                                                          | 153 ms: 1.06x faster                                                |
| tomli_loads                      | 1.62 sec                                                        | 1.53 sec: 1.06x faster                                              |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.14 ms: 1.06x faster                                               |
| sqlglot_v2_parse                 | 958 us                                                          | 909 us: 1.05x faster                                                |
| scimark_fft                      | 226 ms                                                          | 215 ms: 1.05x faster                                                |
| ascii85_small                    | 13.6 ms                                                         | 12.9 ms: 1.05x faster                                               |
| thrift                           | 2.02 ms                                                         | 1.93 ms: 1.05x faster                                               |
| hexiom                           | 4.30 ms                                                         | 4.12 ms: 1.04x faster                                               |
| chaos                            | 45.1 ms                                                         | 43.2 ms: 1.04x faster                                               |
| quadtree_nbody                   | 626 ms                                                          | 600 ms: 1.04x faster                                                |
| json                             | 3.51 ms                                                         | 3.36 ms: 1.04x faster                                               |
| fannkuch                         | 246 ms                                                          | 237 ms: 1.04x faster                                                |
| regex_compile                    | 98.5 ms                                                         | 95.0 ms: 1.04x faster                                               |
| xml_etree_process                | 46.6 ms                                                         | 45.1 ms: 1.03x faster                                               |
| xml_etree_generate               | 64.2 ms                                                         | 62.2 ms: 1.03x faster                                               |
| python_startup_no_site           | 6.46 ms                                                         | 6.26 ms: 1.03x faster                                               |
| pickle_dict                      | 22.0 us                                                         | 21.3 us: 1.03x faster                                               |
| genshi_xml                       | 41.3 ms                                                         | 40.3 ms: 1.03x faster                                               |
| comprehensions                   | 10.9 us                                                         | 10.7 us: 1.02x faster                                               |
| tornado_http                     | 101 ms                                                          | 98.7 ms: 1.02x faster                                               |
| chameleon                        | 9.95 ms                                                         | 9.74 ms: 1.02x faster                                               |
| sympy_integrate                  | 15.8 ms                                                         | 15.5 ms: 1.02x faster                                               |
| decimal_factorial                | 177 ms                                                          | 174 ms: 1.02x faster                                                |
| json_dumps                       | 6.95 ms                                                         | 6.82 ms: 1.02x faster                                               |
| logging_simple                   | 4.71 us                                                         | 4.63 us: 1.02x faster                                               |
| typing_runtime_protocols         | 113 us                                                          | 112 us: 1.01x faster                                                |
| pycparser                        | 860 ms                                                          | 850 ms: 1.01x faster                                                |
| python_startup                   | 9.51 ms                                                         | 9.41 ms: 1.01x faster                                               |
| urlsafe_base64_small             | 325 us                                                          | 322 us: 1.01x faster                                                |
| pidigits                         | 189 ms                                                          | 188 ms: 1.00x faster                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.28 sec: 1.00x faster                                              |
| sympy_expand                     | 336 ms                                                          | 336 ms: 1.00x faster                                                |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 80.8 ms: 1.00x slower                                               |
| sympy_sum                        | 106 ms                                                          | 107 ms: 1.01x slower                                                |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.17 ms: 1.01x slower                                               |
| pickle_list                      | 3.14 us                                                         | 3.17 us: 1.01x slower                                               |
| base85_large                     | 252 ms                                                          | 254 ms: 1.01x slower                                                |
| fastapi_http                     | 218 ms                                                          | 220 ms: 1.01x slower                                                |
| regex_v8                         | 15.2 ms                                                         | 15.4 ms: 1.01x slower                                               |
| spectral_norm                    | 65.9 ms                                                         | 66.6 ms: 1.01x slower                                               |
| deltablue                        | 2.41 ms                                                         | 2.45 ms: 1.02x slower                                               |
| raytrace                         | 195 ms                                                          | 199 ms: 1.02x slower                                                |
| asyncio_websockets               | 303 ms                                                          | 309 ms: 1.02x slower                                                |
| mypy2                            | 724 ms                                                          | 742 ms: 1.02x slower                                                |
| logging_silent                   | 61.0 ns                                                         | 62.6 ns: 1.03x slower                                               |
| unpickle_list                    | 3.33 us                                                         | 3.42 us: 1.03x slower                                               |
| coroutines                       | 15.4 ms                                                         | 15.8 ms: 1.03x slower                                               |
| base32_large                     | 296 ms                                                          | 305 ms: 1.03x slower                                                |
| meteor_contest                   | 84.4 ms                                                         | 87.6 ms: 1.04x slower                                               |
| docutils                         | 1.89 sec                                                        | 1.96 sec: 1.04x slower                                              |
| base85_small                     | 4.59 ms                                                         | 4.77 ms: 1.04x slower                                               |
| thread_counter_naive             | 20.6 ms                                                         | 21.5 ms: 1.04x slower                                               |
| mako                             | 7.16 ms                                                         | 7.47 ms: 1.04x slower                                               |
| base32_small                     | 5.79 ms                                                         | 6.06 ms: 1.05x slower                                               |
| base64_large                     | 3.33 ms                                                         | 3.49 ms: 1.05x slower                                               |
| gc_traversal                     | 3.07 ms                                                         | 3.22 ms: 1.05x slower                                               |
| unpickle_pure_python             | 151 us                                                          | 159 us: 1.06x slower                                                |
| django_template                  | 27.6 ms                                                         | 29.1 ms: 1.06x slower                                               |
| noop                             | 20.5 ns                                                         | 21.7 ns: 1.06x slower                                               |
| crypto_pyaes                     | 50.9 ms                                                         | 54.2 ms: 1.06x slower                                               |
| nqueens                          | 53.6 ms                                                         | 57.3 ms: 1.07x slower                                               |
| thread_mandelbrot_naive          | 210 ms                                                          | 225 ms: 1.07x slower                                                |
| pickle_pure_python               | 223 us                                                          | 242 us: 1.08x slower                                                |
| pickle                           | 7.44 us                                                         | 8.24 us: 1.11x slower                                               |
| thread_mandelbrot_optimized      | 208 ms                                                          | 232 ms: 1.12x slower                                                |
| create_gc_cycles                 | 1.75 ms                                                         | 1.97 ms: 1.12x slower                                               |
| coverage                         | 55.8 ms                                                         | 63.1 ms: 1.13x slower                                               |
| thread_memo_optimized            | 15.3 ms                                                         | 17.4 ms: 1.14x slower                                               |
| nbody                            | 65.9 ms                                                         | 75.3 ms: 1.14x slower                                               |
| thread_accumulate_naive          | 33.4 ms                                                         | 38.7 ms: 1.16x slower                                               |
| thread_counter_optimized         | 16.5 ms                                                         | 19.7 ms: 1.19x slower                                               |
| thread_accumulate_optimized      | 32.3 ms                                                         | 38.7 ms: 1.20x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 349 ms: 1.22x slower                                                |
| thread_pipeline_optimized        | 20.9 ms                                                         | 26.3 ms: 1.26x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 225 ms: 1.28x slower                                                |
| argparse_subparsers              | 452 us                                                          | 672 us: 1.49x slower                                                |
| argparse_many_optionals          | 12.8 ms                                                         | 34.0 ms: 2.65x slower                                               |
| async_tree_eager_tg              | 58.6 ms                                                         | 179 ms: 3.06x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.07x faster                                                        |

Benchmark hidden because not significant (8): generators, base64_small, unpickle, sqlglot_v2_optimize, json_loads, logging_format, scimark_lu, sympy_str
Ignored benchmarks (4) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: networkx_connected_components, networkx_k_core, networkx_shortest_path, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.073x faster

# HPT report

- Reliability score: 99.98% likely to be faster
- 90% likely to have a speedup of 1.02x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.10x