# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.128x faster
- HPT reliability: 98.10%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.58x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 11.3 ms: 1.02x slower                                              |
| docutils       | 1.89 sec                                                           | 2.01 sec: 1.06x slower                                             |
| fastapi_http   | 215 ms                                                             | 190 ms: 1.13x faster                                               |
| html5lib       | 50.9 ms                                                            | 44.9 ms: 1.13x faster                                              |
| tornado_http   | 98.9 ms                                                            | 93.0 ms: 1.06x faster                                              |
| Geometric mean | (ref)                                                              | 1.05x faster                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_io_tg                 | 781 ms                                                             | 396 ms: 1.97x faster                                               |
| async_tree_memoization_tg        | 421 ms                                                             | 222 ms: 1.89x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 389 ms: 1.88x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 166 ms: 1.75x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 436 ms: 1.73x faster                                               |
| async_tree_io                    | 743 ms                                                             | 432 ms: 1.72x faster                                               |
| async_tree_none                  | 312 ms                                                             | 205 ms: 1.52x faster                                               |
| async_tree_memoization           | 392 ms                                                             | 258 ms: 1.52x faster                                               |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 364 ms: 1.39x faster                                               |
| coroutines                       | 18.2 ms                                                            | 14.9 ms: 1.23x faster                                              |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 403 ms: 1.23x faster                                               |
| async_tree_eager_memoization     | 221 ms                                                             | 180 ms: 1.23x faster                                               |
| asyncio_websockets               | 313 ms                                                             | 289 ms: 1.08x faster                                               |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 332 ms: 1.03x faster                                               |
| async_generators                 | 251 ms                                                             | 249 ms: 1.01x faster                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.38 sec: 1.08x slower                                             |
| async_tree_eager                 | 88.3 ms                                                            | 97.6 ms: 1.11x slower                                              |
| asyncio_tcp                      | 316 ms                                                             | 362 ms: 1.15x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 350 ms: 1.16x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 207 ms: 1.18x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 148 ms: 2.60x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.20x faster                                                       |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 20.2 ns: 1.06x faster                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                             | 184 ms: 1.04x slower                                               |
| decimal_pi        | 228 ms                                                             | 243 ms: 1.06x slower                                               |
| Geometric mean    | (ref)                                                              | 1.05x slower                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 51.3 ms: 1.15x faster                                              |
| quadtree_nbody | 675 ms                                                             | 666 ms: 1.01x faster                                               |
| pidigits       | 216 ms                                                             | 214 ms: 1.01x faster                                               |
| nbody          | 75.8 ms                                                            | 83.1 ms: 1.10x slower                                              |
| Geometric mean | (ref)                                                              | 1.02x faster                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 1.96 ms: 1.19x faster                                              |
| regex_dna      | 159 ms                                                             | 149 ms: 1.07x faster                                               |
| regex_v8       | 15.0 ms                                                            | 14.1 ms: 1.06x faster                                              |
| regex_compile  | 102 ms                                                             | 105 ms: 1.03x slower                                               |
| Geometric mean | (ref)                                                              | 1.07x faster                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.07 ms: 7.03x faster                                              |
| base16_small         | 836 us                                                             | 245 us: 3.41x faster                                               |
| xml_etree_iterparse  | 86.8 ms                                                            | 69.5 ms: 1.25x faster                                              |
| tomli_loads          | 1.77 sec                                                           | 1.53 sec: 1.16x faster                                             |
| ascii85_small        | 15.7 ms                                                            | 14.3 ms: 1.10x faster                                              |
| ascii85_large        | 824 ms                                                             | 751 ms: 1.10x faster                                               |
| base32_large         | 325 ms                                                             | 305 ms: 1.07x faster                                               |
| base32_small         | 6.46 ms                                                            | 6.06 ms: 1.07x faster                                              |
| xml_etree_parse      | 121 ms                                                             | 113 ms: 1.06x faster                                               |
| xml_etree_generate   | 70.6 ms                                                            | 67.5 ms: 1.05x faster                                              |
| unpickle_list        | 3.42 us                                                            | 3.30 us: 1.04x faster                                              |
| unpickle             | 10.8 us                                                            | 10.5 us: 1.03x faster                                              |
| base85_large         | 267 ms                                                             | 261 ms: 1.02x faster                                               |
| xml_etree_process    | 49.9 ms                                                            | 48.8 ms: 1.02x faster                                              |
| base64_small         | 222 us                                                             | 220 us: 1.01x faster                                               |
| base64_large         | 5.69 ms                                                            | 5.68 ms: 1.00x faster                                              |
| urlsafe_base64_small | 328 us                                                             | 332 us: 1.01x slower                                               |
| pickle_pure_python   | 245 us                                                             | 249 us: 1.02x slower                                               |
| json_dumps           | 7.26 ms                                                            | 7.45 ms: 1.03x slower                                              |
| json_loads           | 18.2 us                                                            | 19.2 us: 1.05x slower                                              |
| pickle_dict          | 19.0 us                                                            | 20.4 us: 1.07x slower                                              |
| pickle               | 7.21 us                                                            | 7.80 us: 1.08x slower                                              |
| pickle_list          | 2.66 us                                                            | 2.95 us: 1.11x slower                                              |
| Geometric mean       | (ref)                                                              | 1.16x faster                                                       |

Benchmark hidden because not significant (2): unpickle_pure_python, base85_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                            | 11.5 ms: 1.21x slower                                              |
| python_startup_no_site | 6.49 ms                                                            | 8.15 ms: 1.26x slower                                              |
| Geometric mean         | (ref)                                                              | 1.23x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 19.8 ms: 1.07x faster                                              |
| genshi_xml      | 46.3 ms                                                            | 45.2 ms: 1.02x faster                                              |
| django_template | 28.8 ms                                                            | 31.8 ms: 1.10x slower                                              |
| mako            | 8.30 ms                                                            | 11.4 ms: 1.37x slower                                              |
| Geometric mean  | (ref)                                                              | 1.08x slower                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_counter_optimized    | 19.7 ms                                                            | 5.08 ms: 3.88x faster                                              |
| thread_mandelbrot_optimized | 189 ms                                                             | 52.8 ms: 3.58x faster                                              |
| thread_mandelbrot_naive     | 190 ms                                                             | 53.2 ms: 3.57x faster                                              |
| thread_pipeline_optimized   | 22.8 ms                                                            | 6.54 ms: 3.48x faster                                              |
| thread_accumulate_optimized | 35.3 ms                                                            | 10.4 ms: 3.40x faster                                              |
| thread_montecarlo_optimized | 14.2 ms                                                            | 4.60 ms: 3.09x faster                                              |
| thread_memo_optimized       | 16.8 ms                                                            | 5.51 ms: 3.05x faster                                              |
| thread_accumulate_naive     | 36.5 ms                                                            | 13.1 ms: 2.79x faster                                              |
| thread_pipeline_naive       | 49.8 ms                                                            | 26.1 ms: 1.91x faster                                              |
| thread_memo_naive           | 37.9 ms                                                            | 23.5 ms: 1.61x faster                                              |
| thread_counter_naive        | 23.7 ms                                                            | 20.3 ms: 1.17x faster                                              |
| thread_montecarlo_naive     | 18.1 ms                                                            | 25.4 ms: 1.40x slower                                              |
| Geometric mean              | (ref)                                                              | 2.42x faster                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.07 ms: 7.03x faster                                              |
| thread_counter_optimized         | 19.7 ms                                                            | 5.08 ms: 3.88x faster                                              |
| thread_mandelbrot_optimized      | 189 ms                                                             | 52.8 ms: 3.58x faster                                              |
| thread_mandelbrot_naive          | 190 ms                                                             | 53.2 ms: 3.57x faster                                              |
| thread_pipeline_optimized        | 22.8 ms                                                            | 6.54 ms: 3.48x faster                                              |
| base16_small                     | 836 us                                                             | 245 us: 3.41x faster                                               |
| thread_accumulate_optimized      | 35.3 ms                                                            | 10.4 ms: 3.40x faster                                              |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 4.60 ms: 3.09x faster                                              |
| thread_memo_optimized            | 16.8 ms                                                            | 5.51 ms: 3.05x faster                                              |
| thread_accumulate_naive          | 36.5 ms                                                            | 13.1 ms: 2.79x faster                                              |
| gc_traversal                     | 3.20 ms                                                            | 1.59 ms: 2.01x faster                                              |
| mdp                              | 2.05 sec                                                           | 1.03 sec: 1.99x faster                                             |
| async_tree_io_tg                 | 781 ms                                                             | 396 ms: 1.97x faster                                               |
| thread_pipeline_naive            | 49.8 ms                                                            | 26.1 ms: 1.91x faster                                              |
| async_tree_memoization_tg        | 421 ms                                                             | 222 ms: 1.89x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 389 ms: 1.88x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 166 ms: 1.75x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 436 ms: 1.73x faster                                               |
| async_tree_io                    | 743 ms                                                             | 432 ms: 1.72x faster                                               |
| thread_memo_naive                | 37.9 ms                                                            | 23.5 ms: 1.61x faster                                              |
| async_tree_none                  | 312 ms                                                             | 205 ms: 1.52x faster                                               |
| async_tree_memoization           | 392 ms                                                             | 258 ms: 1.52x faster                                               |
| create_gc_cycles                 | 1.77 ms                                                            | 1.26 ms: 1.40x faster                                              |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 364 ms: 1.39x faster                                               |
| go                               | 129 ms                                                             | 99.9 ms: 1.29x faster                                              |
| xml_etree_iterparse              | 86.8 ms                                                            | 69.5 ms: 1.25x faster                                              |
| deepcopy_memo                    | 27.8 us                                                            | 22.5 us: 1.24x faster                                              |
| deepcopy                         | 267 us                                                             | 217 us: 1.23x faster                                               |
| coroutines                       | 18.2 ms                                                            | 14.9 ms: 1.23x faster                                              |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 403 ms: 1.23x faster                                               |
| async_tree_eager_memoization     | 221 ms                                                             | 180 ms: 1.23x faster                                               |
| scimark_sor                      | 96.2 ms                                                            | 80.3 ms: 1.20x faster                                              |
| regex_effbot                     | 2.33 ms                                                            | 1.96 ms: 1.19x faster                                              |
| thread_counter_naive             | 23.7 ms                                                            | 20.3 ms: 1.17x faster                                              |
| tomli_loads                      | 1.77 sec                                                           | 1.53 sec: 1.16x faster                                             |
| float                            | 59.2 ms                                                            | 51.3 ms: 1.15x faster                                              |
| fastapi_http                     | 215 ms                                                             | 190 ms: 1.13x faster                                               |
| html5lib                         | 50.9 ms                                                            | 44.9 ms: 1.13x faster                                              |
| pyflate                          | 374 ms                                                             | 335 ms: 1.12x faster                                               |
| ascii85_small                    | 15.7 ms                                                            | 14.3 ms: 1.10x faster                                              |
| ascii85_large                    | 824 ms                                                             | 751 ms: 1.10x faster                                               |
| asyncio_websockets               | 313 ms                                                             | 289 ms: 1.08x faster                                               |
| deepcopy_reduce                  | 2.36 us                                                            | 2.20 us: 1.07x faster                                              |
| genshi_text                      | 21.1 ms                                                            | 19.8 ms: 1.07x faster                                              |
| base32_large                     | 325 ms                                                             | 305 ms: 1.07x faster                                               |
| pycparser                        | 901 ms                                                             | 846 ms: 1.07x faster                                               |
| base32_small                     | 6.46 ms                                                            | 6.06 ms: 1.07x faster                                              |
| regex_dna                        | 159 ms                                                             | 149 ms: 1.07x faster                                               |
| xml_etree_parse                  | 121 ms                                                             | 113 ms: 1.06x faster                                               |
| regex_v8                         | 15.0 ms                                                            | 14.1 ms: 1.06x faster                                              |
| tornado_http                     | 98.9 ms                                                            | 93.0 ms: 1.06x faster                                              |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.18 sec: 1.06x faster                                             |
| noop                             | 21.4 ns                                                            | 20.2 ns: 1.06x faster                                              |
| xml_etree_generate               | 70.6 ms                                                            | 67.5 ms: 1.05x faster                                              |
| unpickle_list                    | 3.42 us                                                            | 3.30 us: 1.04x faster                                              |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 332 ms: 1.03x faster                                               |
| unpickle                         | 10.8 us                                                            | 10.5 us: 1.03x faster                                              |
| genshi_xml                       | 46.3 ms                                                            | 45.2 ms: 1.02x faster                                              |
| base85_large                     | 267 ms                                                             | 261 ms: 1.02x faster                                               |
| json                             | 3.50 ms                                                            | 3.42 ms: 1.02x faster                                              |
| richards                         | 38.2 ms                                                            | 37.3 ms: 1.02x faster                                              |
| thrift                           | 2.07 ms                                                            | 2.03 ms: 1.02x faster                                              |
| richards_super                   | 43.8 ms                                                            | 42.9 ms: 1.02x faster                                              |
| xml_etree_process                | 49.9 ms                                                            | 48.8 ms: 1.02x faster                                              |
| networkx_k_core                  | 2.16 sec                                                           | 2.13 sec: 1.01x faster                                             |
| quadtree_nbody                   | 675 ms                                                             | 666 ms: 1.01x faster                                               |
| base64_small                     | 222 us                                                             | 220 us: 1.01x faster                                               |
| async_generators                 | 251 ms                                                             | 249 ms: 1.01x faster                                               |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 41.8 ms: 1.01x faster                                              |
| pidigits                         | 216 ms                                                             | 214 ms: 1.01x faster                                               |
| base64_large                     | 5.69 ms                                                            | 5.68 ms: 1.00x faster                                              |
| urlsafe_base64_small             | 328 us                                                             | 332 us: 1.01x slower                                               |
| chameleon                        | 11.1 ms                                                            | 11.3 ms: 1.02x slower                                              |
| pickle_pure_python               | 245 us                                                             | 249 us: 1.02x slower                                               |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 85.4 ms: 1.02x slower                                              |
| scimark_fft                      | 216 ms                                                             | 221 ms: 1.02x slower                                               |
| networkx_connected_components    | 443 ms                                                             | 452 ms: 1.02x slower                                               |
| logging_silent                   | 60.1 ns                                                            | 61.5 ns: 1.02x slower                                              |
| json_dumps                       | 7.26 ms                                                            | 7.45 ms: 1.03x slower                                              |
| regex_compile                    | 102 ms                                                             | 105 ms: 1.03x slower                                               |
| chaos                            | 43.6 ms                                                            | 44.9 ms: 1.03x slower                                              |
| hexiom                           | 4.75 ms                                                            | 4.90 ms: 1.03x slower                                              |
| pprint_safe_repr                 | 546 ms                                                             | 565 ms: 1.04x slower                                               |
| networkx_shortest_path           | 454 ms                                                             | 473 ms: 1.04x slower                                               |
| decimal_factorial                | 177 ms                                                             | 184 ms: 1.04x slower                                               |
| logging_simple                   | 5.06 us                                                            | 5.28 us: 1.05x slower                                              |
| json_loads                       | 18.2 us                                                            | 19.2 us: 1.05x slower                                              |
| pprint_pformat                   | 1.13 sec                                                           | 1.19 sec: 1.06x slower                                             |
| sympy_integrate                  | 15.4 ms                                                            | 16.3 ms: 1.06x slower                                              |
| decimal_pi                       | 228 ms                                                             | 243 ms: 1.06x slower                                               |
| logging_format                   | 5.62 us                                                            | 5.98 us: 1.06x slower                                              |
| docutils                         | 1.89 sec                                                           | 2.01 sec: 1.06x slower                                             |
| mypy2                            | 741 ms                                                             | 791 ms: 1.07x slower                                               |
| deltablue                        | 2.59 ms                                                            | 2.77 ms: 1.07x slower                                              |
| pickle_dict                      | 19.0 us                                                            | 20.4 us: 1.07x slower                                              |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.31 ms: 1.07x slower                                              |
| generators                       | 22.2 ms                                                            | 23.8 ms: 1.07x slower                                              |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.38 sec: 1.08x slower                                             |
| comprehensions                   | 11.4 us                                                            | 12.4 us: 1.08x slower                                              |
| sympy_sum                        | 104 ms                                                             | 113 ms: 1.08x slower                                               |
| pickle                           | 7.21 us                                                            | 7.80 us: 1.08x slower                                              |
| telco                            | 5.37 ms                                                            | 5.81 ms: 1.08x slower                                              |
| nqueens                          | 58.3 ms                                                            | 63.9 ms: 1.10x slower                                              |
| nbody                            | 75.8 ms                                                            | 83.1 ms: 1.10x slower                                              |
| sqlglot_v2_parse                 | 979 us                                                             | 1.08 ms: 1.10x slower                                              |
| django_template                  | 28.8 ms                                                            | 31.8 ms: 1.10x slower                                              |
| sympy_str                        | 193 ms                                                             | 213 ms: 1.10x slower                                               |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.3 ms: 1.10x slower                                              |
| async_tree_eager                 | 88.3 ms                                                            | 97.6 ms: 1.11x slower                                              |
| raytrace                         | 197 ms                                                             | 218 ms: 1.11x slower                                               |
| pickle_list                      | 2.66 us                                                            | 2.95 us: 1.11x slower                                              |
| crypto_pyaes                     | 55.6 ms                                                            | 62.4 ms: 1.12x slower                                              |
| sympy_expand                     | 331 ms                                                             | 375 ms: 1.13x slower                                               |
| meteor_contest                   | 85.7 ms                                                            | 97.7 ms: 1.14x slower                                              |
| asyncio_tcp                      | 316 ms                                                             | 362 ms: 1.15x slower                                               |
| scimark_lu                       | 70.2 ms                                                            | 81.2 ms: 1.16x slower                                              |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 350 ms: 1.16x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 207 ms: 1.18x slower                                               |
| typing_runtime_protocols         | 112 us                                                             | 136 us: 1.21x slower                                               |
| python_startup                   | 9.51 ms                                                            | 11.5 ms: 1.21x slower                                              |
| python_startup_no_site           | 6.49 ms                                                            | 8.15 ms: 1.26x slower                                              |
| coverage                         | 55.0 ms                                                            | 71.1 ms: 1.29x slower                                              |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 3.81 ms: 1.33x slower                                              |
| unpack_sequence                  | 26.4 ns                                                            | 36.0 ns: 1.36x slower                                              |
| mako                             | 8.30 ms                                                            | 11.4 ms: 1.37x slower                                              |
| thread_montecarlo_naive          | 18.1 ms                                                            | 25.4 ms: 1.40x slower                                              |
| argparse_subparsers              | 449 us                                                             | 712 us: 1.58x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 148 ms: 2.60x slower                                               |
| argparse_many_optionals          | 12.9 ms                                                            | 36.6 ms: 2.83x slower                                              |
| Geometric mean                   | (ref)                                                              | 1.13x faster                                                       |

Benchmark hidden because not significant (8): pylint, fannkuch, pathlib, unpickle_pure_python, spectral_norm, scimark_monte_carlo, base85_small, xdsl_constant_fold

- Geometric mean (including insignificant results): 1.128x faster

# HPT report

- Reliability score: 98.10% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.58x