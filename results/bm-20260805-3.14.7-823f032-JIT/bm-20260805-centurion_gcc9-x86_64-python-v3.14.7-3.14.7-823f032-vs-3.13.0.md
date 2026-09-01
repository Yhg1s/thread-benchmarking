# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.043x faster
- HPT reliability: 98.32%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.07x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 10.1 ms: 1.02x slower                                           |
| docutils       | 1.89 sec                                                        | 1.94 sec: 1.03x slower                                          |
| fastapi_http   | 218 ms                                                          | 212 ms: 1.03x faster                                            |
| html5lib       | 51.7 ms                                                         | 48.7 ms: 1.06x faster                                           |
| tornado_http   | 101 ms                                                          | 104 ms: 1.03x slower                                            |
| Geometric mean | (ref)                                                           | 1.00x faster                                                    |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_memoization_tg        | 419 ms                                                          | 343 ms: 1.22x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 333 ms: 1.16x faster                                            |
| async_tree_none                  | 308 ms                                                          | 266 ms: 1.16x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 651 ms: 1.15x faster                                            |
| async_tree_io_tg                 | 778 ms                                                          | 694 ms: 1.12x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 197 ms: 1.11x faster                                            |
| async_tree_eager_io_tg           | 728 ms                                                          | 667 ms: 1.09x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 268 ms: 1.08x faster                                            |
| async_tree_io                    | 741 ms                                                          | 686 ms: 1.08x faster                                            |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 457 ms: 1.07x faster                                            |
| asyncio_tcp                      | 318 ms                                                          | 297 ms: 1.07x faster                                            |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 450 ms: 1.05x faster                                            |
| async_tree_eager                 | 89.6 ms                                                         | 85.9 ms: 1.04x faster                                           |
| asyncio_websockets               | 303 ms                                                          | 298 ms: 1.02x faster                                            |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 320 ms: 1.01x faster                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.29 sec: 1.00x slower                                          |
| coroutines                       | 15.4 ms                                                         | 16.4 ms: 1.06x slower                                           |
| async_generators                 | 240 ms                                                          | 257 ms: 1.07x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 397 ms: 1.39x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 282 ms: 1.61x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 207 ms: 3.53x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.04x slower                                                    |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 16.8 ns: 1.22x faster                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                          | 204 ms: 1.09x faster                                            |
| decimal_factorial | 177 ms                                                          | 175 ms: 1.01x faster                                            |
| Geometric mean    | (ref)                                                           | 1.05x faster                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 42.1 ms: 1.35x faster                                           |
| quadtree_nbody | 626 ms                                                          | 592 ms: 1.06x faster                                            |
| pidigits       | 189 ms                                                          | 187 ms: 1.01x faster                                            |
| nbody          | 65.9 ms                                                         | 70.1 ms: 1.06x slower                                           |
| Geometric mean | (ref)                                                           | 1.08x faster                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 2.09 ms: 1.10x faster                                           |
| regex_dna      | 162 ms                                                          | 153 ms: 1.06x faster                                            |
| regex_compile  | 98.5 ms                                                         | 95.2 ms: 1.04x faster                                           |
| regex_v8       | 15.2 ms                                                         | 14.9 ms: 1.02x faster                                           |
| Geometric mean | (ref)                                                           | 1.05x faster                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 5.25 ms: 7.05x faster                                           |
| base16_small         | 740 us                                                          | 310 us: 2.39x faster                                            |
| ascii85_large        | 717 ms                                                          | 613 ms: 1.17x faster                                            |
| tomli_loads          | 1.62 sec                                                        | 1.42 sec: 1.14x faster                                          |
| pickle_list          | 3.14 us                                                         | 2.79 us: 1.13x faster                                           |
| unpickle_pure_python | 151 us                                                          | 134 us: 1.12x faster                                            |
| ascii85_small        | 13.6 ms                                                         | 12.2 ms: 1.12x faster                                           |
| xml_etree_generate   | 64.2 ms                                                         | 58.5 ms: 1.10x faster                                           |
| xml_etree_process    | 46.6 ms                                                         | 42.9 ms: 1.09x faster                                           |
| base85_large         | 252 ms                                                          | 242 ms: 1.04x faster                                            |
| xml_etree_iterparse  | 79.9 ms                                                         | 77.6 ms: 1.03x faster                                           |
| pickle_dict          | 22.0 us                                                         | 21.5 us: 1.02x faster                                           |
| base85_small         | 4.59 ms                                                         | 4.51 ms: 1.02x faster                                           |
| base64_large         | 3.33 ms                                                         | 3.31 ms: 1.01x faster                                           |
| base64_small         | 177 us                                                          | 179 us: 1.01x slower                                            |
| base32_large         | 296 ms                                                          | 298 ms: 1.01x slower                                            |
| unpickle             | 10.5 us                                                         | 10.7 us: 1.02x slower                                           |
| base32_small         | 5.79 ms                                                         | 5.90 ms: 1.02x slower                                           |
| json_dumps           | 6.95 ms                                                         | 7.28 ms: 1.05x slower                                           |
| unpickle_list        | 3.33 us                                                         | 3.51 us: 1.05x slower                                           |
| xml_etree_parse      | 104 ms                                                          | 112 ms: 1.07x slower                                            |
| pickle_pure_python   | 223 us                                                          | 247 us: 1.11x slower                                            |
| pickle               | 7.44 us                                                         | 8.38 us: 1.13x slower                                           |
| json_loads           | 16.2 us                                                         | 19.6 us: 1.21x slower                                           |
| Geometric mean       | (ref)                                                           | 1.13x faster                                                    |

Benchmark hidden because not significant (1): urlsafe_base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 6.49 ms: 1.01x slower                                           |
| python_startup         | 9.51 ms                                                         | 9.96 ms: 1.05x slower                                           |
| Geometric mean         | (ref)                                                           | 1.03x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| mako            | 7.16 ms                                                         | 6.48 ms: 1.10x faster                                           |
| genshi_text     | 17.8 ms                                                         | 17.3 ms: 1.03x faster                                           |
| genshi_xml      | 41.3 ms                                                         | 41.7 ms: 1.01x slower                                           |
| django_template | 27.6 ms                                                         | 28.5 ms: 1.03x slower                                           |
| Geometric mean  | (ref)                                                           | 1.02x faster                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_memo_naive           | 36.1 ms                                                         | 10.8 ms: 3.36x faster                                           |
| thread_pipeline_naive       | 47.3 ms                                                         | 30.7 ms: 1.54x faster                                           |
| thread_memo_optimized       | 15.3 ms                                                         | 15.0 ms: 1.02x faster                                           |
| thread_counter_naive        | 20.6 ms                                                         | 20.3 ms: 1.01x faster                                           |
| thread_montecarlo_optimized | 14.5 ms                                                         | 14.4 ms: 1.01x faster                                           |
| thread_accumulate_naive     | 33.4 ms                                                         | 33.3 ms: 1.00x faster                                           |
| thread_mandelbrot_naive     | 210 ms                                                          | 211 ms: 1.00x slower                                            |
| thread_pipeline_optimized   | 20.9 ms                                                         | 21.0 ms: 1.01x slower                                           |
| thread_counter_optimized    | 16.5 ms                                                         | 16.7 ms: 1.01x slower                                           |
| thread_accumulate_optimized | 32.3 ms                                                         | 32.7 ms: 1.01x slower                                           |
| thread_mandelbrot_optimized | 208 ms                                                          | 212 ms: 1.02x slower                                            |
| thread_montecarlo_naive     | 19.0 ms                                                         | 19.7 ms: 1.03x slower                                           |
| Geometric mean              | (ref)                                                           | 1.14x faster                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 5.25 ms: 7.05x faster                                           |
| thread_memo_naive                | 36.1 ms                                                         | 10.8 ms: 3.36x faster                                           |
| base16_small                     | 740 us                                                          | 310 us: 2.39x faster                                            |
| mdp                              | 2.15 sec                                                        | 954 ms: 2.25x faster                                            |
| argparse_many_optionals          | 12.8 ms                                                         | 7.62 ms: 1.68x faster                                           |
| thread_pipeline_naive            | 47.3 ms                                                         | 30.7 ms: 1.54x faster                                           |
| deepcopy_memo                    | 26.5 us                                                         | 18.4 us: 1.44x faster                                           |
| richards                         | 37.8 ms                                                         | 27.6 ms: 1.37x faster                                           |
| deepcopy                         | 269 us                                                          | 197 us: 1.37x faster                                            |
| float                            | 57.0 ms                                                         | 42.1 ms: 1.35x faster                                           |
| richards_super                   | 42.8 ms                                                         | 32.2 ms: 1.33x faster                                           |
| async_tree_memoization_tg        | 419 ms                                                          | 343 ms: 1.22x faster                                            |
| noop                             | 20.5 ns                                                         | 16.8 ns: 1.22x faster                                           |
| scimark_fft                      | 226 ms                                                          | 186 ms: 1.21x faster                                            |
| deepcopy_reduce                  | 2.40 us                                                         | 2.03 us: 1.18x faster                                           |
| deltablue                        | 2.41 ms                                                         | 2.05 ms: 1.17x faster                                           |
| go                               | 117 ms                                                          | 100 ms: 1.17x faster                                            |
| ascii85_large                    | 717 ms                                                          | 613 ms: 1.17x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 333 ms: 1.16x faster                                            |
| async_tree_none                  | 308 ms                                                          | 266 ms: 1.16x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 651 ms: 1.15x faster                                            |
| spectral_norm                    | 65.9 ms                                                         | 57.4 ms: 1.15x faster                                           |
| tomli_loads                      | 1.62 sec                                                        | 1.42 sec: 1.14x faster                                          |
| pyflate                          | 342 ms                                                          | 303 ms: 1.13x faster                                            |
| pickle_list                      | 3.14 us                                                         | 2.79 us: 1.13x faster                                           |
| unpickle_pure_python             | 151 us                                                          | 134 us: 1.12x faster                                            |
| async_tree_io_tg                 | 778 ms                                                          | 694 ms: 1.12x faster                                            |
| ascii85_small                    | 13.6 ms                                                         | 12.2 ms: 1.12x faster                                           |
| async_tree_eager_memoization     | 219 ms                                                          | 197 ms: 1.11x faster                                            |
| bpe_tokeniser                    | 3.30 sec                                                        | 2.98 sec: 1.11x faster                                          |
| mako                             | 7.16 ms                                                         | 6.48 ms: 1.10x faster                                           |
| regex_effbot                     | 2.30 ms                                                         | 2.09 ms: 1.10x faster                                           |
| xml_etree_generate               | 64.2 ms                                                         | 58.5 ms: 1.10x faster                                           |
| scimark_monte_carlo              | 46.5 ms                                                         | 42.7 ms: 1.09x faster                                           |
| async_tree_eager_io_tg           | 728 ms                                                          | 667 ms: 1.09x faster                                            |
| decimal_pi                       | 222 ms                                                          | 204 ms: 1.09x faster                                            |
| xml_etree_process                | 46.6 ms                                                         | 42.9 ms: 1.09x faster                                           |
| telco                            | 5.83 ms                                                         | 5.38 ms: 1.08x faster                                           |
| async_tree_none_tg               | 291 ms                                                          | 268 ms: 1.08x faster                                            |
| async_tree_io                    | 741 ms                                                          | 686 ms: 1.08x faster                                            |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 2.93 ms: 1.07x faster                                           |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 457 ms: 1.07x faster                                            |
| asyncio_tcp                      | 318 ms                                                          | 297 ms: 1.07x faster                                            |
| html5lib                         | 51.7 ms                                                         | 48.7 ms: 1.06x faster                                           |
| quadtree_nbody                   | 626 ms                                                          | 592 ms: 1.06x faster                                            |
| regex_dna                        | 162 ms                                                          | 153 ms: 1.06x faster                                            |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 450 ms: 1.05x faster                                            |
| scimark_sor                      | 78.9 ms                                                         | 75.3 ms: 1.05x faster                                           |
| async_tree_eager                 | 89.6 ms                                                         | 85.9 ms: 1.04x faster                                           |
| base85_large                     | 252 ms                                                          | 242 ms: 1.04x faster                                            |
| regex_compile                    | 98.5 ms                                                         | 95.2 ms: 1.04x faster                                           |
| fastapi_http                     | 218 ms                                                          | 212 ms: 1.03x faster                                            |
| xml_etree_iterparse              | 79.9 ms                                                         | 77.6 ms: 1.03x faster                                           |
| genshi_text                      | 17.8 ms                                                         | 17.3 ms: 1.03x faster                                           |
| pickle_dict                      | 22.0 us                                                         | 21.5 us: 1.02x faster                                           |
| networkx_connected_components    | 425 ms                                                          | 416 ms: 1.02x faster                                            |
| regex_v8                         | 15.2 ms                                                         | 14.9 ms: 1.02x faster                                           |
| asyncio_websockets               | 303 ms                                                          | 298 ms: 1.02x faster                                            |
| fannkuch                         | 246 ms                                                          | 242 ms: 1.02x faster                                            |
| base85_small                     | 4.59 ms                                                         | 4.51 ms: 1.02x faster                                           |
| thread_memo_optimized            | 15.3 ms                                                         | 15.0 ms: 1.02x faster                                           |
| thrift                           | 2.02 ms                                                         | 1.99 ms: 1.02x faster                                           |
| thread_counter_naive             | 20.6 ms                                                         | 20.3 ms: 1.01x faster                                           |
| decimal_factorial                | 177 ms                                                          | 175 ms: 1.01x faster                                            |
| networkx_shortest_path           | 437 ms                                                          | 432 ms: 1.01x faster                                            |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 14.4 ms: 1.01x faster                                           |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 320 ms: 1.01x faster                                            |
| pidigits                         | 189 ms                                                          | 187 ms: 1.01x faster                                            |
| base64_large                     | 3.33 ms                                                         | 3.31 ms: 1.01x faster                                           |
| thread_accumulate_naive          | 33.4 ms                                                         | 33.3 ms: 1.00x faster                                           |
| thread_mandelbrot_naive          | 210 ms                                                          | 211 ms: 1.00x slower                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.29 sec: 1.00x slower                                          |
| python_startup_no_site           | 6.46 ms                                                         | 6.49 ms: 1.01x slower                                           |
| base64_small                     | 177 us                                                          | 179 us: 1.01x slower                                            |
| thread_pipeline_optimized        | 20.9 ms                                                         | 21.0 ms: 1.01x slower                                           |
| base32_large                     | 296 ms                                                          | 298 ms: 1.01x slower                                            |
| sympy_integrate                  | 15.8 ms                                                         | 16.0 ms: 1.01x slower                                           |
| genshi_xml                       | 41.3 ms                                                         | 41.7 ms: 1.01x slower                                           |
| thread_counter_optimized         | 16.5 ms                                                         | 16.7 ms: 1.01x slower                                           |
| thread_accumulate_optimized      | 32.3 ms                                                         | 32.7 ms: 1.01x slower                                           |
| meteor_contest                   | 84.4 ms                                                         | 85.5 ms: 1.01x slower                                           |
| unpickle                         | 10.5 us                                                         | 10.7 us: 1.02x slower                                           |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.23 ms: 1.02x slower                                           |
| base32_small                     | 5.79 ms                                                         | 5.90 ms: 1.02x slower                                           |
| chameleon                        | 9.95 ms                                                         | 10.1 ms: 1.02x slower                                           |
| thread_mandelbrot_optimized      | 208 ms                                                          | 212 ms: 1.02x slower                                            |
| pathlib                          | 12.8 ms                                                         | 13.1 ms: 1.02x slower                                           |
| sympy_sum                        | 106 ms                                                          | 109 ms: 1.03x slower                                            |
| docutils                         | 1.89 sec                                                        | 1.94 sec: 1.03x slower                                          |
| sympy_str                        | 197 ms                                                          | 203 ms: 1.03x slower                                            |
| scimark_lu                       | 74.5 ms                                                         | 76.9 ms: 1.03x slower                                           |
| django_template                  | 27.6 ms                                                         | 28.5 ms: 1.03x slower                                           |
| thread_montecarlo_naive          | 19.0 ms                                                         | 19.7 ms: 1.03x slower                                           |
| tornado_http                     | 101 ms                                                          | 104 ms: 1.03x slower                                            |
| logging_format                   | 5.25 us                                                         | 5.45 us: 1.04x slower                                           |
| raytrace                         | 195 ms                                                          | 203 ms: 1.04x slower                                            |
| logging_simple                   | 4.71 us                                                         | 4.89 us: 1.04x slower                                           |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 41.7 ms: 1.04x slower                                           |
| sympy_expand                     | 336 ms                                                          | 350 ms: 1.04x slower                                            |
| coverage                         | 55.8 ms                                                         | 58.0 ms: 1.04x slower                                           |
| python_startup                   | 9.51 ms                                                         | 9.96 ms: 1.05x slower                                           |
| json_dumps                       | 6.95 ms                                                         | 7.28 ms: 1.05x slower                                           |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 84.5 ms: 1.05x slower                                           |
| unpickle_list                    | 3.33 us                                                         | 3.51 us: 1.05x slower                                           |
| hexiom                           | 4.30 ms                                                         | 4.53 ms: 1.05x slower                                           |
| typing_runtime_protocols         | 113 us                                                          | 119 us: 1.06x slower                                            |
| pycparser                        | 860 ms                                                          | 911 ms: 1.06x slower                                            |
| nbody                            | 65.9 ms                                                         | 70.1 ms: 1.06x slower                                           |
| coroutines                       | 15.4 ms                                                         | 16.4 ms: 1.06x slower                                           |
| async_generators                 | 240 ms                                                          | 257 ms: 1.07x slower                                            |
| xml_etree_parse                  | 104 ms                                                          | 112 ms: 1.07x slower                                            |
| sqlalchemy_imperative            | 13.9 ms                                                         | 14.9 ms: 1.07x slower                                           |
| create_gc_cycles                 | 1.75 ms                                                         | 1.89 ms: 1.08x slower                                           |
| json                             | 3.51 ms                                                         | 3.80 ms: 1.08x slower                                           |
| nqueens                          | 53.6 ms                                                         | 58.2 ms: 1.08x slower                                           |
| logging_silent                   | 61.0 ns                                                         | 66.4 ns: 1.09x slower                                           |
| comprehensions                   | 10.9 us                                                         | 12.0 us: 1.09x slower                                           |
| pickle_pure_python               | 223 us                                                          | 247 us: 1.11x slower                                            |
| gc_traversal                     | 3.07 ms                                                         | 3.43 ms: 1.12x slower                                           |
| pickle                           | 7.44 us                                                         | 8.38 us: 1.13x slower                                           |
| crypto_pyaes                     | 50.9 ms                                                         | 57.6 ms: 1.13x slower                                           |
| argparse_subparsers              | 452 us                                                          | 518 us: 1.15x slower                                            |
| pprint_pformat                   | 1.09 sec                                                        | 1.28 sec: 1.17x slower                                          |
| pprint_safe_repr                 | 530 ms                                                          | 632 ms: 1.19x slower                                            |
| json_loads                       | 16.2 us                                                         | 19.6 us: 1.21x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 397 ms: 1.39x slower                                            |
| mypy2                            | 724 ms                                                          | 1.06 sec: 1.47x slower                                          |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 282 ms: 1.61x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 207 ms: 3.53x slower                                            |
| unpack_sequence                  | 27.1 ns                                                         | 103 ns: 3.81x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.04x faster                                                    |

Benchmark hidden because not significant (7): networkx_k_core, xdsl_constant_fold, generators, sqlglot_v2_parse, urlsafe_base64_small, chaos, pylint

- Geometric mean (including insignificant results): 1.043x faster

# HPT report

- Reliability score: 98.32% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.07x