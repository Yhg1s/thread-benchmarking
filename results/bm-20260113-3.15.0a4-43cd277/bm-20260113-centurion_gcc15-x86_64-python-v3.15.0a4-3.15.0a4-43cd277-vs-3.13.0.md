# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.102x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.03x faster
- Memory change: 1.10x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 10.6 ms: 1.03x faster                                                |
| docutils       | 1.98 sec                                                         | 2.01 sec: 1.02x slower                                               |
| fastapi_http   | 215 ms                                                           | 208 ms: 1.03x faster                                                 |
| html5lib       | 49.1 ms                                                          | 43.4 ms: 1.13x faster                                                |
| tornado_http   | 99.2 ms                                                          | 97.8 ms: 1.01x faster                                                |
| Geometric mean | (ref)                                                            | 1.04x faster                                                         |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| async_tree_io_tg                 | 777 ms                                                           | 485 ms: 1.60x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 469 ms: 1.60x faster                                                 |
| async_tree_memoization_tg        | 417 ms                                                           | 262 ms: 1.59x faster                                                 |
| async_tree_eager_io_tg           | 724 ms                                                           | 468 ms: 1.55x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 485 ms: 1.53x faster                                                 |
| async_tree_memoization           | 389 ms                                                           | 265 ms: 1.47x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 217 ms: 1.43x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 203 ms: 1.43x faster                                                 |
| async_tree_eager_memoization     | 215 ms                                                           | 166 ms: 1.29x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 437 ms: 1.21x faster                                                 |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 439 ms: 1.17x faster                                                 |
| asyncio_tcp                      | 326 ms                                                           | 279 ms: 1.17x faster                                                 |
| async_tree_eager                 | 90.0 ms                                                          | 77.5 ms: 1.16x faster                                                |
| coroutines                       | 17.6 ms                                                          | 15.4 ms: 1.15x faster                                                |
| async_generators                 | 262 ms                                                           | 240 ms: 1.09x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 353 ms: 1.02x faster                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.27 sec: 1.02x faster                                               |
| asyncio_websockets               | 304 ms                                                           | 309 ms: 1.02x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 410 ms: 1.28x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 227 ms: 1.31x slower                                                 |
| async_tree_eager_tg              | 58.6 ms                                                          | 178 ms: 3.03x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.15x faster                                                         |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 19.4 ns: 1.05x faster                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 207 ms: 1.02x faster                                                 |
| decimal_factorial | 173 ms                                                           | 171 ms: 1.01x faster                                                 |
| Geometric mean    | (ref)                                                            | 1.01x faster                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 48.0 ms: 1.18x faster                                                |
| quadtree_nbody | 620 ms                                                           | 593 ms: 1.05x faster                                                 |
| nbody          | 66.8 ms                                                          | 65.8 ms: 1.02x faster                                                |
| pidigits       | 181 ms                                                           | 182 ms: 1.00x slower                                                 |
| Geometric mean | (ref)                                                            | 1.06x faster                                                         |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.80 ms: 1.11x faster                                                |
| regex_compile  | 97.7 ms                                                          | 90.8 ms: 1.08x faster                                                |
| regex_dna      | 144 ms                                                           | 140 ms: 1.03x faster                                                 |
| regex_v8       | 14.7 ms                                                          | 15.2 ms: 1.04x slower                                                |
| Geometric mean | (ref)                                                            | 1.04x faster                                                         |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.09 ms: 6.21x faster                                                |
| base16_small         | 656 us                                                           | 307 us: 2.13x faster                                                 |
| ascii85_large        | 814 ms                                                           | 653 ms: 1.25x faster                                                 |
| ascii85_small        | 15.5 ms                                                          | 12.7 ms: 1.22x faster                                                |
| json_dumps           | 7.49 ms                                                          | 6.72 ms: 1.11x faster                                                |
| xml_etree_parse      | 107 ms                                                           | 99.3 ms: 1.08x faster                                                |
| base64_large         | 6.32 ms                                                          | 5.87 ms: 1.08x faster                                                |
| tomli_loads          | 1.63 sec                                                         | 1.53 sec: 1.06x faster                                               |
| base64_small         | 228 us                                                           | 221 us: 1.03x faster                                                 |
| pickle_dict          | 21.9 us                                                          | 21.3 us: 1.03x faster                                                |
| base32_large         | 286 ms                                                           | 279 ms: 1.02x faster                                                 |
| urlsafe_base64_small | 379 us                                                           | 372 us: 1.02x faster                                                 |
| unpickle_pure_python | 149 us                                                           | 151 us: 1.02x slower                                                 |
| unpickle_list        | 3.45 us                                                          | 3.51 us: 1.02x slower                                                |
| unpickle             | 10.3 us                                                          | 10.5 us: 1.02x slower                                                |
| xml_etree_process    | 48.1 ms                                                          | 49.3 ms: 1.03x slower                                                |
| json_loads           | 16.7 us                                                          | 17.3 us: 1.04x slower                                                |
| xml_etree_generate   | 66.3 ms                                                          | 68.8 ms: 1.04x slower                                                |
| pickle_pure_python   | 223 us                                                           | 233 us: 1.04x slower                                                 |
| base85_small         | 4.41 ms                                                          | 4.60 ms: 1.04x slower                                                |
| pickle_list          | 3.03 us                                                          | 3.33 us: 1.10x slower                                                |
| pickle               | 8.22 us                                                          | 9.36 us: 1.14x slower                                                |
| Geometric mean       | (ref)                                                            | 1.13x faster                                                         |

Benchmark hidden because not significant (3): base32_small, xml_etree_iterparse, base85_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 6.09 ms: 1.04x faster                                                |
| python_startup         | 9.38 ms                                                          | 9.27 ms: 1.01x faster                                                |
| Geometric mean         | (ref)                                                            | 1.03x faster                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| genshi_text     | 17.6 ms                                                          | 16.2 ms: 1.08x faster                                                |
| genshi_xml      | 39.7 ms                                                          | 39.5 ms: 1.01x faster                                                |
| django_template | 27.3 ms                                                          | 28.8 ms: 1.06x slower                                                |
| mako            | 7.43 ms                                                          | 9.06 ms: 1.22x slower                                                |
| Geometric mean  | (ref)                                                            | 1.04x slower                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 9.85 ms: 3.96x faster                                                |
| thread_pipeline_naive       | 52.1 ms                                                          | 37.3 ms: 1.39x faster                                                |
| thread_montecarlo_naive     | 17.8 ms                                                          | 15.4 ms: 1.16x faster                                                |
| thread_montecarlo_optimized | 13.3 ms                                                          | 13.3 ms: 1.00x faster                                                |
| thread_mandelbrot_naive     | 220 ms                                                           | 219 ms: 1.00x faster                                                 |
| thread_mandelbrot_optimized | 218 ms                                                           | 219 ms: 1.01x slower                                                 |
| thread_counter_naive        | 22.6 ms                                                          | 22.8 ms: 1.01x slower                                                |
| thread_memo_optimized       | 18.2 ms                                                          | 19.3 ms: 1.06x slower                                                |
| thread_accumulate_naive     | 40.9 ms                                                          | 45.4 ms: 1.11x slower                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 20.9 ms: 1.12x slower                                                |
| thread_accumulate_optimized | 39.8 ms                                                          | 45.4 ms: 1.14x slower                                                |
| thread_pipeline_optimized   | 25.6 ms                                                          | 29.5 ms: 1.15x slower                                                |
| Geometric mean              | (ref)                                                            | 1.11x faster                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.09 ms: 6.21x faster                                                |
| thread_memo_naive                | 39.0 ms                                                          | 9.85 ms: 3.96x faster                                                |
| mdp                              | 2.11 sec                                                         | 914 ms: 2.31x faster                                                 |
| base16_small                     | 656 us                                                           | 307 us: 2.13x faster                                                 |
| argparse_many_optionals          | 12.6 ms                                                          | 7.44 ms: 1.69x faster                                                |
| async_tree_io_tg                 | 777 ms                                                           | 485 ms: 1.60x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 469 ms: 1.60x faster                                                 |
| async_tree_memoization_tg        | 417 ms                                                           | 262 ms: 1.59x faster                                                 |
| deepcopy_memo                    | 26.6 us                                                          | 16.7 us: 1.59x faster                                                |
| async_tree_eager_io_tg           | 724 ms                                                           | 468 ms: 1.55x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 485 ms: 1.53x faster                                                 |
| go                               | 121 ms                                                           | 80.6 ms: 1.50x faster                                                |
| async_tree_memoization           | 389 ms                                                           | 265 ms: 1.47x faster                                                 |
| deepcopy                         | 267 us                                                           | 186 us: 1.44x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 217 ms: 1.43x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 203 ms: 1.43x faster                                                 |
| thread_pipeline_naive            | 52.1 ms                                                          | 37.3 ms: 1.39x faster                                                |
| scimark_sor                      | 97.0 ms                                                          | 70.6 ms: 1.37x faster                                                |
| async_tree_eager_memoization     | 215 ms                                                           | 166 ms: 1.29x faster                                                 |
| ascii85_large                    | 814 ms                                                           | 653 ms: 1.25x faster                                                 |
| ascii85_small                    | 15.5 ms                                                          | 12.7 ms: 1.22x faster                                                |
| pyflate                          | 358 ms                                                           | 297 ms: 1.21x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 437 ms: 1.21x faster                                                 |
| scimark_monte_carlo              | 44.3 ms                                                          | 37.0 ms: 1.20x faster                                                |
| deepcopy_reduce                  | 2.37 us                                                          | 2.00 us: 1.18x faster                                                |
| float                            | 56.6 ms                                                          | 48.0 ms: 1.18x faster                                                |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 439 ms: 1.17x faster                                                 |
| asyncio_tcp                      | 326 ms                                                           | 279 ms: 1.17x faster                                                 |
| pathlib                          | 12.4 ms                                                          | 10.7 ms: 1.16x faster                                                |
| async_tree_eager                 | 90.0 ms                                                          | 77.5 ms: 1.16x faster                                                |
| thread_montecarlo_naive          | 17.8 ms                                                          | 15.4 ms: 1.16x faster                                                |
| fannkuch                         | 265 ms                                                           | 229 ms: 1.16x faster                                                 |
| coroutines                       | 17.6 ms                                                          | 15.4 ms: 1.15x faster                                                |
| richards                         | 36.8 ms                                                          | 32.4 ms: 1.14x faster                                                |
| chaos                            | 45.0 ms                                                          | 39.7 ms: 1.13x faster                                                |
| html5lib                         | 49.1 ms                                                          | 43.4 ms: 1.13x faster                                                |
| hexiom                           | 4.42 ms                                                          | 3.92 ms: 1.13x faster                                                |
| richards_super                   | 41.3 ms                                                          | 37.0 ms: 1.12x faster                                                |
| json_dumps                       | 7.49 ms                                                          | 6.72 ms: 1.11x faster                                                |
| thrift                           | 2.07 ms                                                          | 1.86 ms: 1.11x faster                                                |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.06 sec: 1.11x faster                                               |
| regex_effbot                     | 1.99 ms                                                          | 1.80 ms: 1.11x faster                                                |
| networkx_k_core                  | 2.15 sec                                                         | 1.94 sec: 1.11x faster                                               |
| telco                            | 5.50 ms                                                          | 4.98 ms: 1.10x faster                                                |
| pprint_safe_repr                 | 541 ms                                                           | 493 ms: 1.10x faster                                                 |
| async_generators                 | 262 ms                                                           | 240 ms: 1.09x faster                                                 |
| genshi_text                      | 17.6 ms                                                          | 16.2 ms: 1.08x faster                                                |
| pylint                           | 226 ms                                                           | 209 ms: 1.08x faster                                                 |
| xml_etree_parse                  | 107 ms                                                           | 99.3 ms: 1.08x faster                                                |
| scimark_fft                      | 211 ms                                                           | 195 ms: 1.08x faster                                                 |
| generators                       | 22.0 ms                                                          | 20.4 ms: 1.08x faster                                                |
| pprint_pformat                   | 1.11 sec                                                         | 1.03 sec: 1.08x faster                                               |
| comprehensions                   | 11.6 us                                                          | 10.8 us: 1.08x faster                                                |
| scimark_lu                       | 70.2 ms                                                          | 65.2 ms: 1.08x faster                                                |
| base64_large                     | 6.32 ms                                                          | 5.87 ms: 1.08x faster                                                |
| regex_compile                    | 97.7 ms                                                          | 90.8 ms: 1.08x faster                                                |
| pycparser                        | 884 ms                                                           | 824 ms: 1.07x faster                                                 |
| meteor_contest                   | 89.9 ms                                                          | 84.1 ms: 1.07x faster                                                |
| xdsl_constant_fold               | 36.7 ms                                                          | 34.5 ms: 1.06x faster                                                |
| tomli_loads                      | 1.63 sec                                                         | 1.53 sec: 1.06x faster                                               |
| spectral_norm                    | 64.1 ms                                                          | 60.5 ms: 1.06x faster                                                |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.14 ms: 1.05x faster                                                |
| deltablue                        | 2.52 ms                                                          | 2.39 ms: 1.05x faster                                                |
| noop                             | 20.4 ns                                                          | 19.4 ns: 1.05x faster                                                |
| quadtree_nbody                   | 620 ms                                                           | 593 ms: 1.05x faster                                                 |
| sympy_integrate                  | 15.4 ms                                                          | 14.7 ms: 1.05x faster                                                |
| sqlglot_v2_parse                 | 953 us                                                           | 913 us: 1.04x faster                                                 |
| python_startup_no_site           | 6.36 ms                                                          | 6.09 ms: 1.04x faster                                                |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.55 ms: 1.04x faster                                                |
| networkx_shortest_path           | 464 ms                                                           | 445 ms: 1.04x faster                                                 |
| nqueens                          | 57.3 ms                                                          | 55.0 ms: 1.04x faster                                                |
| networkx_connected_components    | 460 ms                                                           | 442 ms: 1.04x faster                                                 |
| raytrace                         | 199 ms                                                           | 191 ms: 1.04x faster                                                 |
| base64_small                     | 228 us                                                           | 221 us: 1.03x faster                                                 |
| chameleon                        | 10.9 ms                                                          | 10.6 ms: 1.03x faster                                                |
| fastapi_http                     | 215 ms                                                           | 208 ms: 1.03x faster                                                 |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 38.8 ms: 1.03x faster                                                |
| json                             | 3.49 ms                                                          | 3.40 ms: 1.03x faster                                                |
| regex_dna                        | 144 ms                                                           | 140 ms: 1.03x faster                                                 |
| pickle_dict                      | 21.9 us                                                          | 21.3 us: 1.03x faster                                                |
| base32_large                     | 286 ms                                                           | 279 ms: 1.02x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 353 ms: 1.02x faster                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.27 sec: 1.02x faster                                               |
| urlsafe_base64_small             | 379 us                                                           | 372 us: 1.02x faster                                                 |
| nbody                            | 66.8 ms                                                          | 65.8 ms: 1.02x faster                                                |
| decimal_pi                       | 210 ms                                                           | 207 ms: 1.02x faster                                                 |
| tornado_http                     | 99.2 ms                                                          | 97.8 ms: 1.01x faster                                                |
| logging_silent                   | 60.6 ns                                                          | 59.8 ns: 1.01x faster                                                |
| python_startup                   | 9.38 ms                                                          | 9.27 ms: 1.01x faster                                                |
| logging_simple                   | 4.60 us                                                          | 4.57 us: 1.01x faster                                                |
| logging_format                   | 5.23 us                                                          | 5.20 us: 1.01x faster                                                |
| typing_runtime_protocols         | 106 us                                                           | 105 us: 1.01x faster                                                 |
| genshi_xml                       | 39.7 ms                                                          | 39.5 ms: 1.01x faster                                                |
| decimal_factorial                | 173 ms                                                           | 171 ms: 1.01x faster                                                 |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 78.7 ms: 1.01x faster                                                |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 13.3 ms: 1.00x faster                                                |
| thread_mandelbrot_naive          | 220 ms                                                           | 219 ms: 1.00x faster                                                 |
| sympy_str                        | 193 ms                                                           | 194 ms: 1.00x slower                                                 |
| pidigits                         | 181 ms                                                           | 182 ms: 1.00x slower                                                 |
| unpack_sequence                  | 26.2 ns                                                          | 26.4 ns: 1.01x slower                                                |
| thread_mandelbrot_optimized      | 218 ms                                                           | 219 ms: 1.01x slower                                                 |
| thread_counter_naive             | 22.6 ms                                                          | 22.8 ms: 1.01x slower                                                |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                                 |
| sympy_expand                     | 330 ms                                                           | 335 ms: 1.02x slower                                                 |
| coverage                         | 52.2 ms                                                          | 53.0 ms: 1.02x slower                                                |
| docutils                         | 1.98 sec                                                         | 2.01 sec: 1.02x slower                                               |
| asyncio_websockets               | 304 ms                                                           | 309 ms: 1.02x slower                                                 |
| unpickle_pure_python             | 149 us                                                           | 151 us: 1.02x slower                                                 |
| unpickle_list                    | 3.45 us                                                          | 3.51 us: 1.02x slower                                                |
| mypy2                            | 726 ms                                                           | 740 ms: 1.02x slower                                                 |
| unpickle                         | 10.3 us                                                          | 10.5 us: 1.02x slower                                                |
| crypto_pyaes                     | 50.0 ms                                                          | 51.0 ms: 1.02x slower                                                |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.1 ms: 1.02x slower                                                |
| xml_etree_process                | 48.1 ms                                                          | 49.3 ms: 1.03x slower                                                |
| json_loads                       | 16.7 us                                                          | 17.3 us: 1.04x slower                                                |
| regex_v8                         | 14.7 ms                                                          | 15.2 ms: 1.04x slower                                                |
| xml_etree_generate               | 66.3 ms                                                          | 68.8 ms: 1.04x slower                                                |
| pickle_pure_python               | 223 us                                                           | 233 us: 1.04x slower                                                 |
| base85_small                     | 4.41 ms                                                          | 4.60 ms: 1.04x slower                                                |
| gc_traversal                     | 3.16 ms                                                          | 3.30 ms: 1.04x slower                                                |
| django_template                  | 27.3 ms                                                          | 28.8 ms: 1.06x slower                                                |
| argparse_subparsers              | 446 us                                                           | 472 us: 1.06x slower                                                 |
| thread_memo_optimized            | 18.2 ms                                                          | 19.3 ms: 1.06x slower                                                |
| pickle_list                      | 3.03 us                                                          | 3.33 us: 1.10x slower                                                |
| thread_accumulate_naive          | 40.9 ms                                                          | 45.4 ms: 1.11x slower                                                |
| thread_counter_optimized         | 18.7 ms                                                          | 20.9 ms: 1.12x slower                                                |
| pickle                           | 8.22 us                                                          | 9.36 us: 1.14x slower                                                |
| thread_accumulate_optimized      | 39.8 ms                                                          | 45.4 ms: 1.14x slower                                                |
| create_gc_cycles                 | 1.70 ms                                                          | 1.94 ms: 1.14x slower                                                |
| thread_pipeline_optimized        | 25.6 ms                                                          | 29.5 ms: 1.15x slower                                                |
| mako                             | 7.43 ms                                                          | 9.06 ms: 1.22x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 410 ms: 1.28x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 227 ms: 1.31x slower                                                 |
| async_tree_eager_tg              | 58.6 ms                                                          | 178 ms: 3.03x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.10x faster                                                         |

Benchmark hidden because not significant (3): base32_small, xml_etree_iterparse, base85_large

- Geometric mean (including insignificant results): 1.102x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.04x
- 95% likely to have a speedup of 1.04x
- 99% likely to have a speedup of 1.03x

# Memory
- memory change: 1.10x