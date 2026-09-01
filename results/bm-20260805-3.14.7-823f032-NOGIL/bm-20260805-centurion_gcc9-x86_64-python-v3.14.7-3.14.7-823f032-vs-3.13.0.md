# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.067x faster
- HPT reliability: 78.16%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.57x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 11.4 ms: 1.15x slower                                           |
| docutils       | 1.89 sec                                                        | 2.05 sec: 1.08x slower                                          |
| fastapi_http   | 218 ms                                                          | 191 ms: 1.14x faster                                            |
| html5lib       | 51.7 ms                                                         | 47.9 ms: 1.08x faster                                           |
| tornado_http   | 101 ms                                                          | 96.9 ms: 1.04x faster                                           |
| Geometric mean | (ref)                                                           | 1.01x faster                                                    |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_io_tg                 | 778 ms                                                          | 482 ms: 1.61x faster                                            |
| async_tree_memoization_tg        | 419 ms                                                          | 277 ms: 1.51x faster                                            |
| async_tree_eager_io_tg           | 728 ms                                                          | 484 ms: 1.50x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 507 ms: 1.48x faster                                            |
| async_tree_io                    | 741 ms                                                          | 528 ms: 1.40x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 215 ms: 1.35x faster                                            |
| async_tree_none                  | 308 ms                                                          | 240 ms: 1.28x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 306 ms: 1.27x faster                                            |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 402 ms: 1.22x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 195 ms: 1.12x faster                                            |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 431 ms: 1.10x faster                                            |
| asyncio_tcp                      | 318 ms                                                          | 305 ms: 1.04x faster                                            |
| asyncio_websockets               | 303 ms                                                          | 295 ms: 1.03x faster                                            |
| coroutines                       | 15.4 ms                                                         | 15.1 ms: 1.02x faster                                           |
| async_generators                 | 240 ms                                                          | 256 ms: 1.07x slower                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.39 sec: 1.08x slower                                          |
| async_tree_eager                 | 89.6 ms                                                         | 100 ms: 1.12x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 382 ms: 1.34x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 264 ms: 1.51x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 191 ms: 3.26x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.06x faster                                                    |

Benchmark hidden because not significant (1): async_tree_eager_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 21.6 ns: 1.05x slower                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                          | 191 ms: 1.08x slower                                            |
| decimal_pi        | 222 ms                                                          | 249 ms: 1.12x slower                                            |
| Geometric mean    | (ref)                                                           | 1.10x slower                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 53.7 ms: 1.06x faster                                           |
| pidigits       | 189 ms                                                          | 186 ms: 1.01x faster                                            |
| quadtree_nbody | 626 ms                                                          | 658 ms: 1.05x slower                                            |
| nbody          | 65.9 ms                                                         | 81.8 ms: 1.24x slower                                           |
| Geometric mean | (ref)                                                           | 1.05x slower                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 2.00 ms: 1.15x faster                                           |
| regex_dna      | 162 ms                                                          | 151 ms: 1.07x faster                                            |
| regex_v8       | 15.2 ms                                                         | 14.4 ms: 1.06x faster                                           |
| regex_compile  | 98.5 ms                                                         | 104 ms: 1.06x slower                                            |
| Geometric mean | (ref)                                                           | 1.05x faster                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 4.97 ms: 7.44x faster                                           |
| base16_small         | 740 us                                                          | 295 us: 2.51x faster                                            |
| xml_etree_iterparse  | 79.9 ms                                                         | 67.8 ms: 1.18x faster                                           |
| tomli_loads          | 1.62 sec                                                        | 1.55 sec: 1.04x faster                                          |
| xml_etree_parse      | 104 ms                                                          | 101 ms: 1.03x faster                                            |
| base64_large         | 3.33 ms                                                         | 3.37 ms: 1.01x slower                                           |
| pickle_dict          | 22.0 us                                                         | 22.4 us: 1.02x slower                                           |
| urlsafe_base64_small | 325 us                                                          | 335 us: 1.03x slower                                            |
| ascii85_large        | 717 ms                                                          | 743 ms: 1.04x slower                                            |
| ascii85_small        | 13.6 ms                                                         | 14.2 ms: 1.04x slower                                           |
| base85_large         | 252 ms                                                          | 265 ms: 1.05x slower                                            |
| xml_etree_generate   | 64.2 ms                                                         | 67.7 ms: 1.06x slower                                           |
| xml_etree_process    | 46.6 ms                                                         | 49.3 ms: 1.06x slower                                           |
| unpickle_pure_python | 151 us                                                          | 159 us: 1.06x slower                                            |
| base85_small         | 4.59 ms                                                         | 4.92 ms: 1.07x slower                                           |
| base32_large         | 296 ms                                                          | 321 ms: 1.09x slower                                            |
| base32_small         | 5.79 ms                                                         | 6.39 ms: 1.10x slower                                           |
| pickle_pure_python   | 223 us                                                          | 253 us: 1.13x slower                                            |
| json_dumps           | 6.95 ms                                                         | 7.98 ms: 1.15x slower                                           |
| pickle               | 7.44 us                                                         | 8.55 us: 1.15x slower                                           |
| unpickle             | 10.5 us                                                         | 12.2 us: 1.16x slower                                           |
| unpickle_list        | 3.33 us                                                         | 3.90 us: 1.17x slower                                           |
| pickle_list          | 3.14 us                                                         | 4.01 us: 1.28x slower                                           |
| json_loads           | 16.2 us                                                         | 25.0 us: 1.54x slower                                           |
| Geometric mean       | (ref)                                                           | 1.05x faster                                                    |

Benchmark hidden because not significant (1): base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                         | 11.9 ms: 1.25x slower                                           |
| python_startup_no_site | 6.46 ms                                                         | 8.35 ms: 1.29x slower                                           |
| Geometric mean         | (ref)                                                           | 1.27x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| genshi_xml      | 41.3 ms                                                         | 44.5 ms: 1.08x slower                                           |
| genshi_text     | 17.8 ms                                                         | 19.6 ms: 1.10x slower                                           |
| django_template | 27.6 ms                                                         | 30.6 ms: 1.11x slower                                           |
| mako            | 7.16 ms                                                         | 11.0 ms: 1.53x slower                                           |
| Geometric mean  | (ref)                                                           | 1.19x slower                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_mandelbrot_naive     | 210 ms                                                          | 61.7 ms: 3.41x faster                                           |
| thread_counter_optimized    | 16.5 ms                                                         | 4.90 ms: 3.38x faster                                           |
| thread_accumulate_optimized | 32.3 ms                                                         | 9.61 ms: 3.36x faster                                           |
| thread_pipeline_optimized   | 20.9 ms                                                         | 6.23 ms: 3.35x faster                                           |
| thread_mandelbrot_optimized | 208 ms                                                          | 63.4 ms: 3.27x faster                                           |
| thread_montecarlo_optimized | 14.5 ms                                                         | 4.80 ms: 3.02x faster                                           |
| thread_memo_optimized       | 15.3 ms                                                         | 5.42 ms: 2.82x faster                                           |
| thread_accumulate_naive     | 33.4 ms                                                         | 12.5 ms: 2.68x faster                                           |
| thread_pipeline_naive       | 47.3 ms                                                         | 27.0 ms: 1.75x faster                                           |
| thread_memo_naive           | 36.1 ms                                                         | 23.6 ms: 1.53x faster                                           |
| thread_counter_naive        | 20.6 ms                                                         | 21.1 ms: 1.02x slower                                           |
| thread_montecarlo_naive     | 19.0 ms                                                         | 29.3 ms: 1.54x slower                                           |
| Geometric mean              | (ref)                                                           | 2.25x faster                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 4.97 ms: 7.44x faster                                           |
| thread_mandelbrot_naive          | 210 ms                                                          | 61.7 ms: 3.41x faster                                           |
| thread_counter_optimized         | 16.5 ms                                                         | 4.90 ms: 3.38x faster                                           |
| thread_accumulate_optimized      | 32.3 ms                                                         | 9.61 ms: 3.36x faster                                           |
| thread_pipeline_optimized        | 20.9 ms                                                         | 6.23 ms: 3.35x faster                                           |
| thread_mandelbrot_optimized      | 208 ms                                                          | 63.4 ms: 3.27x faster                                           |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 4.80 ms: 3.02x faster                                           |
| thread_memo_optimized            | 15.3 ms                                                         | 5.42 ms: 2.82x faster                                           |
| thread_accumulate_naive          | 33.4 ms                                                         | 12.5 ms: 2.68x faster                                           |
| base16_small                     | 740 us                                                          | 295 us: 2.51x faster                                            |
| mdp                              | 2.15 sec                                                        | 1.01 sec: 2.13x faster                                          |
| gc_traversal                     | 3.07 ms                                                         | 1.68 ms: 1.82x faster                                           |
| thread_pipeline_naive            | 47.3 ms                                                         | 27.0 ms: 1.75x faster                                           |
| argparse_many_optionals          | 12.8 ms                                                         | 7.90 ms: 1.62x faster                                           |
| async_tree_io_tg                 | 778 ms                                                          | 482 ms: 1.61x faster                                            |
| thread_memo_naive                | 36.1 ms                                                         | 23.6 ms: 1.53x faster                                           |
| async_tree_memoization_tg        | 419 ms                                                          | 277 ms: 1.51x faster                                            |
| async_tree_eager_io_tg           | 728 ms                                                          | 484 ms: 1.50x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 507 ms: 1.48x faster                                            |
| async_tree_io                    | 741 ms                                                          | 528 ms: 1.40x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 215 ms: 1.35x faster                                            |
| create_gc_cycles                 | 1.75 ms                                                         | 1.34 ms: 1.31x faster                                           |
| async_tree_none                  | 308 ms                                                          | 240 ms: 1.28x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 306 ms: 1.27x faster                                            |
| go                               | 117 ms                                                          | 94.7 ms: 1.24x faster                                           |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 402 ms: 1.22x faster                                            |
| deepcopy_memo                    | 26.5 us                                                         | 21.8 us: 1.21x faster                                           |
| deepcopy                         | 269 us                                                          | 224 us: 1.20x faster                                            |
| xml_etree_iterparse              | 79.9 ms                                                         | 67.8 ms: 1.18x faster                                           |
| regex_effbot                     | 2.30 ms                                                         | 2.00 ms: 1.15x faster                                           |
| fastapi_http                     | 218 ms                                                          | 191 ms: 1.14x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 195 ms: 1.12x faster                                            |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 431 ms: 1.10x faster                                            |
| html5lib                         | 51.7 ms                                                         | 47.9 ms: 1.08x faster                                           |
| regex_dna                        | 162 ms                                                          | 151 ms: 1.07x faster                                            |
| float                            | 57.0 ms                                                         | 53.7 ms: 1.06x faster                                           |
| regex_v8                         | 15.2 ms                                                         | 14.4 ms: 1.06x faster                                           |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.15 sec: 1.05x faster                                          |
| tomli_loads                      | 1.62 sec                                                        | 1.55 sec: 1.04x faster                                          |
| tornado_http                     | 101 ms                                                          | 96.9 ms: 1.04x faster                                           |
| asyncio_tcp                      | 318 ms                                                          | 305 ms: 1.04x faster                                            |
| xml_etree_parse                  | 104 ms                                                          | 101 ms: 1.03x faster                                            |
| deepcopy_reduce                  | 2.40 us                                                         | 2.34 us: 1.03x faster                                           |
| asyncio_websockets               | 303 ms                                                          | 295 ms: 1.03x faster                                            |
| pycparser                        | 860 ms                                                          | 837 ms: 1.03x faster                                            |
| coroutines                       | 15.4 ms                                                         | 15.1 ms: 1.02x faster                                           |
| richards                         | 37.8 ms                                                         | 37.2 ms: 1.02x faster                                           |
| pidigits                         | 189 ms                                                          | 186 ms: 1.01x faster                                            |
| thrift                           | 2.02 ms                                                         | 2.00 ms: 1.01x faster                                           |
| pprint_safe_repr                 | 530 ms                                                          | 533 ms: 1.01x slower                                            |
| base64_large                     | 3.33 ms                                                         | 3.37 ms: 1.01x slower                                           |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 40.7 ms: 1.02x slower                                           |
| pickle_dict                      | 22.0 us                                                         | 22.4 us: 1.02x slower                                           |
| thread_counter_naive             | 20.6 ms                                                         | 21.1 ms: 1.02x slower                                           |
| urlsafe_base64_small             | 325 us                                                          | 335 us: 1.03x slower                                            |
| pprint_pformat                   | 1.09 sec                                                        | 1.12 sec: 1.03x slower                                          |
| ascii85_large                    | 717 ms                                                          | 743 ms: 1.04x slower                                            |
| telco                            | 5.83 ms                                                         | 6.08 ms: 1.04x slower                                           |
| ascii85_small                    | 13.6 ms                                                         | 14.2 ms: 1.04x slower                                           |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 84.0 ms: 1.04x slower                                           |
| quadtree_nbody                   | 626 ms                                                          | 658 ms: 1.05x slower                                            |
| base85_large                     | 252 ms                                                          | 265 ms: 1.05x slower                                            |
| noop                             | 20.5 ns                                                         | 21.6 ns: 1.05x slower                                           |
| xml_etree_generate               | 64.2 ms                                                         | 67.7 ms: 1.06x slower                                           |
| sympy_integrate                  | 15.8 ms                                                         | 16.7 ms: 1.06x slower                                           |
| regex_compile                    | 98.5 ms                                                         | 104 ms: 1.06x slower                                            |
| xml_etree_process                | 46.6 ms                                                         | 49.3 ms: 1.06x slower                                           |
| unpickle_pure_python             | 151 us                                                          | 159 us: 1.06x slower                                            |
| async_generators                 | 240 ms                                                          | 256 ms: 1.07x slower                                            |
| scimark_sor                      | 78.9 ms                                                         | 84.2 ms: 1.07x slower                                           |
| sympy_sum                        | 106 ms                                                          | 114 ms: 1.07x slower                                            |
| chaos                            | 45.1 ms                                                         | 48.4 ms: 1.07x slower                                           |
| base85_small                     | 4.59 ms                                                         | 4.92 ms: 1.07x slower                                           |
| scimark_fft                      | 226 ms                                                          | 243 ms: 1.08x slower                                            |
| xdsl_constant_fold               | 36.7 ms                                                         | 39.5 ms: 1.08x slower                                           |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.30 ms: 1.08x slower                                           |
| decimal_factorial                | 177 ms                                                          | 191 ms: 1.08x slower                                            |
| genshi_xml                       | 41.3 ms                                                         | 44.5 ms: 1.08x slower                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.39 sec: 1.08x slower                                          |
| sympy_str                        | 197 ms                                                          | 213 ms: 1.08x slower                                            |
| docutils                         | 1.89 sec                                                        | 2.05 sec: 1.08x slower                                          |
| hexiom                           | 4.30 ms                                                         | 4.67 ms: 1.09x slower                                           |
| base32_large                     | 296 ms                                                          | 321 ms: 1.09x slower                                            |
| sympy_expand                     | 336 ms                                                          | 367 ms: 1.09x slower                                            |
| scimark_monte_carlo              | 46.5 ms                                                         | 51.0 ms: 1.10x slower                                           |
| sqlglot_v2_parse                 | 958 us                                                          | 1.05 ms: 1.10x slower                                           |
| genshi_text                      | 17.8 ms                                                         | 19.6 ms: 1.10x slower                                           |
| base32_small                     | 5.79 ms                                                         | 6.39 ms: 1.10x slower                                           |
| django_template                  | 27.6 ms                                                         | 30.6 ms: 1.11x slower                                           |
| async_tree_eager                 | 89.6 ms                                                         | 100 ms: 1.12x slower                                            |
| decimal_pi                       | 222 ms                                                          | 249 ms: 1.12x slower                                            |
| deltablue                        | 2.41 ms                                                         | 2.71 ms: 1.13x slower                                           |
| spectral_norm                    | 65.9 ms                                                         | 74.3 ms: 1.13x slower                                           |
| scimark_lu                       | 74.5 ms                                                         | 84.5 ms: 1.13x slower                                           |
| pickle_pure_python               | 223 us                                                          | 253 us: 1.13x slower                                            |
| logging_silent                   | 61.0 ns                                                         | 69.8 ns: 1.14x slower                                           |
| chameleon                        | 9.95 ms                                                         | 11.4 ms: 1.15x slower                                           |
| json_dumps                       | 6.95 ms                                                         | 7.98 ms: 1.15x slower                                           |
| unpack_sequence                  | 27.1 ns                                                         | 31.1 ns: 1.15x slower                                           |
| pickle                           | 7.44 us                                                         | 8.55 us: 1.15x slower                                           |
| comprehensions                   | 10.9 us                                                         | 12.6 us: 1.15x slower                                           |
| unpickle                         | 10.5 us                                                         | 12.2 us: 1.16x slower                                           |
| meteor_contest                   | 84.4 ms                                                         | 97.9 ms: 1.16x slower                                           |
| unpickle_list                    | 3.33 us                                                         | 3.90 us: 1.17x slower                                           |
| raytrace                         | 195 ms                                                          | 229 ms: 1.17x slower                                            |
| networkx_connected_components    | 425 ms                                                          | 501 ms: 1.18x slower                                            |
| networkx_shortest_path           | 437 ms                                                          | 516 ms: 1.18x slower                                            |
| nqueens                          | 53.6 ms                                                         | 63.6 ms: 1.19x slower                                           |
| argparse_subparsers              | 452 us                                                          | 536 us: 1.19x slower                                            |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.73 ms: 1.19x slower                                           |
| logging_simple                   | 4.71 us                                                         | 5.61 us: 1.19x slower                                           |
| logging_format                   | 5.25 us                                                         | 6.30 us: 1.20x slower                                           |
| typing_runtime_protocols         | 113 us                                                          | 136 us: 1.20x slower                                            |
| json                             | 3.51 ms                                                         | 4.28 ms: 1.22x slower                                           |
| fannkuch                         | 246 ms                                                          | 305 ms: 1.24x slower                                            |
| nbody                            | 65.9 ms                                                         | 81.8 ms: 1.24x slower                                           |
| python_startup                   | 9.51 ms                                                         | 11.9 ms: 1.25x slower                                           |
| pickle_list                      | 3.14 us                                                         | 4.01 us: 1.28x slower                                           |
| crypto_pyaes                     | 50.9 ms                                                         | 65.3 ms: 1.28x slower                                           |
| python_startup_no_site           | 6.46 ms                                                         | 8.35 ms: 1.29x slower                                           |
| mypy2                            | 724 ms                                                          | 941 ms: 1.30x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 382 ms: 1.34x slower                                            |
| coverage                         | 55.8 ms                                                         | 79.2 ms: 1.42x slower                                           |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 264 ms: 1.51x slower                                            |
| mako                             | 7.16 ms                                                         | 11.0 ms: 1.53x slower                                           |
| json_loads                       | 16.2 us                                                         | 25.0 us: 1.54x slower                                           |
| thread_montecarlo_naive          | 19.0 ms                                                         | 29.3 ms: 1.54x slower                                           |
| async_tree_eager_tg              | 58.6 ms                                                         | 191 ms: 3.26x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.07x faster                                                    |

Benchmark hidden because not significant (8): networkx_k_core, async_tree_eager_cpu_io_mixed, base64_small, pylint, pyflate, pathlib, generators, richards_super
Ignored benchmarks (1) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.067x faster

# HPT report

- Reliability score: 78.16% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.57x