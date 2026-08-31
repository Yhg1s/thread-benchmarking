# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.058x faster
- HPT reliability: 99.88%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.04x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 10.1 ms: 1.02x slower                                           |
| docutils       | 1.89 sec                                                        | 2.05 sec: 1.08x slower                                          |
| fastapi_http   | 218 ms                                                          | 212 ms: 1.03x faster                                            |
| html5lib       | 51.7 ms                                                         | 48.5 ms: 1.07x faster                                           |
| tornado_http   | 101 ms                                                          | 102 ms: 1.01x slower                                            |
| Geometric mean | (ref)                                                           | 1.00x slower                                                    |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_memoization_tg        | 419 ms                                                          | 273 ms: 1.54x faster                                            |
| async_tree_io_tg                 | 778 ms                                                          | 528 ms: 1.47x faster                                            |
| async_tree_io                    | 741 ms                                                          | 520 ms: 1.43x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 531 ms: 1.41x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 277 ms: 1.40x faster                                            |
| async_tree_none                  | 308 ms                                                          | 225 ms: 1.37x faster                                            |
| async_tree_eager_io_tg           | 728 ms                                                          | 540 ms: 1.35x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 223 ms: 1.30x faster                                            |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 399 ms: 1.23x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 183 ms: 1.20x faster                                            |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 401 ms: 1.18x faster                                            |
| asyncio_tcp                      | 318 ms                                                          | 292 ms: 1.09x faster                                            |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 311 ms: 1.04x faster                                            |
| async_tree_eager                 | 89.6 ms                                                         | 86.6 ms: 1.03x faster                                           |
| coroutines                       | 15.4 ms                                                         | 15.6 ms: 1.01x slower                                           |
| async_generators                 | 240 ms                                                          | 245 ms: 1.02x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 360 ms: 1.26x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 241 ms: 1.38x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 176 ms: 3.00x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.09x faster                                                    |

Benchmark hidden because not significant (2): asyncio_websockets, asyncio_tcp_ssl

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 16.8 ns: 1.22x faster                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                          | 198 ms: 1.12x faster                                            |
| decimal_factorial | 177 ms                                                          | 173 ms: 1.02x faster                                            |
| Geometric mean    | (ref)                                                           | 1.07x faster                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 39.8 ms: 1.43x faster                                           |
| quadtree_nbody | 626 ms                                                          | 585 ms: 1.07x faster                                            |
| pidigits       | 189 ms                                                          | 189 ms: 1.00x slower                                            |
| nbody          | 65.9 ms                                                         | 80.8 ms: 1.23x slower                                           |
| Geometric mean | (ref)                                                           | 1.06x faster                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 1.98 ms: 1.16x faster                                           |
| regex_dna      | 162 ms                                                          | 150 ms: 1.08x faster                                            |
| regex_compile  | 98.5 ms                                                         | 95.2 ms: 1.03x faster                                           |
| regex_v8       | 15.2 ms                                                         | 15.6 ms: 1.02x slower                                           |
| Geometric mean | (ref)                                                           | 1.06x faster                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 5.34 ms: 6.93x faster                                           |
| base16_small         | 740 us                                                          | 312 us: 2.37x faster                                            |
| ascii85_large        | 717 ms                                                          | 600 ms: 1.19x faster                                            |
| tomli_loads          | 1.62 sec                                                        | 1.38 sec: 1.17x faster                                          |
| unpickle_pure_python | 151 us                                                          | 130 us: 1.16x faster                                            |
| ascii85_small        | 13.6 ms                                                         | 11.8 ms: 1.15x faster                                           |
| xml_etree_generate   | 64.2 ms                                                         | 57.4 ms: 1.12x faster                                           |
| xml_etree_process    | 46.6 ms                                                         | 41.9 ms: 1.11x faster                                           |
| xml_etree_parse      | 104 ms                                                          | 94.0 ms: 1.11x faster                                           |
| base85_large         | 252 ms                                                          | 237 ms: 1.06x faster                                            |
| xml_etree_iterparse  | 79.9 ms                                                         | 75.4 ms: 1.06x faster                                           |
| base85_small         | 4.59 ms                                                         | 4.43 ms: 1.04x faster                                           |
| base32_large         | 296 ms                                                          | 288 ms: 1.03x faster                                            |
| pickle_dict          | 22.0 us                                                         | 21.5 us: 1.02x faster                                           |
| base32_small         | 5.79 ms                                                         | 5.70 ms: 1.02x faster                                           |
| unpickle             | 10.5 us                                                         | 10.5 us: 1.01x faster                                           |
| unpickle_list        | 3.33 us                                                         | 3.35 us: 1.01x slower                                           |
| urlsafe_base64_small | 325 us                                                          | 332 us: 1.02x slower                                            |
| base64_small         | 177 us                                                          | 185 us: 1.04x slower                                            |
| pickle_list          | 3.14 us                                                         | 3.27 us: 1.04x slower                                           |
| json_loads           | 16.2 us                                                         | 17.4 us: 1.07x slower                                           |
| base64_large         | 3.33 ms                                                         | 3.63 ms: 1.09x slower                                           |
| pickle_pure_python   | 223 us                                                          | 246 us: 1.10x slower                                            |
| pickle               | 7.44 us                                                         | 8.42 us: 1.13x slower                                           |
| Geometric mean       | (ref)                                                           | 1.15x faster                                                    |

Benchmark hidden because not significant (1): json_dumps

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 6.39 ms: 1.01x faster                                           |
| python_startup         | 9.51 ms                                                         | 9.78 ms: 1.03x slower                                           |
| Geometric mean         | (ref)                                                           | 1.01x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| mako            | 7.16 ms                                                         | 6.41 ms: 1.12x faster                                           |
| genshi_text     | 17.8 ms                                                         | 16.3 ms: 1.09x faster                                           |
| genshi_xml      | 41.3 ms                                                         | 40.3 ms: 1.03x faster                                           |
| django_template | 27.6 ms                                                         | 28.5 ms: 1.03x slower                                           |
| Geometric mean  | (ref)                                                           | 1.05x faster                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_memo_naive           | 36.1 ms                                                         | 10.8 ms: 3.33x faster                                           |
| thread_pipeline_naive       | 47.3 ms                                                         | 30.9 ms: 1.53x faster                                           |
| thread_counter_naive        | 20.6 ms                                                         | 19.5 ms: 1.06x faster                                           |
| thread_memo_optimized       | 15.3 ms                                                         | 15.0 ms: 1.02x faster                                           |
| thread_counter_optimized    | 16.5 ms                                                         | 16.2 ms: 1.02x faster                                           |
| thread_montecarlo_optimized | 14.5 ms                                                         | 14.4 ms: 1.01x faster                                           |
| thread_montecarlo_naive     | 19.0 ms                                                         | 18.9 ms: 1.01x faster                                           |
| thread_pipeline_optimized   | 20.9 ms                                                         | 21.0 ms: 1.01x slower                                           |
| thread_accumulate_optimized | 32.3 ms                                                         | 32.6 ms: 1.01x slower                                           |
| thread_mandelbrot_naive     | 210 ms                                                          | 216 ms: 1.03x slower                                            |
| thread_mandelbrot_optimized | 208 ms                                                          | 219 ms: 1.05x slower                                            |
| Geometric mean              | (ref)                                                           | 1.15x faster                                                    |

Benchmark hidden because not significant (1): thread_accumulate_naive

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 5.34 ms: 6.93x faster                                           |
| thread_memo_naive                | 36.1 ms                                                         | 10.8 ms: 3.33x faster                                           |
| base16_small                     | 740 us                                                          | 312 us: 2.37x faster                                            |
| mdp                              | 2.15 sec                                                        | 944 ms: 2.27x faster                                            |
| async_tree_memoization_tg        | 419 ms                                                          | 273 ms: 1.54x faster                                            |
| thread_pipeline_naive            | 47.3 ms                                                         | 30.9 ms: 1.53x faster                                           |
| deepcopy_memo                    | 26.5 us                                                         | 17.9 us: 1.48x faster                                           |
| async_tree_io_tg                 | 778 ms                                                          | 528 ms: 1.47x faster                                            |
| float                            | 57.0 ms                                                         | 39.8 ms: 1.43x faster                                           |
| async_tree_io                    | 741 ms                                                          | 520 ms: 1.43x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 531 ms: 1.41x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 277 ms: 1.40x faster                                            |
| richards                         | 37.8 ms                                                         | 27.1 ms: 1.39x faster                                           |
| async_tree_none                  | 308 ms                                                          | 225 ms: 1.37x faster                                            |
| deepcopy                         | 269 us                                                          | 196 us: 1.37x faster                                            |
| async_tree_eager_io_tg           | 728 ms                                                          | 540 ms: 1.35x faster                                            |
| richards_super                   | 42.8 ms                                                         | 31.9 ms: 1.34x faster                                           |
| async_tree_none_tg               | 291 ms                                                          | 223 ms: 1.30x faster                                            |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 399 ms: 1.23x faster                                            |
| scimark_fft                      | 226 ms                                                          | 185 ms: 1.22x faster                                            |
| noop                             | 20.5 ns                                                         | 16.8 ns: 1.22x faster                                           |
| async_tree_eager_memoization     | 219 ms                                                          | 183 ms: 1.20x faster                                            |
| deepcopy_reduce                  | 2.40 us                                                         | 2.01 us: 1.20x faster                                           |
| ascii85_large                    | 717 ms                                                          | 600 ms: 1.19x faster                                            |
| go                               | 117 ms                                                          | 98.4 ms: 1.19x faster                                           |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 401 ms: 1.18x faster                                            |
| tomli_loads                      | 1.62 sec                                                        | 1.38 sec: 1.17x faster                                          |
| deltablue                        | 2.41 ms                                                         | 2.05 ms: 1.17x faster                                           |
| unpickle_pure_python             | 151 us                                                          | 130 us: 1.16x faster                                            |
| regex_effbot                     | 2.30 ms                                                         | 1.98 ms: 1.16x faster                                           |
| pyflate                          | 342 ms                                                          | 296 ms: 1.16x faster                                            |
| spectral_norm                    | 65.9 ms                                                         | 57.2 ms: 1.15x faster                                           |
| bpe_tokeniser                    | 3.30 sec                                                        | 2.87 sec: 1.15x faster                                          |
| ascii85_small                    | 13.6 ms                                                         | 11.8 ms: 1.15x faster                                           |
| decimal_pi                       | 222 ms                                                          | 198 ms: 1.12x faster                                            |
| xml_etree_generate               | 64.2 ms                                                         | 57.4 ms: 1.12x faster                                           |
| mako                             | 7.16 ms                                                         | 6.41 ms: 1.12x faster                                           |
| xml_etree_process                | 46.6 ms                                                         | 41.9 ms: 1.11x faster                                           |
| scimark_monte_carlo              | 46.5 ms                                                         | 41.8 ms: 1.11x faster                                           |
| xml_etree_parse                  | 104 ms                                                          | 94.0 ms: 1.11x faster                                           |
| genshi_text                      | 17.8 ms                                                         | 16.3 ms: 1.09x faster                                           |
| asyncio_tcp                      | 318 ms                                                          | 292 ms: 1.09x faster                                            |
| regex_dna                        | 162 ms                                                          | 150 ms: 1.08x faster                                            |
| quadtree_nbody                   | 626 ms                                                          | 585 ms: 1.07x faster                                            |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 2.94 ms: 1.07x faster                                           |
| html5lib                         | 51.7 ms                                                         | 48.5 ms: 1.07x faster                                           |
| networkx_k_core                  | 2.16 sec                                                        | 2.03 sec: 1.06x faster                                          |
| base85_large                     | 252 ms                                                          | 237 ms: 1.06x faster                                            |
| xml_etree_iterparse              | 79.9 ms                                                         | 75.4 ms: 1.06x faster                                           |
| thread_counter_naive             | 20.6 ms                                                         | 19.5 ms: 1.06x faster                                           |
| fannkuch                         | 246 ms                                                          | 236 ms: 1.04x faster                                            |
| scimark_sor                      | 78.9 ms                                                         | 75.9 ms: 1.04x faster                                           |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 311 ms: 1.04x faster                                            |
| base85_small                     | 4.59 ms                                                         | 4.43 ms: 1.04x faster                                           |
| regex_compile                    | 98.5 ms                                                         | 95.2 ms: 1.03x faster                                           |
| async_tree_eager                 | 89.6 ms                                                         | 86.6 ms: 1.03x faster                                           |
| fastapi_http                     | 218 ms                                                          | 212 ms: 1.03x faster                                            |
| meteor_contest                   | 84.4 ms                                                         | 82.2 ms: 1.03x faster                                           |
| base32_large                     | 296 ms                                                          | 288 ms: 1.03x faster                                            |
| genshi_xml                       | 41.3 ms                                                         | 40.3 ms: 1.03x faster                                           |
| telco                            | 5.83 ms                                                         | 5.69 ms: 1.02x faster                                           |
| pickle_dict                      | 22.0 us                                                         | 21.5 us: 1.02x faster                                           |
| json                             | 3.51 ms                                                         | 3.43 ms: 1.02x faster                                           |
| decimal_factorial                | 177 ms                                                          | 173 ms: 1.02x faster                                            |
| thread_memo_optimized            | 15.3 ms                                                         | 15.0 ms: 1.02x faster                                           |
| thread_counter_optimized         | 16.5 ms                                                         | 16.2 ms: 1.02x faster                                           |
| base32_small                     | 5.79 ms                                                         | 5.70 ms: 1.02x faster                                           |
| thrift                           | 2.02 ms                                                         | 1.99 ms: 1.01x faster                                           |
| python_startup_no_site           | 6.46 ms                                                         | 6.39 ms: 1.01x faster                                           |
| sympy_integrate                  | 15.8 ms                                                         | 15.7 ms: 1.01x faster                                           |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 14.4 ms: 1.01x faster                                           |
| thread_montecarlo_naive          | 19.0 ms                                                         | 18.9 ms: 1.01x faster                                           |
| unpickle                         | 10.5 us                                                         | 10.5 us: 1.01x faster                                           |
| pidigits                         | 189 ms                                                          | 189 ms: 1.00x slower                                            |
| thread_pipeline_optimized        | 20.9 ms                                                         | 21.0 ms: 1.01x slower                                           |
| pycparser                        | 860 ms                                                          | 865 ms: 1.01x slower                                            |
| unpickle_list                    | 3.33 us                                                         | 3.35 us: 1.01x slower                                           |
| thread_accumulate_optimized      | 32.3 ms                                                         | 32.6 ms: 1.01x slower                                           |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 81.1 ms: 1.01x slower                                           |
| sympy_str                        | 197 ms                                                          | 199 ms: 1.01x slower                                            |
| scimark_lu                       | 74.5 ms                                                         | 75.2 ms: 1.01x slower                                           |
| sympy_expand                     | 336 ms                                                          | 341 ms: 1.01x slower                                            |
| coroutines                       | 15.4 ms                                                         | 15.6 ms: 1.01x slower                                           |
| tornado_http                     | 101 ms                                                          | 102 ms: 1.01x slower                                            |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 40.7 ms: 1.02x slower                                           |
| logging_simple                   | 4.71 us                                                         | 4.79 us: 1.02x slower                                           |
| logging_format                   | 5.25 us                                                         | 5.34 us: 1.02x slower                                           |
| chameleon                        | 9.95 ms                                                         | 10.1 ms: 1.02x slower                                           |
| typing_runtime_protocols         | 113 us                                                          | 115 us: 1.02x slower                                            |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.23 ms: 1.02x slower                                           |
| sympy_sum                        | 106 ms                                                          | 108 ms: 1.02x slower                                            |
| async_generators                 | 240 ms                                                          | 245 ms: 1.02x slower                                            |
| urlsafe_base64_small             | 325 us                                                          | 332 us: 1.02x slower                                            |
| raytrace                         | 195 ms                                                          | 200 ms: 1.02x slower                                            |
| regex_v8                         | 15.2 ms                                                         | 15.6 ms: 1.02x slower                                           |
| thread_mandelbrot_naive          | 210 ms                                                          | 216 ms: 1.03x slower                                            |
| python_startup                   | 9.51 ms                                                         | 9.78 ms: 1.03x slower                                           |
| django_template                  | 27.6 ms                                                         | 28.5 ms: 1.03x slower                                           |
| pathlib                          | 12.8 ms                                                         | 13.3 ms: 1.04x slower                                           |
| base64_small                     | 177 us                                                          | 185 us: 1.04x slower                                            |
| pickle_list                      | 3.14 us                                                         | 3.27 us: 1.04x slower                                           |
| coverage                         | 55.8 ms                                                         | 58.5 ms: 1.05x slower                                           |
| mypy2                            | 724 ms                                                          | 760 ms: 1.05x slower                                            |
| hexiom                           | 4.30 ms                                                         | 4.52 ms: 1.05x slower                                           |
| nqueens                          | 53.6 ms                                                         | 56.3 ms: 1.05x slower                                           |
| thread_mandelbrot_optimized      | 208 ms                                                          | 219 ms: 1.05x slower                                            |
| gc_traversal                     | 3.07 ms                                                         | 3.24 ms: 1.05x slower                                           |
| comprehensions                   | 10.9 us                                                         | 11.5 us: 1.05x slower                                           |
| sqlalchemy_imperative            | 13.9 ms                                                         | 14.9 ms: 1.07x slower                                           |
| json_loads                       | 16.2 us                                                         | 17.4 us: 1.07x slower                                           |
| logging_silent                   | 61.0 ns                                                         | 66.0 ns: 1.08x slower                                           |
| docutils                         | 1.89 sec                                                        | 2.05 sec: 1.08x slower                                          |
| base64_large                     | 3.33 ms                                                         | 3.63 ms: 1.09x slower                                           |
| pickle_pure_python               | 223 us                                                          | 246 us: 1.10x slower                                            |
| crypto_pyaes                     | 50.9 ms                                                         | 56.3 ms: 1.11x slower                                           |
| create_gc_cycles                 | 1.75 ms                                                         | 1.96 ms: 1.12x slower                                           |
| pickle                           | 7.44 us                                                         | 8.42 us: 1.13x slower                                           |
| pprint_pformat                   | 1.09 sec                                                        | 1.33 sec: 1.22x slower                                          |
| nbody                            | 65.9 ms                                                         | 80.8 ms: 1.23x slower                                           |
| pprint_safe_repr                 | 530 ms                                                          | 667 ms: 1.26x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 360 ms: 1.26x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 241 ms: 1.38x slower                                            |
| argparse_subparsers              | 452 us                                                          | 705 us: 1.56x slower                                            |
| argparse_many_optionals          | 12.8 ms                                                         | 34.1 ms: 2.66x slower                                           |
| async_tree_eager_tg              | 58.6 ms                                                         | 176 ms: 3.00x slower                                            |
| unpack_sequence                  | 27.1 ns                                                         | 103 ns: 3.79x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.06x faster                                                    |

Benchmark hidden because not significant (11): generators, asyncio_websockets, chaos, networkx_shortest_path, xdsl_constant_fold, thread_accumulate_naive, asyncio_tcp_ssl, networkx_connected_components, sqlglot_v2_parse, json_dumps, pylint

- Geometric mean (including insignificant results): 1.058x faster

# HPT report

- Reliability score: 99.88% likely to be faster
- 90% likely to have a speedup of 1.01x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.04x