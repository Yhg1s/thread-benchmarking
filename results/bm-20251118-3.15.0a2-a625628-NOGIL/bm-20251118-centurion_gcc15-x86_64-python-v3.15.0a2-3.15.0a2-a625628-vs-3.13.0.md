# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.121x faster
- HPT reliability: 95.27%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.63x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 11.7 ms: 1.07x slower                                                |
| docutils       | 1.98 sec                                                         | 2.05 sec: 1.04x slower                                               |
| fastapi_http   | 215 ms                                                           | 181 ms: 1.18x faster                                                 |
| html5lib       | 49.1 ms                                                          | 44.9 ms: 1.09x faster                                                |
| tornado_http   | 99.2 ms                                                          | 91.8 ms: 1.08x faster                                                |
| Geometric mean | (ref)                                                            | 1.05x faster                                                         |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| async_tree_io_tg                 | 777 ms                                                           | 392 ms: 1.98x faster                                                 |
| async_tree_eager_io_tg           | 724 ms                                                           | 384 ms: 1.88x faster                                                 |
| async_tree_memoization_tg        | 417 ms                                                           | 226 ms: 1.85x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 417 ms: 1.80x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 425 ms: 1.74x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 170 ms: 1.70x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 198 ms: 1.56x faster                                                 |
| async_tree_memoization           | 389 ms                                                           | 249 ms: 1.56x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 379 ms: 1.39x faster                                                 |
| async_tree_eager_memoization     | 215 ms                                                           | 166 ms: 1.29x faster                                                 |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 401 ms: 1.28x faster                                                 |
| coroutines                       | 17.6 ms                                                          | 15.2 ms: 1.15x faster                                                |
| asyncio_tcp                      | 326 ms                                                           | 299 ms: 1.09x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 331 ms: 1.09x faster                                                 |
| asyncio_websockets               | 304 ms                                                           | 291 ms: 1.04x faster                                                 |
| async_tree_eager                 | 90.0 ms                                                          | 88.4 ms: 1.02x faster                                                |
| async_generators                 | 262 ms                                                           | 264 ms: 1.01x slower                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.37 sec: 1.07x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 357 ms: 1.11x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 203 ms: 1.18x slower                                                 |
| async_tree_eager_tg              | 58.6 ms                                                          | 149 ms: 2.55x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.24x faster                                                         |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 21.4 ns: 1.05x slower                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                           | 184 ms: 1.07x slower                                                 |
| decimal_pi        | 210 ms                                                           | 231 ms: 1.10x slower                                                 |
| Geometric mean    | (ref)                                                            | 1.09x slower                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 49.3 ms: 1.15x faster                                                |
| pidigits       | 181 ms                                                           | 179 ms: 1.01x faster                                                 |
| quadtree_nbody | 620 ms                                                           | 615 ms: 1.01x faster                                                 |
| nbody          | 66.8 ms                                                          | 83.1 ms: 1.24x slower                                                |
| Geometric mean | (ref)                                                            | 1.01x slower                                                         |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.79 ms: 1.12x faster                                                |
| regex_dna      | 144 ms                                                           | 142 ms: 1.01x faster                                                 |
| regex_v8       | 14.7 ms                                                          | 14.6 ms: 1.00x faster                                                |
| regex_compile  | 97.7 ms                                                          | 100 ms: 1.03x slower                                                 |
| Geometric mean | (ref)                                                            | 1.03x faster                                                         |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.09 ms: 6.21x faster                                                |
| base16_small         | 656 us                                                           | 299 us: 2.20x faster                                                 |
| tomli_loads          | 1.63 sec                                                         | 1.44 sec: 1.13x faster                                               |
| base64_large         | 6.32 ms                                                          | 5.63 ms: 1.12x faster                                                |
| ascii85_large        | 814 ms                                                           | 739 ms: 1.10x faster                                                 |
| xml_etree_iterparse  | 69.6 ms                                                          | 63.8 ms: 1.09x faster                                                |
| ascii85_small        | 15.5 ms                                                          | 14.2 ms: 1.09x faster                                                |
| xml_etree_parse      | 107 ms                                                           | 98.9 ms: 1.09x faster                                                |
| base64_small         | 228 us                                                           | 217 us: 1.05x faster                                                 |
| json_dumps           | 7.49 ms                                                          | 7.23 ms: 1.04x faster                                                |
| pickle_dict          | 21.9 us                                                          | 21.2 us: 1.03x faster                                                |
| urlsafe_base64_small | 379 us                                                           | 371 us: 1.02x faster                                                 |
| pickle_list          | 3.03 us                                                          | 3.24 us: 1.07x slower                                                |
| base32_small         | 5.69 ms                                                          | 6.13 ms: 1.08x slower                                                |
| unpickle_pure_python | 149 us                                                           | 160 us: 1.08x slower                                                 |
| base32_large         | 286 ms                                                           | 309 ms: 1.08x slower                                                 |
| unpickle             | 10.3 us                                                          | 11.1 us: 1.08x slower                                                |
| base85_large         | 243 ms                                                           | 266 ms: 1.10x slower                                                 |
| xml_etree_process    | 48.1 ms                                                          | 52.9 ms: 1.10x slower                                                |
| pickle               | 8.22 us                                                          | 9.11 us: 1.11x slower                                                |
| xml_etree_generate   | 66.3 ms                                                          | 73.8 ms: 1.11x slower                                                |
| base85_small         | 4.41 ms                                                          | 4.95 ms: 1.12x slower                                                |
| json_loads           | 16.7 us                                                          | 19.5 us: 1.17x slower                                                |
| pickle_pure_python   | 223 us                                                           | 265 us: 1.19x slower                                                 |
| unpickle_list        | 3.45 us                                                          | 4.46 us: 1.29x slower                                                |
| Geometric mean       | (ref)                                                            | 1.08x faster                                                         |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup         | 9.38 ms                                                          | 11.5 ms: 1.23x slower                                                |
| python_startup_no_site | 6.36 ms                                                          | 8.04 ms: 1.26x slower                                                |
| Geometric mean         | (ref)                                                            | 1.25x slower                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| genshi_xml      | 39.7 ms                                                          | 41.5 ms: 1.04x slower                                                |
| genshi_text     | 17.6 ms                                                          | 18.9 ms: 1.07x slower                                                |
| django_template | 27.3 ms                                                          | 29.9 ms: 1.10x slower                                                |
| mako            | 7.43 ms                                                          | 11.0 ms: 1.49x slower                                                |
| Geometric mean  | (ref)                                                            | 1.16x slower                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 220 ms                                                           | 61.0 ms: 3.60x faster                                                |
| thread_mandelbrot_optimized | 218 ms                                                           | 60.5 ms: 3.60x faster                                                |
| thread_pipeline_optimized   | 25.6 ms                                                          | 7.32 ms: 3.50x faster                                                |
| thread_accumulate_optimized | 39.8 ms                                                          | 11.7 ms: 3.40x faster                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 5.73 ms: 3.26x faster                                                |
| thread_memo_optimized       | 18.2 ms                                                          | 6.11 ms: 2.98x faster                                                |
| thread_accumulate_naive     | 40.9 ms                                                          | 13.8 ms: 2.97x faster                                                |
| thread_montecarlo_optimized | 13.3 ms                                                          | 4.75 ms: 2.81x faster                                                |
| thread_pipeline_naive       | 52.1 ms                                                          | 24.5 ms: 2.12x faster                                                |
| thread_memo_naive           | 39.0 ms                                                          | 21.1 ms: 1.85x faster                                                |
| thread_counter_naive        | 22.6 ms                                                          | 20.8 ms: 1.09x faster                                                |
| thread_montecarlo_naive     | 17.8 ms                                                          | 24.9 ms: 1.40x slower                                                |
| Geometric mean              | (ref)                                                            | 2.41x faster                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.09 ms: 6.21x faster                                                |
| thread_mandelbrot_naive          | 220 ms                                                           | 61.0 ms: 3.60x faster                                                |
| thread_mandelbrot_optimized      | 218 ms                                                           | 60.5 ms: 3.60x faster                                                |
| thread_pipeline_optimized        | 25.6 ms                                                          | 7.32 ms: 3.50x faster                                                |
| thread_accumulate_optimized      | 39.8 ms                                                          | 11.7 ms: 3.40x faster                                                |
| thread_counter_optimized         | 18.7 ms                                                          | 5.73 ms: 3.26x faster                                                |
| thread_memo_optimized            | 18.2 ms                                                          | 6.11 ms: 2.98x faster                                                |
| thread_accumulate_naive          | 40.9 ms                                                          | 13.8 ms: 2.97x faster                                                |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 4.75 ms: 2.81x faster                                                |
| mdp                              | 2.11 sec                                                         | 959 ms: 2.20x faster                                                 |
| base16_small                     | 656 us                                                           | 299 us: 2.20x faster                                                 |
| gc_traversal                     | 3.16 ms                                                          | 1.48 ms: 2.13x faster                                                |
| thread_pipeline_naive            | 52.1 ms                                                          | 24.5 ms: 2.12x faster                                                |
| async_tree_io_tg                 | 777 ms                                                           | 392 ms: 1.98x faster                                                 |
| async_tree_eager_io_tg           | 724 ms                                                           | 384 ms: 1.88x faster                                                 |
| async_tree_memoization_tg        | 417 ms                                                           | 226 ms: 1.85x faster                                                 |
| thread_memo_naive                | 39.0 ms                                                          | 21.1 ms: 1.85x faster                                                |
| async_tree_eager_io              | 749 ms                                                           | 417 ms: 1.80x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 425 ms: 1.74x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 170 ms: 1.70x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 198 ms: 1.56x faster                                                 |
| async_tree_memoization           | 389 ms                                                           | 249 ms: 1.56x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 379 ms: 1.39x faster                                                 |
| go                               | 121 ms                                                           | 90.0 ms: 1.35x faster                                                |
| deepcopy_memo                    | 26.6 us                                                          | 20.0 us: 1.33x faster                                                |
| deepcopy                         | 267 us                                                           | 202 us: 1.32x faster                                                 |
| create_gc_cycles                 | 1.70 ms                                                          | 1.31 ms: 1.30x faster                                                |
| async_tree_eager_memoization     | 215 ms                                                           | 166 ms: 1.29x faster                                                 |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 401 ms: 1.28x faster                                                 |
| scimark_sor                      | 97.0 ms                                                          | 81.1 ms: 1.20x faster                                                |
| fastapi_http                     | 215 ms                                                           | 181 ms: 1.18x faster                                                 |
| coroutines                       | 17.6 ms                                                          | 15.2 ms: 1.15x faster                                                |
| pathlib                          | 12.4 ms                                                          | 10.8 ms: 1.15x faster                                                |
| float                            | 56.6 ms                                                          | 49.3 ms: 1.15x faster                                                |
| tomli_loads                      | 1.63 sec                                                         | 1.44 sec: 1.13x faster                                               |
| base64_large                     | 6.32 ms                                                          | 5.63 ms: 1.12x faster                                                |
| regex_effbot                     | 1.99 ms                                                          | 1.79 ms: 1.12x faster                                                |
| pycparser                        | 884 ms                                                           | 796 ms: 1.11x faster                                                 |
| pyflate                          | 358 ms                                                           | 323 ms: 1.11x faster                                                 |
| ascii85_large                    | 814 ms                                                           | 739 ms: 1.10x faster                                                 |
| asyncio_tcp                      | 326 ms                                                           | 299 ms: 1.09x faster                                                 |
| html5lib                         | 49.1 ms                                                          | 44.9 ms: 1.09x faster                                                |
| xml_etree_iterparse              | 69.6 ms                                                          | 63.8 ms: 1.09x faster                                                |
| ascii85_small                    | 15.5 ms                                                          | 14.2 ms: 1.09x faster                                                |
| thread_counter_naive             | 22.6 ms                                                          | 20.8 ms: 1.09x faster                                                |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 331 ms: 1.09x faster                                                 |
| xml_etree_parse                  | 107 ms                                                           | 98.9 ms: 1.09x faster                                                |
| thrift                           | 2.07 ms                                                          | 1.91 ms: 1.08x faster                                                |
| tornado_http                     | 99.2 ms                                                          | 91.8 ms: 1.08x faster                                                |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.16 sec: 1.08x faster                                               |
| deepcopy_reduce                  | 2.37 us                                                          | 2.25 us: 1.05x faster                                                |
| base64_small                     | 228 us                                                           | 217 us: 1.05x faster                                                 |
| asyncio_websockets               | 304 ms                                                           | 291 ms: 1.04x faster                                                 |
| pprint_safe_repr                 | 541 ms                                                           | 520 ms: 1.04x faster                                                 |
| json_dumps                       | 7.49 ms                                                          | 7.23 ms: 1.04x faster                                                |
| pickle_dict                      | 21.9 us                                                          | 21.2 us: 1.03x faster                                                |
| hexiom                           | 4.42 ms                                                          | 4.31 ms: 1.03x faster                                                |
| urlsafe_base64_small             | 379 us                                                           | 371 us: 1.02x faster                                                 |
| pprint_pformat                   | 1.11 sec                                                         | 1.09 sec: 1.02x faster                                               |
| async_tree_eager                 | 90.0 ms                                                          | 88.4 ms: 1.02x faster                                                |
| pidigits                         | 181 ms                                                           | 179 ms: 1.01x faster                                                 |
| regex_dna                        | 144 ms                                                           | 142 ms: 1.01x faster                                                 |
| deltablue                        | 2.52 ms                                                          | 2.49 ms: 1.01x faster                                                |
| quadtree_nbody                   | 620 ms                                                           | 615 ms: 1.01x faster                                                 |
| regex_v8                         | 14.7 ms                                                          | 14.6 ms: 1.00x faster                                                |
| comprehensions                   | 11.6 us                                                          | 11.7 us: 1.00x slower                                                |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 40.3 ms: 1.01x slower                                                |
| async_generators                 | 262 ms                                                           | 264 ms: 1.01x slower                                                 |
| scimark_fft                      | 211 ms                                                           | 213 ms: 1.01x slower                                                 |
| richards                         | 36.8 ms                                                          | 37.4 ms: 1.02x slower                                                |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 80.4 ms: 1.02x slower                                                |
| chaos                            | 45.0 ms                                                          | 45.9 ms: 1.02x slower                                                |
| sympy_integrate                  | 15.4 ms                                                          | 15.8 ms: 1.02x slower                                                |
| regex_compile                    | 97.7 ms                                                          | 100 ms: 1.03x slower                                                 |
| docutils                         | 1.98 sec                                                         | 2.05 sec: 1.04x slower                                               |
| json                             | 3.49 ms                                                          | 3.63 ms: 1.04x slower                                                |
| genshi_xml                       | 39.7 ms                                                          | 41.5 ms: 1.04x slower                                                |
| scimark_monte_carlo              | 44.3 ms                                                          | 46.3 ms: 1.05x slower                                                |
| logging_silent                   | 60.6 ns                                                          | 63.3 ns: 1.05x slower                                                |
| xdsl_constant_fold               | 36.7 ms                                                          | 38.5 ms: 1.05x slower                                                |
| sympy_sum                        | 104 ms                                                           | 109 ms: 1.05x slower                                                 |
| noop                             | 20.4 ns                                                          | 21.4 ns: 1.05x slower                                                |
| mypy2                            | 726 ms                                                           | 766 ms: 1.05x slower                                                 |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.26 ms: 1.06x slower                                                |
| meteor_contest                   | 89.9 ms                                                          | 95.1 ms: 1.06x slower                                                |
| richards_super                   | 41.3 ms                                                          | 43.8 ms: 1.06x slower                                                |
| sympy_str                        | 193 ms                                                           | 205 ms: 1.06x slower                                                 |
| sympy_expand                     | 330 ms                                                           | 351 ms: 1.06x slower                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.37 sec: 1.07x slower                                               |
| chameleon                        | 10.9 ms                                                          | 11.7 ms: 1.07x slower                                                |
| logging_format                   | 5.23 us                                                          | 5.58 us: 1.07x slower                                                |
| pickle_list                      | 3.03 us                                                          | 3.24 us: 1.07x slower                                                |
| decimal_factorial                | 173 ms                                                           | 184 ms: 1.07x slower                                                 |
| genshi_text                      | 17.6 ms                                                          | 18.9 ms: 1.07x slower                                                |
| sqlglot_v2_parse                 | 953 us                                                           | 1.03 ms: 1.08x slower                                                |
| nqueens                          | 57.3 ms                                                          | 61.8 ms: 1.08x slower                                                |
| base32_small                     | 5.69 ms                                                          | 6.13 ms: 1.08x slower                                                |
| unpickle_pure_python             | 149 us                                                           | 160 us: 1.08x slower                                                 |
| logging_simple                   | 4.60 us                                                          | 4.97 us: 1.08x slower                                                |
| scimark_lu                       | 70.2 ms                                                          | 76.0 ms: 1.08x slower                                                |
| base32_large                     | 286 ms                                                           | 309 ms: 1.08x slower                                                 |
| unpickle                         | 10.3 us                                                          | 11.1 us: 1.08x slower                                                |
| fannkuch                         | 265 ms                                                           | 290 ms: 1.09x slower                                                 |
| base85_large                     | 243 ms                                                           | 266 ms: 1.10x slower                                                 |
| django_template                  | 27.3 ms                                                          | 29.9 ms: 1.10x slower                                                |
| xml_etree_process                | 48.1 ms                                                          | 52.9 ms: 1.10x slower                                                |
| decimal_pi                       | 210 ms                                                           | 231 ms: 1.10x slower                                                 |
| pickle                           | 8.22 us                                                          | 9.11 us: 1.11x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 357 ms: 1.11x slower                                                 |
| spectral_norm                    | 64.1 ms                                                          | 71.2 ms: 1.11x slower                                                |
| xml_etree_generate               | 66.3 ms                                                          | 73.8 ms: 1.11x slower                                                |
| sqlalchemy_imperative            | 13.8 ms                                                          | 15.5 ms: 1.12x slower                                                |
| base85_small                     | 4.41 ms                                                          | 4.95 ms: 1.12x slower                                                |
| raytrace                         | 199 ms                                                           | 224 ms: 1.13x slower                                                 |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 3.08 ms: 1.16x slower                                                |
| json_loads                       | 16.7 us                                                          | 19.5 us: 1.17x slower                                                |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 203 ms: 1.18x slower                                                 |
| pickle_pure_python               | 223 us                                                           | 265 us: 1.19x slower                                                 |
| typing_runtime_protocols         | 106 us                                                           | 126 us: 1.19x slower                                                 |
| unpack_sequence                  | 26.2 ns                                                          | 31.8 ns: 1.21x slower                                                |
| python_startup                   | 9.38 ms                                                          | 11.5 ms: 1.23x slower                                                |
| nbody                            | 66.8 ms                                                          | 83.1 ms: 1.24x slower                                                |
| crypto_pyaes                     | 50.0 ms                                                          | 63.2 ms: 1.26x slower                                                |
| python_startup_no_site           | 6.36 ms                                                          | 8.04 ms: 1.26x slower                                                |
| unpickle_list                    | 3.45 us                                                          | 4.46 us: 1.29x slower                                                |
| thread_montecarlo_naive          | 17.8 ms                                                          | 24.9 ms: 1.40x slower                                                |
| coverage                         | 52.2 ms                                                          | 75.1 ms: 1.44x slower                                                |
| mako                             | 7.43 ms                                                          | 11.0 ms: 1.49x slower                                                |
| argparse_subparsers              | 446 us                                                           | 701 us: 1.57x slower                                                 |
| async_tree_eager_tg              | 58.6 ms                                                          | 149 ms: 2.55x slower                                                 |
| argparse_many_optionals          | 12.6 ms                                                          | 36.4 ms: 2.90x slower                                                |
| Geometric mean                   | (ref)                                                            | 1.12x faster                                                         |

Benchmark hidden because not significant (3): pylint, generators, telco
Ignored benchmarks (3) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json: networkx_connected_components, networkx_k_core, networkx_shortest_path

- Geometric mean (including insignificant results): 1.121x faster

# HPT report

- Reliability score: 95.27% likely to be faster
- 90% likely to have a speedup of 1.01x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.63x