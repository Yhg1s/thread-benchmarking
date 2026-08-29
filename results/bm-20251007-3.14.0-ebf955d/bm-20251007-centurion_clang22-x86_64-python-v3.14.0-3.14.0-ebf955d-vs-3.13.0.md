# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.065x faster
- HPT reliability: 99.98%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.10x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 10.3 ms: 1.08x faster                                              |
| docutils       | 1.89 sec                                                           | 1.98 sec: 1.05x slower                                             |
| fastapi_http   | 215 ms                                                             | 222 ms: 1.03x slower                                               |
| html5lib       | 50.9 ms                                                            | 45.3 ms: 1.12x faster                                              |
| tornado_http   | 98.9 ms                                                            | 101 ms: 1.02x slower                                               |
| Geometric mean | (ref)                                                              | 1.02x faster                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 279 ms: 1.51x faster                                               |
| async_tree_io_tg                 | 781 ms                                                             | 545 ms: 1.43x faster                                               |
| async_tree_memoization           | 392 ms                                                             | 285 ms: 1.38x faster                                               |
| async_tree_io                    | 743 ms                                                             | 549 ms: 1.35x faster                                               |
| async_tree_none                  | 312 ms                                                             | 233 ms: 1.34x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 568 ms: 1.33x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 224 ms: 1.29x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 565 ms: 1.29x faster                                               |
| async_tree_eager_memoization     | 221 ms                                                             | 183 ms: 1.21x faster                                               |
| coroutines                       | 18.2 ms                                                            | 15.1 ms: 1.20x faster                                              |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 427 ms: 1.19x faster                                               |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 429 ms: 1.15x faster                                               |
| async_generators                 | 251 ms                                                             | 231 ms: 1.09x faster                                               |
| async_tree_eager                 | 88.3 ms                                                            | 83.0 ms: 1.06x faster                                              |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 327 ms: 1.05x faster                                               |
| asyncio_websockets               | 313 ms                                                             | 305 ms: 1.03x faster                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.29 sec: 1.01x slower                                             |
| asyncio_tcp                      | 316 ms                                                             | 324 ms: 1.02x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 374 ms: 1.24x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 236 ms: 1.35x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 182 ms: 3.21x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.08x faster                                                       |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 19.2 ns: 1.12x faster                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 209 ms: 1.09x faster                                               |
| decimal_factorial | 177 ms                                                             | 174 ms: 1.01x faster                                               |
| Geometric mean    | (ref)                                                              | 1.05x faster                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 51.2 ms: 1.16x faster                                              |
| quadtree_nbody | 675 ms                                                             | 654 ms: 1.03x faster                                               |
| nbody          | 75.8 ms                                                            | 74.2 ms: 1.02x faster                                              |
| pidigits       | 216 ms                                                             | 216 ms: 1.00x slower                                               |
| Geometric mean | (ref)                                                              | 1.05x faster                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 1.98 ms: 1.18x faster                                              |
| regex_dna      | 159 ms                                                             | 147 ms: 1.08x faster                                               |
| regex_compile  | 102 ms                                                             | 97.0 ms: 1.06x faster                                              |
| Geometric mean | (ref)                                                              | 1.08x faster                                                       |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.35 ms: 6.72x faster                                              |
| base16_small         | 836 us                                                             | 265 us: 3.16x faster                                               |
| ascii85_large        | 824 ms                                                             | 681 ms: 1.21x faster                                               |
| ascii85_small        | 15.7 ms                                                            | 13.0 ms: 1.21x faster                                              |
| tomli_loads          | 1.77 sec                                                           | 1.49 sec: 1.19x faster                                             |
| base32_small         | 6.46 ms                                                            | 5.71 ms: 1.13x faster                                              |
| unpickle_list        | 3.42 us                                                            | 3.03 us: 1.13x faster                                              |
| base32_large         | 325 ms                                                             | 289 ms: 1.12x faster                                               |
| base85_large         | 267 ms                                                             | 249 ms: 1.07x faster                                               |
| base85_small         | 4.85 ms                                                            | 4.66 ms: 1.04x faster                                              |
| xml_etree_generate   | 70.6 ms                                                            | 68.1 ms: 1.04x faster                                              |
| unpickle             | 10.8 us                                                            | 10.5 us: 1.03x faster                                              |
| xml_etree_parse      | 121 ms                                                             | 118 ms: 1.03x faster                                               |
| xml_etree_iterparse  | 86.8 ms                                                            | 85.5 ms: 1.02x faster                                              |
| unpickle_pure_python | 161 us                                                             | 163 us: 1.01x slower                                               |
| json_loads           | 18.2 us                                                            | 18.6 us: 1.02x slower                                              |
| pickle_pure_python   | 245 us                                                             | 251 us: 1.02x slower                                               |
| base64_small         | 222 us                                                             | 227 us: 1.02x slower                                               |
| json_dumps           | 7.26 ms                                                            | 7.52 ms: 1.04x slower                                              |
| urlsafe_base64_small | 328 us                                                             | 340 us: 1.04x slower                                               |
| pickle_dict          | 19.0 us                                                            | 20.0 us: 1.05x slower                                              |
| pickle               | 7.21 us                                                            | 8.04 us: 1.12x slower                                              |
| pickle_list          | 2.66 us                                                            | 3.03 us: 1.14x slower                                              |
| Geometric mean       | (ref)                                                              | 1.16x faster                                                       |

Benchmark hidden because not significant (2): base64_large, xml_etree_process

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.52 ms: 1.00x slower                                              |
| python_startup         | 9.51 ms                                                            | 9.93 ms: 1.04x slower                                              |
| Geometric mean         | (ref)                                                              | 1.02x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 18.0 ms: 1.17x faster                                              |
| genshi_xml      | 46.3 ms                                                            | 43.2 ms: 1.07x faster                                              |
| mako            | 8.30 ms                                                            | 8.69 ms: 1.05x slower                                              |
| django_template | 28.8 ms                                                            | 30.5 ms: 1.06x slower                                              |
| Geometric mean  | (ref)                                                              | 1.03x faster                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 12.4 ms: 3.05x faster                                              |
| thread_pipeline_naive       | 49.8 ms                                                            | 34.9 ms: 1.43x faster                                              |
| thread_montecarlo_naive     | 18.1 ms                                                            | 14.3 ms: 1.27x faster                                              |
| thread_counter_naive        | 23.7 ms                                                            | 21.2 ms: 1.12x faster                                              |
| thread_montecarlo_optimized | 14.2 ms                                                            | 12.9 ms: 1.10x faster                                              |
| thread_counter_optimized    | 19.7 ms                                                            | 18.3 ms: 1.08x faster                                              |
| thread_memo_optimized       | 16.8 ms                                                            | 17.5 ms: 1.04x slower                                              |
| thread_mandelbrot_optimized | 189 ms                                                             | 205 ms: 1.09x slower                                               |
| thread_mandelbrot_naive     | 190 ms                                                             | 207 ms: 1.09x slower                                               |
| thread_accumulate_naive     | 36.5 ms                                                            | 40.4 ms: 1.11x slower                                              |
| thread_accumulate_optimized | 35.3 ms                                                            | 39.5 ms: 1.12x slower                                              |
| thread_pipeline_optimized   | 22.8 ms                                                            | 25.8 ms: 1.13x slower                                              |
| Geometric mean              | (ref)                                                              | 1.13x faster                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.35 ms: 6.72x faster                                              |
| base16_small                     | 836 us                                                             | 265 us: 3.16x faster                                               |
| thread_memo_naive                | 37.9 ms                                                            | 12.4 ms: 3.05x faster                                              |
| mdp                              | 2.05 sec                                                           | 971 ms: 2.12x faster                                               |
| async_tree_memoization_tg        | 421 ms                                                             | 279 ms: 1.51x faster                                               |
| deepcopy_memo                    | 27.8 us                                                            | 19.1 us: 1.45x faster                                              |
| async_tree_io_tg                 | 781 ms                                                             | 545 ms: 1.43x faster                                               |
| thread_pipeline_naive            | 49.8 ms                                                            | 34.9 ms: 1.43x faster                                              |
| go                               | 129 ms                                                             | 91.1 ms: 1.42x faster                                              |
| async_tree_memoization           | 392 ms                                                             | 285 ms: 1.38x faster                                               |
| async_tree_io                    | 743 ms                                                             | 549 ms: 1.35x faster                                               |
| deepcopy                         | 267 us                                                             | 198 us: 1.35x faster                                               |
| async_tree_none                  | 312 ms                                                             | 233 ms: 1.34x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 568 ms: 1.33x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 224 ms: 1.29x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 565 ms: 1.29x faster                                               |
| thread_montecarlo_naive          | 18.1 ms                                                            | 14.3 ms: 1.27x faster                                              |
| scimark_sor                      | 96.2 ms                                                            | 78.2 ms: 1.23x faster                                              |
| ascii85_large                    | 824 ms                                                             | 681 ms: 1.21x faster                                               |
| pyflate                          | 374 ms                                                             | 309 ms: 1.21x faster                                               |
| async_tree_eager_memoization     | 221 ms                                                             | 183 ms: 1.21x faster                                               |
| ascii85_small                    | 15.7 ms                                                            | 13.0 ms: 1.21x faster                                              |
| coroutines                       | 18.2 ms                                                            | 15.1 ms: 1.20x faster                                              |
| tomli_loads                      | 1.77 sec                                                           | 1.49 sec: 1.19x faster                                             |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 427 ms: 1.19x faster                                               |
| regex_effbot                     | 2.33 ms                                                            | 1.98 ms: 1.18x faster                                              |
| genshi_text                      | 21.1 ms                                                            | 18.0 ms: 1.17x faster                                              |
| deepcopy_reduce                  | 2.36 us                                                            | 2.02 us: 1.17x faster                                              |
| fannkuch                         | 287 ms                                                             | 246 ms: 1.16x faster                                               |
| float                            | 59.2 ms                                                            | 51.2 ms: 1.16x faster                                              |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 429 ms: 1.15x faster                                               |
| base32_small                     | 6.46 ms                                                            | 5.71 ms: 1.13x faster                                              |
| unpickle_list                    | 3.42 us                                                            | 3.03 us: 1.13x faster                                              |
| html5lib                         | 50.9 ms                                                            | 45.3 ms: 1.12x faster                                              |
| base32_large                     | 325 ms                                                             | 289 ms: 1.12x faster                                               |
| thread_counter_naive             | 23.7 ms                                                            | 21.2 ms: 1.12x faster                                              |
| noop                             | 21.4 ns                                                            | 19.2 ns: 1.12x faster                                              |
| scimark_monte_carlo              | 47.2 ms                                                            | 42.3 ms: 1.11x faster                                              |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 12.9 ms: 1.10x faster                                              |
| richards                         | 38.2 ms                                                            | 34.7 ms: 1.10x faster                                              |
| decimal_pi                       | 228 ms                                                             | 209 ms: 1.09x faster                                               |
| async_generators                 | 251 ms                                                             | 231 ms: 1.09x faster                                               |
| richards_super                   | 43.8 ms                                                            | 40.3 ms: 1.09x faster                                              |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.11 sec: 1.09x faster                                             |
| chameleon                        | 11.1 ms                                                            | 10.3 ms: 1.08x faster                                              |
| thread_counter_optimized         | 19.7 ms                                                            | 18.3 ms: 1.08x faster                                              |
| regex_dna                        | 159 ms                                                             | 147 ms: 1.08x faster                                               |
| genshi_xml                       | 46.3 ms                                                            | 43.2 ms: 1.07x faster                                              |
| base85_large                     | 267 ms                                                             | 249 ms: 1.07x faster                                               |
| spectral_norm                    | 68.6 ms                                                            | 64.1 ms: 1.07x faster                                              |
| async_tree_eager                 | 88.3 ms                                                            | 83.0 ms: 1.06x faster                                              |
| regex_compile                    | 102 ms                                                             | 97.0 ms: 1.06x faster                                              |
| hexiom                           | 4.75 ms                                                            | 4.50 ms: 1.06x faster                                              |
| networkx_k_core                  | 2.16 sec                                                           | 2.05 sec: 1.05x faster                                             |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 327 ms: 1.05x faster                                               |
| networkx_connected_components    | 443 ms                                                             | 425 ms: 1.04x faster                                               |
| base85_small                     | 4.85 ms                                                            | 4.66 ms: 1.04x faster                                              |
| xml_etree_generate               | 70.6 ms                                                            | 68.1 ms: 1.04x faster                                              |
| thrift                           | 2.07 ms                                                            | 2.00 ms: 1.04x faster                                              |
| unpickle                         | 10.8 us                                                            | 10.5 us: 1.03x faster                                              |
| quadtree_nbody                   | 675 ms                                                             | 654 ms: 1.03x faster                                               |
| xml_etree_parse                  | 121 ms                                                             | 118 ms: 1.03x faster                                               |
| pycparser                        | 901 ms                                                             | 878 ms: 1.03x faster                                               |
| asyncio_websockets               | 313 ms                                                             | 305 ms: 1.03x faster                                               |
| sqlglot_v2_parse                 | 979 us                                                             | 954 us: 1.03x faster                                               |
| pprint_pformat                   | 1.13 sec                                                           | 1.10 sec: 1.03x faster                                             |
| scimark_fft                      | 216 ms                                                             | 211 ms: 1.02x faster                                               |
| nbody                            | 75.8 ms                                                            | 74.2 ms: 1.02x faster                                              |
| pprint_safe_repr                 | 546 ms                                                             | 534 ms: 1.02x faster                                               |
| sympy_integrate                  | 15.4 ms                                                            | 15.1 ms: 1.02x faster                                              |
| networkx_shortest_path           | 454 ms                                                             | 447 ms: 1.02x faster                                               |
| chaos                            | 43.6 ms                                                            | 42.9 ms: 1.02x faster                                              |
| xml_etree_iterparse              | 86.8 ms                                                            | 85.5 ms: 1.02x faster                                              |
| logging_silent                   | 60.1 ns                                                            | 59.2 ns: 1.01x faster                                              |
| decimal_factorial                | 177 ms                                                             | 174 ms: 1.01x faster                                               |
| json                             | 3.50 ms                                                            | 3.46 ms: 1.01x faster                                              |
| coverage                         | 55.0 ms                                                            | 54.5 ms: 1.01x faster                                              |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 41.8 ms: 1.01x faster                                              |
| logging_simple                   | 5.06 us                                                            | 5.02 us: 1.01x faster                                              |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.21 ms: 1.01x faster                                              |
| meteor_contest                   | 85.7 ms                                                            | 85.4 ms: 1.00x faster                                              |
| pidigits                         | 216 ms                                                             | 216 ms: 1.00x slower                                               |
| python_startup_no_site           | 6.49 ms                                                            | 6.52 ms: 1.00x slower                                              |
| telco                            | 5.37 ms                                                            | 5.39 ms: 1.01x slower                                              |
| unpickle_pure_python             | 161 us                                                             | 163 us: 1.01x slower                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.29 sec: 1.01x slower                                             |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.89 ms: 1.01x slower                                              |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 84.9 ms: 1.01x slower                                              |
| crypto_pyaes                     | 55.6 ms                                                            | 56.7 ms: 1.02x slower                                              |
| raytrace                         | 197 ms                                                             | 201 ms: 1.02x slower                                               |
| tornado_http                     | 98.9 ms                                                            | 101 ms: 1.02x slower                                               |
| json_loads                       | 18.2 us                                                            | 18.6 us: 1.02x slower                                              |
| pickle_pure_python               | 245 us                                                             | 251 us: 1.02x slower                                               |
| asyncio_tcp                      | 316 ms                                                             | 324 ms: 1.02x slower                                               |
| base64_small                     | 222 us                                                             | 227 us: 1.02x slower                                               |
| nqueens                          | 58.3 ms                                                            | 59.8 ms: 1.02x slower                                              |
| typing_runtime_protocols         | 112 us                                                             | 115 us: 1.02x slower                                               |
| fastapi_http                     | 215 ms                                                             | 222 ms: 1.03x slower                                               |
| sympy_str                        | 193 ms                                                             | 200 ms: 1.04x slower                                               |
| sympy_expand                     | 331 ms                                                             | 344 ms: 1.04x slower                                               |
| json_dumps                       | 7.26 ms                                                            | 7.52 ms: 1.04x slower                                              |
| pathlib                          | 12.2 ms                                                            | 12.7 ms: 1.04x slower                                              |
| urlsafe_base64_small             | 328 us                                                             | 340 us: 1.04x slower                                               |
| sympy_sum                        | 104 ms                                                             | 109 ms: 1.04x slower                                               |
| thread_memo_optimized            | 16.8 ms                                                            | 17.5 ms: 1.04x slower                                              |
| python_startup                   | 9.51 ms                                                            | 9.93 ms: 1.04x slower                                              |
| docutils                         | 1.89 sec                                                           | 1.98 sec: 1.05x slower                                             |
| mako                             | 8.30 ms                                                            | 8.69 ms: 1.05x slower                                              |
| pickle_dict                      | 19.0 us                                                            | 20.0 us: 1.05x slower                                              |
| gc_traversal                     | 3.20 ms                                                            | 3.36 ms: 1.05x slower                                              |
| mypy2                            | 741 ms                                                             | 780 ms: 1.05x slower                                               |
| django_template                  | 28.8 ms                                                            | 30.5 ms: 1.06x slower                                              |
| scimark_lu                       | 70.2 ms                                                            | 74.7 ms: 1.06x slower                                              |
| sqlalchemy_imperative            | 13.9 ms                                                            | 14.8 ms: 1.06x slower                                              |
| deltablue                        | 2.59 ms                                                            | 2.76 ms: 1.07x slower                                              |
| logging_format                   | 5.62 us                                                            | 6.00 us: 1.07x slower                                              |
| thread_mandelbrot_optimized      | 189 ms                                                             | 205 ms: 1.09x slower                                               |
| generators                       | 22.2 ms                                                            | 24.2 ms: 1.09x slower                                              |
| thread_mandelbrot_naive          | 190 ms                                                             | 207 ms: 1.09x slower                                               |
| thread_accumulate_naive          | 36.5 ms                                                            | 40.4 ms: 1.11x slower                                              |
| pickle                           | 7.21 us                                                            | 8.04 us: 1.12x slower                                              |
| thread_accumulate_optimized      | 35.3 ms                                                            | 39.5 ms: 1.12x slower                                              |
| thread_pipeline_optimized        | 22.8 ms                                                            | 25.8 ms: 1.13x slower                                              |
| create_gc_cycles                 | 1.77 ms                                                            | 2.02 ms: 1.14x slower                                              |
| pickle_list                      | 2.66 us                                                            | 3.03 us: 1.14x slower                                              |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 374 ms: 1.24x slower                                               |
| unpack_sequence                  | 26.4 ns                                                            | 35.6 ns: 1.35x slower                                              |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 236 ms: 1.35x slower                                               |
| argparse_subparsers              | 449 us                                                             | 687 us: 1.53x slower                                               |
| argparse_many_optionals          | 12.9 ms                                                            | 34.5 ms: 2.67x slower                                              |
| async_tree_eager_tg              | 56.8 ms                                                            | 182 ms: 3.21x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.06x faster                                                       |

Benchmark hidden because not significant (6): pylint, xdsl_constant_fold, comprehensions, regex_v8, base64_large, xml_etree_process

- Geometric mean (including insignificant results): 1.065x faster

# HPT report

- Reliability score: 99.98% likely to be faster
- 90% likely to have a speedup of 1.02x
- 95% likely to have a speedup of 1.02x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.10x