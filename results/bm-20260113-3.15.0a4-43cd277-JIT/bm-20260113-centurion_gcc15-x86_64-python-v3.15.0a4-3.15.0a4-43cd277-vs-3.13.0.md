# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.143x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.05x faster
- Memory change: 1.10x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 10.6 ms: 1.03x faster                                                |
| docutils       | 1.98 sec                                                         | 2.10 sec: 1.06x slower                                               |
| fastapi_http   | 215 ms                                                           | 200 ms: 1.07x faster                                                 |
| html5lib       | 49.1 ms                                                          | 43.2 ms: 1.14x faster                                                |
| Geometric mean | (ref)                                                            | 1.03x faster                                                         |

Benchmark hidden because not significant (1): tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| async_tree_memoization_tg        | 417 ms                                                           | 253 ms: 1.65x faster                                                 |
| async_tree_io_tg                 | 777 ms                                                           | 471 ms: 1.65x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 468 ms: 1.60x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 476 ms: 1.56x faster                                                 |
| async_tree_eager_io_tg           | 724 ms                                                           | 469 ms: 1.54x faster                                                 |
| async_tree_memoization           | 389 ms                                                           | 254 ms: 1.53x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 206 ms: 1.51x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 207 ms: 1.40x faster                                                 |
| async_tree_eager_memoization     | 215 ms                                                           | 170 ms: 1.26x faster                                                 |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 427 ms: 1.21x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 439 ms: 1.20x faster                                                 |
| asyncio_tcp                      | 326 ms                                                           | 273 ms: 1.19x faster                                                 |
| coroutines                       | 17.6 ms                                                          | 15.2 ms: 1.16x faster                                                |
| async_tree_eager                 | 90.0 ms                                                          | 78.3 ms: 1.15x faster                                                |
| async_generators                 | 262 ms                                                           | 258 ms: 1.02x faster                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.27 sec: 1.02x faster                                               |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 363 ms: 1.01x slower                                                 |
| asyncio_websockets               | 304 ms                                                           | 310 ms: 1.02x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 407 ms: 1.27x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 229 ms: 1.33x slower                                                 |
| async_tree_eager_tg              | 58.6 ms                                                          | 170 ms: 2.91x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.15x faster                                                         |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 16.7 ns: 1.22x faster                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 191 ms: 1.10x faster                                                 |
| decimal_factorial | 173 ms                                                           | 171 ms: 1.01x faster                                                 |
| Geometric mean    | (ref)                                                            | 1.05x faster                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 38.7 ms: 1.46x faster                                                |
| nbody          | 66.8 ms                                                          | 49.0 ms: 1.36x faster                                                |
| quadtree_nbody | 620 ms                                                           | 517 ms: 1.20x faster                                                 |
| pidigits       | 181 ms                                                           | 181 ms: 1.00x faster                                                 |
| Geometric mean | (ref)                                                            | 1.24x faster                                                         |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_compile  | 97.7 ms                                                          | 81.2 ms: 1.20x faster                                                |
| regex_effbot   | 1.99 ms                                                          | 1.80 ms: 1.11x faster                                                |
| regex_dna      | 144 ms                                                           | 139 ms: 1.03x faster                                                 |
| regex_v8       | 14.7 ms                                                          | 15.3 ms: 1.04x slower                                                |
| Geometric mean | (ref)                                                            | 1.07x faster                                                         |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.09 ms: 6.21x faster                                                |
| base16_small         | 656 us                                                           | 269 us: 2.44x faster                                                 |
| ascii85_large        | 814 ms                                                           | 536 ms: 1.52x faster                                                 |
| ascii85_small        | 15.5 ms                                                          | 10.6 ms: 1.47x faster                                                |
| unpickle_pure_python | 149 us                                                           | 116 us: 1.28x faster                                                 |
| urlsafe_base64_small | 379 us                                                           | 306 us: 1.24x faster                                                 |
| json_dumps           | 7.49 ms                                                          | 6.17 ms: 1.21x faster                                                |
| base64_small         | 228 us                                                           | 190 us: 1.20x faster                                                 |
| tomli_loads          | 1.63 sec                                                         | 1.43 sec: 1.14x faster                                               |
| base85_large         | 243 ms                                                           | 225 ms: 1.08x faster                                                 |
| xml_etree_parse      | 107 ms                                                           | 99.4 ms: 1.08x faster                                                |
| base64_large         | 6.32 ms                                                          | 5.86 ms: 1.08x faster                                                |
| pickle_pure_python   | 223 us                                                           | 208 us: 1.07x faster                                                 |
| base85_small         | 4.41 ms                                                          | 4.12 ms: 1.07x faster                                                |
| xml_etree_process    | 48.1 ms                                                          | 45.1 ms: 1.07x faster                                                |
| xml_etree_generate   | 66.3 ms                                                          | 63.2 ms: 1.05x faster                                                |
| base32_small         | 5.69 ms                                                          | 5.53 ms: 1.03x faster                                                |
| xml_etree_iterparse  | 69.6 ms                                                          | 68.0 ms: 1.02x faster                                                |
| pickle_dict          | 21.9 us                                                          | 21.4 us: 1.02x faster                                                |
| base32_large         | 286 ms                                                           | 281 ms: 1.01x faster                                                 |
| unpickle             | 10.3 us                                                          | 10.5 us: 1.02x slower                                                |
| unpickle_list        | 3.45 us                                                          | 3.55 us: 1.03x slower                                                |
| json_loads           | 16.7 us                                                          | 17.6 us: 1.05x slower                                                |
| pickle_list          | 3.03 us                                                          | 3.26 us: 1.08x slower                                                |
| pickle               | 8.22 us                                                          | 9.19 us: 1.12x slower                                                |
| Geometric mean       | (ref)                                                            | 1.21x faster                                                         |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 6.15 ms: 1.03x faster                                                |
| python_startup         | 9.38 ms                                                          | 9.36 ms: 1.00x faster                                                |
| Geometric mean         | (ref)                                                            | 1.02x faster                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| mako            | 7.43 ms                                                          | 6.56 ms: 1.13x faster                                                |
| genshi_text     | 17.6 ms                                                          | 16.9 ms: 1.04x faster                                                |
| django_template | 27.3 ms                                                          | 28.8 ms: 1.06x slower                                                |
| genshi_xml      | 39.7 ms                                                          | 44.8 ms: 1.13x slower                                                |
| Geometric mean  | (ref)                                                            | 1.00x slower                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 8.90 ms: 4.38x faster                                                |
| thread_pipeline_naive       | 52.1 ms                                                          | 33.1 ms: 1.58x faster                                                |
| thread_mandelbrot_naive     | 220 ms                                                           | 190 ms: 1.16x faster                                                 |
| thread_mandelbrot_optimized | 218 ms                                                           | 193 ms: 1.13x faster                                                 |
| thread_counter_naive        | 22.6 ms                                                          | 20.6 ms: 1.10x faster                                                |
| thread_montecarlo_naive     | 17.8 ms                                                          | 16.4 ms: 1.09x faster                                                |
| thread_memo_optimized       | 18.2 ms                                                          | 17.5 ms: 1.04x faster                                                |
| thread_montecarlo_optimized | 13.3 ms                                                          | 13.3 ms: 1.00x faster                                                |
| thread_accumulate_naive     | 40.9 ms                                                          | 41.1 ms: 1.01x slower                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 18.9 ms: 1.01x slower                                                |
| thread_pipeline_optimized   | 25.6 ms                                                          | 26.2 ms: 1.02x slower                                                |
| thread_accumulate_optimized | 39.8 ms                                                          | 40.8 ms: 1.03x slower                                                |
| Geometric mean              | (ref)                                                            | 1.22x faster                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.09 ms: 6.21x faster                                                |
| thread_memo_naive                | 39.0 ms                                                          | 8.90 ms: 4.38x faster                                                |
| base16_small                     | 656 us                                                           | 269 us: 2.44x faster                                                 |
| richards                         | 36.8 ms                                                          | 16.0 ms: 2.31x faster                                                |
| richards_super                   | 41.3 ms                                                          | 19.5 ms: 2.12x faster                                                |
| mdp                              | 2.11 sec                                                         | 1.10 sec: 1.91x faster                                               |
| deepcopy_memo                    | 26.6 us                                                          | 15.5 us: 1.71x faster                                                |
| argparse_many_optionals          | 12.6 ms                                                          | 7.37 ms: 1.70x faster                                                |
| go                               | 121 ms                                                           | 71.7 ms: 1.69x faster                                                |
| async_tree_memoization_tg        | 417 ms                                                           | 253 ms: 1.65x faster                                                 |
| async_tree_io_tg                 | 777 ms                                                           | 471 ms: 1.65x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 468 ms: 1.60x faster                                                 |
| thread_pipeline_naive            | 52.1 ms                                                          | 33.1 ms: 1.58x faster                                                |
| async_tree_io                    | 741 ms                                                           | 476 ms: 1.56x faster                                                 |
| async_tree_eager_io_tg           | 724 ms                                                           | 469 ms: 1.54x faster                                                 |
| async_tree_memoization           | 389 ms                                                           | 254 ms: 1.53x faster                                                 |
| ascii85_large                    | 814 ms                                                           | 536 ms: 1.52x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 206 ms: 1.51x faster                                                 |
| ascii85_small                    | 15.5 ms                                                          | 10.6 ms: 1.47x faster                                                |
| float                            | 56.6 ms                                                          | 38.7 ms: 1.46x faster                                                |
| scimark_sor                      | 97.0 ms                                                          | 66.8 ms: 1.45x faster                                                |
| scimark_monte_carlo              | 44.3 ms                                                          | 31.2 ms: 1.42x faster                                                |
| pyflate                          | 358 ms                                                           | 254 ms: 1.41x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 207 ms: 1.40x faster                                                 |
| scimark_fft                      | 211 ms                                                           | 153 ms: 1.37x faster                                                 |
| nbody                            | 66.8 ms                                                          | 49.0 ms: 1.36x faster                                                |
| fannkuch                         | 265 ms                                                           | 199 ms: 1.34x faster                                                 |
| deltablue                        | 2.52 ms                                                          | 1.92 ms: 1.31x faster                                                |
| deepcopy                         | 267 us                                                           | 208 us: 1.29x faster                                                 |
| unpickle_pure_python             | 149 us                                                           | 116 us: 1.28x faster                                                 |
| logging_silent                   | 60.6 ns                                                          | 47.9 ns: 1.26x faster                                                |
| async_tree_eager_memoization     | 215 ms                                                           | 170 ms: 1.26x faster                                                 |
| urlsafe_base64_small             | 379 us                                                           | 306 us: 1.24x faster                                                 |
| spectral_norm                    | 64.1 ms                                                          | 52.4 ms: 1.22x faster                                                |
| telco                            | 5.50 ms                                                          | 4.51 ms: 1.22x faster                                                |
| noop                             | 20.4 ns                                                          | 16.7 ns: 1.22x faster                                                |
| scimark_lu                       | 70.2 ms                                                          | 57.7 ms: 1.22x faster                                                |
| json_dumps                       | 7.49 ms                                                          | 6.17 ms: 1.21x faster                                                |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 427 ms: 1.21x faster                                                 |
| base64_small                     | 228 us                                                           | 190 us: 1.20x faster                                                 |
| regex_compile                    | 97.7 ms                                                          | 81.2 ms: 1.20x faster                                                |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 439 ms: 1.20x faster                                                 |
| quadtree_nbody                   | 620 ms                                                           | 517 ms: 1.20x faster                                                 |
| asyncio_tcp                      | 326 ms                                                           | 273 ms: 1.19x faster                                                 |
| bpe_tokeniser                    | 3.40 sec                                                         | 2.88 sec: 1.18x faster                                               |
| pathlib                          | 12.4 ms                                                          | 10.6 ms: 1.17x faster                                                |
| thread_mandelbrot_naive          | 220 ms                                                           | 190 ms: 1.16x faster                                                 |
| coroutines                       | 17.6 ms                                                          | 15.2 ms: 1.16x faster                                                |
| async_tree_eager                 | 90.0 ms                                                          | 78.3 ms: 1.15x faster                                                |
| thrift                           | 2.07 ms                                                          | 1.81 ms: 1.14x faster                                                |
| tomli_loads                      | 1.63 sec                                                         | 1.43 sec: 1.14x faster                                               |
| html5lib                         | 49.1 ms                                                          | 43.2 ms: 1.14x faster                                                |
| mako                             | 7.43 ms                                                          | 6.56 ms: 1.13x faster                                                |
| thread_mandelbrot_optimized      | 218 ms                                                           | 193 ms: 1.13x faster                                                 |
| networkx_k_core                  | 2.15 sec                                                         | 1.91 sec: 1.13x faster                                               |
| deepcopy_reduce                  | 2.37 us                                                          | 2.11 us: 1.12x faster                                                |
| chaos                            | 45.0 ms                                                          | 40.3 ms: 1.12x faster                                                |
| regex_effbot                     | 1.99 ms                                                          | 1.80 ms: 1.11x faster                                                |
| meteor_contest                   | 89.9 ms                                                          | 81.4 ms: 1.10x faster                                                |
| thread_counter_naive             | 22.6 ms                                                          | 20.6 ms: 1.10x faster                                                |
| decimal_pi                       | 210 ms                                                           | 191 ms: 1.10x faster                                                 |
| thread_montecarlo_naive          | 17.8 ms                                                          | 16.4 ms: 1.09x faster                                                |
| sqlglot_v2_parse                 | 953 us                                                           | 881 us: 1.08x faster                                                 |
| base85_large                     | 243 ms                                                           | 225 ms: 1.08x faster                                                 |
| xml_etree_parse                  | 107 ms                                                           | 99.4 ms: 1.08x faster                                                |
| base64_large                     | 6.32 ms                                                          | 5.86 ms: 1.08x faster                                                |
| fastapi_http                     | 215 ms                                                           | 200 ms: 1.07x faster                                                 |
| pickle_pure_python               | 223 us                                                           | 208 us: 1.07x faster                                                 |
| base85_small                     | 4.41 ms                                                          | 4.12 ms: 1.07x faster                                                |
| json                             | 3.49 ms                                                          | 3.27 ms: 1.07x faster                                                |
| crypto_pyaes                     | 50.0 ms                                                          | 46.8 ms: 1.07x faster                                                |
| xml_etree_process                | 48.1 ms                                                          | 45.1 ms: 1.07x faster                                                |
| pycparser                        | 884 ms                                                           | 828 ms: 1.07x faster                                                 |
| networkx_connected_components    | 460 ms                                                           | 432 ms: 1.06x faster                                                 |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.51 ms: 1.06x faster                                                |
| pprint_safe_repr                 | 541 ms                                                           | 513 ms: 1.06x faster                                                 |
| networkx_shortest_path           | 464 ms                                                           | 441 ms: 1.05x faster                                                 |
| xml_etree_generate               | 66.3 ms                                                          | 63.2 ms: 1.05x faster                                                |
| generators                       | 22.0 ms                                                          | 21.0 ms: 1.05x faster                                                |
| thread_memo_optimized            | 18.2 ms                                                          | 17.5 ms: 1.04x faster                                                |
| raytrace                         | 199 ms                                                           | 191 ms: 1.04x faster                                                 |
| genshi_text                      | 17.6 ms                                                          | 16.9 ms: 1.04x faster                                                |
| pprint_pformat                   | 1.11 sec                                                         | 1.07 sec: 1.03x faster                                               |
| python_startup_no_site           | 6.36 ms                                                          | 6.15 ms: 1.03x faster                                                |
| regex_dna                        | 144 ms                                                           | 139 ms: 1.03x faster                                                 |
| base32_small                     | 5.69 ms                                                          | 5.53 ms: 1.03x faster                                                |
| chameleon                        | 10.9 ms                                                          | 10.6 ms: 1.03x faster                                                |
| xml_etree_iterparse              | 69.6 ms                                                          | 68.0 ms: 1.02x faster                                                |
| logging_simple                   | 4.60 us                                                          | 4.50 us: 1.02x faster                                                |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.17 ms: 1.02x faster                                                |
| pickle_dict                      | 21.9 us                                                          | 21.4 us: 1.02x faster                                                |
| comprehensions                   | 11.6 us                                                          | 11.4 us: 1.02x faster                                                |
| hexiom                           | 4.42 ms                                                          | 4.34 ms: 1.02x faster                                                |
| async_generators                 | 262 ms                                                           | 258 ms: 1.02x faster                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.27 sec: 1.02x faster                                               |
| base32_large                     | 286 ms                                                           | 281 ms: 1.01x faster                                                 |
| logging_format                   | 5.23 us                                                          | 5.17 us: 1.01x faster                                                |
| decimal_factorial                | 173 ms                                                           | 171 ms: 1.01x faster                                                 |
| pidigits                         | 181 ms                                                           | 181 ms: 1.00x faster                                                 |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 13.3 ms: 1.00x faster                                                |
| python_startup                   | 9.38 ms                                                          | 9.36 ms: 1.00x faster                                                |
| thread_accumulate_naive          | 40.9 ms                                                          | 41.1 ms: 1.01x slower                                                |
| coverage                         | 52.2 ms                                                          | 52.7 ms: 1.01x slower                                                |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 363 ms: 1.01x slower                                                 |
| thread_counter_optimized         | 18.7 ms                                                          | 18.9 ms: 1.01x slower                                                |
| typing_runtime_protocols         | 106 us                                                           | 108 us: 1.02x slower                                                 |
| unpickle                         | 10.3 us                                                          | 10.5 us: 1.02x slower                                                |
| asyncio_websockets               | 304 ms                                                           | 310 ms: 1.02x slower                                                 |
| nqueens                          | 57.3 ms                                                          | 58.6 ms: 1.02x slower                                                |
| thread_pipeline_optimized        | 25.6 ms                                                          | 26.2 ms: 1.02x slower                                                |
| thread_accumulate_optimized      | 39.8 ms                                                          | 40.8 ms: 1.03x slower                                                |
| unpickle_list                    | 3.45 us                                                          | 3.55 us: 1.03x slower                                                |
| regex_v8                         | 14.7 ms                                                          | 15.3 ms: 1.04x slower                                                |
| gc_traversal                     | 3.16 ms                                                          | 3.30 ms: 1.04x slower                                                |
| sympy_integrate                  | 15.4 ms                                                          | 16.2 ms: 1.05x slower                                                |
| json_loads                       | 16.7 us                                                          | 17.6 us: 1.05x slower                                                |
| django_template                  | 27.3 ms                                                          | 28.8 ms: 1.06x slower                                                |
| sympy_expand                     | 330 ms                                                           | 350 ms: 1.06x slower                                                 |
| docutils                         | 1.98 sec                                                         | 2.10 sec: 1.06x slower                                               |
| argparse_subparsers              | 446 us                                                           | 477 us: 1.07x slower                                                 |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.8 ms: 1.07x slower                                                |
| pickle_list                      | 3.03 us                                                          | 3.26 us: 1.08x slower                                                |
| pickle                           | 8.22 us                                                          | 9.19 us: 1.12x slower                                                |
| sympy_sum                        | 104 ms                                                           | 117 ms: 1.13x slower                                                 |
| genshi_xml                       | 39.7 ms                                                          | 44.8 ms: 1.13x slower                                                |
| create_gc_cycles                 | 1.70 ms                                                          | 1.94 ms: 1.14x slower                                                |
| sympy_str                        | 193 ms                                                           | 222 ms: 1.15x slower                                                 |
| pylint                           | 226 ms                                                           | 261 ms: 1.15x slower                                                 |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 47.4 ms: 1.19x slower                                                |
| mypy2                            | 726 ms                                                           | 866 ms: 1.19x slower                                                 |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 94.5 ms: 1.19x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 407 ms: 1.27x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 229 ms: 1.33x slower                                                 |
| unpack_sequence                  | 26.2 ns                                                          | 63.5 ns: 2.42x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                          | 170 ms: 2.91x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.14x faster                                                         |

Benchmark hidden because not significant (2): xdsl_constant_fold, tornado_http

- Geometric mean (including insignificant results): 1.143x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.06x
- 95% likely to have a speedup of 1.06x
- 99% likely to have a speedup of 1.05x

# Memory
- memory change: 1.10x