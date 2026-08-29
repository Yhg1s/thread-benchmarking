# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.072x faster
- HPT reliability: 87.92%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.58x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 10.9 ms: 1.09x slower                                           |
| docutils       | 1.89 sec                                                        | 2.06 sec: 1.09x slower                                          |
| fastapi_http   | 218 ms                                                          | 191 ms: 1.14x faster                                            |
| html5lib       | 51.7 ms                                                         | 49.3 ms: 1.05x faster                                           |
| tornado_http   | 101 ms                                                          | 94.8 ms: 1.06x faster                                           |
| Geometric mean | (ref)                                                           | 1.01x faster                                                    |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_io_tg                 | 778 ms                                                          | 413 ms: 1.88x faster                                            |
| async_tree_eager_io_tg           | 728 ms                                                          | 404 ms: 1.80x faster                                            |
| async_tree_memoization_tg        | 419 ms                                                          | 237 ms: 1.77x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 434 ms: 1.73x faster                                            |
| async_tree_io                    | 741 ms                                                          | 446 ms: 1.66x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 181 ms: 1.61x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 265 ms: 1.46x faster                                            |
| async_tree_none                  | 308 ms                                                          | 213 ms: 1.44x faster                                            |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 359 ms: 1.36x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 179 ms: 1.23x faster                                            |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 392 ms: 1.21x faster                                            |
| asyncio_websockets               | 303 ms                                                          | 289 ms: 1.05x faster                                            |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 316 ms: 1.02x faster                                            |
| asyncio_tcp                      | 318 ms                                                          | 314 ms: 1.01x faster                                            |
| coroutines                       | 15.4 ms                                                         | 15.6 ms: 1.01x slower                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.39 sec: 1.08x slower                                          |
| async_tree_eager                 | 89.6 ms                                                         | 98.7 ms: 1.10x slower                                           |
| async_generators                 | 240 ms                                                          | 266 ms: 1.11x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 340 ms: 1.19x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 214 ms: 1.22x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 160 ms: 2.73x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.16x faster                                                    |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 21.9 ns: 1.07x slower                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                          | 189 ms: 1.07x slower                                            |
| decimal_pi        | 222 ms                                                          | 246 ms: 1.11x slower                                            |
| Geometric mean    | (ref)                                                           | 1.09x slower                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 51.5 ms: 1.11x faster                                           |
| pidigits       | 189 ms                                                          | 185 ms: 1.02x faster                                            |
| quadtree_nbody | 626 ms                                                          | 662 ms: 1.06x slower                                            |
| nbody          | 65.9 ms                                                         | 83.2 ms: 1.26x slower                                           |
| Geometric mean | (ref)                                                           | 1.04x slower                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 1.98 ms: 1.16x faster                                           |
| regex_v8       | 15.2 ms                                                         | 14.2 ms: 1.07x faster                                           |
| regex_dna      | 162 ms                                                          | 154 ms: 1.05x faster                                            |
| regex_compile  | 98.5 ms                                                         | 105 ms: 1.07x slower                                            |
| Geometric mean | (ref)                                                           | 1.05x faster                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 4.94 ms: 7.49x faster                                           |
| base16_small         | 740 us                                                          | 291 us: 2.54x faster                                            |
| xml_etree_iterparse  | 79.9 ms                                                         | 65.0 ms: 1.23x faster                                           |
| xml_etree_parse      | 104 ms                                                          | 92.5 ms: 1.13x faster                                           |
| base64_small         | 177 us                                                          | 176 us: 1.01x faster                                            |
| pickle_dict          | 22.0 us                                                         | 22.0 us: 1.00x slower                                           |
| base64_large         | 3.33 ms                                                         | 3.34 ms: 1.00x slower                                           |
| urlsafe_base64_small | 325 us                                                          | 328 us: 1.01x slower                                            |
| pickle_list          | 3.14 us                                                         | 3.21 us: 1.02x slower                                           |
| ascii85_large        | 717 ms                                                          | 741 ms: 1.03x slower                                            |
| xml_etree_generate   | 64.2 ms                                                         | 66.5 ms: 1.04x slower                                           |
| unpickle_pure_python | 151 us                                                          | 158 us: 1.05x slower                                            |
| ascii85_small        | 13.6 ms                                                         | 14.2 ms: 1.05x slower                                           |
| base85_large         | 252 ms                                                          | 267 ms: 1.06x slower                                            |
| xml_etree_process    | 46.6 ms                                                         | 49.5 ms: 1.06x slower                                           |
| base85_small         | 4.59 ms                                                         | 4.90 ms: 1.07x slower                                           |
| base32_large         | 296 ms                                                          | 323 ms: 1.09x slower                                            |
| base32_small         | 5.79 ms                                                         | 6.37 ms: 1.10x slower                                           |
| unpickle             | 10.5 us                                                         | 11.6 us: 1.10x slower                                           |
| pickle               | 7.44 us                                                         | 8.41 us: 1.13x slower                                           |
| pickle_pure_python   | 223 us                                                          | 256 us: 1.15x slower                                            |
| json_dumps           | 6.95 ms                                                         | 7.98 ms: 1.15x slower                                           |
| unpickle_list        | 3.33 us                                                         | 3.94 us: 1.18x slower                                           |
| json_loads           | 16.2 us                                                         | 20.2 us: 1.25x slower                                           |
| Geometric mean       | (ref)                                                           | 1.08x faster                                                    |

Benchmark hidden because not significant (1): tomli_loads

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                         | 11.8 ms: 1.24x slower                                           |
| python_startup_no_site | 6.46 ms                                                         | 8.33 ms: 1.29x slower                                           |
| Geometric mean         | (ref)                                                           | 1.27x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| genshi_xml      | 41.3 ms                                                         | 43.2 ms: 1.05x slower                                           |
| genshi_text     | 17.8 ms                                                         | 19.8 ms: 1.11x slower                                           |
| django_template | 27.6 ms                                                         | 30.9 ms: 1.12x slower                                           |
| mako            | 7.16 ms                                                         | 11.5 ms: 1.61x slower                                           |
| Geometric mean  | (ref)                                                           | 1.20x slower                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_counter_optimized    | 16.5 ms                                                         | 4.96 ms: 3.34x faster                                           |
| thread_mandelbrot_naive     | 210 ms                                                          | 63.1 ms: 3.33x faster                                           |
| thread_pipeline_optimized   | 20.9 ms                                                         | 6.27 ms: 3.33x faster                                           |
| thread_accumulate_optimized | 32.3 ms                                                         | 9.78 ms: 3.31x faster                                           |
| thread_mandelbrot_optimized | 208 ms                                                          | 63.7 ms: 3.26x faster                                           |
| thread_montecarlo_optimized | 14.5 ms                                                         | 4.87 ms: 2.97x faster                                           |
| thread_memo_optimized       | 15.3 ms                                                         | 5.48 ms: 2.79x faster                                           |
| thread_accumulate_naive     | 33.4 ms                                                         | 12.6 ms: 2.65x faster                                           |
| thread_pipeline_naive       | 47.3 ms                                                         | 27.3 ms: 1.73x faster                                           |
| thread_memo_naive           | 36.1 ms                                                         | 24.2 ms: 1.49x faster                                           |
| thread_counter_naive        | 20.6 ms                                                         | 21.2 ms: 1.03x slower                                           |
| thread_montecarlo_naive     | 19.0 ms                                                         | 26.9 ms: 1.41x slower                                           |
| Geometric mean              | (ref)                                                           | 2.23x faster                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 4.94 ms: 7.49x faster                                           |
| thread_counter_optimized         | 16.5 ms                                                         | 4.96 ms: 3.34x faster                                           |
| thread_mandelbrot_naive          | 210 ms                                                          | 63.1 ms: 3.33x faster                                           |
| thread_pipeline_optimized        | 20.9 ms                                                         | 6.27 ms: 3.33x faster                                           |
| thread_accumulate_optimized      | 32.3 ms                                                         | 9.78 ms: 3.31x faster                                           |
| thread_mandelbrot_optimized      | 208 ms                                                          | 63.7 ms: 3.26x faster                                           |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 4.87 ms: 2.97x faster                                           |
| thread_memo_optimized            | 15.3 ms                                                         | 5.48 ms: 2.79x faster                                           |
| thread_accumulate_naive          | 33.4 ms                                                         | 12.6 ms: 2.65x faster                                           |
| base16_small                     | 740 us                                                          | 291 us: 2.54x faster                                            |
| mdp                              | 2.15 sec                                                        | 1.02 sec: 2.10x faster                                          |
| async_tree_io_tg                 | 778 ms                                                          | 413 ms: 1.88x faster                                            |
| gc_traversal                     | 3.07 ms                                                         | 1.69 ms: 1.82x faster                                           |
| async_tree_eager_io_tg           | 728 ms                                                          | 404 ms: 1.80x faster                                            |
| async_tree_memoization_tg        | 419 ms                                                          | 237 ms: 1.77x faster                                            |
| thread_pipeline_naive            | 47.3 ms                                                         | 27.3 ms: 1.73x faster                                           |
| async_tree_eager_io              | 749 ms                                                          | 434 ms: 1.73x faster                                            |
| async_tree_io                    | 741 ms                                                          | 446 ms: 1.66x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 181 ms: 1.61x faster                                            |
| thread_memo_naive                | 36.1 ms                                                         | 24.2 ms: 1.49x faster                                           |
| async_tree_memoization           | 388 ms                                                          | 265 ms: 1.46x faster                                            |
| async_tree_none                  | 308 ms                                                          | 213 ms: 1.44x faster                                            |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 359 ms: 1.36x faster                                            |
| create_gc_cycles                 | 1.75 ms                                                         | 1.34 ms: 1.31x faster                                           |
| deepcopy                         | 269 us                                                          | 216 us: 1.24x faster                                            |
| xml_etree_iterparse              | 79.9 ms                                                         | 65.0 ms: 1.23x faster                                           |
| async_tree_eager_memoization     | 219 ms                                                          | 179 ms: 1.23x faster                                            |
| go                               | 117 ms                                                          | 96.1 ms: 1.22x faster                                           |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 392 ms: 1.21x faster                                            |
| deepcopy_memo                    | 26.5 us                                                         | 21.9 us: 1.21x faster                                           |
| regex_effbot                     | 2.30 ms                                                         | 1.98 ms: 1.16x faster                                           |
| fastapi_http                     | 218 ms                                                          | 191 ms: 1.14x faster                                            |
| xml_etree_parse                  | 104 ms                                                          | 92.5 ms: 1.13x faster                                           |
| float                            | 57.0 ms                                                         | 51.5 ms: 1.11x faster                                           |
| regex_v8                         | 15.2 ms                                                         | 14.2 ms: 1.07x faster                                           |
| tornado_http                     | 101 ms                                                          | 94.8 ms: 1.06x faster                                           |
| regex_dna                        | 162 ms                                                          | 154 ms: 1.05x faster                                            |
| asyncio_websockets               | 303 ms                                                          | 289 ms: 1.05x faster                                            |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.14 sec: 1.05x faster                                          |
| deepcopy_reduce                  | 2.40 us                                                         | 2.29 us: 1.05x faster                                           |
| html5lib                         | 51.7 ms                                                         | 49.3 ms: 1.05x faster                                           |
| pycparser                        | 860 ms                                                          | 832 ms: 1.03x faster                                            |
| pidigits                         | 189 ms                                                          | 185 ms: 1.02x faster                                            |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 316 ms: 1.02x faster                                            |
| richards                         | 37.8 ms                                                         | 37.2 ms: 1.02x faster                                           |
| base64_small                     | 177 us                                                          | 176 us: 1.01x faster                                            |
| asyncio_tcp                      | 318 ms                                                          | 314 ms: 1.01x faster                                            |
| pickle_dict                      | 22.0 us                                                         | 22.0 us: 1.00x slower                                           |
| base64_large                     | 3.33 ms                                                         | 3.34 ms: 1.00x slower                                           |
| richards_super                   | 42.8 ms                                                         | 43.2 ms: 1.01x slower                                           |
| urlsafe_base64_small             | 325 us                                                          | 328 us: 1.01x slower                                            |
| coroutines                       | 15.4 ms                                                         | 15.6 ms: 1.01x slower                                           |
| pathlib                          | 12.8 ms                                                         | 13.0 ms: 1.02x slower                                           |
| pickle_list                      | 3.14 us                                                         | 3.21 us: 1.02x slower                                           |
| thread_counter_naive             | 20.6 ms                                                         | 21.2 ms: 1.03x slower                                           |
| ascii85_large                    | 717 ms                                                          | 741 ms: 1.03x slower                                            |
| xml_etree_generate               | 64.2 ms                                                         | 66.5 ms: 1.04x slower                                           |
| pprint_safe_repr                 | 530 ms                                                          | 553 ms: 1.04x slower                                            |
| genshi_xml                       | 41.3 ms                                                         | 43.2 ms: 1.05x slower                                           |
| unpickle_pure_python             | 151 us                                                          | 158 us: 1.05x slower                                            |
| ascii85_small                    | 13.6 ms                                                         | 14.2 ms: 1.05x slower                                           |
| pprint_pformat                   | 1.09 sec                                                        | 1.15 sec: 1.05x slower                                          |
| quadtree_nbody                   | 626 ms                                                          | 662 ms: 1.06x slower                                            |
| base85_large                     | 252 ms                                                          | 267 ms: 1.06x slower                                            |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 42.5 ms: 1.06x slower                                           |
| xml_etree_process                | 46.6 ms                                                         | 49.5 ms: 1.06x slower                                           |
| base85_small                     | 4.59 ms                                                         | 4.90 ms: 1.07x slower                                           |
| chaos                            | 45.1 ms                                                         | 48.2 ms: 1.07x slower                                           |
| json                             | 3.51 ms                                                         | 3.74 ms: 1.07x slower                                           |
| decimal_factorial                | 177 ms                                                          | 189 ms: 1.07x slower                                            |
| noop                             | 20.5 ns                                                         | 21.9 ns: 1.07x slower                                           |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 86.1 ms: 1.07x slower                                           |
| regex_compile                    | 98.5 ms                                                         | 105 ms: 1.07x slower                                            |
| sympy_integrate                  | 15.8 ms                                                         | 17.0 ms: 1.07x slower                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.39 sec: 1.08x slower                                          |
| deltablue                        | 2.41 ms                                                         | 2.59 ms: 1.08x slower                                           |
| mypy2                            | 724 ms                                                          | 783 ms: 1.08x slower                                            |
| sympy_sum                        | 106 ms                                                          | 115 ms: 1.08x slower                                            |
| telco                            | 5.83 ms                                                         | 6.30 ms: 1.08x slower                                           |
| sympy_str                        | 197 ms                                                          | 213 ms: 1.08x slower                                            |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.31 ms: 1.09x slower                                           |
| sympy_expand                     | 336 ms                                                          | 367 ms: 1.09x slower                                            |
| chameleon                        | 9.95 ms                                                         | 10.9 ms: 1.09x slower                                           |
| docutils                         | 1.89 sec                                                        | 2.06 sec: 1.09x slower                                          |
| base32_large                     | 296 ms                                                          | 323 ms: 1.09x slower                                            |
| scimark_sor                      | 78.9 ms                                                         | 86.4 ms: 1.09x slower                                           |
| base32_small                     | 5.79 ms                                                         | 6.37 ms: 1.10x slower                                           |
| unpickle                         | 10.5 us                                                         | 11.6 us: 1.10x slower                                           |
| async_tree_eager                 | 89.6 ms                                                         | 98.7 ms: 1.10x slower                                           |
| decimal_pi                       | 222 ms                                                          | 246 ms: 1.11x slower                                            |
| hexiom                           | 4.30 ms                                                         | 4.77 ms: 1.11x slower                                           |
| genshi_text                      | 17.8 ms                                                         | 19.8 ms: 1.11x slower                                           |
| async_generators                 | 240 ms                                                          | 266 ms: 1.11x slower                                            |
| scimark_fft                      | 226 ms                                                          | 251 ms: 1.11x slower                                            |
| sqlglot_v2_parse                 | 958 us                                                          | 1.07 ms: 1.11x slower                                           |
| django_template                  | 27.6 ms                                                         | 30.9 ms: 1.12x slower                                           |
| logging_format                   | 5.25 us                                                         | 5.91 us: 1.13x slower                                           |
| scimark_monte_carlo              | 46.5 ms                                                         | 52.6 ms: 1.13x slower                                           |
| pickle                           | 7.44 us                                                         | 8.41 us: 1.13x slower                                           |
| spectral_norm                    | 65.9 ms                                                         | 75.3 ms: 1.14x slower                                           |
| logging_simple                   | 4.71 us                                                         | 5.38 us: 1.14x slower                                           |
| pickle_pure_python               | 223 us                                                          | 256 us: 1.15x slower                                            |
| json_dumps                       | 6.95 ms                                                         | 7.98 ms: 1.15x slower                                           |
| comprehensions                   | 10.9 us                                                         | 12.6 us: 1.16x slower                                           |
| meteor_contest                   | 84.4 ms                                                         | 97.6 ms: 1.16x slower                                           |
| networkx_connected_components    | 425 ms                                                          | 495 ms: 1.17x slower                                            |
| networkx_shortest_path           | 437 ms                                                          | 510 ms: 1.17x slower                                            |
| logging_silent                   | 61.0 ns                                                         | 71.3 ns: 1.17x slower                                           |
| unpickle_list                    | 3.33 us                                                         | 3.94 us: 1.18x slower                                           |
| raytrace                         | 195 ms                                                          | 231 ms: 1.18x slower                                            |
| scimark_lu                       | 74.5 ms                                                         | 88.2 ms: 1.18x slower                                           |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.73 ms: 1.19x slower                                           |
| nqueens                          | 53.6 ms                                                         | 63.9 ms: 1.19x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 340 ms: 1.19x slower                                            |
| typing_runtime_protocols         | 113 us                                                          | 137 us: 1.21x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 214 ms: 1.22x slower                                            |
| python_startup                   | 9.51 ms                                                         | 11.8 ms: 1.24x slower                                           |
| json_loads                       | 16.2 us                                                         | 20.2 us: 1.25x slower                                           |
| fannkuch                         | 246 ms                                                          | 310 ms: 1.26x slower                                            |
| nbody                            | 65.9 ms                                                         | 83.2 ms: 1.26x slower                                           |
| crypto_pyaes                     | 50.9 ms                                                         | 65.3 ms: 1.28x slower                                           |
| python_startup_no_site           | 6.46 ms                                                         | 8.33 ms: 1.29x slower                                           |
| unpack_sequence                  | 27.1 ns                                                         | 35.5 ns: 1.31x slower                                           |
| thread_montecarlo_naive          | 19.0 ms                                                         | 26.9 ms: 1.41x slower                                           |
| coverage                         | 55.8 ms                                                         | 80.7 ms: 1.45x slower                                           |
| mako                             | 7.16 ms                                                         | 11.5 ms: 1.61x slower                                           |
| argparse_subparsers              | 452 us                                                          | 740 us: 1.64x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 160 ms: 2.73x slower                                            |
| argparse_many_optionals          | 12.8 ms                                                         | 37.0 ms: 2.88x slower                                           |
| Geometric mean                   | (ref)                                                           | 1.07x faster                                                    |

Benchmark hidden because not significant (7): generators, thrift, networkx_k_core, pyflate, tomli_loads, pylint, xdsl_constant_fold
Ignored benchmarks (1) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.072x faster

# HPT report

- Reliability score: 87.92% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.58x