# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.093x faster
- HPT reliability: 67.60%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.58x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 11.8 ms: 1.08x slower                                            |
| docutils       | 1.98 sec                                                         | 2.09 sec: 1.06x slower                                           |
| fastapi_http   | 215 ms                                                           | 183 ms: 1.17x faster                                             |
| html5lib       | 49.1 ms                                                          | 45.4 ms: 1.08x faster                                            |
| tornado_http   | 99.2 ms                                                          | 94.9 ms: 1.05x faster                                            |
| Geometric mean | (ref)                                                            | 1.03x faster                                                     |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_io_tg                 | 777 ms                                                           | 484 ms: 1.60x faster                                             |
| async_tree_memoization_tg        | 417 ms                                                           | 273 ms: 1.53x faster                                             |
| async_tree_eager_io_tg           | 724 ms                                                           | 477 ms: 1.52x faster                                             |
| async_tree_io                    | 741 ms                                                           | 507 ms: 1.46x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 518 ms: 1.44x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 210 ms: 1.38x faster                                             |
| async_tree_none                  | 310 ms                                                           | 236 ms: 1.31x faster                                             |
| async_tree_memoization           | 389 ms                                                           | 299 ms: 1.30x faster                                             |
| coroutines                       | 17.6 ms                                                          | 14.7 ms: 1.20x faster                                            |
| async_tree_eager_memoization     | 215 ms                                                           | 182 ms: 1.18x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 461 ms: 1.14x faster                                             |
| asyncio_tcp                      | 326 ms                                                           | 300 ms: 1.09x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 486 ms: 1.06x faster                                             |
| asyncio_websockets               | 304 ms                                                           | 289 ms: 1.05x faster                                             |
| async_generators                 | 262 ms                                                           | 264 ms: 1.01x slower                                             |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 372 ms: 1.03x slower                                             |
| async_tree_eager                 | 90.0 ms                                                          | 93.0 ms: 1.03x slower                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.39 sec: 1.07x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 442 ms: 1.38x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 252 ms: 1.46x slower                                             |
| async_tree_eager_tg              | 58.6 ms                                                          | 188 ms: 3.21x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.08x faster                                                     |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 20.1 ns: 1.01x faster                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                           | 186 ms: 1.08x slower                                             |
| decimal_pi        | 210 ms                                                           | 238 ms: 1.14x slower                                             |
| Geometric mean    | (ref)                                                            | 1.11x slower                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 53.5 ms: 1.06x faster                                            |
| pidigits       | 181 ms                                                           | 178 ms: 1.02x faster                                             |
| nbody          | 66.8 ms                                                          | 82.4 ms: 1.23x slower                                            |
| Geometric mean | (ref)                                                            | 1.03x slower                                                     |

Benchmark hidden because not significant (1): quadtree_nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.91 ms: 1.05x faster                                            |
| regex_dna      | 144 ms                                                           | 144 ms: 1.01x slower                                             |
| regex_v8       | 14.7 ms                                                          | 14.8 ms: 1.01x slower                                            |
| regex_compile  | 97.7 ms                                                          | 101 ms: 1.04x slower                                             |
| Geometric mean | (ref)                                                            | 1.00x slower                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.35 ms: 5.90x faster                                            |
| base16_small         | 656 us                                                           | 295 us: 2.23x faster                                             |
| base64_large         | 6.32 ms                                                          | 4.97 ms: 1.27x faster                                            |
| ascii85_large        | 814 ms                                                           | 743 ms: 1.10x faster                                             |
| ascii85_small        | 15.5 ms                                                          | 14.2 ms: 1.09x faster                                            |
| base64_small         | 228 us                                                           | 210 us: 1.09x faster                                             |
| tomli_loads          | 1.63 sec                                                         | 1.51 sec: 1.08x faster                                           |
| xml_etree_iterparse  | 69.6 ms                                                          | 65.8 ms: 1.06x faster                                            |
| urlsafe_base64_small | 379 us                                                           | 361 us: 1.05x faster                                             |
| xml_etree_parse      | 107 ms                                                           | 106 ms: 1.02x faster                                             |
| pickle_dict          | 21.9 us                                                          | 21.5 us: 1.01x faster                                            |
| unpickle_pure_python | 149 us                                                           | 158 us: 1.06x slower                                             |
| base85_small         | 4.41 ms                                                          | 4.70 ms: 1.07x slower                                            |
| json_dumps           | 7.49 ms                                                          | 8.00 ms: 1.07x slower                                            |
| base32_small         | 5.69 ms                                                          | 6.10 ms: 1.07x slower                                            |
| pickle_pure_python   | 223 us                                                           | 239 us: 1.07x slower                                             |
| base32_large         | 286 ms                                                           | 307 ms: 1.07x slower                                             |
| base85_large         | 243 ms                                                           | 264 ms: 1.09x slower                                             |
| unpickle             | 10.3 us                                                          | 11.3 us: 1.10x slower                                            |
| pickle               | 8.22 us                                                          | 9.13 us: 1.11x slower                                            |
| xml_etree_process    | 48.1 ms                                                          | 54.3 ms: 1.13x slower                                            |
| xml_etree_generate   | 66.3 ms                                                          | 75.1 ms: 1.13x slower                                            |
| pickle_list          | 3.03 us                                                          | 3.91 us: 1.29x slower                                            |
| unpickle_list        | 3.45 us                                                          | 4.54 us: 1.32x slower                                            |
| json_loads           | 16.7 us                                                          | 24.9 us: 1.49x slower                                            |
| Geometric mean       | (ref)                                                            | 1.06x faster                                                     |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup         | 9.38 ms                                                          | 11.7 ms: 1.25x slower                                            |
| python_startup_no_site | 6.36 ms                                                          | 8.17 ms: 1.28x slower                                            |
| Geometric mean         | (ref)                                                            | 1.27x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| genshi_xml      | 39.7 ms                                                          | 41.8 ms: 1.05x slower                                            |
| genshi_text     | 17.6 ms                                                          | 19.4 ms: 1.10x slower                                            |
| django_template | 27.3 ms                                                          | 31.2 ms: 1.14x slower                                            |
| mako            | 7.43 ms                                                          | 11.9 ms: 1.60x slower                                            |
| Geometric mean  | (ref)                                                            | 1.21x slower                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_counter_optimized    | 18.7 ms                                                          | 5.21 ms: 3.59x faster                                            |
| thread_pipeline_optimized   | 25.6 ms                                                          | 7.14 ms: 3.59x faster                                            |
| thread_mandelbrot_naive     | 220 ms                                                           | 61.6 ms: 3.57x faster                                            |
| thread_accumulate_optimized | 39.8 ms                                                          | 11.2 ms: 3.53x faster                                            |
| thread_mandelbrot_optimized | 218 ms                                                           | 62.2 ms: 3.50x faster                                            |
| thread_memo_optimized       | 18.2 ms                                                          | 6.05 ms: 3.01x faster                                            |
| thread_montecarlo_optimized | 13.3 ms                                                          | 4.46 ms: 2.98x faster                                            |
| thread_accumulate_naive     | 40.9 ms                                                          | 13.7 ms: 2.97x faster                                            |
| thread_pipeline_naive       | 52.1 ms                                                          | 26.9 ms: 1.94x faster                                            |
| thread_memo_naive           | 39.0 ms                                                          | 23.9 ms: 1.63x faster                                            |
| thread_counter_naive        | 22.6 ms                                                          | 21.0 ms: 1.08x faster                                            |
| thread_montecarlo_naive     | 17.8 ms                                                          | 25.3 ms: 1.42x slower                                            |
| Geometric mean              | (ref)                                                            | 2.40x faster                                                     |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.35 ms: 5.90x faster                                            |
| thread_counter_optimized         | 18.7 ms                                                          | 5.21 ms: 3.59x faster                                            |
| thread_pipeline_optimized        | 25.6 ms                                                          | 7.14 ms: 3.59x faster                                            |
| thread_mandelbrot_naive          | 220 ms                                                           | 61.6 ms: 3.57x faster                                            |
| thread_accumulate_optimized      | 39.8 ms                                                          | 11.2 ms: 3.53x faster                                            |
| thread_mandelbrot_optimized      | 218 ms                                                           | 62.2 ms: 3.50x faster                                            |
| thread_memo_optimized            | 18.2 ms                                                          | 6.05 ms: 3.01x faster                                            |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 4.46 ms: 2.98x faster                                            |
| thread_accumulate_naive          | 40.9 ms                                                          | 13.7 ms: 2.97x faster                                            |
| base16_small                     | 656 us                                                           | 295 us: 2.23x faster                                             |
| gc_traversal                     | 3.16 ms                                                          | 1.46 ms: 2.17x faster                                            |
| mdp                              | 2.11 sec                                                         | 974 ms: 2.17x faster                                             |
| thread_pipeline_naive            | 52.1 ms                                                          | 26.9 ms: 1.94x faster                                            |
| argparse_many_optionals          | 12.6 ms                                                          | 7.63 ms: 1.65x faster                                            |
| thread_memo_naive                | 39.0 ms                                                          | 23.9 ms: 1.63x faster                                            |
| async_tree_io_tg                 | 777 ms                                                           | 484 ms: 1.60x faster                                             |
| async_tree_memoization_tg        | 417 ms                                                           | 273 ms: 1.53x faster                                             |
| async_tree_eager_io_tg           | 724 ms                                                           | 477 ms: 1.52x faster                                             |
| async_tree_io                    | 741 ms                                                           | 507 ms: 1.46x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 518 ms: 1.44x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 210 ms: 1.38x faster                                             |
| go                               | 121 ms                                                           | 90.5 ms: 1.34x faster                                            |
| create_gc_cycles                 | 1.70 ms                                                          | 1.29 ms: 1.31x faster                                            |
| async_tree_none                  | 310 ms                                                           | 236 ms: 1.31x faster                                             |
| async_tree_memoization           | 389 ms                                                           | 299 ms: 1.30x faster                                             |
| base64_large                     | 6.32 ms                                                          | 4.97 ms: 1.27x faster                                            |
| deepcopy                         | 267 us                                                           | 213 us: 1.25x faster                                             |
| deepcopy_memo                    | 26.6 us                                                          | 21.6 us: 1.23x faster                                            |
| scimark_sor                      | 97.0 ms                                                          | 80.9 ms: 1.20x faster                                            |
| coroutines                       | 17.6 ms                                                          | 14.7 ms: 1.20x faster                                            |
| async_tree_eager_memoization     | 215 ms                                                           | 182 ms: 1.18x faster                                             |
| fastapi_http                     | 215 ms                                                           | 183 ms: 1.17x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 461 ms: 1.14x faster                                             |
| thrift                           | 2.07 ms                                                          | 1.89 ms: 1.10x faster                                            |
| ascii85_large                    | 814 ms                                                           | 743 ms: 1.10x faster                                             |
| ascii85_small                    | 15.5 ms                                                          | 14.2 ms: 1.09x faster                                            |
| asyncio_tcp                      | 326 ms                                                           | 300 ms: 1.09x faster                                             |
| pycparser                        | 884 ms                                                           | 812 ms: 1.09x faster                                             |
| base64_small                     | 228 us                                                           | 210 us: 1.09x faster                                             |
| html5lib                         | 49.1 ms                                                          | 45.4 ms: 1.08x faster                                            |
| tomli_loads                      | 1.63 sec                                                         | 1.51 sec: 1.08x faster                                           |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.16 sec: 1.08x faster                                           |
| thread_counter_naive             | 22.6 ms                                                          | 21.0 ms: 1.08x faster                                            |
| pyflate                          | 358 ms                                                           | 336 ms: 1.07x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 486 ms: 1.06x faster                                             |
| float                            | 56.6 ms                                                          | 53.5 ms: 1.06x faster                                            |
| xml_etree_iterparse              | 69.6 ms                                                          | 65.8 ms: 1.06x faster                                            |
| asyncio_websockets               | 304 ms                                                           | 289 ms: 1.05x faster                                             |
| urlsafe_base64_small             | 379 us                                                           | 361 us: 1.05x faster                                             |
| regex_effbot                     | 1.99 ms                                                          | 1.91 ms: 1.05x faster                                            |
| tornado_http                     | 99.2 ms                                                          | 94.9 ms: 1.05x faster                                            |
| pprint_safe_repr                 | 541 ms                                                           | 521 ms: 1.04x faster                                             |
| generators                       | 22.0 ms                                                          | 21.2 ms: 1.04x faster                                            |
| deepcopy_reduce                  | 2.37 us                                                          | 2.29 us: 1.04x faster                                            |
| pylint                           | 226 ms                                                           | 219 ms: 1.03x faster                                             |
| pprint_pformat                   | 1.11 sec                                                         | 1.08 sec: 1.02x faster                                           |
| pathlib                          | 12.4 ms                                                          | 12.2 ms: 1.02x faster                                            |
| xml_etree_parse                  | 107 ms                                                           | 106 ms: 1.02x faster                                             |
| pidigits                         | 181 ms                                                           | 178 ms: 1.02x faster                                             |
| pickle_dict                      | 21.9 us                                                          | 21.5 us: 1.01x faster                                            |
| noop                             | 20.4 ns                                                          | 20.1 ns: 1.01x faster                                            |
| hexiom                           | 4.42 ms                                                          | 4.40 ms: 1.00x faster                                            |
| regex_dna                        | 144 ms                                                           | 144 ms: 1.01x slower                                             |
| regex_v8                         | 14.7 ms                                                          | 14.8 ms: 1.01x slower                                            |
| async_generators                 | 262 ms                                                           | 264 ms: 1.01x slower                                             |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 40.5 ms: 1.01x slower                                            |
| chaos                            | 45.0 ms                                                          | 45.6 ms: 1.01x slower                                            |
| logging_silent                   | 60.6 ns                                                          | 62.2 ns: 1.03x slower                                            |
| scimark_monte_carlo              | 44.3 ms                                                          | 45.5 ms: 1.03x slower                                            |
| sympy_integrate                  | 15.4 ms                                                          | 15.9 ms: 1.03x slower                                            |
| richards_super                   | 41.3 ms                                                          | 42.7 ms: 1.03x slower                                            |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 372 ms: 1.03x slower                                             |
| async_tree_eager                 | 90.0 ms                                                          | 93.0 ms: 1.03x slower                                            |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 81.9 ms: 1.04x slower                                            |
| regex_compile                    | 97.7 ms                                                          | 101 ms: 1.04x slower                                             |
| genshi_xml                       | 39.7 ms                                                          | 41.8 ms: 1.05x slower                                            |
| scimark_fft                      | 211 ms                                                           | 222 ms: 1.05x slower                                             |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.26 ms: 1.05x slower                                            |
| spectral_norm                    | 64.1 ms                                                          | 67.6 ms: 1.06x slower                                            |
| sympy_sum                        | 104 ms                                                           | 110 ms: 1.06x slower                                             |
| docutils                         | 1.98 sec                                                         | 2.09 sec: 1.06x slower                                           |
| xdsl_constant_fold               | 36.7 ms                                                          | 38.8 ms: 1.06x slower                                            |
| sympy_str                        | 193 ms                                                           | 206 ms: 1.06x slower                                             |
| unpickle_pure_python             | 149 us                                                           | 158 us: 1.06x slower                                             |
| base85_small                     | 4.41 ms                                                          | 4.70 ms: 1.07x slower                                            |
| json_dumps                       | 7.49 ms                                                          | 8.00 ms: 1.07x slower                                            |
| base32_small                     | 5.69 ms                                                          | 6.10 ms: 1.07x slower                                            |
| pickle_pure_python               | 223 us                                                           | 239 us: 1.07x slower                                             |
| nqueens                          | 57.3 ms                                                          | 61.5 ms: 1.07x slower                                            |
| base32_large                     | 286 ms                                                           | 307 ms: 1.07x slower                                             |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.39 sec: 1.07x slower                                           |
| sympy_expand                     | 330 ms                                                           | 356 ms: 1.08x slower                                             |
| decimal_factorial                | 173 ms                                                           | 186 ms: 1.08x slower                                             |
| chameleon                        | 10.9 ms                                                          | 11.8 ms: 1.08x slower                                            |
| raytrace                         | 199 ms                                                           | 215 ms: 1.08x slower                                             |
| networkx_k_core                  | 2.15 sec                                                         | 2.33 sec: 1.08x slower                                           |
| sqlglot_v2_parse                 | 953 us                                                           | 1.03 ms: 1.08x slower                                            |
| meteor_contest                   | 89.9 ms                                                          | 97.5 ms: 1.08x slower                                            |
| base85_large                     | 243 ms                                                           | 264 ms: 1.09x slower                                             |
| sqlalchemy_imperative            | 13.8 ms                                                          | 15.2 ms: 1.10x slower                                            |
| fannkuch                         | 265 ms                                                           | 291 ms: 1.10x slower                                             |
| comprehensions                   | 11.6 us                                                          | 12.8 us: 1.10x slower                                            |
| genshi_text                      | 17.6 ms                                                          | 19.4 ms: 1.10x slower                                            |
| unpickle                         | 10.3 us                                                          | 11.3 us: 1.10x slower                                            |
| scimark_lu                       | 70.2 ms                                                          | 77.7 ms: 1.11x slower                                            |
| logging_format                   | 5.23 us                                                          | 5.80 us: 1.11x slower                                            |
| pickle                           | 8.22 us                                                          | 9.13 us: 1.11x slower                                            |
| logging_simple                   | 4.60 us                                                          | 5.14 us: 1.12x slower                                            |
| xml_etree_process                | 48.1 ms                                                          | 54.3 ms: 1.13x slower                                            |
| xml_etree_generate               | 66.3 ms                                                          | 75.1 ms: 1.13x slower                                            |
| decimal_pi                       | 210 ms                                                           | 238 ms: 1.14x slower                                             |
| django_template                  | 27.3 ms                                                          | 31.2 ms: 1.14x slower                                            |
| networkx_connected_components    | 460 ms                                                           | 535 ms: 1.16x slower                                             |
| argparse_subparsers              | 446 us                                                           | 523 us: 1.17x slower                                             |
| telco                            | 5.50 ms                                                          | 6.49 ms: 1.18x slower                                            |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 3.16 ms: 1.19x slower                                            |
| mypy2                            | 726 ms                                                           | 868 ms: 1.20x slower                                             |
| networkx_shortest_path           | 464 ms                                                           | 555 ms: 1.20x slower                                             |
| unpack_sequence                  | 26.2 ns                                                          | 31.4 ns: 1.20x slower                                            |
| json                             | 3.49 ms                                                          | 4.20 ms: 1.20x slower                                            |
| typing_runtime_protocols         | 106 us                                                           | 128 us: 1.21x slower                                             |
| nbody                            | 66.8 ms                                                          | 82.4 ms: 1.23x slower                                            |
| python_startup                   | 9.38 ms                                                          | 11.7 ms: 1.25x slower                                            |
| crypto_pyaes                     | 50.0 ms                                                          | 62.6 ms: 1.25x slower                                            |
| python_startup_no_site           | 6.36 ms                                                          | 8.17 ms: 1.28x slower                                            |
| pickle_list                      | 3.03 us                                                          | 3.91 us: 1.29x slower                                            |
| unpickle_list                    | 3.45 us                                                          | 4.54 us: 1.32x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 442 ms: 1.38x slower                                             |
| coverage                         | 52.2 ms                                                          | 73.6 ms: 1.41x slower                                            |
| thread_montecarlo_naive          | 17.8 ms                                                          | 25.3 ms: 1.42x slower                                            |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 252 ms: 1.46x slower                                             |
| json_loads                       | 16.7 us                                                          | 24.9 us: 1.49x slower                                            |
| mako                             | 7.43 ms                                                          | 11.9 ms: 1.60x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                          | 188 ms: 3.21x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.09x faster                                                     |

Benchmark hidden because not significant (3): deltablue, quadtree_nbody, richards

- Geometric mean (including insignificant results): 1.093x faster

# HPT report

- Reliability score: 67.60% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.58x