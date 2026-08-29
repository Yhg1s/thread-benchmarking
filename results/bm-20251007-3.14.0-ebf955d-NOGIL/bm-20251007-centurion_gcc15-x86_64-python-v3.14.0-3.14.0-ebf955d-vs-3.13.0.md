# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.092x faster
- HPT reliability: 65.01%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.61x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 11.9 ms: 1.09x slower                                            |
| docutils       | 1.98 sec                                                         | 2.12 sec: 1.07x slower                                           |
| fastapi_http   | 215 ms                                                           | 185 ms: 1.16x faster                                             |
| html5lib       | 49.1 ms                                                          | 45.7 ms: 1.07x faster                                            |
| tornado_http   | 99.2 ms                                                          | 93.5 ms: 1.06x faster                                            |
| Geometric mean | (ref)                                                            | 1.03x faster                                                     |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_io_tg                 | 777 ms                                                           | 412 ms: 1.89x faster                                             |
| async_tree_memoization_tg        | 417 ms                                                           | 235 ms: 1.77x faster                                             |
| async_tree_eager_io_tg           | 724 ms                                                           | 409 ms: 1.77x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 431 ms: 1.74x faster                                             |
| async_tree_io                    | 741 ms                                                           | 440 ms: 1.68x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 178 ms: 1.62x faster                                             |
| async_tree_memoization           | 389 ms                                                           | 258 ms: 1.51x faster                                             |
| async_tree_none                  | 310 ms                                                           | 208 ms: 1.49x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 392 ms: 1.34x faster                                             |
| async_tree_eager_memoization     | 215 ms                                                           | 173 ms: 1.24x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 418 ms: 1.23x faster                                             |
| coroutines                       | 17.6 ms                                                          | 15.2 ms: 1.16x faster                                            |
| asyncio_websockets               | 304 ms                                                           | 290 ms: 1.05x faster                                             |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 345 ms: 1.04x faster                                             |
| async_generators                 | 262 ms                                                           | 270 ms: 1.03x slower                                             |
| async_tree_eager                 | 90.0 ms                                                          | 96.0 ms: 1.07x slower                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.38 sec: 1.07x slower                                           |
| asyncio_tcp                      | 326 ms                                                           | 360 ms: 1.10x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 376 ms: 1.17x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 213 ms: 1.23x slower                                             |
| async_tree_eager_tg              | 58.6 ms                                                          | 160 ms: 2.72x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.18x faster                                                     |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 21.3 ns: 1.04x slower                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                           | 188 ms: 1.09x slower                                             |
| decimal_pi        | 210 ms                                                           | 241 ms: 1.15x slower                                             |
| Geometric mean    | (ref)                                                            | 1.12x slower                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 51.8 ms: 1.09x faster                                            |
| pidigits       | 181 ms                                                           | 178 ms: 1.02x faster                                             |
| quadtree_nbody | 620 ms                                                           | 626 ms: 1.01x slower                                             |
| nbody          | 66.8 ms                                                          | 83.7 ms: 1.25x slower                                            |
| Geometric mean | (ref)                                                            | 1.03x slower                                                     |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.76 ms: 1.13x faster                                            |
| regex_dna      | 144 ms                                                           | 141 ms: 1.02x faster                                             |
| regex_v8       | 14.7 ms                                                          | 15.3 ms: 1.04x slower                                            |
| regex_compile  | 97.7 ms                                                          | 103 ms: 1.05x slower                                             |
| Geometric mean | (ref)                                                            | 1.01x faster                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.35 ms: 5.90x faster                                            |
| base16_small         | 656 us                                                           | 300 us: 2.19x faster                                             |
| ascii85_large        | 814 ms                                                           | 735 ms: 1.11x faster                                             |
| xml_etree_iterparse  | 69.6 ms                                                          | 63.4 ms: 1.10x faster                                            |
| xml_etree_parse      | 107 ms                                                           | 98.7 ms: 1.09x faster                                            |
| ascii85_small        | 15.5 ms                                                          | 14.3 ms: 1.08x faster                                            |
| tomli_loads          | 1.63 sec                                                         | 1.53 sec: 1.07x faster                                           |
| pickle_dict          | 21.9 us                                                          | 21.3 us: 1.03x faster                                            |
| base64_large         | 6.32 ms                                                          | 6.33 ms: 1.00x slower                                            |
| urlsafe_base64_small | 379 us                                                           | 386 us: 1.02x slower                                             |
| base64_small         | 228 us                                                           | 233 us: 1.02x slower                                             |
| pickle_pure_python   | 223 us                                                           | 234 us: 1.05x slower                                             |
| base85_large         | 243 ms                                                           | 255 ms: 1.05x slower                                             |
| unpickle_pure_python | 149 us                                                           | 157 us: 1.05x slower                                             |
| pickle_list          | 3.03 us                                                          | 3.20 us: 1.06x slower                                            |
| base32_small         | 5.69 ms                                                          | 6.14 ms: 1.08x slower                                            |
| base85_small         | 4.41 ms                                                          | 4.77 ms: 1.08x slower                                            |
| json_dumps           | 7.49 ms                                                          | 8.11 ms: 1.08x slower                                            |
| xml_etree_generate   | 66.3 ms                                                          | 72.0 ms: 1.09x slower                                            |
| base32_large         | 286 ms                                                           | 310 ms: 1.09x slower                                             |
| unpickle             | 10.3 us                                                          | 11.3 us: 1.10x slower                                            |
| xml_etree_process    | 48.1 ms                                                          | 53.3 ms: 1.11x slower                                            |
| pickle               | 8.22 us                                                          | 9.14 us: 1.11x slower                                            |
| json_loads           | 16.7 us                                                          | 20.3 us: 1.22x slower                                            |
| unpickle_list        | 3.45 us                                                          | 4.53 us: 1.31x slower                                            |
| Geometric mean       | (ref)                                                            | 1.07x faster                                                     |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup         | 9.38 ms                                                          | 11.6 ms: 1.24x slower                                            |
| python_startup_no_site | 6.36 ms                                                          | 8.10 ms: 1.27x slower                                            |
| Geometric mean         | (ref)                                                            | 1.26x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| genshi_xml      | 39.7 ms                                                          | 41.7 ms: 1.05x slower                                            |
| genshi_text     | 17.6 ms                                                          | 19.5 ms: 1.11x slower                                            |
| django_template | 27.3 ms                                                          | 31.2 ms: 1.14x slower                                            |
| mako            | 7.43 ms                                                          | 11.9 ms: 1.61x slower                                            |
| Geometric mean  | (ref)                                                            | 1.21x slower                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_pipeline_optimized   | 25.6 ms                                                          | 7.15 ms: 3.58x faster                                            |
| thread_counter_optimized    | 18.7 ms                                                          | 5.28 ms: 3.54x faster                                            |
| thread_accumulate_optimized | 39.8 ms                                                          | 11.3 ms: 3.52x faster                                            |
| thread_mandelbrot_naive     | 220 ms                                                           | 62.7 ms: 3.51x faster                                            |
| thread_mandelbrot_optimized | 218 ms                                                           | 62.0 ms: 3.51x faster                                            |
| thread_memo_optimized       | 18.2 ms                                                          | 5.92 ms: 3.07x faster                                            |
| thread_accumulate_naive     | 40.9 ms                                                          | 13.9 ms: 2.94x faster                                            |
| thread_montecarlo_optimized | 13.3 ms                                                          | 4.75 ms: 2.81x faster                                            |
| thread_pipeline_naive       | 52.1 ms                                                          | 27.2 ms: 1.91x faster                                            |
| thread_memo_naive           | 39.0 ms                                                          | 24.0 ms: 1.62x faster                                            |
| thread_counter_naive        | 22.6 ms                                                          | 21.0 ms: 1.08x faster                                            |
| thread_montecarlo_naive     | 17.8 ms                                                          | 26.3 ms: 1.47x slower                                            |
| Geometric mean              | (ref)                                                            | 2.37x faster                                                     |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.35 ms: 5.90x faster                                            |
| thread_pipeline_optimized        | 25.6 ms                                                          | 7.15 ms: 3.58x faster                                            |
| thread_counter_optimized         | 18.7 ms                                                          | 5.28 ms: 3.54x faster                                            |
| thread_accumulate_optimized      | 39.8 ms                                                          | 11.3 ms: 3.52x faster                                            |
| thread_mandelbrot_naive          | 220 ms                                                           | 62.7 ms: 3.51x faster                                            |
| thread_mandelbrot_optimized      | 218 ms                                                           | 62.0 ms: 3.51x faster                                            |
| thread_memo_optimized            | 18.2 ms                                                          | 5.92 ms: 3.07x faster                                            |
| thread_accumulate_naive          | 40.9 ms                                                          | 13.9 ms: 2.94x faster                                            |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 4.75 ms: 2.81x faster                                            |
| base16_small                     | 656 us                                                           | 300 us: 2.19x faster                                             |
| mdp                              | 2.11 sec                                                         | 990 ms: 2.13x faster                                             |
| gc_traversal                     | 3.16 ms                                                          | 1.56 ms: 2.03x faster                                            |
| thread_pipeline_naive            | 52.1 ms                                                          | 27.2 ms: 1.91x faster                                            |
| async_tree_io_tg                 | 777 ms                                                           | 412 ms: 1.89x faster                                             |
| async_tree_memoization_tg        | 417 ms                                                           | 235 ms: 1.77x faster                                             |
| async_tree_eager_io_tg           | 724 ms                                                           | 409 ms: 1.77x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 431 ms: 1.74x faster                                             |
| async_tree_io                    | 741 ms                                                           | 440 ms: 1.68x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 178 ms: 1.62x faster                                             |
| thread_memo_naive                | 39.0 ms                                                          | 24.0 ms: 1.62x faster                                            |
| async_tree_memoization           | 389 ms                                                           | 258 ms: 1.51x faster                                             |
| async_tree_none                  | 310 ms                                                           | 208 ms: 1.49x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 392 ms: 1.34x faster                                             |
| create_gc_cycles                 | 1.70 ms                                                          | 1.29 ms: 1.31x faster                                            |
| go                               | 121 ms                                                           | 92.3 ms: 1.31x faster                                            |
| async_tree_eager_memoization     | 215 ms                                                           | 173 ms: 1.24x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 418 ms: 1.23x faster                                             |
| deepcopy                         | 267 us                                                           | 218 us: 1.22x faster                                             |
| deepcopy_memo                    | 26.6 us                                                          | 22.1 us: 1.20x faster                                            |
| scimark_sor                      | 97.0 ms                                                          | 81.1 ms: 1.20x faster                                            |
| fastapi_http                     | 215 ms                                                           | 185 ms: 1.16x faster                                             |
| coroutines                       | 17.6 ms                                                          | 15.2 ms: 1.16x faster                                            |
| regex_effbot                     | 1.99 ms                                                          | 1.76 ms: 1.13x faster                                            |
| ascii85_large                    | 814 ms                                                           | 735 ms: 1.11x faster                                             |
| pyflate                          | 358 ms                                                           | 324 ms: 1.11x faster                                             |
| xml_etree_iterparse              | 69.6 ms                                                          | 63.4 ms: 1.10x faster                                            |
| pycparser                        | 884 ms                                                           | 808 ms: 1.09x faster                                             |
| float                            | 56.6 ms                                                          | 51.8 ms: 1.09x faster                                            |
| xml_etree_parse                  | 107 ms                                                           | 98.7 ms: 1.09x faster                                            |
| ascii85_small                    | 15.5 ms                                                          | 14.3 ms: 1.08x faster                                            |
| thread_counter_naive             | 22.6 ms                                                          | 21.0 ms: 1.08x faster                                            |
| thrift                           | 2.07 ms                                                          | 1.92 ms: 1.07x faster                                            |
| html5lib                         | 49.1 ms                                                          | 45.7 ms: 1.07x faster                                            |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.18 sec: 1.07x faster                                           |
| tomli_loads                      | 1.63 sec                                                         | 1.53 sec: 1.07x faster                                           |
| tornado_http                     | 99.2 ms                                                          | 93.5 ms: 1.06x faster                                            |
| asyncio_websockets               | 304 ms                                                           | 290 ms: 1.05x faster                                             |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 345 ms: 1.04x faster                                             |
| generators                       | 22.0 ms                                                          | 21.2 ms: 1.04x faster                                            |
| pickle_dict                      | 21.9 us                                                          | 21.3 us: 1.03x faster                                            |
| pprint_safe_repr                 | 541 ms                                                           | 529 ms: 1.02x faster                                             |
| deltablue                        | 2.52 ms                                                          | 2.46 ms: 1.02x faster                                            |
| deepcopy_reduce                  | 2.37 us                                                          | 2.33 us: 1.02x faster                                            |
| regex_dna                        | 144 ms                                                           | 141 ms: 1.02x faster                                             |
| pidigits                         | 181 ms                                                           | 178 ms: 1.02x faster                                             |
| pprint_pformat                   | 1.11 sec                                                         | 1.10 sec: 1.00x faster                                           |
| base64_large                     | 6.32 ms                                                          | 6.33 ms: 1.00x slower                                            |
| richards                         | 36.8 ms                                                          | 37.1 ms: 1.01x slower                                            |
| hexiom                           | 4.42 ms                                                          | 4.46 ms: 1.01x slower                                            |
| quadtree_nbody                   | 620 ms                                                           | 626 ms: 1.01x slower                                             |
| chaos                            | 45.0 ms                                                          | 45.6 ms: 1.01x slower                                            |
| pathlib                          | 12.4 ms                                                          | 12.6 ms: 1.02x slower                                            |
| urlsafe_base64_small             | 379 us                                                           | 386 us: 1.02x slower                                             |
| base64_small                     | 228 us                                                           | 233 us: 1.02x slower                                             |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 40.9 ms: 1.02x slower                                            |
| async_generators                 | 262 ms                                                           | 270 ms: 1.03x slower                                             |
| sympy_integrate                  | 15.4 ms                                                          | 16.0 ms: 1.04x slower                                            |
| regex_v8                         | 14.7 ms                                                          | 15.3 ms: 1.04x slower                                            |
| scimark_monte_carlo              | 44.3 ms                                                          | 46.1 ms: 1.04x slower                                            |
| noop                             | 20.4 ns                                                          | 21.3 ns: 1.04x slower                                            |
| genshi_xml                       | 39.7 ms                                                          | 41.7 ms: 1.05x slower                                            |
| pickle_pure_python               | 223 us                                                           | 234 us: 1.05x slower                                             |
| base85_large                     | 243 ms                                                           | 255 ms: 1.05x slower                                             |
| regex_compile                    | 97.7 ms                                                          | 103 ms: 1.05x slower                                             |
| richards_super                   | 41.3 ms                                                          | 43.6 ms: 1.05x slower                                            |
| unpickle_pure_python             | 149 us                                                           | 157 us: 1.05x slower                                             |
| pickle_list                      | 3.03 us                                                          | 3.20 us: 1.06x slower                                            |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 83.6 ms: 1.06x slower                                            |
| sympy_sum                        | 104 ms                                                           | 110 ms: 1.06x slower                                             |
| logging_silent                   | 60.6 ns                                                          | 64.4 ns: 1.06x slower                                            |
| async_tree_eager                 | 90.0 ms                                                          | 96.0 ms: 1.07x slower                                            |
| networkx_connected_components    | 460 ms                                                           | 491 ms: 1.07x slower                                             |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.28 ms: 1.07x slower                                            |
| docutils                         | 1.98 sec                                                         | 2.12 sec: 1.07x slower                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.38 sec: 1.07x slower                                           |
| nqueens                          | 57.3 ms                                                          | 61.4 ms: 1.07x slower                                            |
| json                             | 3.49 ms                                                          | 3.75 ms: 1.07x slower                                            |
| sympy_str                        | 193 ms                                                           | 208 ms: 1.07x slower                                             |
| mypy2                            | 726 ms                                                           | 783 ms: 1.08x slower                                             |
| base32_small                     | 5.69 ms                                                          | 6.14 ms: 1.08x slower                                            |
| base85_small                     | 4.41 ms                                                          | 4.77 ms: 1.08x slower                                            |
| meteor_contest                   | 89.9 ms                                                          | 97.4 ms: 1.08x slower                                            |
| json_dumps                       | 7.49 ms                                                          | 8.11 ms: 1.08x slower                                            |
| chameleon                        | 10.9 ms                                                          | 11.9 ms: 1.09x slower                                            |
| xml_etree_generate               | 66.3 ms                                                          | 72.0 ms: 1.09x slower                                            |
| base32_large                     | 286 ms                                                           | 310 ms: 1.09x slower                                             |
| decimal_factorial                | 173 ms                                                           | 188 ms: 1.09x slower                                             |
| logging_format                   | 5.23 us                                                          | 5.71 us: 1.09x slower                                            |
| sympy_expand                     | 330 ms                                                           | 360 ms: 1.09x slower                                             |
| sqlglot_v2_parse                 | 953 us                                                           | 1.04 ms: 1.09x slower                                            |
| spectral_norm                    | 64.1 ms                                                          | 70.0 ms: 1.09x slower                                            |
| comprehensions                   | 11.6 us                                                          | 12.7 us: 1.09x slower                                            |
| networkx_shortest_path           | 464 ms                                                           | 509 ms: 1.10x slower                                             |
| unpickle                         | 10.3 us                                                          | 11.3 us: 1.10x slower                                            |
| fannkuch                         | 265 ms                                                           | 291 ms: 1.10x slower                                             |
| asyncio_tcp                      | 326 ms                                                           | 360 ms: 1.10x slower                                             |
| scimark_fft                      | 211 ms                                                           | 233 ms: 1.11x slower                                             |
| telco                            | 5.50 ms                                                          | 6.10 ms: 1.11x slower                                            |
| xml_etree_process                | 48.1 ms                                                          | 53.3 ms: 1.11x slower                                            |
| sqlalchemy_imperative            | 13.8 ms                                                          | 15.3 ms: 1.11x slower                                            |
| genshi_text                      | 17.6 ms                                                          | 19.5 ms: 1.11x slower                                            |
| pickle                           | 8.22 us                                                          | 9.14 us: 1.11x slower                                            |
| scimark_lu                       | 70.2 ms                                                          | 78.1 ms: 1.11x slower                                            |
| logging_simple                   | 4.60 us                                                          | 5.14 us: 1.12x slower                                            |
| raytrace                         | 199 ms                                                           | 225 ms: 1.13x slower                                             |
| django_template                  | 27.3 ms                                                          | 31.2 ms: 1.14x slower                                            |
| decimal_pi                       | 210 ms                                                           | 241 ms: 1.15x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 376 ms: 1.17x slower                                             |
| json_loads                       | 16.7 us                                                          | 20.3 us: 1.22x slower                                            |
| typing_runtime_protocols         | 106 us                                                           | 130 us: 1.23x slower                                             |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 3.27 ms: 1.23x slower                                            |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 213 ms: 1.23x slower                                             |
| crypto_pyaes                     | 50.0 ms                                                          | 61.7 ms: 1.23x slower                                            |
| python_startup                   | 9.38 ms                                                          | 11.6 ms: 1.24x slower                                            |
| nbody                            | 66.8 ms                                                          | 83.7 ms: 1.25x slower                                            |
| python_startup_no_site           | 6.36 ms                                                          | 8.10 ms: 1.27x slower                                            |
| unpack_sequence                  | 26.2 ns                                                          | 33.8 ns: 1.29x slower                                            |
| unpickle_list                    | 3.45 us                                                          | 4.53 us: 1.31x slower                                            |
| coverage                         | 52.2 ms                                                          | 76.0 ms: 1.46x slower                                            |
| thread_montecarlo_naive          | 17.8 ms                                                          | 26.3 ms: 1.47x slower                                            |
| argparse_subparsers              | 446 us                                                           | 717 us: 1.61x slower                                             |
| mako                             | 7.43 ms                                                          | 11.9 ms: 1.61x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                          | 160 ms: 2.72x slower                                             |
| argparse_many_optionals          | 12.6 ms                                                          | 36.2 ms: 2.88x slower                                            |
| Geometric mean                   | (ref)                                                            | 1.09x faster                                                     |

Benchmark hidden because not significant (3): pylint, networkx_k_core, xdsl_constant_fold

- Geometric mean (including insignificant results): 1.092x faster

# HPT report

- Reliability score: 65.01% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.61x