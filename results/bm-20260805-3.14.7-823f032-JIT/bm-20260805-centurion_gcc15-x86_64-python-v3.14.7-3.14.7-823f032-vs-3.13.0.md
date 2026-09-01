# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.071x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.02x faster
- Memory change: 1.09x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 10.8 ms: 1.01x faster                                            |
| docutils       | 1.98 sec                                                         | 1.99 sec: 1.01x slower                                           |
| fastapi_http   | 215 ms                                                           | 205 ms: 1.05x faster                                             |
| html5lib       | 49.1 ms                                                          | 45.2 ms: 1.09x faster                                            |
| tornado_http   | 99.2 ms                                                          | 101 ms: 1.01x slower                                             |
| Geometric mean | (ref)                                                            | 1.02x faster                                                     |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_memoization_tg        | 417 ms                                                           | 336 ms: 1.24x faster                                             |
| async_tree_memoization           | 389 ms                                                           | 321 ms: 1.21x faster                                             |
| async_tree_none                  | 310 ms                                                           | 255 ms: 1.21x faster                                             |
| coroutines                       | 17.6 ms                                                          | 14.8 ms: 1.19x faster                                            |
| async_tree_eager_io              | 749 ms                                                           | 638 ms: 1.17x faster                                             |
| async_tree_io_tg                 | 777 ms                                                           | 681 ms: 1.14x faster                                             |
| async_tree_eager_memoization     | 215 ms                                                           | 189 ms: 1.14x faster                                             |
| async_tree_io                    | 741 ms                                                           | 665 ms: 1.11x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 464 ms: 1.11x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 476 ms: 1.11x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 263 ms: 1.10x faster                                             |
| async_tree_eager_io_tg           | 724 ms                                                           | 662 ms: 1.09x faster                                             |
| asyncio_tcp                      | 326 ms                                                           | 304 ms: 1.07x faster                                             |
| async_tree_eager                 | 90.0 ms                                                          | 84.4 ms: 1.07x faster                                            |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 340 ms: 1.06x faster                                             |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.29 sec: 1.00x faster                                           |
| async_generators                 | 262 ms                                                           | 264 ms: 1.01x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 419 ms: 1.30x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 278 ms: 1.61x slower                                             |
| async_tree_eager_tg              | 58.6 ms                                                          | 206 ms: 3.52x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.01x slower                                                     |

Benchmark hidden because not significant (1): asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 15.7 ns: 1.30x faster                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 198 ms: 1.06x faster                                             |
| decimal_factorial | 173 ms                                                           | 170 ms: 1.02x faster                                             |
| Geometric mean    | (ref)                                                            | 1.04x faster                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 42.2 ms: 1.34x faster                                            |
| quadtree_nbody | 620 ms                                                           | 557 ms: 1.11x faster                                             |
| nbody          | 66.8 ms                                                          | 62.7 ms: 1.07x faster                                            |
| Geometric mean | (ref)                                                            | 1.12x faster                                                     |

Benchmark hidden because not significant (1): pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.77 ms: 1.12x faster                                            |
| regex_compile  | 97.7 ms                                                          | 92.1 ms: 1.06x faster                                            |
| regex_dna      | 144 ms                                                           | 139 ms: 1.03x faster                                             |
| regex_v8       | 14.7 ms                                                          | 15.4 ms: 1.05x slower                                            |
| Geometric mean | (ref)                                                            | 1.04x faster                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 7.44 ms: 4.24x faster                                            |
| base16_small         | 656 us                                                           | 334 us: 1.97x faster                                             |
| ascii85_small        | 15.5 ms                                                          | 11.6 ms: 1.34x faster                                            |
| ascii85_large        | 814 ms                                                           | 647 ms: 1.26x faster                                             |
| base64_large         | 6.32 ms                                                          | 5.04 ms: 1.25x faster                                            |
| tomli_loads          | 1.63 sec                                                         | 1.34 sec: 1.21x faster                                           |
| unpickle_pure_python | 149 us                                                           | 131 us: 1.13x faster                                             |
| base85_large         | 243 ms                                                           | 220 ms: 1.11x faster                                             |
| base64_small         | 228 us                                                           | 213 us: 1.07x faster                                             |
| base85_small         | 4.41 ms                                                          | 4.17 ms: 1.06x faster                                            |
| urlsafe_base64_small | 379 us                                                           | 358 us: 1.06x faster                                             |
| xml_etree_process    | 48.1 ms                                                          | 46.7 ms: 1.03x faster                                            |
| pickle_dict          | 21.9 us                                                          | 21.2 us: 1.03x faster                                            |
| base32_large         | 286 ms                                                           | 278 ms: 1.03x faster                                             |
| base32_small         | 5.69 ms                                                          | 5.56 ms: 1.02x faster                                            |
| xml_etree_generate   | 66.3 ms                                                          | 65.0 ms: 1.02x faster                                            |
| unpickle             | 10.3 us                                                          | 10.5 us: 1.02x slower                                            |
| pickle_pure_python   | 223 us                                                           | 234 us: 1.05x slower                                             |
| unpickle_list        | 3.45 us                                                          | 3.66 us: 1.06x slower                                            |
| xml_etree_iterparse  | 69.6 ms                                                          | 74.1 ms: 1.06x slower                                            |
| json_loads           | 16.7 us                                                          | 18.8 us: 1.13x slower                                            |
| pickle               | 8.22 us                                                          | 9.29 us: 1.13x slower                                            |
| pickle_list          | 3.03 us                                                          | 3.87 us: 1.28x slower                                            |
| Geometric mean       | (ref)                                                            | 1.12x faster                                                     |

Benchmark hidden because not significant (2): json_dumps, xml_etree_parse

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 6.35 ms: 1.00x faster                                            |
| python_startup         | 9.38 ms                                                          | 9.77 ms: 1.04x slower                                            |
| Geometric mean         | (ref)                                                            | 1.02x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| genshi_text     | 17.6 ms                                                          | 16.2 ms: 1.09x faster                                            |
| genshi_xml      | 39.7 ms                                                          | 39.2 ms: 1.01x faster                                            |
| django_template | 27.3 ms                                                          | 28.5 ms: 1.05x slower                                            |
| Geometric mean  | (ref)                                                            | 1.01x faster                                                     |

Benchmark hidden because not significant (1): mako

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 11.0 ms: 3.56x faster                                            |
| thread_pipeline_naive       | 52.1 ms                                                          | 34.6 ms: 1.50x faster                                            |
| thread_counter_naive        | 22.6 ms                                                          | 20.3 ms: 1.11x faster                                            |
| thread_counter_optimized    | 18.7 ms                                                          | 17.5 ms: 1.07x faster                                            |
| thread_memo_optimized       | 18.2 ms                                                          | 17.1 ms: 1.06x faster                                            |
| thread_mandelbrot_naive     | 220 ms                                                           | 208 ms: 1.06x faster                                             |
| thread_mandelbrot_optimized | 218 ms                                                           | 209 ms: 1.04x faster                                             |
| thread_pipeline_optimized   | 25.6 ms                                                          | 25.0 ms: 1.02x faster                                            |
| thread_accumulate_naive     | 40.9 ms                                                          | 40.1 ms: 1.02x faster                                            |
| thread_accumulate_optimized | 39.8 ms                                                          | 39.2 ms: 1.01x faster                                            |
| thread_montecarlo_optimized | 13.3 ms                                                          | 13.5 ms: 1.02x slower                                            |
| thread_montecarlo_naive     | 17.8 ms                                                          | 18.2 ms: 1.02x slower                                            |
| Geometric mean              | (ref)                                                            | 1.18x faster                                                     |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 7.44 ms: 4.24x faster                                            |
| thread_memo_naive                | 39.0 ms                                                          | 11.0 ms: 3.56x faster                                            |
| mdp                              | 2.11 sec                                                         | 931 ms: 2.27x faster                                             |
| base16_small                     | 656 us                                                           | 334 us: 1.97x faster                                             |
| argparse_many_optionals          | 12.6 ms                                                          | 7.47 ms: 1.68x faster                                            |
| thread_pipeline_naive            | 52.1 ms                                                          | 34.6 ms: 1.50x faster                                            |
| deepcopy_memo                    | 26.6 us                                                          | 18.1 us: 1.47x faster                                            |
| deepcopy                         | 267 us                                                           | 189 us: 1.41x faster                                             |
| scimark_sor                      | 97.0 ms                                                          | 70.4 ms: 1.38x faster                                            |
| float                            | 56.6 ms                                                          | 42.2 ms: 1.34x faster                                            |
| ascii85_small                    | 15.5 ms                                                          | 11.6 ms: 1.34x faster                                            |
| richards                         | 36.8 ms                                                          | 27.7 ms: 1.33x faster                                            |
| noop                             | 20.4 ns                                                          | 15.7 ns: 1.30x faster                                            |
| richards_super                   | 41.3 ms                                                          | 32.0 ms: 1.29x faster                                            |
| deltablue                        | 2.52 ms                                                          | 1.97 ms: 1.28x faster                                            |
| ascii85_large                    | 814 ms                                                           | 647 ms: 1.26x faster                                             |
| go                               | 121 ms                                                           | 96.6 ms: 1.25x faster                                            |
| base64_large                     | 6.32 ms                                                          | 5.04 ms: 1.25x faster                                            |
| scimark_fft                      | 211 ms                                                           | 168 ms: 1.25x faster                                             |
| async_tree_memoization_tg        | 417 ms                                                           | 336 ms: 1.24x faster                                             |
| deepcopy_reduce                  | 2.37 us                                                          | 1.93 us: 1.23x faster                                            |
| tomli_loads                      | 1.63 sec                                                         | 1.34 sec: 1.21x faster                                           |
| async_tree_memoization           | 389 ms                                                           | 321 ms: 1.21x faster                                             |
| async_tree_none                  | 310 ms                                                           | 255 ms: 1.21x faster                                             |
| pyflate                          | 358 ms                                                           | 298 ms: 1.20x faster                                             |
| coroutines                       | 17.6 ms                                                          | 14.8 ms: 1.19x faster                                            |
| scimark_monte_carlo              | 44.3 ms                                                          | 37.7 ms: 1.18x faster                                            |
| async_tree_eager_io              | 749 ms                                                           | 638 ms: 1.17x faster                                             |
| fannkuch                         | 265 ms                                                           | 227 ms: 1.17x faster                                             |
| spectral_norm                    | 64.1 ms                                                          | 55.5 ms: 1.15x faster                                            |
| async_tree_io_tg                 | 777 ms                                                           | 681 ms: 1.14x faster                                             |
| async_tree_eager_memoization     | 215 ms                                                           | 189 ms: 1.14x faster                                             |
| unpickle_pure_python             | 149 us                                                           | 131 us: 1.13x faster                                             |
| regex_effbot                     | 1.99 ms                                                          | 1.77 ms: 1.12x faster                                            |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.05 sec: 1.11x faster                                           |
| thread_counter_naive             | 22.6 ms                                                          | 20.3 ms: 1.11x faster                                            |
| async_tree_io                    | 741 ms                                                           | 665 ms: 1.11x faster                                             |
| quadtree_nbody                   | 620 ms                                                           | 557 ms: 1.11x faster                                             |
| thrift                           | 2.07 ms                                                          | 1.86 ms: 1.11x faster                                            |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 464 ms: 1.11x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 476 ms: 1.11x faster                                             |
| base85_large                     | 243 ms                                                           | 220 ms: 1.11x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 263 ms: 1.10x faster                                             |
| chaos                            | 45.0 ms                                                          | 41.1 ms: 1.10x faster                                            |
| async_tree_eager_io_tg           | 724 ms                                                           | 662 ms: 1.09x faster                                             |
| generators                       | 22.0 ms                                                          | 20.2 ms: 1.09x faster                                            |
| genshi_text                      | 17.6 ms                                                          | 16.2 ms: 1.09x faster                                            |
| html5lib                         | 49.1 ms                                                          | 45.2 ms: 1.09x faster                                            |
| networkx_connected_components    | 460 ms                                                           | 427 ms: 1.08x faster                                             |
| base64_small                     | 228 us                                                           | 213 us: 1.07x faster                                             |
| asyncio_tcp                      | 326 ms                                                           | 304 ms: 1.07x faster                                             |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.48 ms: 1.07x faster                                            |
| networkx_shortest_path           | 464 ms                                                           | 433 ms: 1.07x faster                                             |
| thread_counter_optimized         | 18.7 ms                                                          | 17.5 ms: 1.07x faster                                            |
| async_tree_eager                 | 90.0 ms                                                          | 84.4 ms: 1.07x faster                                            |
| nbody                            | 66.8 ms                                                          | 62.7 ms: 1.07x faster                                            |
| thread_memo_optimized            | 18.2 ms                                                          | 17.1 ms: 1.06x faster                                            |
| regex_compile                    | 97.7 ms                                                          | 92.1 ms: 1.06x faster                                            |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 340 ms: 1.06x faster                                             |
| scimark_lu                       | 70.2 ms                                                          | 66.3 ms: 1.06x faster                                            |
| decimal_pi                       | 210 ms                                                           | 198 ms: 1.06x faster                                             |
| thread_mandelbrot_naive          | 220 ms                                                           | 208 ms: 1.06x faster                                             |
| base85_small                     | 4.41 ms                                                          | 4.17 ms: 1.06x faster                                            |
| urlsafe_base64_small             | 379 us                                                           | 358 us: 1.06x faster                                             |
| meteor_contest                   | 89.9 ms                                                          | 85.8 ms: 1.05x faster                                            |
| nqueens                          | 57.3 ms                                                          | 54.7 ms: 1.05x faster                                            |
| fastapi_http                     | 215 ms                                                           | 205 ms: 1.05x faster                                             |
| thread_mandelbrot_optimized      | 218 ms                                                           | 209 ms: 1.04x faster                                             |
| sympy_integrate                  | 15.4 ms                                                          | 14.9 ms: 1.03x faster                                            |
| xml_etree_process                | 48.1 ms                                                          | 46.7 ms: 1.03x faster                                            |
| pickle_dict                      | 21.9 us                                                          | 21.2 us: 1.03x faster                                            |
| regex_dna                        | 144 ms                                                           | 139 ms: 1.03x faster                                             |
| telco                            | 5.50 ms                                                          | 5.35 ms: 1.03x faster                                            |
| base32_large                     | 286 ms                                                           | 278 ms: 1.03x faster                                             |
| networkx_k_core                  | 2.15 sec                                                         | 2.10 sec: 1.02x faster                                           |
| base32_small                     | 5.69 ms                                                          | 5.56 ms: 1.02x faster                                            |
| thread_pipeline_optimized        | 25.6 ms                                                          | 25.0 ms: 1.02x faster                                            |
| sqlglot_v2_parse                 | 953 us                                                           | 933 us: 1.02x faster                                             |
| thread_accumulate_naive          | 40.9 ms                                                          | 40.1 ms: 1.02x faster                                            |
| xml_etree_generate               | 66.3 ms                                                          | 65.0 ms: 1.02x faster                                            |
| raytrace                         | 199 ms                                                           | 195 ms: 1.02x faster                                             |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 39.4 ms: 1.02x faster                                            |
| gc_traversal                     | 3.16 ms                                                          | 3.11 ms: 1.02x faster                                            |
| logging_format                   | 5.23 us                                                          | 5.15 us: 1.02x faster                                            |
| decimal_factorial                | 173 ms                                                           | 170 ms: 1.02x faster                                             |
| logging_simple                   | 4.60 us                                                          | 4.53 us: 1.02x faster                                            |
| thread_accumulate_optimized      | 39.8 ms                                                          | 39.2 ms: 1.01x faster                                            |
| genshi_xml                       | 39.7 ms                                                          | 39.2 ms: 1.01x faster                                            |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.18 ms: 1.01x faster                                            |
| chameleon                        | 10.9 ms                                                          | 10.8 ms: 1.01x faster                                            |
| logging_silent                   | 60.6 ns                                                          | 60.1 ns: 1.01x faster                                            |
| hexiom                           | 4.42 ms                                                          | 4.40 ms: 1.00x faster                                            |
| sympy_str                        | 193 ms                                                           | 192 ms: 1.00x faster                                             |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 78.8 ms: 1.00x faster                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.29 sec: 1.00x faster                                           |
| python_startup_no_site           | 6.36 ms                                                          | 6.35 ms: 1.00x faster                                            |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.00x slower                                             |
| docutils                         | 1.98 sec                                                         | 1.99 sec: 1.01x slower                                           |
| async_generators                 | 262 ms                                                           | 264 ms: 1.01x slower                                             |
| tornado_http                     | 99.2 ms                                                          | 101 ms: 1.01x slower                                             |
| pathlib                          | 12.4 ms                                                          | 12.6 ms: 1.01x slower                                            |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 13.5 ms: 1.02x slower                                            |
| json                             | 3.49 ms                                                          | 3.56 ms: 1.02x slower                                            |
| thread_montecarlo_naive          | 17.8 ms                                                          | 18.2 ms: 1.02x slower                                            |
| sympy_expand                     | 330 ms                                                           | 338 ms: 1.02x slower                                             |
| unpickle                         | 10.3 us                                                          | 10.5 us: 1.02x slower                                            |
| typing_runtime_protocols         | 106 us                                                           | 109 us: 1.03x slower                                             |
| coverage                         | 52.2 ms                                                          | 53.9 ms: 1.03x slower                                            |
| comprehensions                   | 11.6 us                                                          | 12.0 us: 1.04x slower                                            |
| python_startup                   | 9.38 ms                                                          | 9.77 ms: 1.04x slower                                            |
| django_template                  | 27.3 ms                                                          | 28.5 ms: 1.05x slower                                            |
| pickle_pure_python               | 223 us                                                           | 234 us: 1.05x slower                                             |
| regex_v8                         | 14.7 ms                                                          | 15.4 ms: 1.05x slower                                            |
| unpickle_list                    | 3.45 us                                                          | 3.66 us: 1.06x slower                                            |
| xml_etree_iterparse              | 69.6 ms                                                          | 74.1 ms: 1.06x slower                                            |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.7 ms: 1.06x slower                                            |
| create_gc_cycles                 | 1.70 ms                                                          | 1.82 ms: 1.07x slower                                            |
| crypto_pyaes                     | 50.0 ms                                                          | 54.4 ms: 1.09x slower                                            |
| json_loads                       | 16.7 us                                                          | 18.8 us: 1.13x slower                                            |
| pickle                           | 8.22 us                                                          | 9.29 us: 1.13x slower                                            |
| argparse_subparsers              | 446 us                                                           | 505 us: 1.13x slower                                             |
| pprint_safe_repr                 | 541 ms                                                           | 620 ms: 1.15x slower                                             |
| pprint_pformat                   | 1.11 sec                                                         | 1.27 sec: 1.15x slower                                           |
| pickle_list                      | 3.03 us                                                          | 3.87 us: 1.28x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 419 ms: 1.30x slower                                             |
| mypy2                            | 726 ms                                                           | 1.04 sec: 1.43x slower                                           |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 278 ms: 1.61x slower                                             |
| async_tree_eager_tg              | 58.6 ms                                                          | 206 ms: 3.52x slower                                             |
| unpack_sequence                  | 26.2 ns                                                          | 102 ns: 3.88x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.07x faster                                                     |

Benchmark hidden because not significant (8): xdsl_constant_fold, json_dumps, xml_etree_parse, pidigits, mako, asyncio_websockets, pylint, pycparser

- Geometric mean (including insignificant results): 1.071x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.04x
- 95% likely to have a speedup of 1.03x
- 99% likely to have a speedup of 1.02x

# Memory
- memory change: 1.09x