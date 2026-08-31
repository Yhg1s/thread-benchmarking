# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.090x faster
- HPT reliability: 70.70%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.59x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 10.9 ms: 1.09x slower                                               |
| docutils       | 1.89 sec                                                        | 2.00 sec: 1.06x slower                                              |
| fastapi_http   | 218 ms                                                          | 190 ms: 1.15x faster                                                |
| html5lib       | 51.7 ms                                                         | 47.2 ms: 1.10x faster                                               |
| tornado_http   | 101 ms                                                          | 92.7 ms: 1.09x faster                                               |
| Geometric mean | (ref)                                                           | 1.03x faster                                                        |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_io_tg                 | 778 ms                                                          | 385 ms: 2.02x faster                                                |
| async_tree_eager_io_tg           | 728 ms                                                          | 385 ms: 1.89x faster                                                |
| async_tree_memoization_tg        | 419 ms                                                          | 226 ms: 1.85x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 420 ms: 1.78x faster                                                |
| async_tree_io                    | 741 ms                                                          | 422 ms: 1.76x faster                                                |
| async_tree_none_tg               | 291 ms                                                          | 168 ms: 1.73x faster                                                |
| async_tree_memoization           | 388 ms                                                          | 250 ms: 1.55x faster                                                |
| async_tree_none                  | 308 ms                                                          | 201 ms: 1.53x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 347 ms: 1.41x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 172 ms: 1.27x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 372 ms: 1.27x faster                                                |
| asyncio_tcp                      | 318 ms                                                          | 299 ms: 1.06x faster                                                |
| asyncio_websockets               | 303 ms                                                          | 288 ms: 1.05x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 308 ms: 1.05x faster                                                |
| coroutines                       | 15.4 ms                                                         | 15.7 ms: 1.02x slower                                               |
| async_generators                 | 240 ms                                                          | 248 ms: 1.03x slower                                                |
| async_tree_eager                 | 89.6 ms                                                         | 93.6 ms: 1.05x slower                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.37 sec: 1.06x slower                                              |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 332 ms: 1.16x slower                                                |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 211 ms: 1.20x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                         | 152 ms: 2.60x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.21x faster                                                        |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 23.1 ns: 1.13x slower                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                          | 189 ms: 1.07x slower                                                |
| decimal_pi        | 222 ms                                                          | 243 ms: 1.09x slower                                                |
| Geometric mean    | (ref)                                                           | 1.08x slower                                                        |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 51.1 ms: 1.12x faster                                               |
| pidigits       | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| quadtree_nbody | 626 ms                                                          | 652 ms: 1.04x slower                                                |
| nbody          | 65.9 ms                                                         | 82.2 ms: 1.25x slower                                               |
| Geometric mean | (ref)                                                           | 1.04x slower                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 2.01 ms: 1.14x faster                                               |
| regex_dna      | 162 ms                                                          | 151 ms: 1.07x faster                                                |
| regex_v8       | 15.2 ms                                                         | 14.8 ms: 1.03x faster                                               |
| regex_compile  | 98.5 ms                                                         | 105 ms: 1.07x slower                                                |
| Geometric mean | (ref)                                                           | 1.04x faster                                                        |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 4.76 ms: 7.76x faster                                               |
| base16_small         | 740 us                                                          | 295 us: 2.51x faster                                                |
| xml_etree_iterparse  | 79.9 ms                                                         | 65.6 ms: 1.22x faster                                               |
| xml_etree_parse      | 104 ms                                                          | 92.7 ms: 1.12x faster                                               |
| tomli_loads          | 1.62 sec                                                        | 1.58 sec: 1.02x faster                                              |
| base64_small         | 177 us                                                          | 176 us: 1.01x faster                                                |
| pickle_dict          | 22.0 us                                                         | 22.2 us: 1.01x slower                                               |
| base64_large         | 3.33 ms                                                         | 3.39 ms: 1.02x slower                                               |
| urlsafe_base64_small | 325 us                                                          | 334 us: 1.03x slower                                                |
| ascii85_small        | 13.6 ms                                                         | 14.3 ms: 1.05x slower                                               |
| xml_etree_generate   | 64.2 ms                                                         | 67.8 ms: 1.06x slower                                               |
| ascii85_large        | 717 ms                                                          | 760 ms: 1.06x slower                                                |
| json_dumps           | 6.95 ms                                                         | 7.43 ms: 1.07x slower                                               |
| xml_etree_process    | 46.6 ms                                                         | 49.9 ms: 1.07x slower                                               |
| unpickle_pure_python | 151 us                                                          | 163 us: 1.08x slower                                                |
| base32_large         | 296 ms                                                          | 325 ms: 1.10x slower                                                |
| base85_large         | 252 ms                                                          | 279 ms: 1.11x slower                                                |
| base85_small         | 4.59 ms                                                         | 5.10 ms: 1.11x slower                                               |
| base32_small         | 5.79 ms                                                         | 6.56 ms: 1.13x slower                                               |
| unpickle             | 10.5 us                                                         | 11.9 us: 1.13x slower                                               |
| pickle               | 7.44 us                                                         | 8.54 us: 1.15x slower                                               |
| pickle_pure_python   | 223 us                                                          | 257 us: 1.15x slower                                                |
| unpickle_list        | 3.33 us                                                         | 3.93 us: 1.18x slower                                               |
| json_loads           | 16.2 us                                                         | 19.2 us: 1.19x slower                                               |
| Geometric mean       | (ref)                                                           | 1.07x faster                                                        |

Benchmark hidden because not significant (1): pickle_list

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                         | 11.7 ms: 1.23x slower                                               |
| python_startup_no_site | 6.46 ms                                                         | 8.22 ms: 1.27x slower                                               |
| Geometric mean         | (ref)                                                           | 1.25x slower                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| genshi_xml      | 41.3 ms                                                         | 42.7 ms: 1.03x slower                                               |
| genshi_text     | 17.8 ms                                                         | 19.3 ms: 1.08x slower                                               |
| django_template | 27.6 ms                                                         | 31.0 ms: 1.12x slower                                               |
| mako            | 7.16 ms                                                         | 11.6 ms: 1.62x slower                                               |
| Geometric mean  | (ref)                                                           | 1.19x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 210 ms                                                          | 61.6 ms: 3.41x faster                                               |
| thread_mandelbrot_optimized | 208 ms                                                          | 63.1 ms: 3.29x faster                                               |
| thread_pipeline_optimized   | 20.9 ms                                                         | 6.58 ms: 3.17x faster                                               |
| thread_accumulate_optimized | 32.3 ms                                                         | 10.7 ms: 3.01x faster                                               |
| thread_counter_optimized    | 16.5 ms                                                         | 5.58 ms: 2.97x faster                                               |
| thread_montecarlo_optimized | 14.5 ms                                                         | 5.02 ms: 2.89x faster                                               |
| thread_memo_optimized       | 15.3 ms                                                         | 5.70 ms: 2.68x faster                                               |
| thread_accumulate_naive     | 33.4 ms                                                         | 12.8 ms: 2.62x faster                                               |
| thread_pipeline_naive       | 47.3 ms                                                         | 24.2 ms: 1.95x faster                                               |
| thread_memo_naive           | 36.1 ms                                                         | 22.3 ms: 1.62x faster                                               |
| thread_counter_naive        | 20.6 ms                                                         | 20.5 ms: 1.01x faster                                               |
| thread_montecarlo_naive     | 19.0 ms                                                         | 30.1 ms: 1.58x slower                                               |
| Geometric mean              | (ref)                                                           | 2.20x faster                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 4.76 ms: 7.76x faster                                               |
| thread_mandelbrot_naive          | 210 ms                                                          | 61.6 ms: 3.41x faster                                               |
| thread_mandelbrot_optimized      | 208 ms                                                          | 63.1 ms: 3.29x faster                                               |
| thread_pipeline_optimized        | 20.9 ms                                                         | 6.58 ms: 3.17x faster                                               |
| thread_accumulate_optimized      | 32.3 ms                                                         | 10.7 ms: 3.01x faster                                               |
| thread_counter_optimized         | 16.5 ms                                                         | 5.58 ms: 2.97x faster                                               |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 5.02 ms: 2.89x faster                                               |
| thread_memo_optimized            | 15.3 ms                                                         | 5.70 ms: 2.68x faster                                               |
| thread_accumulate_naive          | 33.4 ms                                                         | 12.8 ms: 2.62x faster                                               |
| base16_small                     | 740 us                                                          | 295 us: 2.51x faster                                                |
| mdp                              | 2.15 sec                                                        | 999 ms: 2.15x faster                                                |
| async_tree_io_tg                 | 778 ms                                                          | 385 ms: 2.02x faster                                                |
| thread_pipeline_naive            | 47.3 ms                                                         | 24.2 ms: 1.95x faster                                               |
| async_tree_eager_io_tg           | 728 ms                                                          | 385 ms: 1.89x faster                                                |
| async_tree_memoization_tg        | 419 ms                                                          | 226 ms: 1.85x faster                                                |
| gc_traversal                     | 3.07 ms                                                         | 1.66 ms: 1.85x faster                                               |
| async_tree_eager_io              | 749 ms                                                          | 420 ms: 1.78x faster                                                |
| async_tree_io                    | 741 ms                                                          | 422 ms: 1.76x faster                                                |
| async_tree_none_tg               | 291 ms                                                          | 168 ms: 1.73x faster                                                |
| thread_memo_naive                | 36.1 ms                                                         | 22.3 ms: 1.62x faster                                               |
| async_tree_memoization           | 388 ms                                                          | 250 ms: 1.55x faster                                                |
| async_tree_none                  | 308 ms                                                          | 201 ms: 1.53x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 347 ms: 1.41x faster                                                |
| deepcopy_memo                    | 26.5 us                                                         | 19.7 us: 1.35x faster                                               |
| deepcopy                         | 269 us                                                          | 208 us: 1.29x faster                                                |
| create_gc_cycles                 | 1.75 ms                                                         | 1.36 ms: 1.29x faster                                               |
| async_tree_eager_memoization     | 219 ms                                                          | 172 ms: 1.27x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 372 ms: 1.27x faster                                                |
| xml_etree_iterparse              | 79.9 ms                                                         | 65.6 ms: 1.22x faster                                               |
| go                               | 117 ms                                                          | 96.0 ms: 1.22x faster                                               |
| fastapi_http                     | 218 ms                                                          | 190 ms: 1.15x faster                                                |
| regex_effbot                     | 2.30 ms                                                         | 2.01 ms: 1.14x faster                                               |
| xml_etree_parse                  | 104 ms                                                          | 92.7 ms: 1.12x faster                                               |
| float                            | 57.0 ms                                                         | 51.1 ms: 1.12x faster                                               |
| pathlib                          | 12.8 ms                                                         | 11.5 ms: 1.11x faster                                               |
| html5lib                         | 51.7 ms                                                         | 47.2 ms: 1.10x faster                                               |
| tornado_http                     | 101 ms                                                          | 92.7 ms: 1.09x faster                                               |
| regex_dna                        | 162 ms                                                          | 151 ms: 1.07x faster                                                |
| deepcopy_reduce                  | 2.40 us                                                         | 2.26 us: 1.07x faster                                               |
| asyncio_tcp                      | 318 ms                                                          | 299 ms: 1.06x faster                                                |
| asyncio_websockets               | 303 ms                                                          | 288 ms: 1.05x faster                                                |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.14 sec: 1.05x faster                                              |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 308 ms: 1.05x faster                                                |
| pycparser                        | 860 ms                                                          | 824 ms: 1.04x faster                                                |
| regex_v8                         | 15.2 ms                                                         | 14.8 ms: 1.03x faster                                               |
| tomli_loads                      | 1.62 sec                                                        | 1.58 sec: 1.02x faster                                              |
| telco                            | 5.83 ms                                                         | 5.73 ms: 1.02x faster                                               |
| richards                         | 37.8 ms                                                         | 37.4 ms: 1.01x faster                                               |
| pidigits                         | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| thrift                           | 2.02 ms                                                         | 2.00 ms: 1.01x faster                                               |
| base64_small                     | 177 us                                                          | 176 us: 1.01x faster                                                |
| thread_counter_naive             | 20.6 ms                                                         | 20.5 ms: 1.01x faster                                               |
| pickle_dict                      | 22.0 us                                                         | 22.2 us: 1.01x slower                                               |
| base64_large                     | 3.33 ms                                                         | 3.39 ms: 1.02x slower                                               |
| coroutines                       | 15.4 ms                                                         | 15.7 ms: 1.02x slower                                               |
| pprint_pformat                   | 1.09 sec                                                        | 1.11 sec: 1.02x slower                                              |
| pprint_safe_repr                 | 530 ms                                                          | 543 ms: 1.02x slower                                                |
| json                             | 3.51 ms                                                         | 3.60 ms: 1.03x slower                                               |
| urlsafe_base64_small             | 325 us                                                          | 334 us: 1.03x slower                                                |
| richards_super                   | 42.8 ms                                                         | 44.0 ms: 1.03x slower                                               |
| scimark_fft                      | 226 ms                                                          | 233 ms: 1.03x slower                                                |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 83.1 ms: 1.03x slower                                               |
| async_generators                 | 240 ms                                                          | 248 ms: 1.03x slower                                                |
| genshi_xml                       | 41.3 ms                                                         | 42.7 ms: 1.03x slower                                               |
| pyflate                          | 342 ms                                                          | 355 ms: 1.04x slower                                                |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 41.7 ms: 1.04x slower                                               |
| quadtree_nbody                   | 626 ms                                                          | 652 ms: 1.04x slower                                                |
| async_tree_eager                 | 89.6 ms                                                         | 93.6 ms: 1.05x slower                                               |
| ascii85_small                    | 13.6 ms                                                         | 14.3 ms: 1.05x slower                                               |
| sympy_integrate                  | 15.8 ms                                                         | 16.6 ms: 1.05x slower                                               |
| xml_etree_generate               | 64.2 ms                                                         | 67.8 ms: 1.06x slower                                               |
| docutils                         | 1.89 sec                                                        | 2.00 sec: 1.06x slower                                              |
| ascii85_large                    | 717 ms                                                          | 760 ms: 1.06x slower                                                |
| xdsl_constant_fold               | 36.7 ms                                                         | 39.0 ms: 1.06x slower                                               |
| sympy_expand                     | 336 ms                                                          | 358 ms: 1.06x slower                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.37 sec: 1.06x slower                                              |
| sympy_sum                        | 106 ms                                                          | 113 ms: 1.07x slower                                                |
| regex_compile                    | 98.5 ms                                                         | 105 ms: 1.07x slower                                                |
| decimal_factorial                | 177 ms                                                          | 189 ms: 1.07x slower                                                |
| mypy2                            | 724 ms                                                          | 774 ms: 1.07x slower                                                |
| chaos                            | 45.1 ms                                                         | 48.2 ms: 1.07x slower                                               |
| hexiom                           | 4.30 ms                                                         | 4.60 ms: 1.07x slower                                               |
| json_dumps                       | 6.95 ms                                                         | 7.43 ms: 1.07x slower                                               |
| xml_etree_process                | 46.6 ms                                                         | 49.9 ms: 1.07x slower                                               |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.29 ms: 1.07x slower                                               |
| sympy_str                        | 197 ms                                                          | 211 ms: 1.07x slower                                                |
| scimark_sor                      | 78.9 ms                                                         | 85.3 ms: 1.08x slower                                               |
| genshi_text                      | 17.8 ms                                                         | 19.3 ms: 1.08x slower                                               |
| unpickle_pure_python             | 151 us                                                          | 163 us: 1.08x slower                                                |
| logging_silent                   | 61.0 ns                                                         | 66.4 ns: 1.09x slower                                               |
| chameleon                        | 9.95 ms                                                         | 10.9 ms: 1.09x slower                                               |
| decimal_pi                       | 222 ms                                                          | 243 ms: 1.09x slower                                                |
| sqlglot_v2_parse                 | 958 us                                                          | 1.05 ms: 1.09x slower                                               |
| deltablue                        | 2.41 ms                                                         | 2.64 ms: 1.10x slower                                               |
| logging_simple                   | 4.71 us                                                         | 5.17 us: 1.10x slower                                               |
| comprehensions                   | 10.9 us                                                         | 12.0 us: 1.10x slower                                               |
| base32_large                     | 296 ms                                                          | 325 ms: 1.10x slower                                                |
| base85_large                     | 252 ms                                                          | 279 ms: 1.11x slower                                                |
| base85_small                     | 4.59 ms                                                         | 5.10 ms: 1.11x slower                                               |
| logging_format                   | 5.25 us                                                         | 5.86 us: 1.12x slower                                               |
| django_template                  | 27.6 ms                                                         | 31.0 ms: 1.12x slower                                               |
| noop                             | 20.5 ns                                                         | 23.1 ns: 1.13x slower                                               |
| base32_small                     | 5.79 ms                                                         | 6.56 ms: 1.13x slower                                               |
| scimark_monte_carlo              | 46.5 ms                                                         | 52.8 ms: 1.13x slower                                               |
| unpickle                         | 10.5 us                                                         | 11.9 us: 1.13x slower                                               |
| pickle                           | 7.44 us                                                         | 8.54 us: 1.15x slower                                               |
| pickle_pure_python               | 223 us                                                          | 257 us: 1.15x slower                                                |
| scimark_lu                       | 74.5 ms                                                         | 86.0 ms: 1.15x slower                                               |
| spectral_norm                    | 65.9 ms                                                         | 76.4 ms: 1.16x slower                                               |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.65 ms: 1.16x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 332 ms: 1.16x slower                                                |
| unpickle_list                    | 3.33 us                                                         | 3.93 us: 1.18x slower                                               |
| raytrace                         | 195 ms                                                          | 231 ms: 1.18x slower                                                |
| json_loads                       | 16.2 us                                                         | 19.2 us: 1.19x slower                                               |
| fannkuch                         | 246 ms                                                          | 292 ms: 1.19x slower                                                |
| meteor_contest                   | 84.4 ms                                                         | 101 ms: 1.19x slower                                                |
| unpack_sequence                  | 27.1 ns                                                         | 32.4 ns: 1.20x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 211 ms: 1.20x slower                                                |
| typing_runtime_protocols         | 113 us                                                          | 136 us: 1.21x slower                                                |
| python_startup                   | 9.51 ms                                                         | 11.7 ms: 1.23x slower                                               |
| nqueens                          | 53.6 ms                                                         | 66.7 ms: 1.24x slower                                               |
| nbody                            | 65.9 ms                                                         | 82.2 ms: 1.25x slower                                               |
| crypto_pyaes                     | 50.9 ms                                                         | 64.2 ms: 1.26x slower                                               |
| python_startup_no_site           | 6.46 ms                                                         | 8.22 ms: 1.27x slower                                               |
| coverage                         | 55.8 ms                                                         | 79.5 ms: 1.43x slower                                               |
| thread_montecarlo_naive          | 19.0 ms                                                         | 30.1 ms: 1.58x slower                                               |
| argparse_subparsers              | 452 us                                                          | 718 us: 1.59x slower                                                |
| mako                             | 7.16 ms                                                         | 11.6 ms: 1.62x slower                                               |
| async_tree_eager_tg              | 58.6 ms                                                         | 152 ms: 2.60x slower                                                |
| argparse_many_optionals          | 12.8 ms                                                         | 37.1 ms: 2.89x slower                                               |
| Geometric mean                   | (ref)                                                           | 1.09x faster                                                        |

Benchmark hidden because not significant (3): pylint, pickle_list, generators
Ignored benchmarks (4) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: networkx_connected_components, networkx_k_core, networkx_shortest_path, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.090x faster

# HPT report

- Reliability score: 70.70% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.59x