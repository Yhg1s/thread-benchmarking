# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.080x faster
- HPT reliability: 70.18%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.61x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 12.4 ms: 1.12x slower                                                  |
| docutils       | 1.89 sec                                                           | 2.05 sec: 1.08x slower                                                 |
| fastapi_http   | 215 ms                                                             | 203 ms: 1.06x faster                                                   |
| html5lib       | 50.9 ms                                                            | 49.4 ms: 1.03x faster                                                  |
| tornado_http   | 98.9 ms                                                            | 95.4 ms: 1.04x faster                                                  |
| Geometric mean | (ref)                                                              | 1.01x slower                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_io_tg                 | 781 ms                                                             | 419 ms: 1.86x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 414 ms: 1.76x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 240 ms: 1.75x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 448 ms: 1.68x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 452 ms: 1.64x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 180 ms: 1.61x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 268 ms: 1.46x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 214 ms: 1.46x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 378 ms: 1.34x faster                                                   |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 406 ms: 1.21x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 184 ms: 1.20x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 16.2 ms: 1.12x faster                                                  |
| asyncio_websockets               | 313 ms                                                             | 286 ms: 1.10x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 302 ms: 1.05x faster                                                   |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 338 ms: 1.01x faster                                                   |
| async_generators                 | 251 ms                                                             | 248 ms: 1.01x faster                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.39 sec: 1.08x slower                                                 |
| async_tree_eager                 | 88.3 ms                                                            | 100 ms: 1.14x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 360 ms: 1.20x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 218 ms: 1.25x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 158 ms: 2.78x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.17x faster                                                           |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 22.3 ns: 1.04x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 242 ms: 1.06x slower                                                   |
| decimal_factorial | 177 ms                                                             | 187 ms: 1.06x slower                                                   |
| Geometric mean    | (ref)                                                              | 1.06x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 53.1 ms: 1.11x faster                                                  |
| pidigits       | 216 ms                                                             | 214 ms: 1.01x faster                                                   |
| quadtree_nbody | 675 ms                                                             | 712 ms: 1.06x slower                                                   |
| nbody          | 75.8 ms                                                            | 89.2 ms: 1.18x slower                                                  |
| Geometric mean | (ref)                                                              | 1.03x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 1.95 ms: 1.19x faster                                                  |
| regex_dna      | 159 ms                                                             | 150 ms: 1.06x faster                                                   |
| regex_v8       | 15.0 ms                                                            | 14.9 ms: 1.01x faster                                                  |
| regex_compile  | 102 ms                                                             | 116 ms: 1.14x slower                                                   |
| Geometric mean | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 5.97 ms: 7.15x faster                                                  |
| base16_small         | 836 us                                                             | 255 us: 3.28x faster                                                   |
| xml_etree_iterparse  | 86.8 ms                                                            | 71.5 ms: 1.21x faster                                                  |
| xml_etree_parse      | 121 ms                                                             | 111 ms: 1.09x faster                                                   |
| tomli_loads          | 1.77 sec                                                           | 1.64 sec: 1.08x faster                                                 |
| json_dumps           | 7.26 ms                                                            | 6.91 ms: 1.05x faster                                                  |
| unpickle_list        | 3.42 us                                                            | 3.27 us: 1.05x faster                                                  |
| base64_large         | 5.69 ms                                                            | 5.50 ms: 1.04x faster                                                  |
| unpickle             | 10.8 us                                                            | 10.6 us: 1.02x faster                                                  |
| base32_small         | 6.46 ms                                                            | 6.39 ms: 1.01x faster                                                  |
| pickle_dict          | 19.0 us                                                            | 19.0 us: 1.00x faster                                                  |
| xml_etree_generate   | 70.6 ms                                                            | 72.1 ms: 1.02x slower                                                  |
| ascii85_small        | 15.7 ms                                                            | 16.1 ms: 1.03x slower                                                  |
| urlsafe_base64_small | 328 us                                                             | 338 us: 1.03x slower                                                   |
| ascii85_large        | 824 ms                                                             | 852 ms: 1.03x slower                                                   |
| json_loads           | 18.2 us                                                            | 19.0 us: 1.04x slower                                                  |
| xml_etree_process    | 49.9 ms                                                            | 52.4 ms: 1.05x slower                                                  |
| pickle_list          | 2.66 us                                                            | 2.83 us: 1.06x slower                                                  |
| base85_large         | 267 ms                                                             | 285 ms: 1.07x slower                                                   |
| pickle               | 7.21 us                                                            | 7.72 us: 1.07x slower                                                  |
| base85_small         | 4.85 ms                                                            | 5.39 ms: 1.11x slower                                                  |
| pickle_pure_python   | 245 us                                                             | 283 us: 1.16x slower                                                   |
| unpickle_pure_python | 161 us                                                             | 189 us: 1.17x slower                                                   |
| Geometric mean       | (ref)                                                              | 1.12x faster                                                           |

Benchmark hidden because not significant (2): base64_small, base32_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                            | 11.5 ms: 1.21x slower                                                  |
| python_startup_no_site | 6.49 ms                                                            | 8.11 ms: 1.25x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.23x slower                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 21.7 ms: 1.03x slower                                                  |
| genshi_xml      | 46.3 ms                                                            | 51.2 ms: 1.11x slower                                                  |
| django_template | 28.8 ms                                                            | 35.6 ms: 1.24x slower                                                  |
| mako            | 8.30 ms                                                            | 11.9 ms: 1.44x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.19x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 190 ms                                                             | 52.9 ms: 3.59x faster                                                  |
| thread_mandelbrot_optimized | 189 ms                                                             | 52.8 ms: 3.58x faster                                                  |
| thread_counter_optimized    | 19.7 ms                                                            | 5.79 ms: 3.41x faster                                                  |
| thread_pipeline_optimized   | 22.8 ms                                                            | 7.08 ms: 3.21x faster                                                  |
| thread_accumulate_optimized | 35.3 ms                                                            | 11.2 ms: 3.15x faster                                                  |
| thread_montecarlo_optimized | 14.2 ms                                                            | 4.72 ms: 3.01x faster                                                  |
| thread_memo_optimized       | 16.8 ms                                                            | 5.86 ms: 2.87x faster                                                  |
| thread_accumulate_naive     | 36.5 ms                                                            | 13.2 ms: 2.77x faster                                                  |
| thread_pipeline_naive       | 49.8 ms                                                            | 24.7 ms: 2.02x faster                                                  |
| thread_memo_naive           | 37.9 ms                                                            | 21.3 ms: 1.78x faster                                                  |
| thread_counter_naive        | 23.7 ms                                                            | 20.6 ms: 1.15x faster                                                  |
| thread_montecarlo_naive     | 18.1 ms                                                            | 25.4 ms: 1.40x slower                                                  |
| Geometric mean              | (ref)                                                              | 2.37x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 5.97 ms: 7.15x faster                                                  |
| thread_mandelbrot_naive          | 190 ms                                                             | 52.9 ms: 3.59x faster                                                  |
| thread_mandelbrot_optimized      | 189 ms                                                             | 52.8 ms: 3.58x faster                                                  |
| thread_counter_optimized         | 19.7 ms                                                            | 5.79 ms: 3.41x faster                                                  |
| base16_small                     | 836 us                                                             | 255 us: 3.28x faster                                                   |
| thread_pipeline_optimized        | 22.8 ms                                                            | 7.08 ms: 3.21x faster                                                  |
| thread_accumulate_optimized      | 35.3 ms                                                            | 11.2 ms: 3.15x faster                                                  |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 4.72 ms: 3.01x faster                                                  |
| thread_memo_optimized            | 16.8 ms                                                            | 5.86 ms: 2.87x faster                                                  |
| thread_accumulate_naive          | 36.5 ms                                                            | 13.2 ms: 2.77x faster                                                  |
| gc_traversal                     | 3.20 ms                                                            | 1.55 ms: 2.06x faster                                                  |
| thread_pipeline_naive            | 49.8 ms                                                            | 24.7 ms: 2.02x faster                                                  |
| mdp                              | 2.05 sec                                                           | 1.07 sec: 1.92x faster                                                 |
| async_tree_io_tg                 | 781 ms                                                             | 419 ms: 1.86x faster                                                   |
| thread_memo_naive                | 37.9 ms                                                            | 21.3 ms: 1.78x faster                                                  |
| async_tree_eager_io_tg           | 731 ms                                                             | 414 ms: 1.76x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 240 ms: 1.75x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 448 ms: 1.68x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 452 ms: 1.64x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 180 ms: 1.61x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 268 ms: 1.46x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 214 ms: 1.46x faster                                                   |
| create_gc_cycles                 | 1.77 ms                                                            | 1.24 ms: 1.43x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 378 ms: 1.34x faster                                                   |
| deepcopy_memo                    | 27.8 us                                                            | 22.1 us: 1.26x faster                                                  |
| go                               | 129 ms                                                             | 106 ms: 1.22x faster                                                   |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 406 ms: 1.21x faster                                                   |
| xml_etree_iterparse              | 86.8 ms                                                            | 71.5 ms: 1.21x faster                                                  |
| async_tree_eager_memoization     | 221 ms                                                             | 184 ms: 1.20x faster                                                   |
| regex_effbot                     | 2.33 ms                                                            | 1.95 ms: 1.19x faster                                                  |
| deepcopy                         | 267 us                                                             | 229 us: 1.17x faster                                                   |
| thread_counter_naive             | 23.7 ms                                                            | 20.6 ms: 1.15x faster                                                  |
| coroutines                       | 18.2 ms                                                            | 16.2 ms: 1.12x faster                                                  |
| float                            | 59.2 ms                                                            | 53.1 ms: 1.11x faster                                                  |
| asyncio_websockets               | 313 ms                                                             | 286 ms: 1.10x faster                                                   |
| pathlib                          | 12.2 ms                                                            | 11.1 ms: 1.10x faster                                                  |
| xml_etree_parse                  | 121 ms                                                             | 111 ms: 1.09x faster                                                   |
| tomli_loads                      | 1.77 sec                                                           | 1.64 sec: 1.08x faster                                                 |
| fastapi_http                     | 215 ms                                                             | 203 ms: 1.06x faster                                                   |
| regex_dna                        | 159 ms                                                             | 150 ms: 1.06x faster                                                   |
| pyflate                          | 374 ms                                                             | 355 ms: 1.05x faster                                                   |
| json_dumps                       | 7.26 ms                                                            | 6.91 ms: 1.05x faster                                                  |
| asyncio_tcp                      | 316 ms                                                             | 302 ms: 1.05x faster                                                   |
| unpickle_list                    | 3.42 us                                                            | 3.27 us: 1.05x faster                                                  |
| tornado_http                     | 98.9 ms                                                            | 95.4 ms: 1.04x faster                                                  |
| base64_large                     | 5.69 ms                                                            | 5.50 ms: 1.04x faster                                                  |
| html5lib                         | 50.9 ms                                                            | 49.4 ms: 1.03x faster                                                  |
| unpickle                         | 10.8 us                                                            | 10.6 us: 1.02x faster                                                  |
| json                             | 3.50 ms                                                            | 3.43 ms: 1.02x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 338 ms: 1.01x faster                                                   |
| async_generators                 | 251 ms                                                             | 248 ms: 1.01x faster                                                   |
| base32_small                     | 6.46 ms                                                            | 6.39 ms: 1.01x faster                                                  |
| regex_v8                         | 15.0 ms                                                            | 14.9 ms: 1.01x faster                                                  |
| pidigits                         | 216 ms                                                             | 214 ms: 1.01x faster                                                   |
| pickle_dict                      | 19.0 us                                                            | 19.0 us: 1.00x faster                                                  |
| pycparser                        | 901 ms                                                             | 910 ms: 1.01x slower                                                   |
| xml_etree_generate               | 70.6 ms                                                            | 72.1 ms: 1.02x slower                                                  |
| ascii85_small                    | 15.7 ms                                                            | 16.1 ms: 1.03x slower                                                  |
| genshi_text                      | 21.1 ms                                                            | 21.7 ms: 1.03x slower                                                  |
| scimark_sor                      | 96.2 ms                                                            | 99.2 ms: 1.03x slower                                                  |
| urlsafe_base64_small             | 328 us                                                             | 338 us: 1.03x slower                                                   |
| ascii85_large                    | 824 ms                                                             | 852 ms: 1.03x slower                                                   |
| json_loads                       | 18.2 us                                                            | 19.0 us: 1.04x slower                                                  |
| noop                             | 21.4 ns                                                            | 22.3 ns: 1.04x slower                                                  |
| spectral_norm                    | 68.6 ms                                                            | 71.7 ms: 1.05x slower                                                  |
| xml_etree_process                | 49.9 ms                                                            | 52.4 ms: 1.05x slower                                                  |
| deepcopy_reduce                  | 2.36 us                                                            | 2.48 us: 1.05x slower                                                  |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 44.4 ms: 1.05x slower                                                  |
| quadtree_nbody                   | 675 ms                                                             | 712 ms: 1.06x slower                                                   |
| telco                            | 5.37 ms                                                            | 5.68 ms: 1.06x slower                                                  |
| decimal_pi                       | 228 ms                                                             | 242 ms: 1.06x slower                                                   |
| decimal_factorial                | 177 ms                                                             | 187 ms: 1.06x slower                                                   |
| pickle_list                      | 2.66 us                                                            | 2.83 us: 1.06x slower                                                  |
| base85_large                     | 267 ms                                                             | 285 ms: 1.07x slower                                                   |
| thrift                           | 2.07 ms                                                            | 2.22 ms: 1.07x slower                                                  |
| pickle                           | 7.21 us                                                            | 7.72 us: 1.07x slower                                                  |
| scimark_fft                      | 216 ms                                                             | 234 ms: 1.08x slower                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.39 sec: 1.08x slower                                                 |
| docutils                         | 1.89 sec                                                           | 2.05 sec: 1.08x slower                                                 |
| scimark_monte_carlo              | 47.2 ms                                                            | 51.7 ms: 1.10x slower                                                  |
| sympy_integrate                  | 15.4 ms                                                            | 16.9 ms: 1.10x slower                                                  |
| fannkuch                         | 287 ms                                                             | 316 ms: 1.10x slower                                                   |
| genshi_xml                       | 46.3 ms                                                            | 51.2 ms: 1.11x slower                                                  |
| mypy2                            | 741 ms                                                             | 821 ms: 1.11x slower                                                   |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 92.9 ms: 1.11x slower                                                  |
| base85_small                     | 4.85 ms                                                            | 5.39 ms: 1.11x slower                                                  |
| chameleon                        | 11.1 ms                                                            | 12.4 ms: 1.12x slower                                                  |
| sympy_sum                        | 104 ms                                                             | 118 ms: 1.13x slower                                                   |
| async_tree_eager                 | 88.3 ms                                                            | 100 ms: 1.14x slower                                                   |
| regex_compile                    | 102 ms                                                             | 116 ms: 1.14x slower                                                   |
| meteor_contest                   | 85.7 ms                                                            | 97.7 ms: 1.14x slower                                                  |
| xdsl_constant_fold               | 36.4 ms                                                            | 41.5 ms: 1.14x slower                                                  |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.9 ms: 1.15x slower                                                  |
| hexiom                           | 4.75 ms                                                            | 5.47 ms: 1.15x slower                                                  |
| chaos                            | 43.6 ms                                                            | 50.2 ms: 1.15x slower                                                  |
| pickle_pure_python               | 245 us                                                             | 283 us: 1.16x slower                                                   |
| logging_simple                   | 5.06 us                                                            | 5.86 us: 1.16x slower                                                  |
| pprint_safe_repr                 | 546 ms                                                             | 634 ms: 1.16x slower                                                   |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.42 ms: 1.16x slower                                                  |
| crypto_pyaes                     | 55.6 ms                                                            | 64.6 ms: 1.16x slower                                                  |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 3.32 ms: 1.16x slower                                                  |
| richards                         | 38.2 ms                                                            | 44.4 ms: 1.16x slower                                                  |
| pprint_pformat                   | 1.13 sec                                                           | 1.31 sec: 1.17x slower                                                 |
| comprehensions                   | 11.4 us                                                            | 13.3 us: 1.17x slower                                                  |
| unpickle_pure_python             | 161 us                                                             | 189 us: 1.17x slower                                                   |
| logging_format                   | 5.62 us                                                            | 6.62 us: 1.18x slower                                                  |
| nbody                            | 75.8 ms                                                            | 89.2 ms: 1.18x slower                                                  |
| sympy_str                        | 193 ms                                                             | 228 ms: 1.18x slower                                                   |
| sqlglot_v2_parse                 | 979 us                                                             | 1.16 ms: 1.18x slower                                                  |
| sympy_expand                     | 331 ms                                                             | 393 ms: 1.19x slower                                                   |
| generators                       | 22.2 ms                                                            | 26.4 ms: 1.19x slower                                                  |
| raytrace                         | 197 ms                                                             | 235 ms: 1.19x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 360 ms: 1.20x slower                                                   |
| deltablue                        | 2.59 ms                                                            | 3.13 ms: 1.21x slower                                                  |
| python_startup                   | 9.51 ms                                                            | 11.5 ms: 1.21x slower                                                  |
| nqueens                          | 58.3 ms                                                            | 70.9 ms: 1.22x slower                                                  |
| typing_runtime_protocols         | 112 us                                                             | 137 us: 1.22x slower                                                   |
| logging_silent                   | 60.1 ns                                                            | 73.4 ns: 1.22x slower                                                  |
| django_template                  | 28.8 ms                                                            | 35.6 ms: 1.24x slower                                                  |
| richards_super                   | 43.8 ms                                                            | 54.6 ms: 1.25x slower                                                  |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 218 ms: 1.25x slower                                                   |
| python_startup_no_site           | 6.49 ms                                                            | 8.11 ms: 1.25x slower                                                  |
| scimark_lu                       | 70.2 ms                                                            | 89.6 ms: 1.28x slower                                                  |
| coverage                         | 55.0 ms                                                            | 73.4 ms: 1.33x slower                                                  |
| thread_montecarlo_naive          | 18.1 ms                                                            | 25.4 ms: 1.40x slower                                                  |
| mako                             | 8.30 ms                                                            | 11.9 ms: 1.44x slower                                                  |
| unpack_sequence                  | 26.4 ns                                                            | 38.9 ns: 1.47x slower                                                  |
| argparse_subparsers              | 449 us                                                             | 758 us: 1.69x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 158 ms: 2.78x slower                                                   |
| argparse_many_optionals          | 12.9 ms                                                            | 39.8 ms: 3.08x slower                                                  |
| Geometric mean                   | (ref)                                                              | 1.08x faster                                                           |

Benchmark hidden because not significant (4): bpe_tokeniser, base64_small, base32_large, pylint
Ignored benchmarks (3) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json: networkx_connected_components, networkx_k_core, networkx_shortest_path

- Geometric mean (including insignificant results): 1.080x faster

# HPT report

- Reliability score: 70.18% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.61x