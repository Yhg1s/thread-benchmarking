# Results vs. base

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.189x slower
- HPT reliability: 100.00%
- HPT 99th percentile: 1.18x slower
- Memory change: 1.44x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                                                                 | 16.3 ms: 1.63x slower                                                                                         |
| docutils       | 1.89 sec                                                                                                | 2.32 sec: 1.23x slower                                                                                        |
| fastapi_http   | 218 ms                                                                                                  | 291 ms: 1.33x slower                                                                                          |
| html5lib       | 51.7 ms                                                                                                 | 70.5 ms: 1.36x slower                                                                                         |
| tornado_http   | 101 ms                                                                                                  | 116 ms: 1.15x slower                                                                                          |
| Geometric mean | (ref)                                                                                                   | 1.33x slower                                                                                                  |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 728 ms                                                                                                  | 653 ms: 1.11x faster                                                                                          |
| async_tree_io_tg                 | 778 ms                                                                                                  | 703 ms: 1.11x faster                                                                                          |
| async_tree_eager_io              | 749 ms                                                                                                  | 703 ms: 1.07x faster                                                                                          |
| async_tree_memoization_tg        | 419 ms                                                                                                  | 404 ms: 1.04x faster                                                                                          |
| asyncio_websockets               | 303 ms                                                                                                  | 295 ms: 1.03x faster                                                                                          |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                                                                  | 506 ms: 1.03x slower                                                                                          |
| async_tree_none_tg               | 291 ms                                                                                                  | 313 ms: 1.08x slower                                                                                          |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                | 1.43 sec: 1.11x slower                                                                                        |
| async_tree_memoization           | 388 ms                                                                                                  | 436 ms: 1.13x slower                                                                                          |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                                                                  | 325 ms: 1.14x slower                                                                                          |
| async_tree_cpu_io_mixed          | 474 ms                                                                                                  | 544 ms: 1.15x slower                                                                                          |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                                                                  | 371 ms: 1.15x slower                                                                                          |
| async_tree_none                  | 308 ms                                                                                                  | 355 ms: 1.15x slower                                                                                          |
| async_tree_eager_memoization_tg  | 175 ms                                                                                                  | 204 ms: 1.16x slower                                                                                          |
| async_tree_eager_memoization     | 219 ms                                                                                                  | 257 ms: 1.17x slower                                                                                          |
| asyncio_tcp                      | 318 ms                                                                                                  | 378 ms: 1.19x slower                                                                                          |
| coroutines                       | 15.4 ms                                                                                                 | 19.0 ms: 1.23x slower                                                                                         |
| async_generators                 | 240 ms                                                                                                  | 312 ms: 1.30x slower                                                                                          |
| async_tree_eager                 | 89.6 ms                                                                                                 | 136 ms: 1.52x slower                                                                                          |
| async_tree_eager_tg              | 58.6 ms                                                                                                 | 90.8 ms: 1.55x slower                                                                                         |
| Geometric mean                   | (ref)                                                                                                   | 1.12x slower                                                                                                  |

Benchmark hidden because not significant (1): async_tree_io

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| noop      | 20.5 ns                                                                                                 | 24.6 ns: 1.20x slower                                                                                         |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                                                                  | 190 ms: 1.07x slower                                                                                          |
| decimal_pi        | 222 ms                                                                                                  | 254 ms: 1.15x slower                                                                                          |
| Geometric mean    | (ref)                                                                                                   | 1.11x slower                                                                                                  |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| pidigits       | 189 ms                                                                                                  | 185 ms: 1.02x faster                                                                                          |
| float          | 57.0 ms                                                                                                 | 97.8 ms: 1.72x slower                                                                                         |
| nbody          | 65.9 ms                                                                                                 | 142 ms: 2.15x slower                                                                                          |
| quadtree_nbody | 626 ms                                                                                                  | 1.36 sec: 2.17x slower                                                                                        |
| Geometric mean | (ref)                                                                                                   | 1.67x slower                                                                                                  |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                                                                 | 2.21 ms: 1.04x faster                                                                                         |
| regex_dna      | 162 ms                                                                                                  | 160 ms: 1.01x faster                                                                                          |
| regex_v8       | 15.2 ms                                                                                                 | 15.2 ms: 1.00x faster                                                                                         |
| regex_compile  | 98.5 ms                                                                                                 | 147 ms: 1.49x slower                                                                                          |
| Geometric mean | (ref)                                                                                                   | 1.09x slower                                                                                                  |

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| xml_etree_parse      | 104 ms                                                                                                  | 91.4 ms: 1.14x faster                                                                                         |
| xml_etree_iterparse  | 79.9 ms                                                                                                 | 71.0 ms: 1.13x faster                                                                                         |
| pickle_dict          | 22.0 us                                                                                                 | 21.5 us: 1.02x faster                                                                                         |
| pickle               | 7.44 us                                                                                                 | 7.38 us: 1.01x faster                                                                                         |
| base16_large         | 37.0 ms                                                                                                 | 36.8 ms: 1.01x faster                                                                                         |
| base64_large         | 3.33 ms                                                                                                 | 3.35 ms: 1.01x slower                                                                                         |
| pickle_list          | 3.14 us                                                                                                 | 3.17 us: 1.01x slower                                                                                         |
| unpickle             | 10.5 us                                                                                                 | 11.3 us: 1.08x slower                                                                                         |
| base32_large         | 296 ms                                                                                                  | 327 ms: 1.11x slower                                                                                          |
| base32_small         | 5.79 ms                                                                                                 | 6.56 ms: 1.13x slower                                                                                         |
| unpickle_list        | 3.33 us                                                                                                 | 3.77 us: 1.13x slower                                                                                         |
| json_loads           | 16.2 us                                                                                                 | 18.7 us: 1.15x slower                                                                                         |
| xml_etree_generate   | 64.2 ms                                                                                                 | 74.4 ms: 1.16x slower                                                                                         |
| json_dumps           | 6.95 ms                                                                                                 | 8.33 ms: 1.20x slower                                                                                         |
| base16_small         | 740 us                                                                                                  | 920 us: 1.24x slower                                                                                          |
| base85_large         | 252 ms                                                                                                  | 316 ms: 1.25x slower                                                                                          |
| base85_small         | 4.59 ms                                                                                                 | 5.96 ms: 1.30x slower                                                                                         |
| xml_etree_process    | 46.6 ms                                                                                                 | 60.6 ms: 1.30x slower                                                                                         |
| ascii85_small        | 13.6 ms                                                                                                 | 18.2 ms: 1.34x slower                                                                                         |
| ascii85_large        | 717 ms                                                                                                  | 973 ms: 1.36x slower                                                                                          |
| tomli_loads          | 1.62 sec                                                                                                | 2.24 sec: 1.38x slower                                                                                        |
| base64_small         | 177 us                                                                                                  | 246 us: 1.39x slower                                                                                          |
| urlsafe_base64_small | 325 us                                                                                                  | 456 us: 1.40x slower                                                                                          |
| unpickle_pure_python | 151 us                                                                                                  | 264 us: 1.75x slower                                                                                          |
| pickle_pure_python   | 223 us                                                                                                  | 398 us: 1.78x slower                                                                                          |
| Geometric mean       | (ref)                                                                                                   | 1.19x slower                                                                                                  |

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|------------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                                                                 | 11.6 ms: 1.22x slower                                                                                         |
| python_startup_no_site | 6.46 ms                                                                                                 | 7.98 ms: 1.24x slower                                                                                         |
| Geometric mean         | (ref)                                                                                                   | 1.23x slower                                                                                                  |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| genshi_xml      | 41.3 ms                                                                                                 | 59.7 ms: 1.45x slower                                                                                         |
| django_template | 27.6 ms                                                                                                 | 44.5 ms: 1.61x slower                                                                                         |
| genshi_text     | 17.8 ms                                                                                                 | 30.0 ms: 1.68x slower                                                                                         |
| mako            | 7.16 ms                                                                                                 | 13.7 ms: 1.91x slower                                                                                         |
| Geometric mean  | (ref)                                                                                                   | 1.66x slower                                                                                                  |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| thread_accumulate_optimized | 32.3 ms                                                                                                 | 9.91 ms: 3.26x faster                                                                                         |
| thread_pipeline_optimized   | 20.9 ms                                                                                                 | 6.47 ms: 3.22x faster                                                                                         |
| thread_mandelbrot_naive     | 210 ms                                                                                                  | 67.3 ms: 3.12x faster                                                                                         |
| thread_mandelbrot_optimized | 208 ms                                                                                                  | 66.8 ms: 3.11x faster                                                                                         |
| thread_accumulate_naive     | 33.4 ms                                                                                                 | 11.4 ms: 2.93x faster                                                                                         |
| thread_counter_optimized    | 16.5 ms                                                                                                 | 6.01 ms: 2.75x faster                                                                                         |
| thread_montecarlo_optimized | 14.5 ms                                                                                                 | 5.31 ms: 2.73x faster                                                                                         |
| thread_memo_optimized       | 15.3 ms                                                                                                 | 6.25 ms: 2.44x faster                                                                                         |
| thread_pipeline_naive       | 47.3 ms                                                                                                 | 52.9 ms: 1.12x slower                                                                                         |
| thread_counter_naive        | 20.6 ms                                                                                                 | 27.8 ms: 1.35x slower                                                                                         |
| thread_memo_naive           | 36.1 ms                                                                                                 | 49.9 ms: 1.38x slower                                                                                         |
| thread_montecarlo_naive     | 19.0 ms                                                                                                 | 63.7 ms: 3.35x slower                                                                                         |
| Geometric mean              | (ref)                                                                                                   | 1.74x faster                                                                                                  |

All benchmarks:
===============

| Benchmark                        | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| thread_accumulate_optimized      | 32.3 ms                                                                                                 | 9.91 ms: 3.26x faster                                                                                         |
| thread_pipeline_optimized        | 20.9 ms                                                                                                 | 6.47 ms: 3.22x faster                                                                                         |
| thread_mandelbrot_naive          | 210 ms                                                                                                  | 67.3 ms: 3.12x faster                                                                                         |
| thread_mandelbrot_optimized      | 208 ms                                                                                                  | 66.8 ms: 3.11x faster                                                                                         |
| thread_accumulate_naive          | 33.4 ms                                                                                                 | 11.4 ms: 2.93x faster                                                                                         |
| thread_counter_optimized         | 16.5 ms                                                                                                 | 6.01 ms: 2.75x faster                                                                                         |
| thread_montecarlo_optimized      | 14.5 ms                                                                                                 | 5.31 ms: 2.73x faster                                                                                         |
| thread_memo_optimized            | 15.3 ms                                                                                                 | 6.25 ms: 2.44x faster                                                                                         |
| xml_etree_parse                  | 104 ms                                                                                                  | 91.4 ms: 1.14x faster                                                                                         |
| xml_etree_iterparse              | 79.9 ms                                                                                                 | 71.0 ms: 1.13x faster                                                                                         |
| async_tree_eager_io_tg           | 728 ms                                                                                                  | 653 ms: 1.11x faster                                                                                          |
| async_tree_io_tg                 | 778 ms                                                                                                  | 703 ms: 1.11x faster                                                                                          |
| async_tree_eager_io              | 749 ms                                                                                                  | 703 ms: 1.07x faster                                                                                          |
| regex_effbot                     | 2.30 ms                                                                                                 | 2.21 ms: 1.04x faster                                                                                         |
| async_tree_memoization_tg        | 419 ms                                                                                                  | 404 ms: 1.04x faster                                                                                          |
| asyncio_websockets               | 303 ms                                                                                                  | 295 ms: 1.03x faster                                                                                          |
| pidigits                         | 189 ms                                                                                                  | 185 ms: 1.02x faster                                                                                          |
| pickle_dict                      | 22.0 us                                                                                                 | 21.5 us: 1.02x faster                                                                                         |
| regex_dna                        | 162 ms                                                                                                  | 160 ms: 1.01x faster                                                                                          |
| pickle                           | 7.44 us                                                                                                 | 7.38 us: 1.01x faster                                                                                         |
| base16_large                     | 37.0 ms                                                                                                 | 36.8 ms: 1.01x faster                                                                                         |
| regex_v8                         | 15.2 ms                                                                                                 | 15.2 ms: 1.00x faster                                                                                         |
| base64_large                     | 3.33 ms                                                                                                 | 3.35 ms: 1.01x slower                                                                                         |
| pickle_list                      | 3.14 us                                                                                                 | 3.17 us: 1.01x slower                                                                                         |
| create_gc_cycles                 | 1.75 ms                                                                                                 | 1.78 ms: 1.02x slower                                                                                         |
| gc_traversal                     | 3.07 ms                                                                                                 | 3.15 ms: 1.03x slower                                                                                         |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                                                                  | 506 ms: 1.03x slower                                                                                          |
| json                             | 3.51 ms                                                                                                 | 3.72 ms: 1.06x slower                                                                                         |
| decimal_factorial                | 177 ms                                                                                                  | 190 ms: 1.07x slower                                                                                          |
| unpickle                         | 10.5 us                                                                                                 | 11.3 us: 1.08x slower                                                                                         |
| async_tree_none_tg               | 291 ms                                                                                                  | 313 ms: 1.08x slower                                                                                          |
| networkx_k_core                  | 2.16 sec                                                                                                | 2.38 sec: 1.10x slower                                                                                        |
| base32_large                     | 296 ms                                                                                                  | 327 ms: 1.11x slower                                                                                          |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                | 1.43 sec: 1.11x slower                                                                                        |
| thread_pipeline_naive            | 47.3 ms                                                                                                 | 52.9 ms: 1.12x slower                                                                                         |
| async_tree_memoization           | 388 ms                                                                                                  | 436 ms: 1.13x slower                                                                                          |
| base32_small                     | 5.79 ms                                                                                                 | 6.56 ms: 1.13x slower                                                                                         |
| unpickle_list                    | 3.33 us                                                                                                 | 3.77 us: 1.13x slower                                                                                         |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                                                                  | 325 ms: 1.14x slower                                                                                          |
| decimal_pi                       | 222 ms                                                                                                  | 254 ms: 1.15x slower                                                                                          |
| async_tree_cpu_io_mixed          | 474 ms                                                                                                  | 544 ms: 1.15x slower                                                                                          |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                                                                  | 371 ms: 1.15x slower                                                                                          |
| tornado_http                     | 101 ms                                                                                                  | 116 ms: 1.15x slower                                                                                          |
| async_tree_none                  | 308 ms                                                                                                  | 355 ms: 1.15x slower                                                                                          |
| mdp                              | 2.15 sec                                                                                                | 2.48 sec: 1.15x slower                                                                                        |
| json_loads                       | 16.2 us                                                                                                 | 18.7 us: 1.15x slower                                                                                         |
| generators                       | 21.2 ms                                                                                                 | 24.5 ms: 1.16x slower                                                                                         |
| xml_etree_generate               | 64.2 ms                                                                                                 | 74.4 ms: 1.16x slower                                                                                         |
| async_tree_eager_memoization_tg  | 175 ms                                                                                                  | 204 ms: 1.16x slower                                                                                          |
| async_tree_eager_memoization     | 219 ms                                                                                                  | 257 ms: 1.17x slower                                                                                          |
| networkx_connected_components    | 425 ms                                                                                                  | 505 ms: 1.19x slower                                                                                          |
| asyncio_tcp                      | 318 ms                                                                                                  | 378 ms: 1.19x slower                                                                                          |
| scimark_fft                      | 226 ms                                                                                                  | 270 ms: 1.19x slower                                                                                          |
| json_dumps                       | 6.95 ms                                                                                                 | 8.33 ms: 1.20x slower                                                                                         |
| noop                             | 20.5 ns                                                                                                 | 24.6 ns: 1.20x slower                                                                                         |
| networkx_shortest_path           | 437 ms                                                                                                  | 530 ms: 1.21x slower                                                                                          |
| pylint                           | 227 ms                                                                                                  | 275 ms: 1.21x slower                                                                                          |
| python_startup                   | 9.51 ms                                                                                                 | 11.6 ms: 1.22x slower                                                                                         |
| pathlib                          | 12.8 ms                                                                                                 | 15.6 ms: 1.22x slower                                                                                         |
| scimark_sparse_mat_mult          | 3.14 ms                                                                                                 | 3.85 ms: 1.22x slower                                                                                         |
| docutils                         | 1.89 sec                                                                                                | 2.32 sec: 1.23x slower                                                                                        |
| coroutines                       | 15.4 ms                                                                                                 | 19.0 ms: 1.23x slower                                                                                         |
| python_startup_no_site           | 6.46 ms                                                                                                 | 7.98 ms: 1.24x slower                                                                                         |
| argparse_subparsers              | 452 us                                                                                                  | 558 us: 1.24x slower                                                                                          |
| base16_small                     | 740 us                                                                                                  | 920 us: 1.24x slower                                                                                          |
| telco                            | 5.83 ms                                                                                                 | 7.29 ms: 1.25x slower                                                                                         |
| coverage                         | 55.8 ms                                                                                                 | 69.8 ms: 1.25x slower                                                                                         |
| xdsl_constant_fold               | 36.7 ms                                                                                                 | 46.0 ms: 1.25x slower                                                                                         |
| base85_large                     | 252 ms                                                                                                  | 316 ms: 1.25x slower                                                                                          |
| meteor_contest                   | 84.4 ms                                                                                                 | 107 ms: 1.27x slower                                                                                          |
| bpe_tokeniser                    | 3.30 sec                                                                                                | 4.27 sec: 1.30x slower                                                                                        |
| base85_small                     | 4.59 ms                                                                                                 | 5.96 ms: 1.30x slower                                                                                         |
| async_generators                 | 240 ms                                                                                                  | 312 ms: 1.30x slower                                                                                          |
| xml_etree_process                | 46.6 ms                                                                                                 | 60.6 ms: 1.30x slower                                                                                         |
| pycparser                        | 860 ms                                                                                                  | 1.12 sec: 1.31x slower                                                                                        |
| sympy_integrate                  | 15.8 ms                                                                                                 | 20.8 ms: 1.31x slower                                                                                         |
| fastapi_http                     | 218 ms                                                                                                  | 291 ms: 1.33x slower                                                                                          |
| ascii85_small                    | 13.6 ms                                                                                                 | 18.2 ms: 1.34x slower                                                                                         |
| thread_counter_naive             | 20.6 ms                                                                                                 | 27.8 ms: 1.35x slower                                                                                         |
| ascii85_large                    | 717 ms                                                                                                  | 973 ms: 1.36x slower                                                                                          |
| html5lib                         | 51.7 ms                                                                                                 | 70.5 ms: 1.36x slower                                                                                         |
| thread_memo_naive                | 36.1 ms                                                                                                 | 49.9 ms: 1.38x slower                                                                                         |
| tomli_loads                      | 1.62 sec                                                                                                | 2.24 sec: 1.38x slower                                                                                        |
| base64_small                     | 177 us                                                                                                  | 246 us: 1.39x slower                                                                                          |
| nqueens                          | 53.6 ms                                                                                                 | 74.9 ms: 1.40x slower                                                                                         |
| mypy2                            | 724 ms                                                                                                  | 1.01 sec: 1.40x slower                                                                                        |
| urlsafe_base64_small             | 325 us                                                                                                  | 456 us: 1.40x slower                                                                                          |
| fannkuch                         | 246 ms                                                                                                  | 347 ms: 1.41x slower                                                                                          |
| argparse_many_optionals          | 12.8 ms                                                                                                 | 18.4 ms: 1.43x slower                                                                                         |
| crypto_pyaes                     | 50.9 ms                                                                                                 | 72.9 ms: 1.43x slower                                                                                         |
| pyflate                          | 342 ms                                                                                                  | 490 ms: 1.43x slower                                                                                          |
| sqlglot_v2_optimize              | 40.1 ms                                                                                                 | 57.6 ms: 1.44x slower                                                                                         |
| genshi_xml                       | 41.3 ms                                                                                                 | 59.7 ms: 1.45x slower                                                                                         |
| deepcopy                         | 269 us                                                                                                  | 392 us: 1.46x slower                                                                                          |
| richards                         | 37.8 ms                                                                                                 | 55.0 ms: 1.46x slower                                                                                         |
| sqlglot_v2_normalize             | 80.5 ms                                                                                                 | 118 ms: 1.46x slower                                                                                          |
| deepcopy_reduce                  | 2.40 us                                                                                                 | 3.57 us: 1.49x slower                                                                                         |
| regex_compile                    | 98.5 ms                                                                                                 | 147 ms: 1.49x slower                                                                                          |
| typing_runtime_protocols         | 113 us                                                                                                  | 169 us: 1.50x slower                                                                                          |
| sympy_str                        | 197 ms                                                                                                  | 296 ms: 1.50x slower                                                                                          |
| richards_super                   | 42.8 ms                                                                                                 | 64.6 ms: 1.51x slower                                                                                         |
| async_tree_eager                 | 89.6 ms                                                                                                 | 136 ms: 1.52x slower                                                                                          |
| spectral_norm                    | 65.9 ms                                                                                                 | 102 ms: 1.54x slower                                                                                          |
| deepcopy_memo                    | 26.5 us                                                                                                 | 41.0 us: 1.55x slower                                                                                         |
| async_tree_eager_tg              | 58.6 ms                                                                                                 | 90.8 ms: 1.55x slower                                                                                         |
| comprehensions                   | 10.9 us                                                                                                 | 17.5 us: 1.60x slower                                                                                         |
| django_template                  | 27.6 ms                                                                                                 | 44.5 ms: 1.61x slower                                                                                         |
| pprint_safe_repr                 | 530 ms                                                                                                  | 856 ms: 1.62x slower                                                                                          |
| sympy_expand                     | 336 ms                                                                                                  | 547 ms: 1.63x slower                                                                                          |
| pprint_pformat                   | 1.09 sec                                                                                                | 1.78 sec: 1.63x slower                                                                                        |
| chameleon                        | 9.95 ms                                                                                                 | 16.3 ms: 1.63x slower                                                                                         |
| scimark_monte_carlo              | 46.5 ms                                                                                                 | 76.1 ms: 1.64x slower                                                                                         |
| thrift                           | 2.02 ms                                                                                                 | 3.34 ms: 1.66x slower                                                                                         |
| logging_format                   | 5.25 us                                                                                                 | 8.71 us: 1.66x slower                                                                                         |
| sympy_sum                        | 106 ms                                                                                                  | 178 ms: 1.67x slower                                                                                          |
| genshi_text                      | 17.8 ms                                                                                                 | 30.0 ms: 1.68x slower                                                                                         |
| logging_simple                   | 4.71 us                                                                                                 | 7.96 us: 1.69x slower                                                                                         |
| hexiom                           | 4.30 ms                                                                                                 | 7.30 ms: 1.70x slower                                                                                         |
| float                            | 57.0 ms                                                                                                 | 97.8 ms: 1.72x slower                                                                                         |
| chaos                            | 45.1 ms                                                                                                 | 78.0 ms: 1.73x slower                                                                                         |
| sqlglot_v2_transpile             | 1.20 ms                                                                                                 | 2.11 ms: 1.75x slower                                                                                         |
| unpickle_pure_python             | 151 us                                                                                                  | 264 us: 1.75x slower                                                                                          |
| pickle_pure_python               | 223 us                                                                                                  | 398 us: 1.78x slower                                                                                          |
| go                               | 117 ms                                                                                                  | 209 ms: 1.78x slower                                                                                          |
| logging_silent                   | 61.0 ns                                                                                                 | 115 ns: 1.89x slower                                                                                          |
| raytrace                         | 195 ms                                                                                                  | 373 ms: 1.91x slower                                                                                          |
| mako                             | 7.16 ms                                                                                                 | 13.7 ms: 1.91x slower                                                                                         |
| sqlglot_v2_parse                 | 958 us                                                                                                  | 1.83 ms: 1.91x slower                                                                                         |
| scimark_sor                      | 78.9 ms                                                                                                 | 158 ms: 2.00x slower                                                                                          |
| nbody                            | 65.9 ms                                                                                                 | 142 ms: 2.15x slower                                                                                          |
| quadtree_nbody                   | 626 ms                                                                                                  | 1.36 sec: 2.17x slower                                                                                        |
| scimark_lu                       | 74.5 ms                                                                                                 | 167 ms: 2.25x slower                                                                                          |
| deltablue                        | 2.41 ms                                                                                                 | 5.73 ms: 2.38x slower                                                                                         |
| thread_montecarlo_naive          | 19.0 ms                                                                                                 | 63.7 ms: 3.35x slower                                                                                         |
| unpack_sequence                  | 27.1 ns                                                                                                 | 107 ns: 3.94x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                   | 1.23x slower                                                                                                  |

Benchmark hidden because not significant (1): async_tree_io
Ignored benchmarks (1) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.189x slower

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.20x
- 95% likely to have a slowdown of 1.19x
- 99% likely to have a slowdown of 1.18x

# Memory
- memory change: 1.44x