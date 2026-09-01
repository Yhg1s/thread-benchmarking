# Results vs. base

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.018x faster
- HPT reliability: 99.90%
- HPT 99th percentile: 1.01x slower
- Memory change: 1.46x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| chameleon      | 10.8 ms                                                                                                  | 11.8 ms: 1.09x slower                                                                                          |
| docutils       | 1.95 sec                                                                                                 | 2.09 sec: 1.07x slower                                                                                         |
| fastapi_http   | 211 ms                                                                                                   | 183 ms: 1.15x faster                                                                                           |
| tornado_http   | 101 ms                                                                                                   | 94.9 ms: 1.06x faster                                                                                          |
| Geometric mean | (ref)                                                                                                    | 1.01x faster                                                                                                   |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| async_tree_io_tg                 | 694 ms                                                                                                   | 484 ms: 1.43x faster                                                                                           |
| async_tree_eager_io_tg           | 679 ms                                                                                                   | 477 ms: 1.42x faster                                                                                           |
| async_tree_io                    | 654 ms                                                                                                   | 507 ms: 1.29x faster                                                                                           |
| async_tree_none_tg               | 269 ms                                                                                                   | 210 ms: 1.28x faster                                                                                           |
| async_tree_eager_io              | 649 ms                                                                                                   | 518 ms: 1.25x faster                                                                                           |
| async_tree_memoization_tg        | 331 ms                                                                                                   | 273 ms: 1.21x faster                                                                                           |
| async_tree_eager_memoization_tg  | 283 ms                                                                                                   | 252 ms: 1.13x faster                                                                                           |
| async_tree_memoization           | 335 ms                                                                                                   | 299 ms: 1.12x faster                                                                                           |
| async_tree_eager_tg              | 210 ms                                                                                                   | 188 ms: 1.12x faster                                                                                           |
| async_tree_none                  | 255 ms                                                                                                   | 236 ms: 1.08x faster                                                                                           |
| async_tree_cpu_io_mixed_tg       | 496 ms                                                                                                   | 461 ms: 1.08x faster                                                                                           |
| asyncio_websockets               | 299 ms                                                                                                   | 289 ms: 1.04x faster                                                                                           |
| asyncio_tcp                      | 307 ms                                                                                                   | 300 ms: 1.02x faster                                                                                           |
| coroutines                       | 14.9 ms                                                                                                  | 14.7 ms: 1.01x faster                                                                                          |
| async_tree_eager_cpu_io_mixed_tg | 428 ms                                                                                                   | 442 ms: 1.03x slower                                                                                           |
| async_generators                 | 247 ms                                                                                                   | 264 ms: 1.07x slower                                                                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                 | 1.39 sec: 1.08x slower                                                                                         |
| async_tree_eager_cpu_io_mixed    | 345 ms                                                                                                   | 372 ms: 1.08x slower                                                                                           |
| async_tree_eager                 | 78.9 ms                                                                                                  | 93.0 ms: 1.18x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                    | 1.09x faster                                                                                                   |

Benchmark hidden because not significant (2): async_tree_eager_memoization, async_tree_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| noop      | 18.8 ns                                                                                                  | 20.1 ns: 1.07x slower                                                                                          |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                                                                   | 186 ms: 1.09x slower                                                                                           |
| decimal_pi        | 204 ms                                                                                                   | 238 ms: 1.17x slower                                                                                           |
| Geometric mean    | (ref)                                                                                                    | 1.13x slower                                                                                                   |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| pidigits       | 181 ms                                                                                                   | 178 ms: 1.02x faster                                                                                           |
| quadtree_nbody | 591 ms                                                                                                   | 616 ms: 1.04x slower                                                                                           |
| float          | 49.5 ms                                                                                                  | 53.5 ms: 1.08x slower                                                                                          |
| nbody          | 69.1 ms                                                                                                  | 82.4 ms: 1.19x slower                                                                                          |
| Geometric mean | (ref)                                                                                                    | 1.07x slower                                                                                                   |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| regex_v8       | 15.7 ms                                                                                                  | 14.8 ms: 1.06x faster                                                                                          |
| regex_dna      | 139 ms                                                                                                   | 144 ms: 1.04x slower                                                                                           |
| regex_effbot   | 1.77 ms                                                                                                  | 1.91 ms: 1.07x slower                                                                                          |
| regex_compile  | 92.0 ms                                                                                                  | 101 ms: 1.10x slower                                                                                           |
| Geometric mean | (ref)                                                                                                    | 1.04x slower                                                                                                   |

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| xml_etree_iterparse  | 74.5 ms                                                                                                  | 65.8 ms: 1.13x faster                                                                                          |
| pickle               | 9.59 us                                                                                                  | 9.13 us: 1.05x faster                                                                                          |
| xml_etree_parse      | 109 ms                                                                                                   | 106 ms: 1.03x faster                                                                                           |
| base16_small         | 303 us                                                                                                   | 295 us: 1.03x faster                                                                                           |
| base64_large         | 5.01 ms                                                                                                  | 4.97 ms: 1.01x faster                                                                                          |
| base64_small         | 211 us                                                                                                   | 210 us: 1.00x faster                                                                                           |
| urlsafe_base64_small | 359 us                                                                                                   | 361 us: 1.00x slower                                                                                           |
| pickle_dict          | 21.3 us                                                                                                  | 21.5 us: 1.01x slower                                                                                          |
| pickle_list          | 3.76 us                                                                                                  | 3.91 us: 1.04x slower                                                                                          |
| unpickle_pure_python | 152 us                                                                                                   | 158 us: 1.04x slower                                                                                           |
| xml_etree_generate   | 71.8 ms                                                                                                  | 75.1 ms: 1.05x slower                                                                                          |
| pickle_pure_python   | 228 us                                                                                                   | 239 us: 1.05x slower                                                                                           |
| json_dumps           | 7.59 ms                                                                                                  | 8.00 ms: 1.05x slower                                                                                          |
| base85_small         | 4.44 ms                                                                                                  | 4.70 ms: 1.06x slower                                                                                          |
| tomli_loads          | 1.43 sec                                                                                                 | 1.51 sec: 1.06x slower                                                                                         |
| xml_etree_process    | 50.6 ms                                                                                                  | 54.3 ms: 1.07x slower                                                                                          |
| unpickle             | 10.4 us                                                                                                  | 11.3 us: 1.09x slower                                                                                          |
| base32_large         | 277 ms                                                                                                   | 307 ms: 1.11x slower                                                                                           |
| base32_small         | 5.46 ms                                                                                                  | 6.10 ms: 1.12x slower                                                                                          |
| ascii85_small        | 12.7 ms                                                                                                  | 14.2 ms: 1.12x slower                                                                                          |
| base85_large         | 235 ms                                                                                                   | 264 ms: 1.12x slower                                                                                           |
| ascii85_large        | 657 ms                                                                                                   | 743 ms: 1.13x slower                                                                                           |
| unpickle_list        | 3.60 us                                                                                                  | 4.54 us: 1.26x slower                                                                                          |
| json_loads           | 19.1 us                                                                                                  | 24.9 us: 1.31x slower                                                                                          |
| Geometric mean       | (ref)                                                                                                    | 1.05x slower                                                                                                   |

Benchmark hidden because not significant (1): base16_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.71 ms                                                                                                  | 11.7 ms: 1.20x slower                                                                                          |
| python_startup_no_site | 6.31 ms                                                                                                  | 8.17 ms: 1.29x slower                                                                                          |
| Geometric mean         | (ref)                                                                                                    | 1.25x slower                                                                                                   |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| genshi_xml      | 39.3 ms                                                                                                  | 41.8 ms: 1.06x slower                                                                                          |
| django_template | 28.0 ms                                                                                                  | 31.2 ms: 1.11x slower                                                                                          |
| genshi_text     | 16.4 ms                                                                                                  | 19.4 ms: 1.18x slower                                                                                          |
| mako            | 8.28 ms                                                                                                  | 11.9 ms: 1.44x slower                                                                                          |
| Geometric mean  | (ref)                                                                                                    | 1.19x slower                                                                                                   |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_pipeline_optimized   | 26.7 ms                                                                                                  | 7.14 ms: 3.74x faster                                                                                          |
| thread_accumulate_optimized | 41.5 ms                                                                                                  | 11.2 ms: 3.69x faster                                                                                          |
| thread_mandelbrot_naive     | 225 ms                                                                                                   | 61.6 ms: 3.66x faster                                                                                          |
| thread_mandelbrot_optimized | 225 ms                                                                                                   | 62.2 ms: 3.62x faster                                                                                          |
| thread_counter_optimized    | 18.5 ms                                                                                                  | 5.21 ms: 3.56x faster                                                                                          |
| thread_accumulate_naive     | 42.3 ms                                                                                                  | 13.7 ms: 3.07x faster                                                                                          |
| thread_memo_optimized       | 18.2 ms                                                                                                  | 6.05 ms: 3.01x faster                                                                                          |
| thread_montecarlo_optimized | 12.8 ms                                                                                                  | 4.46 ms: 2.87x faster                                                                                          |
| thread_pipeline_naive       | 35.1 ms                                                                                                  | 26.9 ms: 1.31x faster                                                                                          |
| thread_counter_naive        | 21.2 ms                                                                                                  | 21.0 ms: 1.01x faster                                                                                          |
| thread_montecarlo_naive     | 14.7 ms                                                                                                  | 25.3 ms: 1.72x slower                                                                                          |
| thread_memo_naive           | 11.7 ms                                                                                                  | 23.9 ms: 2.05x slower                                                                                          |
| Geometric mean              | (ref)                                                                                                    | 2.08x faster                                                                                                   |

All benchmarks:
===============

| Benchmark                        | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-NOGIL/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_pipeline_optimized        | 26.7 ms                                                                                                  | 7.14 ms: 3.74x faster                                                                                          |
| thread_accumulate_optimized      | 41.5 ms                                                                                                  | 11.2 ms: 3.69x faster                                                                                          |
| thread_mandelbrot_naive          | 225 ms                                                                                                   | 61.6 ms: 3.66x faster                                                                                          |
| thread_mandelbrot_optimized      | 225 ms                                                                                                   | 62.2 ms: 3.62x faster                                                                                          |
| thread_counter_optimized         | 18.5 ms                                                                                                  | 5.21 ms: 3.56x faster                                                                                          |
| thread_accumulate_naive          | 42.3 ms                                                                                                  | 13.7 ms: 3.07x faster                                                                                          |
| thread_memo_optimized            | 18.2 ms                                                                                                  | 6.05 ms: 3.01x faster                                                                                          |
| thread_montecarlo_optimized      | 12.8 ms                                                                                                  | 4.46 ms: 2.87x faster                                                                                          |
| gc_traversal                     | 3.11 ms                                                                                                  | 1.46 ms: 2.13x faster                                                                                          |
| async_tree_io_tg                 | 694 ms                                                                                                   | 484 ms: 1.43x faster                                                                                           |
| async_tree_eager_io_tg           | 679 ms                                                                                                   | 477 ms: 1.42x faster                                                                                           |
| create_gc_cycles                 | 1.83 ms                                                                                                  | 1.29 ms: 1.41x faster                                                                                          |
| thread_pipeline_naive            | 35.1 ms                                                                                                  | 26.9 ms: 1.31x faster                                                                                          |
| async_tree_io                    | 654 ms                                                                                                   | 507 ms: 1.29x faster                                                                                           |
| async_tree_none_tg               | 269 ms                                                                                                   | 210 ms: 1.28x faster                                                                                           |
| async_tree_eager_io              | 649 ms                                                                                                   | 518 ms: 1.25x faster                                                                                           |
| async_tree_memoization_tg        | 331 ms                                                                                                   | 273 ms: 1.21x faster                                                                                           |
| fastapi_http                     | 211 ms                                                                                                   | 183 ms: 1.15x faster                                                                                           |
| xml_etree_iterparse              | 74.5 ms                                                                                                  | 65.8 ms: 1.13x faster                                                                                          |
| async_tree_eager_memoization_tg  | 283 ms                                                                                                   | 252 ms: 1.13x faster                                                                                           |
| async_tree_memoization           | 335 ms                                                                                                   | 299 ms: 1.12x faster                                                                                           |
| async_tree_eager_tg              | 210 ms                                                                                                   | 188 ms: 1.12x faster                                                                                           |
| async_tree_none                  | 255 ms                                                                                                   | 236 ms: 1.08x faster                                                                                           |
| async_tree_cpu_io_mixed_tg       | 496 ms                                                                                                   | 461 ms: 1.08x faster                                                                                           |
| tornado_http                     | 101 ms                                                                                                   | 94.9 ms: 1.06x faster                                                                                          |
| regex_v8                         | 15.7 ms                                                                                                  | 14.8 ms: 1.06x faster                                                                                          |
| pycparser                        | 859 ms                                                                                                   | 812 ms: 1.06x faster                                                                                           |
| pickle                           | 9.59 us                                                                                                  | 9.13 us: 1.05x faster                                                                                          |
| asyncio_websockets               | 299 ms                                                                                                   | 289 ms: 1.04x faster                                                                                           |
| xml_etree_parse                  | 109 ms                                                                                                   | 106 ms: 1.03x faster                                                                                           |
| base16_small                     | 303 us                                                                                                   | 295 us: 1.03x faster                                                                                           |
| asyncio_tcp                      | 307 ms                                                                                                   | 300 ms: 1.02x faster                                                                                           |
| pidigits                         | 181 ms                                                                                                   | 178 ms: 1.02x faster                                                                                           |
| pathlib                          | 12.4 ms                                                                                                  | 12.2 ms: 1.02x faster                                                                                          |
| coroutines                       | 14.9 ms                                                                                                  | 14.7 ms: 1.01x faster                                                                                          |
| bpe_tokeniser                    | 3.20 sec                                                                                                 | 3.16 sec: 1.01x faster                                                                                         |
| thread_counter_naive             | 21.2 ms                                                                                                  | 21.0 ms: 1.01x faster                                                                                          |
| base64_large                     | 5.01 ms                                                                                                  | 4.97 ms: 1.01x faster                                                                                          |
| base64_small                     | 211 us                                                                                                   | 210 us: 1.00x faster                                                                                           |
| urlsafe_base64_small             | 359 us                                                                                                   | 361 us: 1.00x slower                                                                                           |
| pickle_dict                      | 21.3 us                                                                                                  | 21.5 us: 1.01x slower                                                                                          |
| thrift                           | 1.83 ms                                                                                                  | 1.89 ms: 1.03x slower                                                                                          |
| argparse_many_optionals          | 7.41 ms                                                                                                  | 7.63 ms: 1.03x slower                                                                                          |
| mdp                              | 945 ms                                                                                                   | 974 ms: 1.03x slower                                                                                           |
| async_tree_eager_cpu_io_mixed_tg | 428 ms                                                                                                   | 442 ms: 1.03x slower                                                                                           |
| regex_dna                        | 139 ms                                                                                                   | 144 ms: 1.04x slower                                                                                           |
| sqlglot_v2_optimize              | 39.0 ms                                                                                                  | 40.5 ms: 1.04x slower                                                                                          |
| pickle_list                      | 3.76 us                                                                                                  | 3.91 us: 1.04x slower                                                                                          |
| unpickle_pure_python             | 152 us                                                                                                   | 158 us: 1.04x slower                                                                                           |
| quadtree_nbody                   | 591 ms                                                                                                   | 616 ms: 1.04x slower                                                                                           |
| xml_etree_generate               | 71.8 ms                                                                                                  | 75.1 ms: 1.05x slower                                                                                          |
| sqlglot_v2_normalize             | 78.2 ms                                                                                                  | 81.9 ms: 1.05x slower                                                                                          |
| sympy_sum                        | 105 ms                                                                                                   | 110 ms: 1.05x slower                                                                                           |
| xdsl_constant_fold               | 37.0 ms                                                                                                  | 38.8 ms: 1.05x slower                                                                                          |
| pickle_pure_python               | 228 us                                                                                                   | 239 us: 1.05x slower                                                                                           |
| logging_silent                   | 59.2 ns                                                                                                  | 62.2 ns: 1.05x slower                                                                                          |
| json_dumps                       | 7.59 ms                                                                                                  | 8.00 ms: 1.05x slower                                                                                          |
| base85_small                     | 4.44 ms                                                                                                  | 4.70 ms: 1.06x slower                                                                                          |
| tomli_loads                      | 1.43 sec                                                                                                 | 1.51 sec: 1.06x slower                                                                                         |
| genshi_xml                       | 39.3 ms                                                                                                  | 41.8 ms: 1.06x slower                                                                                          |
| sqlalchemy_imperative            | 14.2 ms                                                                                                  | 15.2 ms: 1.06x slower                                                                                          |
| noop                             | 18.8 ns                                                                                                  | 20.1 ns: 1.07x slower                                                                                          |
| argparse_subparsers              | 489 us                                                                                                   | 523 us: 1.07x slower                                                                                           |
| sympy_expand                     | 333 ms                                                                                                   | 356 ms: 1.07x slower                                                                                           |
| async_generators                 | 247 ms                                                                                                   | 264 ms: 1.07x slower                                                                                           |
| sympy_str                        | 192 ms                                                                                                   | 206 ms: 1.07x slower                                                                                           |
| docutils                         | 1.95 sec                                                                                                 | 2.09 sec: 1.07x slower                                                                                         |
| xml_etree_process                | 50.6 ms                                                                                                  | 54.3 ms: 1.07x slower                                                                                          |
| regex_effbot                     | 1.77 ms                                                                                                  | 1.91 ms: 1.07x slower                                                                                          |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                 | 1.39 sec: 1.08x slower                                                                                         |
| async_tree_eager_cpu_io_mixed    | 345 ms                                                                                                   | 372 ms: 1.08x slower                                                                                           |
| float                            | 49.5 ms                                                                                                  | 53.5 ms: 1.08x slower                                                                                          |
| sympy_integrate                  | 14.7 ms                                                                                                  | 15.9 ms: 1.08x slower                                                                                          |
| pprint_safe_repr                 | 481 ms                                                                                                   | 521 ms: 1.08x slower                                                                                           |
| unpickle                         | 10.4 us                                                                                                  | 11.3 us: 1.09x slower                                                                                          |
| pprint_pformat                   | 996 ms                                                                                                   | 1.08 sec: 1.09x slower                                                                                         |
| chameleon                        | 10.8 ms                                                                                                  | 11.8 ms: 1.09x slower                                                                                          |
| chaos                            | 41.8 ms                                                                                                  | 45.6 ms: 1.09x slower                                                                                          |
| nqueens                          | 56.3 ms                                                                                                  | 61.5 ms: 1.09x slower                                                                                          |
| decimal_factorial                | 170 ms                                                                                                   | 186 ms: 1.09x slower                                                                                           |
| hexiom                           | 4.02 ms                                                                                                  | 4.40 ms: 1.10x slower                                                                                          |
| scimark_fft                      | 202 ms                                                                                                   | 222 ms: 1.10x slower                                                                                           |
| go                               | 82.3 ms                                                                                                  | 90.5 ms: 1.10x slower                                                                                          |
| regex_compile                    | 92.0 ms                                                                                                  | 101 ms: 1.10x slower                                                                                           |
| base32_large                     | 277 ms                                                                                                   | 307 ms: 1.11x slower                                                                                           |
| deepcopy                         | 192 us                                                                                                   | 213 us: 1.11x slower                                                                                           |
| django_template                  | 28.0 ms                                                                                                  | 31.2 ms: 1.11x slower                                                                                          |
| logging_format                   | 5.20 us                                                                                                  | 5.80 us: 1.11x slower                                                                                          |
| spectral_norm                    | 60.6 ms                                                                                                  | 67.6 ms: 1.12x slower                                                                                          |
| base32_small                     | 5.46 ms                                                                                                  | 6.10 ms: 1.12x slower                                                                                          |
| sqlglot_v2_transpile             | 1.13 ms                                                                                                  | 1.26 ms: 1.12x slower                                                                                          |
| ascii85_small                    | 12.7 ms                                                                                                  | 14.2 ms: 1.12x slower                                                                                          |
| raytrace                         | 192 ms                                                                                                   | 215 ms: 1.12x slower                                                                                           |
| logging_simple                   | 4.57 us                                                                                                  | 5.14 us: 1.12x slower                                                                                          |
| base85_large                     | 235 ms                                                                                                   | 264 ms: 1.12x slower                                                                                           |
| scimark_sor                      | 71.8 ms                                                                                                  | 80.9 ms: 1.13x slower                                                                                          |
| pyflate                          | 298 ms                                                                                                   | 336 ms: 1.13x slower                                                                                           |
| networkx_k_core                  | 2.07 sec                                                                                                 | 2.33 sec: 1.13x slower                                                                                         |
| ascii85_large                    | 657 ms                                                                                                   | 743 ms: 1.13x slower                                                                                           |
| deltablue                        | 2.21 ms                                                                                                  | 2.49 ms: 1.13x slower                                                                                          |
| meteor_contest                   | 86.1 ms                                                                                                  | 97.5 ms: 1.13x slower                                                                                          |
| json                             | 3.65 ms                                                                                                  | 4.20 ms: 1.15x slower                                                                                          |
| comprehensions                   | 11.1 us                                                                                                  | 12.8 us: 1.15x slower                                                                                          |
| richards_super                   | 36.8 ms                                                                                                  | 42.7 ms: 1.16x slower                                                                                          |
| richards                         | 31.6 ms                                                                                                  | 36.6 ms: 1.16x slower                                                                                          |
| deepcopy_reduce                  | 1.98 us                                                                                                  | 2.29 us: 1.16x slower                                                                                          |
| scimark_lu                       | 66.8 ms                                                                                                  | 77.7 ms: 1.16x slower                                                                                          |
| sqlglot_v2_parse                 | 887 us                                                                                                   | 1.03 ms: 1.16x slower                                                                                          |
| decimal_pi                       | 204 ms                                                                                                   | 238 ms: 1.17x slower                                                                                           |
| async_tree_eager                 | 78.9 ms                                                                                                  | 93.0 ms: 1.18x slower                                                                                          |
| genshi_text                      | 16.4 ms                                                                                                  | 19.4 ms: 1.18x slower                                                                                          |
| deepcopy_memo                    | 18.2 us                                                                                                  | 21.6 us: 1.19x slower                                                                                          |
| nbody                            | 69.1 ms                                                                                                  | 82.4 ms: 1.19x slower                                                                                          |
| typing_runtime_protocols         | 107 us                                                                                                   | 128 us: 1.20x slower                                                                                           |
| mypy2                            | 725 ms                                                                                                   | 868 ms: 1.20x slower                                                                                           |
| scimark_monte_carlo              | 37.8 ms                                                                                                  | 45.5 ms: 1.20x slower                                                                                          |
| python_startup                   | 9.71 ms                                                                                                  | 11.7 ms: 1.20x slower                                                                                          |
| crypto_pyaes                     | 51.9 ms                                                                                                  | 62.6 ms: 1.21x slower                                                                                          |
| telco                            | 5.37 ms                                                                                                  | 6.49 ms: 1.21x slower                                                                                          |
| scimark_sparse_mat_mult          | 2.59 ms                                                                                                  | 3.16 ms: 1.22x slower                                                                                          |
| networkx_connected_components    | 435 ms                                                                                                   | 535 ms: 1.23x slower                                                                                           |
| fannkuch                         | 234 ms                                                                                                   | 291 ms: 1.24x slower                                                                                           |
| networkx_shortest_path           | 442 ms                                                                                                   | 555 ms: 1.26x slower                                                                                           |
| unpack_sequence                  | 25.0 ns                                                                                                  | 31.4 ns: 1.26x slower                                                                                          |
| unpickle_list                    | 3.60 us                                                                                                  | 4.54 us: 1.26x slower                                                                                          |
| python_startup_no_site           | 6.31 ms                                                                                                  | 8.17 ms: 1.29x slower                                                                                          |
| json_loads                       | 19.1 us                                                                                                  | 24.9 us: 1.31x slower                                                                                          |
| coverage                         | 52.8 ms                                                                                                  | 73.6 ms: 1.40x slower                                                                                          |
| mako                             | 8.28 ms                                                                                                  | 11.9 ms: 1.44x slower                                                                                          |
| thread_montecarlo_naive          | 14.7 ms                                                                                                  | 25.3 ms: 1.72x slower                                                                                          |
| thread_memo_naive                | 11.7 ms                                                                                                  | 23.9 ms: 2.05x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                    | 1.02x faster                                                                                                   |

Benchmark hidden because not significant (6): html5lib, pylint, async_tree_eager_memoization, base16_large, generators, async_tree_cpu_io_mixed

- Geometric mean (including insignificant results): 1.018x faster

# HPT report

- Reliability score: 99.90% likely to be slow
- 90% likely to have a slowdown of 1.03x
- 95% likely to have a slowdown of 1.03x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 1.46x