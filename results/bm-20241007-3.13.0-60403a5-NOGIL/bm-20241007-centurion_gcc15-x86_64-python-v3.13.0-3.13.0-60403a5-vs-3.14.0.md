# Results vs. 3.14.0

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.239x slower
- HPT reliability: 100.00%
- HPT 99th percentile: 1.26x slower
- Memory change: 1.36x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 17.1 ms: 1.61x slower                                            |
| docutils       | 2.02 sec                                                         | 2.41 sec: 1.19x slower                                           |
| fastapi_http   | 215 ms                                                           | 290 ms: 1.35x slower                                             |
| html5lib       | 45.5 ms                                                          | 67.6 ms: 1.49x slower                                            |
| tornado_http   | 101 ms                                                           | 111 ms: 1.11x slower                                             |
| Geometric mean | (ref)                                                            | 1.34x slower                                                     |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_eager_tg              | 179 ms                                                           | 92.3 ms: 1.94x faster                                            |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 197 ms: 1.19x faster                                             |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 347 ms: 1.11x faster                                             |
| asyncio_websockets               | 305 ms                                                           | 296 ms: 1.03x faster                                             |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.44 sec: 1.12x slower                                           |
| asyncio_tcp                      | 332 ms                                                           | 378 ms: 1.14x slower                                             |
| async_tree_eager_io_tg           | 549 ms                                                           | 644 ms: 1.17x slower                                             |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 392 ms: 1.18x slower                                             |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 532 ms: 1.22x slower                                             |
| coroutines                       | 15.4 ms                                                          | 19.4 ms: 1.26x slower                                            |
| async_tree_eager_io              | 548 ms                                                           | 697 ms: 1.27x slower                                             |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 561 ms: 1.30x slower                                             |
| async_tree_io_tg                 | 529 ms                                                           | 695 ms: 1.31x slower                                             |
| async_tree_io                    | 527 ms                                                           | 734 ms: 1.39x slower                                             |
| async_tree_none_tg               | 221 ms                                                           | 309 ms: 1.40x slower                                             |
| async_tree_eager_memoization     | 175 ms                                                           | 251 ms: 1.43x slower                                             |
| async_tree_memoization_tg        | 275 ms                                                           | 395 ms: 1.44x slower                                             |
| async_generators                 | 243 ms                                                           | 364 ms: 1.50x slower                                             |
| async_tree_memoization           | 274 ms                                                           | 419 ms: 1.53x slower                                             |
| async_tree_none                  | 223 ms                                                           | 349 ms: 1.56x slower                                             |
| async_tree_eager                 | 78.8 ms                                                          | 133 ms: 1.69x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.21x slower                                                     |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 24.9 ns: 1.33x slower                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 185 ms: 1.09x slower                                             |
| decimal_pi        | 201 ms                                                           | 232 ms: 1.15x slower                                             |
| Geometric mean    | (ref)                                                            | 1.12x slower                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| pidigits       | 181 ms                                                           | 180 ms: 1.01x faster                                             |
| nbody          | 67.2 ms                                                          | 131 ms: 1.96x slower                                             |
| float          | 48.1 ms                                                          | 95.0 ms: 1.98x slower                                            |
| quadtree_nbody | 602 ms                                                           | 1.36 sec: 2.26x slower                                           |
| Geometric mean | (ref)                                                            | 1.71x slower                                                     |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                          | 15.4 ms: 1.02x slower                                            |
| regex_dna      | 141 ms                                                           | 147 ms: 1.05x slower                                             |
| regex_effbot   | 1.80 ms                                                          | 1.99 ms: 1.11x slower                                            |
| regex_compile  | 91.6 ms                                                          | 146 ms: 1.59x slower                                             |
| Geometric mean | (ref)                                                            | 1.17x slower                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| pickle               | 9.23 us                                                          | 8.26 us: 1.12x faster                                            |
| xml_etree_iterparse  | 76.5 ms                                                          | 69.3 ms: 1.10x faster                                            |
| pickle_list          | 3.26 us                                                          | 3.13 us: 1.04x faster                                            |
| xml_etree_parse      | 102 ms                                                           | 99.7 ms: 1.02x faster                                            |
| base64_large         | 6.31 ms                                                          | 6.33 ms: 1.00x slower                                            |
| pickle_dict          | 21.3 us                                                          | 21.6 us: 1.01x slower                                            |
| unpickle             | 10.3 us                                                          | 10.9 us: 1.05x slower                                            |
| xml_etree_generate   | 71.1 ms                                                          | 76.6 ms: 1.08x slower                                            |
| json_loads           | 17.3 us                                                          | 18.9 us: 1.09x slower                                            |
| base32_large         | 276 ms                                                           | 325 ms: 1.18x slower                                             |
| unpickle_list        | 3.64 us                                                          | 4.38 us: 1.20x slower                                            |
| json_dumps           | 7.37 ms                                                          | 8.96 ms: 1.22x slower                                            |
| base32_small         | 5.43 ms                                                          | 6.64 ms: 1.22x slower                                            |
| xml_etree_process    | 50.0 ms                                                          | 63.1 ms: 1.26x slower                                            |
| base85_large         | 233 ms                                                           | 315 ms: 1.36x slower                                             |
| base85_small         | 4.44 ms                                                          | 6.04 ms: 1.36x slower                                            |
| base64_small         | 230 us                                                           | 320 us: 1.39x slower                                             |
| urlsafe_base64_small | 383 us                                                           | 541 us: 1.41x slower                                             |
| ascii85_large        | 651 ms                                                           | 966 ms: 1.48x slower                                             |
| ascii85_small        | 12.5 ms                                                          | 18.7 ms: 1.50x slower                                            |
| tomli_loads          | 1.41 sec                                                         | 2.19 sec: 1.56x slower                                           |
| unpickle_pure_python | 153 us                                                           | 250 us: 1.63x slower                                             |
| pickle_pure_python   | 234 us                                                           | 394 us: 1.68x slower                                             |
| base16_small         | 298 us                                                           | 830 us: 2.79x slower                                             |
| base16_large         | 5.41 ms                                                          | 30.7 ms: 5.68x slower                                            |
| Geometric mean       | (ref)                                                            | 1.34x slower                                                     |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 11.3 ms: 1.18x slower                                            |
| python_startup_no_site | 6.29 ms                                                          | 7.84 ms: 1.25x slower                                            |
| Geometric mean         | (ref)                                                            | 1.21x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| genshi_xml      | 38.4 ms                                                          | 54.6 ms: 1.42x slower                                            |
| django_template | 28.4 ms                                                          | 44.8 ms: 1.58x slower                                            |
| genshi_text     | 16.4 ms                                                          | 27.9 ms: 1.70x slower                                            |
| mako            | 7.66 ms                                                          | 14.3 ms: 1.86x slower                                            |
| Geometric mean  | (ref)                                                            | 1.63x slower                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_accumulate_optimized | 40.8 ms                                                          | 11.8 ms: 3.45x faster                                            |
| thread_pipeline_optimized   | 26.3 ms                                                          | 7.67 ms: 3.43x faster                                            |
| thread_mandelbrot_optimized | 215 ms                                                           | 65.1 ms: 3.30x faster                                            |
| thread_mandelbrot_naive     | 217 ms                                                           | 66.1 ms: 3.28x faster                                            |
| thread_accumulate_naive     | 41.6 ms                                                          | 13.0 ms: 3.19x faster                                            |
| thread_counter_optimized    | 18.7 ms                                                          | 6.68 ms: 2.79x faster                                            |
| thread_memo_optimized       | 17.9 ms                                                          | 6.85 ms: 2.62x faster                                            |
| thread_montecarlo_optimized | 12.6 ms                                                          | 5.39 ms: 2.34x faster                                            |
| thread_counter_naive        | 21.4 ms                                                          | 27.7 ms: 1.29x slower                                            |
| thread_pipeline_naive       | 35.4 ms                                                          | 50.9 ms: 1.44x slower                                            |
| thread_montecarlo_naive     | 14.6 ms                                                          | 60.8 ms: 4.16x slower                                            |
| thread_memo_naive           | 11.8 ms                                                          | 49.8 ms: 4.21x slower                                            |
| Geometric mean              | (ref)                                                            | 1.57x faster                                                     |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_accumulate_optimized      | 40.8 ms                                                          | 11.8 ms: 3.45x faster                                            |
| thread_pipeline_optimized        | 26.3 ms                                                          | 7.67 ms: 3.43x faster                                            |
| thread_mandelbrot_optimized      | 215 ms                                                           | 65.1 ms: 3.30x faster                                            |
| thread_mandelbrot_naive          | 217 ms                                                           | 66.1 ms: 3.28x faster                                            |
| thread_accumulate_naive          | 41.6 ms                                                          | 13.0 ms: 3.19x faster                                            |
| thread_counter_optimized         | 18.7 ms                                                          | 6.68 ms: 2.79x faster                                            |
| thread_memo_optimized            | 17.9 ms                                                          | 6.85 ms: 2.62x faster                                            |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 5.39 ms: 2.34x faster                                            |
| async_tree_eager_tg              | 179 ms                                                           | 92.3 ms: 1.94x faster                                            |
| argparse_many_optionals          | 33.3 ms                                                          | 18.7 ms: 1.78x faster                                            |
| gc_traversal                     | 3.33 ms                                                          | 2.45 ms: 1.36x faster                                            |
| argparse_subparsers              | 665 us                                                           | 548 us: 1.21x faster                                             |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 197 ms: 1.19x faster                                             |
| create_gc_cycles                 | 1.93 ms                                                          | 1.68 ms: 1.15x faster                                            |
| pickle                           | 9.23 us                                                          | 8.26 us: 1.12x faster                                            |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 347 ms: 1.11x faster                                             |
| xml_etree_iterparse              | 76.5 ms                                                          | 69.3 ms: 1.10x faster                                            |
| pickle_list                      | 3.26 us                                                          | 3.13 us: 1.04x faster                                            |
| asyncio_websockets               | 305 ms                                                           | 296 ms: 1.03x faster                                             |
| xml_etree_parse                  | 102 ms                                                           | 99.7 ms: 1.02x faster                                            |
| pidigits                         | 181 ms                                                           | 180 ms: 1.01x faster                                             |
| base64_large                     | 6.31 ms                                                          | 6.33 ms: 1.00x slower                                            |
| pickle_dict                      | 21.3 us                                                          | 21.6 us: 1.01x slower                                            |
| regex_v8                         | 15.0 ms                                                          | 15.4 ms: 1.02x slower                                            |
| regex_dna                        | 141 ms                                                           | 147 ms: 1.05x slower                                             |
| unpickle                         | 10.3 us                                                          | 10.9 us: 1.05x slower                                            |
| xml_etree_generate               | 71.1 ms                                                          | 76.6 ms: 1.08x slower                                            |
| json                             | 3.42 ms                                                          | 3.73 ms: 1.09x slower                                            |
| decimal_factorial                | 170 ms                                                           | 185 ms: 1.09x slower                                             |
| json_loads                       | 17.3 us                                                          | 18.9 us: 1.09x slower                                            |
| tornado_http                     | 101 ms                                                           | 111 ms: 1.11x slower                                             |
| regex_effbot                     | 1.80 ms                                                          | 1.99 ms: 1.11x slower                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.44 sec: 1.12x slower                                           |
| asyncio_tcp                      | 332 ms                                                           | 378 ms: 1.14x slower                                             |
| networkx_connected_components    | 435 ms                                                           | 501 ms: 1.15x slower                                             |
| decimal_pi                       | 201 ms                                                           | 232 ms: 1.15x slower                                             |
| networkx_k_core                  | 2.07 sec                                                         | 2.41 sec: 1.17x slower                                           |
| coverage                         | 55.4 ms                                                          | 64.8 ms: 1.17x slower                                            |
| async_tree_eager_io_tg           | 549 ms                                                           | 644 ms: 1.17x slower                                             |
| python_startup                   | 9.62 ms                                                          | 11.3 ms: 1.18x slower                                            |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 392 ms: 1.18x slower                                             |
| base32_large                     | 276 ms                                                           | 325 ms: 1.18x slower                                             |
| networkx_shortest_path           | 445 ms                                                           | 527 ms: 1.18x slower                                             |
| docutils                         | 2.02 sec                                                         | 2.41 sec: 1.19x slower                                           |
| unpickle_list                    | 3.64 us                                                          | 4.38 us: 1.20x slower                                            |
| pathlib                          | 12.5 ms                                                          | 15.0 ms: 1.20x slower                                            |
| json_dumps                       | 7.37 ms                                                          | 8.96 ms: 1.22x slower                                            |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 532 ms: 1.22x slower                                             |
| sqlalchemy_imperative            | 14.3 ms                                                          | 17.4 ms: 1.22x slower                                            |
| base32_small                     | 5.43 ms                                                          | 6.64 ms: 1.22x slower                                            |
| python_startup_no_site           | 6.29 ms                                                          | 7.84 ms: 1.25x slower                                            |
| xml_etree_process                | 50.0 ms                                                          | 63.1 ms: 1.26x slower                                            |
| pylint                           | 215 ms                                                           | 272 ms: 1.26x slower                                             |
| coroutines                       | 15.4 ms                                                          | 19.4 ms: 1.26x slower                                            |
| async_tree_eager_io              | 548 ms                                                           | 697 ms: 1.27x slower                                             |
| meteor_contest                   | 83.9 ms                                                          | 108 ms: 1.29x slower                                             |
| thread_counter_naive             | 21.4 ms                                                          | 27.7 ms: 1.29x slower                                            |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 561 ms: 1.30x slower                                             |
| scimark_fft                      | 197 ms                                                           | 258 ms: 1.31x slower                                             |
| async_tree_io_tg                 | 529 ms                                                           | 695 ms: 1.31x slower                                             |
| pycparser                        | 837 ms                                                           | 1.10 sec: 1.32x slower                                           |
| xdsl_constant_fold               | 35.1 ms                                                          | 46.4 ms: 1.32x slower                                            |
| nqueens                          | 56.3 ms                                                          | 74.7 ms: 1.33x slower                                            |
| noop                             | 18.7 ns                                                          | 24.9 ns: 1.33x slower                                            |
| telco                            | 5.26 ms                                                          | 6.99 ms: 1.33x slower                                            |
| mypy2                            | 756 ms                                                           | 1.01 sec: 1.34x slower                                           |
| fastapi_http                     | 215 ms                                                           | 290 ms: 1.35x slower                                             |
| base85_large                     | 233 ms                                                           | 315 ms: 1.36x slower                                             |
| base85_small                     | 4.44 ms                                                          | 6.04 ms: 1.36x slower                                            |
| sympy_integrate                  | 14.7 ms                                                          | 20.1 ms: 1.37x slower                                            |
| generators                       | 20.7 ms                                                          | 28.3 ms: 1.37x slower                                            |
| bpe_tokeniser                    | 3.10 sec                                                         | 4.25 sec: 1.37x slower                                           |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 3.55 ms: 1.38x slower                                            |
| crypto_pyaes                     | 51.5 ms                                                          | 71.0 ms: 1.38x slower                                            |
| base64_small                     | 230 us                                                           | 320 us: 1.39x slower                                             |
| async_tree_io                    | 527 ms                                                           | 734 ms: 1.39x slower                                             |
| async_tree_none_tg               | 221 ms                                                           | 309 ms: 1.40x slower                                             |
| urlsafe_base64_small             | 383 us                                                           | 541 us: 1.41x slower                                             |
| fannkuch                         | 234 ms                                                           | 332 ms: 1.42x slower                                             |
| genshi_xml                       | 38.4 ms                                                          | 54.6 ms: 1.42x slower                                            |
| async_tree_eager_memoization     | 175 ms                                                           | 251 ms: 1.43x slower                                             |
| thread_pipeline_naive            | 35.4 ms                                                          | 50.9 ms: 1.44x slower                                            |
| async_tree_memoization_tg        | 275 ms                                                           | 395 ms: 1.44x slower                                             |
| ascii85_large                    | 651 ms                                                           | 966 ms: 1.48x slower                                             |
| html5lib                         | 45.5 ms                                                          | 67.6 ms: 1.49x slower                                            |
| async_generators                 | 243 ms                                                           | 364 ms: 1.50x slower                                             |
| ascii85_small                    | 12.5 ms                                                          | 18.7 ms: 1.50x slower                                            |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 58.5 ms: 1.51x slower                                            |
| sympy_str                        | 192 ms                                                           | 291 ms: 1.52x slower                                             |
| typing_runtime_protocols         | 106 us                                                           | 161 us: 1.52x slower                                             |
| async_tree_memoization           | 274 ms                                                           | 419 ms: 1.53x slower                                             |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 119 ms: 1.53x slower                                             |
| tomli_loads                      | 1.41 sec                                                         | 2.19 sec: 1.56x slower                                           |
| async_tree_none                  | 223 ms                                                           | 349 ms: 1.56x slower                                             |
| django_template                  | 28.4 ms                                                          | 44.8 ms: 1.58x slower                                            |
| regex_compile                    | 91.6 ms                                                          | 146 ms: 1.59x slower                                             |
| chameleon                        | 10.6 ms                                                          | 17.1 ms: 1.61x slower                                            |
| comprehensions                   | 11.2 us                                                          | 18.1 us: 1.62x slower                                            |
| pyflate                          | 300 ms                                                           | 489 ms: 1.63x slower                                             |
| unpickle_pure_python             | 153 us                                                           | 250 us: 1.63x slower                                             |
| logging_simple                   | 4.72 us                                                          | 7.74 us: 1.64x slower                                            |
| logging_format                   | 5.24 us                                                          | 8.60 us: 1.64x slower                                            |
| sympy_expand                     | 330 ms                                                           | 544 ms: 1.65x slower                                             |
| sympy_sum                        | 104 ms                                                           | 174 ms: 1.67x slower                                             |
| pickle_pure_python               | 234 us                                                           | 394 us: 1.68x slower                                             |
| async_tree_eager                 | 78.8 ms                                                          | 133 ms: 1.69x slower                                             |
| genshi_text                      | 16.4 ms                                                          | 27.9 ms: 1.70x slower                                            |
| spectral_norm                    | 59.6 ms                                                          | 102 ms: 1.71x slower                                             |
| pprint_safe_repr                 | 484 ms                                                           | 849 ms: 1.75x slower                                             |
| deepcopy_reduce                  | 2.05 us                                                          | 3.61 us: 1.77x slower                                            |
| richards                         | 32.5 ms                                                          | 57.7 ms: 1.77x slower                                            |
| pprint_pformat                   | 982 ms                                                           | 1.76 sec: 1.79x slower                                           |
| hexiom                           | 4.00 ms                                                          | 7.20 ms: 1.80x slower                                            |
| thrift                           | 1.84 ms                                                          | 3.35 ms: 1.82x slower                                            |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 2.11 ms: 1.84x slower                                            |
| mako                             | 7.66 ms                                                          | 14.3 ms: 1.86x slower                                            |
| richards_super                   | 37.2 ms                                                          | 69.9 ms: 1.88x slower                                            |
| chaos                            | 41.9 ms                                                          | 79.1 ms: 1.89x slower                                            |
| logging_silent                   | 59.7 ns                                                          | 116 ns: 1.94x slower                                             |
| nbody                            | 67.2 ms                                                          | 131 ms: 1.96x slower                                             |
| float                            | 48.1 ms                                                          | 95.0 ms: 1.98x slower                                            |
| scimark_monte_carlo              | 37.5 ms                                                          | 74.3 ms: 1.98x slower                                            |
| sqlglot_v2_parse                 | 909 us                                                           | 1.82 ms: 2.01x slower                                            |
| deepcopy                         | 195 us                                                           | 394 us: 2.02x slower                                             |
| raytrace                         | 194 ms                                                           | 401 ms: 2.06x slower                                             |
| deepcopy_memo                    | 18.2 us                                                          | 38.9 us: 2.13x slower                                            |
| scimark_sor                      | 72.8 ms                                                          | 159 ms: 2.19x slower                                             |
| quadtree_nbody                   | 602 ms                                                           | 1.36 sec: 2.26x slower                                           |
| scimark_lu                       | 66.7 ms                                                          | 170 ms: 2.55x slower                                             |
| deltablue                        | 2.24 ms                                                          | 5.75 ms: 2.57x slower                                            |
| mdp                              | 935 ms                                                           | 2.41 sec: 2.58x slower                                           |
| go                               | 82.6 ms                                                          | 218 ms: 2.63x slower                                             |
| base16_small                     | 298 us                                                           | 830 us: 2.79x slower                                             |
| unpack_sequence                  | 24.1 ns                                                          | 79.8 ns: 3.32x slower                                            |
| thread_montecarlo_naive          | 14.6 ms                                                          | 60.8 ms: 4.16x slower                                            |
| thread_memo_naive                | 11.8 ms                                                          | 49.8 ms: 4.21x slower                                            |
| base16_large                     | 5.41 ms                                                          | 30.7 ms: 5.68x slower                                            |
| Geometric mean                   | (ref)                                                            | 1.31x slower                                                     |

- Geometric mean (including insignificant results): 1.239x slower

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.30x
- 95% likely to have a slowdown of 1.29x
- 99% likely to have a slowdown of 1.26x

# Memory
- memory change: 1.36x