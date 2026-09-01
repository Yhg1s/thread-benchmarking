# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.055x faster
- HPT reliability: 99.95%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.08x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 10.5 ms: 1.06x faster                                              |
| docutils       | 1.89 sec                                                           | 1.89 sec: 1.00x slower                                             |
| fastapi_http   | 215 ms                                                             | 220 ms: 1.02x slower                                               |
| html5lib       | 50.9 ms                                                            | 48.1 ms: 1.06x faster                                              |
| tornado_http   | 98.9 ms                                                            | 103 ms: 1.04x slower                                               |
| Geometric mean | (ref)                                                              | 1.01x faster                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 345 ms: 1.22x faster                                               |
| coroutines                       | 18.2 ms                                                            | 15.6 ms: 1.17x faster                                              |
| async_tree_none                  | 312 ms                                                             | 270 ms: 1.16x faster                                               |
| async_tree_eager_memoization     | 221 ms                                                             | 193 ms: 1.14x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 670 ms: 1.12x faster                                               |
| async_tree_memoization           | 392 ms                                                             | 354 ms: 1.11x faster                                               |
| async_tree_io_tg                 | 781 ms                                                             | 715 ms: 1.09x faster                                               |
| async_tree_io                    | 743 ms                                                             | 683 ms: 1.09x faster                                               |
| asyncio_websockets               | 313 ms                                                             | 297 ms: 1.05x faster                                               |
| asyncio_tcp                      | 316 ms                                                             | 301 ms: 1.05x faster                                               |
| async_generators                 | 251 ms                                                             | 239 ms: 1.05x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 277 ms: 1.05x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 697 ms: 1.05x faster                                               |
| async_tree_eager                 | 88.3 ms                                                            | 85.4 ms: 1.03x faster                                              |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 480 ms: 1.03x faster                                               |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 494 ms: 1.03x faster                                               |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 339 ms: 1.01x faster                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.28 sec: 1.00x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 420 ms: 1.39x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 291 ms: 1.67x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 215 ms: 3.78x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.04x slower                                                       |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 19.2 ns: 1.12x faster                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 212 ms: 1.08x faster                                               |
| decimal_factorial | 177 ms                                                             | 174 ms: 1.01x faster                                               |
| Geometric mean    | (ref)                                                              | 1.04x faster                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 54.3 ms: 1.09x faster                                              |
| quadtree_nbody | 675 ms                                                             | 631 ms: 1.07x faster                                               |
| nbody          | 75.8 ms                                                            | 74.6 ms: 1.02x faster                                              |
| pidigits       | 216 ms                                                             | 216 ms: 1.00x slower                                               |
| Geometric mean | (ref)                                                              | 1.04x faster                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 2.13 ms: 1.09x faster                                              |
| regex_dna      | 159 ms                                                             | 151 ms: 1.05x faster                                               |
| regex_compile  | 102 ms                                                             | 97.9 ms: 1.05x faster                                              |
| regex_v8       | 15.0 ms                                                            | 15.4 ms: 1.03x slower                                              |
| Geometric mean | (ref)                                                              | 1.04x faster                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.33 ms: 6.74x faster                                              |
| base16_small         | 836 us                                                             | 264 us: 3.17x faster                                               |
| tomli_loads          | 1.77 sec                                                           | 1.50 sec: 1.18x faster                                             |
| ascii85_large        | 824 ms                                                             | 699 ms: 1.18x faster                                               |
| ascii85_small        | 15.7 ms                                                            | 13.4 ms: 1.17x faster                                              |
| base32_small         | 6.46 ms                                                            | 5.68 ms: 1.14x faster                                              |
| unpickle_list        | 3.42 us                                                            | 3.02 us: 1.13x faster                                              |
| base32_large         | 325 ms                                                             | 288 ms: 1.13x faster                                               |
| xml_etree_iterparse  | 86.8 ms                                                            | 80.4 ms: 1.08x faster                                              |
| base85_large         | 267 ms                                                             | 254 ms: 1.05x faster                                               |
| xml_etree_generate   | 70.6 ms                                                            | 67.5 ms: 1.05x faster                                              |
| base85_small         | 4.85 ms                                                            | 4.72 ms: 1.03x faster                                              |
| unpickle             | 10.8 us                                                            | 10.5 us: 1.03x faster                                              |
| xml_etree_process    | 49.9 ms                                                            | 48.9 ms: 1.02x faster                                              |
| base64_large         | 5.69 ms                                                            | 5.68 ms: 1.00x faster                                              |
| base64_small         | 222 us                                                             | 223 us: 1.01x slower                                               |
| pickle_pure_python   | 245 us                                                             | 249 us: 1.02x slower                                               |
| xml_etree_parse      | 121 ms                                                             | 123 ms: 1.02x slower                                               |
| pickle_dict          | 19.0 us                                                            | 19.4 us: 1.02x slower                                              |
| urlsafe_base64_small | 328 us                                                             | 338 us: 1.03x slower                                               |
| json_loads           | 18.2 us                                                            | 19.2 us: 1.05x slower                                              |
| json_dumps           | 7.26 ms                                                            | 7.79 ms: 1.07x slower                                              |
| pickle               | 7.21 us                                                            | 8.05 us: 1.12x slower                                              |
| pickle_list          | 2.66 us                                                            | 3.20 us: 1.20x slower                                              |
| Geometric mean       | (ref)                                                              | 1.16x faster                                                       |

Benchmark hidden because not significant (1): unpickle_pure_python

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.53 ms: 1.01x slower                                              |
| python_startup         | 9.51 ms                                                            | 10.0 ms: 1.05x slower                                              |
| Geometric mean         | (ref)                                                              | 1.03x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 18.2 ms: 1.16x faster                                              |
| genshi_xml      | 46.3 ms                                                            | 43.8 ms: 1.06x faster                                              |
| mako            | 8.30 ms                                                            | 8.64 ms: 1.04x slower                                              |
| django_template | 28.8 ms                                                            | 30.3 ms: 1.05x slower                                              |
| Geometric mean  | (ref)                                                              | 1.03x faster                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 12.3 ms: 3.08x faster                                              |
| thread_pipeline_naive       | 49.8 ms                                                            | 35.3 ms: 1.41x faster                                              |
| thread_montecarlo_naive     | 18.1 ms                                                            | 14.8 ms: 1.23x faster                                              |
| thread_montecarlo_optimized | 14.2 ms                                                            | 12.9 ms: 1.10x faster                                              |
| thread_counter_naive        | 23.7 ms                                                            | 21.6 ms: 1.10x faster                                              |
| thread_counter_optimized    | 19.7 ms                                                            | 18.4 ms: 1.07x faster                                              |
| thread_memo_optimized       | 16.8 ms                                                            | 17.5 ms: 1.04x slower                                              |
| thread_mandelbrot_optimized | 189 ms                                                             | 201 ms: 1.07x slower                                               |
| thread_mandelbrot_naive     | 190 ms                                                             | 202 ms: 1.07x slower                                               |
| thread_accumulate_naive     | 36.5 ms                                                            | 40.0 ms: 1.10x slower                                              |
| thread_accumulate_optimized | 35.3 ms                                                            | 39.0 ms: 1.11x slower                                              |
| thread_pipeline_optimized   | 22.8 ms                                                            | 25.5 ms: 1.12x slower                                              |
| Geometric mean              | (ref)                                                              | 1.13x faster                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.33 ms: 6.74x faster                                              |
| base16_small                     | 836 us                                                             | 264 us: 3.17x faster                                               |
| thread_memo_naive                | 37.9 ms                                                            | 12.3 ms: 3.08x faster                                              |
| mdp                              | 2.05 sec                                                           | 984 ms: 2.09x faster                                               |
| argparse_many_optionals          | 12.9 ms                                                            | 8.02 ms: 1.61x faster                                              |
| deepcopy_memo                    | 27.8 us                                                            | 19.1 us: 1.46x faster                                              |
| thread_pipeline_naive            | 49.8 ms                                                            | 35.3 ms: 1.41x faster                                              |
| go                               | 129 ms                                                             | 93.1 ms: 1.39x faster                                              |
| deepcopy                         | 267 us                                                             | 199 us: 1.34x faster                                               |
| scimark_sor                      | 96.2 ms                                                            | 76.6 ms: 1.26x faster                                              |
| thread_montecarlo_naive          | 18.1 ms                                                            | 14.8 ms: 1.23x faster                                              |
| async_tree_memoization_tg        | 421 ms                                                             | 345 ms: 1.22x faster                                               |
| pyflate                          | 374 ms                                                             | 312 ms: 1.20x faster                                               |
| tomli_loads                      | 1.77 sec                                                           | 1.50 sec: 1.18x faster                                             |
| ascii85_large                    | 824 ms                                                             | 699 ms: 1.18x faster                                               |
| ascii85_small                    | 15.7 ms                                                            | 13.4 ms: 1.17x faster                                              |
| coroutines                       | 18.2 ms                                                            | 15.6 ms: 1.17x faster                                              |
| genshi_text                      | 21.1 ms                                                            | 18.2 ms: 1.16x faster                                              |
| async_tree_none                  | 312 ms                                                             | 270 ms: 1.16x faster                                               |
| fannkuch                         | 287 ms                                                             | 250 ms: 1.15x faster                                               |
| deepcopy_reduce                  | 2.36 us                                                            | 2.06 us: 1.15x faster                                              |
| async_tree_eager_memoization     | 221 ms                                                             | 193 ms: 1.14x faster                                               |
| base32_small                     | 6.46 ms                                                            | 5.68 ms: 1.14x faster                                              |
| unpickle_list                    | 3.42 us                                                            | 3.02 us: 1.13x faster                                              |
| base32_large                     | 325 ms                                                             | 288 ms: 1.13x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 670 ms: 1.12x faster                                               |
| noop                             | 21.4 ns                                                            | 19.2 ns: 1.12x faster                                              |
| async_tree_memoization           | 392 ms                                                             | 354 ms: 1.11x faster                                               |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 12.9 ms: 1.10x faster                                              |
| thread_counter_naive             | 23.7 ms                                                            | 21.6 ms: 1.10x faster                                              |
| regex_effbot                     | 2.33 ms                                                            | 2.13 ms: 1.09x faster                                              |
| async_tree_io_tg                 | 781 ms                                                             | 715 ms: 1.09x faster                                               |
| float                            | 59.2 ms                                                            | 54.3 ms: 1.09x faster                                              |
| richards                         | 38.2 ms                                                            | 35.0 ms: 1.09x faster                                              |
| async_tree_io                    | 743 ms                                                             | 683 ms: 1.09x faster                                               |
| richards_super                   | 43.8 ms                                                            | 40.4 ms: 1.09x faster                                              |
| hexiom                           | 4.75 ms                                                            | 4.39 ms: 1.08x faster                                              |
| xml_etree_iterparse              | 86.8 ms                                                            | 80.4 ms: 1.08x faster                                              |
| decimal_pi                       | 228 ms                                                             | 212 ms: 1.08x faster                                               |
| thread_counter_optimized         | 19.7 ms                                                            | 18.4 ms: 1.07x faster                                              |
| quadtree_nbody                   | 675 ms                                                             | 631 ms: 1.07x faster                                               |
| chameleon                        | 11.1 ms                                                            | 10.5 ms: 1.06x faster                                              |
| genshi_xml                       | 46.3 ms                                                            | 43.8 ms: 1.06x faster                                              |
| html5lib                         | 50.9 ms                                                            | 48.1 ms: 1.06x faster                                              |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.20 sec: 1.06x faster                                             |
| asyncio_websockets               | 313 ms                                                             | 297 ms: 1.05x faster                                               |
| regex_dna                        | 159 ms                                                             | 151 ms: 1.05x faster                                               |
| networkx_k_core                  | 2.16 sec                                                           | 2.05 sec: 1.05x faster                                             |
| asyncio_tcp                      | 316 ms                                                             | 301 ms: 1.05x faster                                               |
| base85_large                     | 267 ms                                                             | 254 ms: 1.05x faster                                               |
| async_generators                 | 251 ms                                                             | 239 ms: 1.05x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 277 ms: 1.05x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 697 ms: 1.05x faster                                               |
| xml_etree_generate               | 70.6 ms                                                            | 67.5 ms: 1.05x faster                                              |
| regex_compile                    | 102 ms                                                             | 97.9 ms: 1.05x faster                                              |
| spectral_norm                    | 68.6 ms                                                            | 66.0 ms: 1.04x faster                                              |
| thrift                           | 2.07 ms                                                            | 2.00 ms: 1.04x faster                                              |
| async_tree_eager                 | 88.3 ms                                                            | 85.4 ms: 1.03x faster                                              |
| networkx_shortest_path           | 454 ms                                                             | 440 ms: 1.03x faster                                               |
| networkx_connected_components    | 443 ms                                                             | 430 ms: 1.03x faster                                               |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 480 ms: 1.03x faster                                               |
| pprint_safe_repr                 | 546 ms                                                             | 531 ms: 1.03x faster                                               |
| base85_small                     | 4.85 ms                                                            | 4.72 ms: 1.03x faster                                              |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 494 ms: 1.03x faster                                               |
| unpickle                         | 10.8 us                                                            | 10.5 us: 1.03x faster                                              |
| comprehensions                   | 11.4 us                                                            | 11.1 us: 1.03x faster                                              |
| chaos                            | 43.6 ms                                                            | 42.5 ms: 1.02x faster                                              |
| pprint_pformat                   | 1.13 sec                                                           | 1.10 sec: 1.02x faster                                             |
| sqlglot_v2_parse                 | 979 us                                                             | 958 us: 1.02x faster                                               |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.19 ms: 1.02x faster                                              |
| xml_etree_process                | 49.9 ms                                                            | 48.9 ms: 1.02x faster                                              |
| nbody                            | 75.8 ms                                                            | 74.6 ms: 1.02x faster                                              |
| decimal_factorial                | 177 ms                                                             | 174 ms: 1.01x faster                                               |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 41.6 ms: 1.01x faster                                              |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 339 ms: 1.01x faster                                               |
| coverage                         | 55.0 ms                                                            | 54.6 ms: 1.01x faster                                              |
| meteor_contest                   | 85.7 ms                                                            | 85.4 ms: 1.00x faster                                              |
| base64_large                     | 5.69 ms                                                            | 5.68 ms: 1.00x faster                                              |
| pidigits                         | 216 ms                                                             | 216 ms: 1.00x slower                                               |
| docutils                         | 1.89 sec                                                           | 1.89 sec: 1.00x slower                                             |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.28 sec: 1.00x slower                                             |
| base64_small                     | 222 us                                                             | 223 us: 1.01x slower                                               |
| python_startup_no_site           | 6.49 ms                                                            | 6.53 ms: 1.01x slower                                              |
| logging_simple                   | 5.06 us                                                            | 5.09 us: 1.01x slower                                              |
| typing_runtime_protocols         | 112 us                                                             | 113 us: 1.01x slower                                               |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 84.5 ms: 1.01x slower                                              |
| mypy2                            | 741 ms                                                             | 753 ms: 1.02x slower                                               |
| gc_traversal                     | 3.20 ms                                                            | 3.25 ms: 1.02x slower                                              |
| pickle_pure_python               | 245 us                                                             | 249 us: 1.02x slower                                               |
| json                             | 3.50 ms                                                            | 3.57 ms: 1.02x slower                                              |
| logging_format                   | 5.62 us                                                            | 5.73 us: 1.02x slower                                              |
| xml_etree_parse                  | 121 ms                                                             | 123 ms: 1.02x slower                                               |
| pickle_dict                      | 19.0 us                                                            | 19.4 us: 1.02x slower                                              |
| scimark_fft                      | 216 ms                                                             | 220 ms: 1.02x slower                                               |
| raytrace                         | 197 ms                                                             | 201 ms: 1.02x slower                                               |
| crypto_pyaes                     | 55.6 ms                                                            | 56.9 ms: 1.02x slower                                              |
| fastapi_http                     | 215 ms                                                             | 220 ms: 1.02x slower                                               |
| regex_v8                         | 15.0 ms                                                            | 15.4 ms: 1.03x slower                                              |
| urlsafe_base64_small             | 328 us                                                             | 338 us: 1.03x slower                                               |
| tornado_http                     | 98.9 ms                                                            | 103 ms: 1.04x slower                                               |
| sympy_expand                     | 331 ms                                                             | 344 ms: 1.04x slower                                               |
| pycparser                        | 901 ms                                                             | 937 ms: 1.04x slower                                               |
| thread_memo_optimized            | 16.8 ms                                                            | 17.5 ms: 1.04x slower                                              |
| mako                             | 8.30 ms                                                            | 8.64 ms: 1.04x slower                                              |
| pathlib                          | 12.2 ms                                                            | 12.7 ms: 1.04x slower                                              |
| sympy_str                        | 193 ms                                                             | 201 ms: 1.04x slower                                               |
| python_startup                   | 9.51 ms                                                            | 10.0 ms: 1.05x slower                                              |
| json_loads                       | 18.2 us                                                            | 19.2 us: 1.05x slower                                              |
| django_template                  | 28.8 ms                                                            | 30.3 ms: 1.05x slower                                              |
| create_gc_cycles                 | 1.77 ms                                                            | 1.87 ms: 1.05x slower                                              |
| sympy_sum                        | 104 ms                                                             | 110 ms: 1.05x slower                                               |
| xdsl_constant_fold               | 36.4 ms                                                            | 38.4 ms: 1.06x slower                                              |
| thread_mandelbrot_optimized      | 189 ms                                                             | 201 ms: 1.07x slower                                               |
| thread_mandelbrot_naive          | 190 ms                                                             | 202 ms: 1.07x slower                                               |
| generators                       | 22.2 ms                                                            | 23.7 ms: 1.07x slower                                              |
| scimark_lu                       | 70.2 ms                                                            | 75.3 ms: 1.07x slower                                              |
| json_dumps                       | 7.26 ms                                                            | 7.79 ms: 1.07x slower                                              |
| nqueens                          | 58.3 ms                                                            | 62.7 ms: 1.07x slower                                              |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.0 ms: 1.08x slower                                              |
| thread_accumulate_naive          | 36.5 ms                                                            | 40.0 ms: 1.10x slower                                              |
| thread_accumulate_optimized      | 35.3 ms                                                            | 39.0 ms: 1.11x slower                                              |
| pickle                           | 7.21 us                                                            | 8.05 us: 1.12x slower                                              |
| argparse_subparsers              | 449 us                                                             | 503 us: 1.12x slower                                               |
| thread_pipeline_optimized        | 22.8 ms                                                            | 25.5 ms: 1.12x slower                                              |
| pickle_list                      | 2.66 us                                                            | 3.20 us: 1.20x slower                                              |
| unpack_sequence                  | 26.4 ns                                                            | 36.4 ns: 1.38x slower                                              |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 420 ms: 1.39x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 291 ms: 1.67x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 215 ms: 3.78x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.05x faster                                                       |

Benchmark hidden because not significant (8): scimark_monte_carlo, scimark_sparse_mat_mult, sympy_integrate, logging_silent, telco, unpickle_pure_python, deltablue, pylint

- Geometric mean (including insignificant results): 1.055x faster

# HPT report

- Reliability score: 99.95% likely to be faster
- 90% likely to have a speedup of 1.02x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.08x