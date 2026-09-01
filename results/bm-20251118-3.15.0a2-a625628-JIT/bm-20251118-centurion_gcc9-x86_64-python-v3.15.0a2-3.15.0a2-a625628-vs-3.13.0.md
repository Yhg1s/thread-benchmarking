# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.100x faster
- HPT reliability: 99.96%
- HPT 99th percentile: 1.02x faster
- Memory change: 1.02x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 10.4 ms: 1.05x slower                                               |
| fastapi_http   | 218 ms                                                          | 210 ms: 1.04x faster                                                |
| html5lib       | 51.7 ms                                                         | 46.8 ms: 1.11x faster                                               |
| tornado_http   | 101 ms                                                          | 102 ms: 1.01x slower                                                |
| Geometric mean | (ref)                                                           | 1.02x faster                                                        |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_io_tg                 | 778 ms                                                          | 471 ms: 1.65x faster                                                |
| async_tree_memoization_tg        | 419 ms                                                          | 258 ms: 1.63x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 469 ms: 1.60x faster                                                |
| async_tree_io                    | 741 ms                                                          | 466 ms: 1.59x faster                                                |
| async_tree_memoization           | 388 ms                                                          | 251 ms: 1.54x faster                                                |
| async_tree_eager_io_tg           | 728 ms                                                          | 472 ms: 1.54x faster                                                |
| async_tree_none                  | 308 ms                                                          | 209 ms: 1.47x faster                                                |
| async_tree_none_tg               | 291 ms                                                          | 205 ms: 1.42x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 378 ms: 1.30x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 382 ms: 1.24x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 179 ms: 1.22x faster                                                |
| asyncio_tcp                      | 318 ms                                                          | 299 ms: 1.06x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 308 ms: 1.05x faster                                                |
| async_tree_eager                 | 89.6 ms                                                         | 86.5 ms: 1.04x faster                                               |
| async_generators                 | 240 ms                                                          | 242 ms: 1.01x slower                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.30 sec: 1.01x slower                                              |
| coroutines                       | 15.4 ms                                                         | 15.7 ms: 1.02x slower                                               |
| asyncio_websockets               | 303 ms                                                          | 325 ms: 1.07x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 350 ms: 1.23x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                         | 171 ms: 2.93x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.16x faster                                                        |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 17.8 ns: 1.15x faster                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                          | 195 ms: 1.14x faster                                                |
| decimal_factorial | 177 ms                                                          | 172 ms: 1.03x faster                                                |
| Geometric mean    | (ref)                                                           | 1.08x faster                                                        |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 39.0 ms: 1.46x faster                                               |
| nbody          | 65.9 ms                                                         | 63.7 ms: 1.03x faster                                               |
| pidigits       | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| Geometric mean | (ref)                                                           | 1.15x faster                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_compile  | 98.5 ms                                                         | 88.0 ms: 1.12x faster                                               |
| regex_effbot   | 2.30 ms                                                         | 2.08 ms: 1.10x faster                                               |
| regex_dna      | 162 ms                                                          | 151 ms: 1.07x faster                                                |
| regex_v8       | 15.2 ms                                                         | 15.8 ms: 1.04x slower                                               |
| Geometric mean | (ref)                                                           | 1.06x faster                                                        |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 4.84 ms: 7.65x faster                                               |
| base16_small         | 740 us                                                          | 257 us: 2.88x faster                                                |
| ascii85_large        | 717 ms                                                          | 574 ms: 1.25x faster                                                |
| urlsafe_base64_small | 325 us                                                          | 261 us: 1.25x faster                                                |
| base64_small         | 177 us                                                          | 148 us: 1.20x faster                                                |
| ascii85_small        | 13.6 ms                                                         | 11.5 ms: 1.18x faster                                               |
| xml_etree_iterparse  | 79.9 ms                                                         | 67.8 ms: 1.18x faster                                               |
| unpickle_pure_python | 151 us                                                          | 128 us: 1.18x faster                                                |
| tomli_loads          | 1.62 sec                                                        | 1.40 sec: 1.16x faster                                              |
| json_dumps           | 6.95 ms                                                         | 6.00 ms: 1.16x faster                                               |
| xml_etree_generate   | 64.2 ms                                                         | 55.6 ms: 1.15x faster                                               |
| xml_etree_process    | 46.6 ms                                                         | 41.4 ms: 1.13x faster                                               |
| xml_etree_parse      | 104 ms                                                          | 92.9 ms: 1.12x faster                                               |
| base85_large         | 252 ms                                                          | 236 ms: 1.07x faster                                                |
| base32_large         | 296 ms                                                          | 280 ms: 1.06x faster                                                |
| pickle_dict          | 22.0 us                                                         | 21.3 us: 1.03x faster                                               |
| base85_small         | 4.59 ms                                                         | 4.45 ms: 1.03x faster                                               |
| unpickle             | 10.5 us                                                         | 10.3 us: 1.03x faster                                               |
| base32_small         | 5.79 ms                                                         | 5.73 ms: 1.01x faster                                               |
| unpickle_list        | 3.33 us                                                         | 3.32 us: 1.00x faster                                               |
| json_loads           | 16.2 us                                                         | 16.3 us: 1.00x slower                                               |
| pickle_pure_python   | 223 us                                                          | 227 us: 1.02x slower                                                |
| pickle_list          | 3.14 us                                                         | 3.19 us: 1.02x slower                                               |
| base64_large         | 3.33 ms                                                         | 3.52 ms: 1.06x slower                                               |
| pickle               | 7.44 us                                                         | 8.32 us: 1.12x slower                                               |
| Geometric mean       | (ref)                                                           | 1.22x faster                                                        |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 6.31 ms: 1.02x faster                                               |
| python_startup         | 9.51 ms                                                         | 9.50 ms: 1.00x faster                                               |
| Geometric mean         | (ref)                                                           | 1.01x faster                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| mako            | 7.16 ms                                                         | 6.12 ms: 1.17x faster                                               |
| genshi_text     | 17.8 ms                                                         | 18.0 ms: 1.01x slower                                               |
| django_template | 27.6 ms                                                         | 29.3 ms: 1.06x slower                                               |
| genshi_xml      | 41.3 ms                                                         | 46.3 ms: 1.12x slower                                               |
| Geometric mean  | (ref)                                                           | 1.01x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_memo_naive           | 36.1 ms                                                         | 8.60 ms: 4.20x faster                                               |
| thread_pipeline_naive       | 47.3 ms                                                         | 30.5 ms: 1.55x faster                                               |
| thread_counter_naive        | 20.6 ms                                                         | 19.0 ms: 1.09x faster                                               |
| thread_mandelbrot_naive     | 210 ms                                                          | 196 ms: 1.07x faster                                                |
| thread_montecarlo_optimized | 14.5 ms                                                         | 13.6 ms: 1.07x faster                                               |
| thread_mandelbrot_optimized | 208 ms                                                          | 194 ms: 1.07x faster                                                |
| thread_montecarlo_naive     | 19.0 ms                                                         | 18.4 ms: 1.03x faster                                               |
| thread_accumulate_naive     | 33.4 ms                                                         | 34.5 ms: 1.03x slower                                               |
| thread_counter_optimized    | 16.5 ms                                                         | 17.3 ms: 1.04x slower                                               |
| thread_accumulate_optimized | 32.3 ms                                                         | 34.0 ms: 1.05x slower                                               |
| thread_pipeline_optimized   | 20.9 ms                                                         | 22.1 ms: 1.06x slower                                               |
| Geometric mean              | (ref)                                                           | 1.18x faster                                                        |

Benchmark hidden because not significant (1): thread_memo_optimized

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 4.84 ms: 7.65x faster                                               |
| thread_memo_naive                | 36.1 ms                                                         | 8.60 ms: 4.20x faster                                               |
| base16_small                     | 740 us                                                          | 257 us: 2.88x faster                                                |
| richards                         | 37.8 ms                                                         | 19.6 ms: 1.93x faster                                               |
| mdp                              | 2.15 sec                                                        | 1.17 sec: 1.84x faster                                              |
| richards_super                   | 42.8 ms                                                         | 23.9 ms: 1.79x faster                                               |
| deepcopy_memo                    | 26.5 us                                                         | 15.2 us: 1.74x faster                                               |
| async_tree_io_tg                 | 778 ms                                                          | 471 ms: 1.65x faster                                                |
| async_tree_memoization_tg        | 419 ms                                                          | 258 ms: 1.63x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 469 ms: 1.60x faster                                                |
| async_tree_io                    | 741 ms                                                          | 466 ms: 1.59x faster                                                |
| thread_pipeline_naive            | 47.3 ms                                                         | 30.5 ms: 1.55x faster                                               |
| async_tree_memoization           | 388 ms                                                          | 251 ms: 1.54x faster                                                |
| async_tree_eager_io_tg           | 728 ms                                                          | 472 ms: 1.54x faster                                                |
| async_tree_none                  | 308 ms                                                          | 209 ms: 1.47x faster                                                |
| float                            | 57.0 ms                                                         | 39.0 ms: 1.46x faster                                               |
| async_tree_none_tg               | 291 ms                                                          | 205 ms: 1.42x faster                                                |
| go                               | 117 ms                                                          | 82.7 ms: 1.41x faster                                               |
| scimark_fft                      | 226 ms                                                          | 169 ms: 1.34x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 378 ms: 1.30x faster                                                |
| scimark_monte_carlo              | 46.5 ms                                                         | 36.0 ms: 1.29x faster                                               |
| spectral_norm                    | 65.9 ms                                                         | 51.8 ms: 1.27x faster                                               |
| ascii85_large                    | 717 ms                                                          | 574 ms: 1.25x faster                                                |
| urlsafe_base64_small             | 325 us                                                          | 261 us: 1.25x faster                                                |
| deepcopy                         | 269 us                                                          | 216 us: 1.25x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 382 ms: 1.24x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 179 ms: 1.22x faster                                                |
| pyflate                          | 342 ms                                                          | 280 ms: 1.22x faster                                                |
| base64_small                     | 177 us                                                          | 148 us: 1.20x faster                                                |
| ascii85_small                    | 13.6 ms                                                         | 11.5 ms: 1.18x faster                                               |
| xml_etree_iterparse              | 79.9 ms                                                         | 67.8 ms: 1.18x faster                                               |
| unpickle_pure_python             | 151 us                                                          | 128 us: 1.18x faster                                                |
| telco                            | 5.83 ms                                                         | 4.97 ms: 1.17x faster                                               |
| mako                             | 7.16 ms                                                         | 6.12 ms: 1.17x faster                                               |
| scimark_lu                       | 74.5 ms                                                         | 63.9 ms: 1.17x faster                                               |
| bpe_tokeniser                    | 3.30 sec                                                        | 2.83 sec: 1.17x faster                                              |
| tomli_loads                      | 1.62 sec                                                        | 1.40 sec: 1.16x faster                                              |
| json_dumps                       | 6.95 ms                                                         | 6.00 ms: 1.16x faster                                               |
| deepcopy_reduce                  | 2.40 us                                                         | 2.08 us: 1.16x faster                                               |
| xml_etree_generate               | 64.2 ms                                                         | 55.6 ms: 1.15x faster                                               |
| noop                             | 20.5 ns                                                         | 17.8 ns: 1.15x faster                                               |
| logging_silent                   | 61.0 ns                                                         | 53.4 ns: 1.14x faster                                               |
| decimal_pi                       | 222 ms                                                          | 195 ms: 1.14x faster                                                |
| xml_etree_process                | 46.6 ms                                                         | 41.4 ms: 1.13x faster                                               |
| xml_etree_parse                  | 104 ms                                                          | 92.9 ms: 1.12x faster                                               |
| regex_compile                    | 98.5 ms                                                         | 88.0 ms: 1.12x faster                                               |
| scimark_sor                      | 78.9 ms                                                         | 70.5 ms: 1.12x faster                                               |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 2.81 ms: 1.12x faster                                               |
| fannkuch                         | 246 ms                                                          | 222 ms: 1.11x faster                                                |
| html5lib                         | 51.7 ms                                                         | 46.8 ms: 1.11x faster                                               |
| regex_effbot                     | 2.30 ms                                                         | 2.08 ms: 1.10x faster                                               |
| deltablue                        | 2.41 ms                                                         | 2.18 ms: 1.10x faster                                               |
| pathlib                          | 12.8 ms                                                         | 11.6 ms: 1.10x faster                                               |
| thread_counter_naive             | 20.6 ms                                                         | 19.0 ms: 1.09x faster                                               |
| json                             | 3.51 ms                                                         | 3.25 ms: 1.08x faster                                               |
| regex_dna                        | 162 ms                                                          | 151 ms: 1.07x faster                                                |
| thread_mandelbrot_naive          | 210 ms                                                          | 196 ms: 1.07x faster                                                |
| meteor_contest                   | 84.4 ms                                                         | 79.0 ms: 1.07x faster                                               |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 13.6 ms: 1.07x faster                                               |
| base85_large                     | 252 ms                                                          | 236 ms: 1.07x faster                                                |
| thread_mandelbrot_optimized      | 208 ms                                                          | 194 ms: 1.07x faster                                                |
| asyncio_tcp                      | 318 ms                                                          | 299 ms: 1.06x faster                                                |
| base32_large                     | 296 ms                                                          | 280 ms: 1.06x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 308 ms: 1.05x faster                                                |
| fastapi_http                     | 218 ms                                                          | 210 ms: 1.04x faster                                                |
| thrift                           | 2.02 ms                                                         | 1.95 ms: 1.04x faster                                               |
| async_tree_eager                 | 89.6 ms                                                         | 86.5 ms: 1.04x faster                                               |
| nbody                            | 65.9 ms                                                         | 63.7 ms: 1.03x faster                                               |
| thread_montecarlo_naive          | 19.0 ms                                                         | 18.4 ms: 1.03x faster                                               |
| pickle_dict                      | 22.0 us                                                         | 21.3 us: 1.03x faster                                               |
| base85_small                     | 4.59 ms                                                         | 4.45 ms: 1.03x faster                                               |
| decimal_factorial                | 177 ms                                                          | 172 ms: 1.03x faster                                                |
| sqlglot_v2_parse                 | 958 us                                                          | 933 us: 1.03x faster                                                |
| generators                       | 21.2 ms                                                         | 20.7 ms: 1.03x faster                                               |
| unpickle                         | 10.5 us                                                         | 10.3 us: 1.03x faster                                               |
| python_startup_no_site           | 6.46 ms                                                         | 6.31 ms: 1.02x faster                                               |
| logging_format                   | 5.25 us                                                         | 5.16 us: 1.02x faster                                               |
| logging_simple                   | 4.71 us                                                         | 4.63 us: 1.02x faster                                               |
| pidigits                         | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| base32_small                     | 5.79 ms                                                         | 5.73 ms: 1.01x faster                                               |
| unpickle_list                    | 3.33 us                                                         | 3.32 us: 1.00x faster                                               |
| python_startup                   | 9.51 ms                                                         | 9.50 ms: 1.00x faster                                               |
| json_loads                       | 16.2 us                                                         | 16.3 us: 1.00x slower                                               |
| async_generators                 | 240 ms                                                          | 242 ms: 1.01x slower                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.30 sec: 1.01x slower                                              |
| tornado_http                     | 101 ms                                                          | 102 ms: 1.01x slower                                                |
| pycparser                        | 860 ms                                                          | 868 ms: 1.01x slower                                                |
| genshi_text                      | 17.8 ms                                                         | 18.0 ms: 1.01x slower                                               |
| pickle_pure_python               | 223 us                                                          | 227 us: 1.02x slower                                                |
| pickle_list                      | 3.14 us                                                         | 3.19 us: 1.02x slower                                               |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.23 ms: 1.02x slower                                               |
| coroutines                       | 15.4 ms                                                         | 15.7 ms: 1.02x slower                                               |
| typing_runtime_protocols         | 113 us                                                          | 116 us: 1.03x slower                                                |
| thread_accumulate_naive          | 33.4 ms                                                         | 34.5 ms: 1.03x slower                                               |
| chaos                            | 45.1 ms                                                         | 46.7 ms: 1.03x slower                                               |
| regex_v8                         | 15.2 ms                                                         | 15.8 ms: 1.04x slower                                               |
| thread_counter_optimized         | 16.5 ms                                                         | 17.3 ms: 1.04x slower                                               |
| comprehensions                   | 10.9 us                                                         | 11.4 us: 1.05x slower                                               |
| gc_traversal                     | 3.07 ms                                                         | 3.21 ms: 1.05x slower                                               |
| pprint_pformat                   | 1.09 sec                                                        | 1.14 sec: 1.05x slower                                              |
| crypto_pyaes                     | 50.9 ms                                                         | 53.4 ms: 1.05x slower                                               |
| chameleon                        | 9.95 ms                                                         | 10.4 ms: 1.05x slower                                               |
| thread_accumulate_optimized      | 32.3 ms                                                         | 34.0 ms: 1.05x slower                                               |
| raytrace                         | 195 ms                                                          | 207 ms: 1.06x slower                                                |
| base64_large                     | 3.33 ms                                                         | 3.52 ms: 1.06x slower                                               |
| pprint_safe_repr                 | 530 ms                                                          | 561 ms: 1.06x slower                                                |
| coverage                         | 55.8 ms                                                         | 59.1 ms: 1.06x slower                                               |
| thread_pipeline_optimized        | 20.9 ms                                                         | 22.1 ms: 1.06x slower                                               |
| django_template                  | 27.6 ms                                                         | 29.3 ms: 1.06x slower                                               |
| sympy_expand                     | 336 ms                                                          | 358 ms: 1.06x slower                                                |
| asyncio_websockets               | 303 ms                                                          | 325 ms: 1.07x slower                                                |
| sympy_integrate                  | 15.8 ms                                                         | 17.5 ms: 1.10x slower                                               |
| pickle                           | 7.44 us                                                         | 8.32 us: 1.12x slower                                               |
| genshi_xml                       | 41.3 ms                                                         | 46.3 ms: 1.12x slower                                               |
| hexiom                           | 4.30 ms                                                         | 4.83 ms: 1.12x slower                                               |
| create_gc_cycles                 | 1.75 ms                                                         | 1.98 ms: 1.13x slower                                               |
| nqueens                          | 53.6 ms                                                         | 60.8 ms: 1.13x slower                                               |
| pylint                           | 227 ms                                                          | 267 ms: 1.18x slower                                                |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 95.4 ms: 1.19x slower                                               |
| sympy_sum                        | 106 ms                                                          | 126 ms: 1.19x slower                                                |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 48.2 ms: 1.20x slower                                               |
| sympy_str                        | 197 ms                                                          | 238 ms: 1.21x slower                                                |
| mypy2                            | 724 ms                                                          | 883 ms: 1.22x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 350 ms: 1.23x slower                                                |
| argparse_subparsers              | 452 us                                                          | 707 us: 1.57x slower                                                |
| unpack_sequence                  | 27.1 ns                                                         | 54.4 ns: 2.01x slower                                               |
| argparse_many_optionals          | 12.8 ms                                                         | 35.1 ms: 2.74x slower                                               |
| async_tree_eager_tg              | 58.6 ms                                                         | 171 ms: 2.93x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.10x faster                                                        |

Benchmark hidden because not significant (2): thread_memo_optimized, xdsl_constant_fold
Ignored benchmarks (7) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: async_tree_eager_memoization_tg, docutils, networkx_connected_components, networkx_k_core, networkx_shortest_path, quadtree_nbody, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.100x faster

# HPT report

- Reliability score: 99.96% likely to be faster
- 90% likely to have a speedup of 1.03x
- 95% likely to have a speedup of 1.03x
- 99% likely to have a speedup of 1.02x

# Memory
- memory change: 1.02x