# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.063x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.09x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 9.52 ms: 1.05x faster                                           |
| docutils       | 1.89 sec                                                        | 1.95 sec: 1.03x slower                                          |
| fastapi_http   | 218 ms                                                          | 216 ms: 1.01x faster                                            |
| html5lib       | 51.7 ms                                                         | 46.9 ms: 1.10x faster                                           |
| Geometric mean | (ref)                                                           | 1.02x faster                                                    |

Benchmark hidden because not significant (1): tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_memoization_tg        | 419 ms                                                          | 277 ms: 1.51x faster                                            |
| async_tree_io_tg                 | 778 ms                                                          | 539 ms: 1.44x faster                                            |
| async_tree_io                    | 741 ms                                                          | 531 ms: 1.40x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 281 ms: 1.38x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 552 ms: 1.36x faster                                            |
| async_tree_none                  | 308 ms                                                          | 228 ms: 1.35x faster                                            |
| async_tree_eager_io_tg           | 728 ms                                                          | 550 ms: 1.32x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 223 ms: 1.30x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 180 ms: 1.22x faster                                            |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 410 ms: 1.19x faster                                            |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 407 ms: 1.16x faster                                            |
| async_tree_eager                 | 89.6 ms                                                         | 81.3 ms: 1.10x faster                                           |
| async_generators                 | 240 ms                                                          | 228 ms: 1.05x faster                                            |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 314 ms: 1.03x faster                                            |
| asyncio_websockets               | 303 ms                                                          | 296 ms: 1.02x faster                                            |
| coroutines                       | 15.4 ms                                                         | 15.1 ms: 1.02x faster                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.28 sec: 1.00x faster                                          |
| asyncio_tcp                      | 318 ms                                                          | 325 ms: 1.02x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 363 ms: 1.27x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 236 ms: 1.35x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 182 ms: 3.11x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.08x faster                                                    |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 19.4 ns: 1.06x faster                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                          | 208 ms: 1.07x faster                                            |
| decimal_factorial | 177 ms                                                          | 173 ms: 1.02x faster                                            |
| Geometric mean    | (ref)                                                           | 1.05x faster                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 47.3 ms: 1.21x faster                                           |
| quadtree_nbody | 626 ms                                                          | 596 ms: 1.05x faster                                            |
| pidigits       | 189 ms                                                          | 189 ms: 1.00x slower                                            |
| nbody          | 65.9 ms                                                         | 67.9 ms: 1.03x slower                                           |
| Geometric mean | (ref)                                                           | 1.05x faster                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 1.95 ms: 1.18x faster                                           |
| regex_dna      | 162 ms                                                          | 150 ms: 1.08x faster                                            |
| regex_compile  | 98.5 ms                                                         | 93.9 ms: 1.05x faster                                           |
| regex_v8       | 15.2 ms                                                         | 14.8 ms: 1.03x faster                                           |
| Geometric mean | (ref)                                                           | 1.08x faster                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 5.33 ms: 6.94x faster                                           |
| base16_small         | 740 us                                                          | 305 us: 2.42x faster                                            |
| tomli_loads          | 1.62 sec                                                        | 1.44 sec: 1.12x faster                                          |
| xml_etree_parse      | 104 ms                                                          | 94.3 ms: 1.11x faster                                           |
| ascii85_large        | 717 ms                                                          | 667 ms: 1.07x faster                                            |
| ascii85_small        | 13.6 ms                                                         | 12.7 ms: 1.07x faster                                           |
| xml_etree_iterparse  | 79.9 ms                                                         | 76.2 ms: 1.05x faster                                           |
| xml_etree_process    | 46.6 ms                                                         | 44.7 ms: 1.04x faster                                           |
| unpickle             | 10.5 us                                                         | 10.2 us: 1.03x faster                                           |
| xml_etree_generate   | 64.2 ms                                                         | 62.6 ms: 1.02x faster                                           |
| pickle_dict          | 22.0 us                                                         | 21.5 us: 1.02x faster                                           |
| base85_large         | 252 ms                                                          | 248 ms: 1.02x faster                                            |
| base32_small         | 5.79 ms                                                         | 5.71 ms: 1.02x faster                                           |
| base32_large         | 296 ms                                                          | 292 ms: 1.01x faster                                            |
| unpickle_pure_python | 151 us                                                          | 152 us: 1.01x slower                                            |
| urlsafe_base64_small | 325 us                                                          | 329 us: 1.01x slower                                            |
| base85_small         | 4.59 ms                                                         | 4.69 ms: 1.02x slower                                           |
| unpickle_list        | 3.33 us                                                         | 3.43 us: 1.03x slower                                           |
| pickle_list          | 3.14 us                                                         | 3.24 us: 1.03x slower                                           |
| base64_small         | 177 us                                                          | 186 us: 1.05x slower                                            |
| pickle_pure_python   | 223 us                                                          | 240 us: 1.07x slower                                            |
| json_loads           | 16.2 us                                                         | 17.5 us: 1.08x slower                                           |
| base64_large         | 3.33 ms                                                         | 3.63 ms: 1.09x slower                                           |
| pickle               | 7.44 us                                                         | 8.20 us: 1.10x slower                                           |
| Geometric mean       | (ref)                                                           | 1.12x faster                                                    |

Benchmark hidden because not significant (1): json_dumps

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 6.38 ms: 1.01x faster                                           |
| python_startup         | 9.51 ms                                                         | 9.73 ms: 1.02x slower                                           |
| Geometric mean         | (ref)                                                           | 1.01x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| genshi_text     | 17.8 ms                                                         | 16.8 ms: 1.06x faster                                           |
| genshi_xml      | 41.3 ms                                                         | 39.5 ms: 1.05x faster                                           |
| django_template | 27.6 ms                                                         | 27.8 ms: 1.01x slower                                           |
| mako            | 7.16 ms                                                         | 7.40 ms: 1.03x slower                                           |
| Geometric mean  | (ref)                                                           | 1.02x faster                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_memo_naive           | 36.1 ms                                                         | 11.5 ms: 3.13x faster                                           |
| thread_pipeline_naive       | 47.3 ms                                                         | 32.0 ms: 1.48x faster                                           |
| thread_montecarlo_naive     | 19.0 ms                                                         | 15.8 ms: 1.21x faster                                           |
| thread_montecarlo_optimized | 14.5 ms                                                         | 13.9 ms: 1.04x faster                                           |
| thread_counter_naive        | 20.6 ms                                                         | 20.2 ms: 1.02x faster                                           |
| thread_counter_optimized    | 16.5 ms                                                         | 17.1 ms: 1.03x slower                                           |
| thread_memo_optimized       | 15.3 ms                                                         | 15.9 ms: 1.04x slower                                           |
| thread_accumulate_naive     | 33.4 ms                                                         | 35.8 ms: 1.07x slower                                           |
| thread_pipeline_optimized   | 20.9 ms                                                         | 22.5 ms: 1.08x slower                                           |
| thread_accumulate_optimized | 32.3 ms                                                         | 35.1 ms: 1.08x slower                                           |
| thread_mandelbrot_naive     | 210 ms                                                          | 233 ms: 1.11x slower                                            |
| thread_mandelbrot_optimized | 208 ms                                                          | 233 ms: 1.12x slower                                            |
| Geometric mean              | (ref)                                                           | 1.11x faster                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 5.33 ms: 6.94x faster                                           |
| thread_memo_naive                | 36.1 ms                                                         | 11.5 ms: 3.13x faster                                           |
| base16_small                     | 740 us                                                          | 305 us: 2.42x faster                                            |
| mdp                              | 2.15 sec                                                        | 946 ms: 2.27x faster                                            |
| async_tree_memoization_tg        | 419 ms                                                          | 277 ms: 1.51x faster                                            |
| thread_pipeline_naive            | 47.3 ms                                                         | 32.0 ms: 1.48x faster                                           |
| deepcopy_memo                    | 26.5 us                                                         | 18.0 us: 1.47x faster                                           |
| async_tree_io_tg                 | 778 ms                                                          | 539 ms: 1.44x faster                                            |
| deepcopy                         | 269 us                                                          | 193 us: 1.40x faster                                            |
| async_tree_io                    | 741 ms                                                          | 531 ms: 1.40x faster                                            |
| go                               | 117 ms                                                          | 84.7 ms: 1.38x faster                                           |
| async_tree_memoization           | 388 ms                                                          | 281 ms: 1.38x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 552 ms: 1.36x faster                                            |
| async_tree_none                  | 308 ms                                                          | 228 ms: 1.35x faster                                            |
| async_tree_eager_io_tg           | 728 ms                                                          | 550 ms: 1.32x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 223 ms: 1.30x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 180 ms: 1.22x faster                                            |
| float                            | 57.0 ms                                                         | 47.3 ms: 1.21x faster                                           |
| thread_montecarlo_naive          | 19.0 ms                                                         | 15.8 ms: 1.21x faster                                           |
| deepcopy_reduce                  | 2.40 us                                                         | 2.00 us: 1.20x faster                                           |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 410 ms: 1.19x faster                                            |
| regex_effbot                     | 2.30 ms                                                         | 1.95 ms: 1.18x faster                                           |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 407 ms: 1.16x faster                                            |
| richards                         | 37.8 ms                                                         | 32.6 ms: 1.16x faster                                           |
| richards_super                   | 42.8 ms                                                         | 37.4 ms: 1.15x faster                                           |
| scimark_monte_carlo              | 46.5 ms                                                         | 40.7 ms: 1.14x faster                                           |
| pyflate                          | 342 ms                                                          | 299 ms: 1.14x faster                                            |
| tomli_loads                      | 1.62 sec                                                        | 1.44 sec: 1.12x faster                                          |
| pprint_safe_repr                 | 530 ms                                                          | 474 ms: 1.12x faster                                            |
| xml_etree_parse                  | 104 ms                                                          | 94.3 ms: 1.11x faster                                           |
| pprint_pformat                   | 1.09 sec                                                        | 989 ms: 1.10x faster                                            |
| html5lib                         | 51.7 ms                                                         | 46.9 ms: 1.10x faster                                           |
| async_tree_eager                 | 89.6 ms                                                         | 81.3 ms: 1.10x faster                                           |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.00 sec: 1.10x faster                                          |
| thrift                           | 2.02 ms                                                         | 1.86 ms: 1.08x faster                                           |
| regex_dna                        | 162 ms                                                          | 150 ms: 1.08x faster                                            |
| ascii85_large                    | 717 ms                                                          | 667 ms: 1.07x faster                                            |
| ascii85_small                    | 13.6 ms                                                         | 12.7 ms: 1.07x faster                                           |
| decimal_pi                       | 222 ms                                                          | 208 ms: 1.07x faster                                            |
| genshi_text                      | 17.8 ms                                                         | 16.8 ms: 1.06x faster                                           |
| noop                             | 20.5 ns                                                         | 19.4 ns: 1.06x faster                                           |
| xdsl_constant_fold               | 36.7 ms                                                         | 34.7 ms: 1.06x faster                                           |
| async_generators                 | 240 ms                                                          | 228 ms: 1.05x faster                                            |
| unpack_sequence                  | 27.1 ns                                                         | 25.8 ns: 1.05x faster                                           |
| sqlglot_v2_parse                 | 958 us                                                          | 911 us: 1.05x faster                                            |
| pylint                           | 227 ms                                                          | 216 ms: 1.05x faster                                            |
| quadtree_nbody                   | 626 ms                                                          | 596 ms: 1.05x faster                                            |
| xml_etree_iterparse              | 79.9 ms                                                         | 76.2 ms: 1.05x faster                                           |
| regex_compile                    | 98.5 ms                                                         | 93.9 ms: 1.05x faster                                           |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.15 ms: 1.05x faster                                           |
| hexiom                           | 4.30 ms                                                         | 4.11 ms: 1.05x faster                                           |
| genshi_xml                       | 41.3 ms                                                         | 39.5 ms: 1.05x faster                                           |
| chameleon                        | 9.95 ms                                                         | 9.52 ms: 1.05x faster                                           |
| generators                       | 21.2 ms                                                         | 20.3 ms: 1.04x faster                                           |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 13.9 ms: 1.04x faster                                           |
| telco                            | 5.83 ms                                                         | 5.59 ms: 1.04x faster                                           |
| networkx_k_core                  | 2.16 sec                                                        | 2.07 sec: 1.04x faster                                          |
| scimark_sor                      | 78.9 ms                                                         | 75.7 ms: 1.04x faster                                           |
| xml_etree_process                | 46.6 ms                                                         | 44.7 ms: 1.04x faster                                           |
| unpickle                         | 10.5 us                                                         | 10.2 us: 1.03x faster                                           |
| chaos                            | 45.1 ms                                                         | 43.8 ms: 1.03x faster                                           |
| deltablue                        | 2.41 ms                                                         | 2.34 ms: 1.03x faster                                           |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 314 ms: 1.03x faster                                            |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 78.2 ms: 1.03x faster                                           |
| sympy_integrate                  | 15.8 ms                                                         | 15.4 ms: 1.03x faster                                           |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 39.0 ms: 1.03x faster                                           |
| regex_v8                         | 15.2 ms                                                         | 14.8 ms: 1.03x faster                                           |
| asyncio_websockets               | 303 ms                                                          | 296 ms: 1.02x faster                                            |
| xml_etree_generate               | 64.2 ms                                                         | 62.6 ms: 1.02x faster                                           |
| json                             | 3.51 ms                                                         | 3.42 ms: 1.02x faster                                           |
| decimal_factorial                | 177 ms                                                          | 173 ms: 1.02x faster                                            |
| pickle_dict                      | 22.0 us                                                         | 21.5 us: 1.02x faster                                           |
| thread_counter_naive             | 20.6 ms                                                         | 20.2 ms: 1.02x faster                                           |
| base85_large                     | 252 ms                                                          | 248 ms: 1.02x faster                                            |
| coroutines                       | 15.4 ms                                                         | 15.1 ms: 1.02x faster                                           |
| base32_small                     | 5.79 ms                                                         | 5.71 ms: 1.02x faster                                           |
| sympy_str                        | 197 ms                                                          | 194 ms: 1.02x faster                                            |
| sympy_expand                     | 336 ms                                                          | 332 ms: 1.01x faster                                            |
| python_startup_no_site           | 6.46 ms                                                         | 6.38 ms: 1.01x faster                                           |
| comprehensions                   | 10.9 us                                                         | 10.8 us: 1.01x faster                                           |
| base32_large                     | 296 ms                                                          | 292 ms: 1.01x faster                                            |
| typing_runtime_protocols         | 113 us                                                          | 112 us: 1.01x faster                                            |
| pycparser                        | 860 ms                                                          | 851 ms: 1.01x faster                                            |
| fastapi_http                     | 218 ms                                                          | 216 ms: 1.01x faster                                            |
| scimark_lu                       | 74.5 ms                                                         | 73.8 ms: 1.01x faster                                           |
| raytrace                         | 195 ms                                                          | 194 ms: 1.01x faster                                            |
| spectral_norm                    | 65.9 ms                                                         | 65.6 ms: 1.00x faster                                           |
| meteor_contest                   | 84.4 ms                                                         | 84.1 ms: 1.00x faster                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.28 sec: 1.00x faster                                          |
| pidigits                         | 189 ms                                                          | 189 ms: 1.00x slower                                            |
| unpickle_pure_python             | 151 us                                                          | 152 us: 1.01x slower                                            |
| django_template                  | 27.6 ms                                                         | 27.8 ms: 1.01x slower                                           |
| urlsafe_base64_small             | 325 us                                                          | 329 us: 1.01x slower                                            |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.18 ms: 1.01x slower                                           |
| pathlib                          | 12.8 ms                                                         | 13.0 ms: 1.02x slower                                           |
| logging_simple                   | 4.71 us                                                         | 4.79 us: 1.02x slower                                           |
| networkx_shortest_path           | 437 ms                                                          | 444 ms: 1.02x slower                                            |
| logging_format                   | 5.25 us                                                         | 5.35 us: 1.02x slower                                           |
| sqlalchemy_imperative            | 13.9 ms                                                         | 14.2 ms: 1.02x slower                                           |
| base85_small                     | 4.59 ms                                                         | 4.69 ms: 1.02x slower                                           |
| asyncio_tcp                      | 318 ms                                                          | 325 ms: 1.02x slower                                            |
| python_startup                   | 9.51 ms                                                         | 9.73 ms: 1.02x slower                                           |
| unpickle_list                    | 3.33 us                                                         | 3.43 us: 1.03x slower                                           |
| networkx_connected_components    | 425 ms                                                          | 438 ms: 1.03x slower                                            |
| coverage                         | 55.8 ms                                                         | 57.4 ms: 1.03x slower                                           |
| nbody                            | 65.9 ms                                                         | 67.9 ms: 1.03x slower                                           |
| docutils                         | 1.89 sec                                                        | 1.95 sec: 1.03x slower                                          |
| pickle_list                      | 3.14 us                                                         | 3.24 us: 1.03x slower                                           |
| mako                             | 7.16 ms                                                         | 7.40 ms: 1.03x slower                                           |
| thread_counter_optimized         | 16.5 ms                                                         | 17.1 ms: 1.03x slower                                           |
| mypy2                            | 724 ms                                                          | 753 ms: 1.04x slower                                            |
| thread_memo_optimized            | 15.3 ms                                                         | 15.9 ms: 1.04x slower                                           |
| base64_small                     | 177 us                                                          | 186 us: 1.05x slower                                            |
| nqueens                          | 53.6 ms                                                         | 56.8 ms: 1.06x slower                                           |
| gc_traversal                     | 3.07 ms                                                         | 3.26 ms: 1.06x slower                                           |
| crypto_pyaes                     | 50.9 ms                                                         | 54.5 ms: 1.07x slower                                           |
| thread_accumulate_naive          | 33.4 ms                                                         | 35.8 ms: 1.07x slower                                           |
| logging_silent                   | 61.0 ns                                                         | 65.3 ns: 1.07x slower                                           |
| pickle_pure_python               | 223 us                                                          | 240 us: 1.07x slower                                            |
| thread_pipeline_optimized        | 20.9 ms                                                         | 22.5 ms: 1.08x slower                                           |
| json_loads                       | 16.2 us                                                         | 17.5 us: 1.08x slower                                           |
| thread_accumulate_optimized      | 32.3 ms                                                         | 35.1 ms: 1.08x slower                                           |
| base64_large                     | 3.33 ms                                                         | 3.63 ms: 1.09x slower                                           |
| pickle                           | 7.44 us                                                         | 8.20 us: 1.10x slower                                           |
| thread_mandelbrot_naive          | 210 ms                                                          | 233 ms: 1.11x slower                                            |
| thread_mandelbrot_optimized      | 208 ms                                                          | 233 ms: 1.12x slower                                            |
| create_gc_cycles                 | 1.75 ms                                                         | 1.96 ms: 1.12x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 363 ms: 1.27x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 236 ms: 1.35x slower                                            |
| argparse_subparsers              | 452 us                                                          | 686 us: 1.52x slower                                            |
| argparse_many_optionals          | 12.8 ms                                                         | 34.4 ms: 2.68x slower                                           |
| async_tree_eager_tg              | 58.6 ms                                                         | 182 ms: 3.11x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.06x faster                                                    |

Benchmark hidden because not significant (5): fannkuch, sympy_sum, scimark_fft, json_dumps, tornado_http

- Geometric mean (including insignificant results): 1.063x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.01x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.09x