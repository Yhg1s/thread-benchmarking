# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.028x faster
- HPT reliability: 99.88%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.03x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 10.4 ms: 1.10x slower                                               |
| fastapi_http   | 216 ms                                                          | 210 ms: 1.03x faster                                                |
| Geometric mean | (ref)                                                           | 1.02x slower                                                        |

Benchmark hidden because not significant (2): html5lib, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_eager_io              | 552 ms                                                          | 469 ms: 1.18x faster                                                |
| async_tree_eager_io_tg           | 550 ms                                                          | 472 ms: 1.17x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 471 ms: 1.15x faster                                                |
| async_tree_io                    | 531 ms                                                          | 466 ms: 1.14x faster                                                |
| async_tree_memoization           | 281 ms                                                          | 251 ms: 1.12x faster                                                |
| async_tree_none_tg               | 223 ms                                                          | 205 ms: 1.09x faster                                                |
| async_tree_none                  | 228 ms                                                          | 209 ms: 1.09x faster                                                |
| asyncio_tcp                      | 325 ms                                                          | 299 ms: 1.09x faster                                                |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 378 ms: 1.09x faster                                                |
| async_tree_memoization_tg        | 277 ms                                                          | 258 ms: 1.08x faster                                                |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 382 ms: 1.07x faster                                                |
| async_tree_eager_tg              | 182 ms                                                          | 171 ms: 1.06x faster                                                |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 350 ms: 1.04x faster                                                |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 308 ms: 1.02x faster                                                |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.30 sec: 1.01x slower                                              |
| coroutines                       | 15.1 ms                                                         | 15.7 ms: 1.04x slower                                               |
| async_generators                 | 228 ms                                                          | 242 ms: 1.06x slower                                                |
| async_tree_eager                 | 81.3 ms                                                         | 86.5 ms: 1.06x slower                                               |
| asyncio_websockets               | 296 ms                                                          | 325 ms: 1.10x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.05x faster                                                        |

Benchmark hidden because not significant (1): async_tree_eager_memoization

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 17.8 ns: 1.09x faster                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_pi        | 208 ms                                                          | 195 ms: 1.06x faster                                                |
| decimal_factorial | 173 ms                                                          | 172 ms: 1.00x faster                                                |
| Geometric mean    | (ref)                                                           | 1.03x faster                                                        |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| float          | 47.3 ms                                                         | 39.0 ms: 1.21x faster                                               |
| nbody          | 67.9 ms                                                         | 63.7 ms: 1.07x faster                                               |
| pidigits       | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| Geometric mean | (ref)                                                           | 1.09x faster                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_compile  | 93.9 ms                                                         | 88.0 ms: 1.07x faster                                               |
| regex_dna      | 150 ms                                                          | 151 ms: 1.00x slower                                                |
| regex_v8       | 14.8 ms                                                         | 15.8 ms: 1.07x slower                                               |
| regex_effbot   | 1.95 ms                                                         | 2.08 ms: 1.07x slower                                               |
| Geometric mean | (ref)                                                           | 1.02x slower                                                        |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| urlsafe_base64_small | 329 us                                                          | 261 us: 1.26x faster                                                |
| base64_small         | 186 us                                                          | 148 us: 1.26x faster                                                |
| base16_small         | 305 us                                                          | 257 us: 1.19x faster                                                |
| unpickle_pure_python | 152 us                                                          | 128 us: 1.19x faster                                                |
| ascii85_large        | 667 ms                                                          | 574 ms: 1.16x faster                                                |
| json_dumps           | 6.95 ms                                                         | 6.00 ms: 1.16x faster                                               |
| xml_etree_generate   | 62.6 ms                                                         | 55.6 ms: 1.13x faster                                               |
| xml_etree_iterparse  | 76.2 ms                                                         | 67.8 ms: 1.12x faster                                               |
| base16_large         | 5.33 ms                                                         | 4.84 ms: 1.10x faster                                               |
| ascii85_small        | 12.7 ms                                                         | 11.5 ms: 1.10x faster                                               |
| xml_etree_process    | 44.7 ms                                                         | 41.4 ms: 1.08x faster                                               |
| json_loads           | 17.5 us                                                         | 16.3 us: 1.07x faster                                               |
| pickle_pure_python   | 240 us                                                          | 227 us: 1.06x faster                                                |
| base85_small         | 4.69 ms                                                         | 4.45 ms: 1.05x faster                                               |
| base85_large         | 248 ms                                                          | 236 ms: 1.05x faster                                                |
| base32_large         | 292 ms                                                          | 280 ms: 1.05x faster                                                |
| unpickle_list        | 3.43 us                                                         | 3.32 us: 1.03x faster                                               |
| tomli_loads          | 1.44 sec                                                        | 1.40 sec: 1.03x faster                                              |
| base64_large         | 3.63 ms                                                         | 3.52 ms: 1.03x faster                                               |
| pickle_list          | 3.24 us                                                         | 3.19 us: 1.01x faster                                               |
| xml_etree_parse      | 94.3 ms                                                         | 92.9 ms: 1.01x faster                                               |
| pickle_dict          | 21.5 us                                                         | 21.3 us: 1.01x faster                                               |
| base32_small         | 5.71 ms                                                         | 5.73 ms: 1.00x slower                                               |
| unpickle             | 10.2 us                                                         | 10.3 us: 1.01x slower                                               |
| pickle               | 8.20 us                                                         | 8.32 us: 1.02x slower                                               |
| Geometric mean       | (ref)                                                           | 1.08x faster                                                        |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 9.50 ms: 1.03x faster                                               |
| python_startup_no_site | 6.38 ms                                                         | 6.31 ms: 1.01x faster                                               |
| Geometric mean         | (ref)                                                           | 1.02x faster                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| mako            | 7.40 ms                                                         | 6.12 ms: 1.21x faster                                               |
| django_template | 27.8 ms                                                         | 29.3 ms: 1.05x slower                                               |
| genshi_text     | 16.8 ms                                                         | 18.0 ms: 1.08x slower                                               |
| genshi_xml      | 39.5 ms                                                         | 46.3 ms: 1.17x slower                                               |
| Geometric mean  | (ref)                                                           | 1.02x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_memo_naive           | 11.5 ms                                                         | 8.60 ms: 1.34x faster                                               |
| thread_mandelbrot_optimized | 233 ms                                                          | 194 ms: 1.20x faster                                                |
| thread_mandelbrot_naive     | 233 ms                                                          | 196 ms: 1.19x faster                                                |
| thread_counter_naive        | 20.2 ms                                                         | 19.0 ms: 1.07x faster                                               |
| thread_pipeline_naive       | 32.0 ms                                                         | 30.5 ms: 1.05x faster                                               |
| thread_memo_optimized       | 15.9 ms                                                         | 15.3 ms: 1.04x faster                                               |
| thread_accumulate_naive     | 35.8 ms                                                         | 34.5 ms: 1.04x faster                                               |
| thread_accumulate_optimized | 35.1 ms                                                         | 34.0 ms: 1.03x faster                                               |
| thread_montecarlo_optimized | 13.9 ms                                                         | 13.6 ms: 1.03x faster                                               |
| thread_pipeline_optimized   | 22.5 ms                                                         | 22.1 ms: 1.02x faster                                               |
| thread_counter_optimized    | 17.1 ms                                                         | 17.3 ms: 1.01x slower                                               |
| thread_montecarlo_naive     | 15.8 ms                                                         | 18.4 ms: 1.17x slower                                               |
| Geometric mean              | (ref)                                                           | 1.06x faster                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| richards                         | 32.6 ms                                                         | 19.6 ms: 1.67x faster                                               |
| richards_super                   | 37.4 ms                                                         | 23.9 ms: 1.56x faster                                               |
| thread_memo_naive                | 11.5 ms                                                         | 8.60 ms: 1.34x faster                                               |
| scimark_fft                      | 226 ms                                                          | 169 ms: 1.34x faster                                                |
| spectral_norm                    | 65.6 ms                                                         | 51.8 ms: 1.27x faster                                               |
| urlsafe_base64_small             | 329 us                                                          | 261 us: 1.26x faster                                                |
| base64_small                     | 186 us                                                          | 148 us: 1.26x faster                                                |
| logging_silent                   | 65.3 ns                                                         | 53.4 ns: 1.22x faster                                               |
| float                            | 47.3 ms                                                         | 39.0 ms: 1.21x faster                                               |
| mako                             | 7.40 ms                                                         | 6.12 ms: 1.21x faster                                               |
| thread_mandelbrot_optimized      | 233 ms                                                          | 194 ms: 1.20x faster                                                |
| base16_small                     | 305 us                                                          | 257 us: 1.19x faster                                                |
| thread_mandelbrot_naive          | 233 ms                                                          | 196 ms: 1.19x faster                                                |
| unpickle_pure_python             | 152 us                                                          | 128 us: 1.19x faster                                                |
| deepcopy_memo                    | 18.0 us                                                         | 15.2 us: 1.18x faster                                               |
| async_tree_eager_io              | 552 ms                                                          | 469 ms: 1.18x faster                                                |
| async_tree_eager_io_tg           | 550 ms                                                          | 472 ms: 1.17x faster                                                |
| ascii85_large                    | 667 ms                                                          | 574 ms: 1.16x faster                                                |
| json_dumps                       | 6.95 ms                                                         | 6.00 ms: 1.16x faster                                               |
| scimark_lu                       | 73.8 ms                                                         | 63.9 ms: 1.16x faster                                               |
| async_tree_io_tg                 | 539 ms                                                          | 471 ms: 1.15x faster                                                |
| async_tree_io                    | 531 ms                                                          | 466 ms: 1.14x faster                                                |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 2.81 ms: 1.13x faster                                               |
| scimark_monte_carlo              | 40.7 ms                                                         | 36.0 ms: 1.13x faster                                               |
| telco                            | 5.59 ms                                                         | 4.97 ms: 1.13x faster                                               |
| xml_etree_generate               | 62.6 ms                                                         | 55.6 ms: 1.13x faster                                               |
| xml_etree_iterparse              | 76.2 ms                                                         | 67.8 ms: 1.12x faster                                               |
| async_tree_memoization           | 281 ms                                                          | 251 ms: 1.12x faster                                                |
| pathlib                          | 13.0 ms                                                         | 11.6 ms: 1.12x faster                                               |
| fannkuch                         | 245 ms                                                          | 222 ms: 1.10x faster                                                |
| base16_large                     | 5.33 ms                                                         | 4.84 ms: 1.10x faster                                               |
| ascii85_small                    | 12.7 ms                                                         | 11.5 ms: 1.10x faster                                               |
| async_tree_none_tg               | 223 ms                                                          | 205 ms: 1.09x faster                                                |
| async_tree_none                  | 228 ms                                                          | 209 ms: 1.09x faster                                                |
| asyncio_tcp                      | 325 ms                                                          | 299 ms: 1.09x faster                                                |
| noop                             | 19.4 ns                                                         | 17.8 ns: 1.09x faster                                               |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 378 ms: 1.09x faster                                                |
| xml_etree_process                | 44.7 ms                                                         | 41.4 ms: 1.08x faster                                               |
| async_tree_memoization_tg        | 277 ms                                                          | 258 ms: 1.08x faster                                                |
| scimark_sor                      | 75.7 ms                                                         | 70.5 ms: 1.07x faster                                               |
| json_loads                       | 17.5 us                                                         | 16.3 us: 1.07x faster                                               |
| deltablue                        | 2.34 ms                                                         | 2.18 ms: 1.07x faster                                               |
| pyflate                          | 299 ms                                                          | 280 ms: 1.07x faster                                                |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 382 ms: 1.07x faster                                                |
| regex_compile                    | 93.9 ms                                                         | 88.0 ms: 1.07x faster                                               |
| thread_counter_naive             | 20.2 ms                                                         | 19.0 ms: 1.07x faster                                               |
| nbody                            | 67.9 ms                                                         | 63.7 ms: 1.07x faster                                               |
| meteor_contest                   | 84.1 ms                                                         | 79.0 ms: 1.07x faster                                               |
| async_tree_eager_tg              | 182 ms                                                          | 171 ms: 1.06x faster                                                |
| decimal_pi                       | 208 ms                                                          | 195 ms: 1.06x faster                                                |
| bpe_tokeniser                    | 3.00 sec                                                        | 2.83 sec: 1.06x faster                                              |
| pickle_pure_python               | 240 us                                                          | 227 us: 1.06x faster                                                |
| base85_small                     | 4.69 ms                                                         | 4.45 ms: 1.05x faster                                               |
| json                             | 3.42 ms                                                         | 3.25 ms: 1.05x faster                                               |
| base85_large                     | 248 ms                                                          | 236 ms: 1.05x faster                                                |
| thread_pipeline_naive            | 32.0 ms                                                         | 30.5 ms: 1.05x faster                                               |
| base32_large                     | 292 ms                                                          | 280 ms: 1.05x faster                                                |
| thread_memo_optimized            | 15.9 ms                                                         | 15.3 ms: 1.04x faster                                               |
| thread_accumulate_naive          | 35.8 ms                                                         | 34.5 ms: 1.04x faster                                               |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 350 ms: 1.04x faster                                                |
| logging_format                   | 5.35 us                                                         | 5.16 us: 1.04x faster                                               |
| unpickle_list                    | 3.43 us                                                         | 3.32 us: 1.03x faster                                               |
| tomli_loads                      | 1.44 sec                                                        | 1.40 sec: 1.03x faster                                              |
| logging_simple                   | 4.79 us                                                         | 4.63 us: 1.03x faster                                               |
| thread_accumulate_optimized      | 35.1 ms                                                         | 34.0 ms: 1.03x faster                                               |
| base64_large                     | 3.63 ms                                                         | 3.52 ms: 1.03x faster                                               |
| fastapi_http                     | 216 ms                                                          | 210 ms: 1.03x faster                                                |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 13.6 ms: 1.03x faster                                               |
| python_startup                   | 9.73 ms                                                         | 9.50 ms: 1.03x faster                                               |
| go                               | 84.7 ms                                                         | 82.7 ms: 1.02x faster                                               |
| crypto_pyaes                     | 54.5 ms                                                         | 53.4 ms: 1.02x faster                                               |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 308 ms: 1.02x faster                                                |
| thread_pipeline_optimized        | 22.5 ms                                                         | 22.1 ms: 1.02x faster                                               |
| pickle_list                      | 3.24 us                                                         | 3.19 us: 1.01x faster                                               |
| xml_etree_parse                  | 94.3 ms                                                         | 92.9 ms: 1.01x faster                                               |
| gc_traversal                     | 3.26 ms                                                         | 3.21 ms: 1.01x faster                                               |
| pidigits                         | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| pickle_dict                      | 21.5 us                                                         | 21.3 us: 1.01x faster                                               |
| python_startup_no_site           | 6.38 ms                                                         | 6.31 ms: 1.01x faster                                               |
| decimal_factorial                | 173 ms                                                          | 172 ms: 1.00x faster                                                |
| regex_dna                        | 150 ms                                                          | 151 ms: 1.00x slower                                                |
| base32_small                     | 5.71 ms                                                         | 5.73 ms: 1.00x slower                                               |
| create_gc_cycles                 | 1.96 ms                                                         | 1.98 ms: 1.01x slower                                               |
| unpickle                         | 10.2 us                                                         | 10.3 us: 1.01x slower                                               |
| thread_counter_optimized         | 17.1 ms                                                         | 17.3 ms: 1.01x slower                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.30 sec: 1.01x slower                                              |
| pickle                           | 8.20 us                                                         | 8.32 us: 1.02x slower                                               |
| pycparser                        | 851 ms                                                          | 868 ms: 1.02x slower                                                |
| argparse_many_optionals          | 34.4 ms                                                         | 35.1 ms: 1.02x slower                                               |
| sqlglot_v2_parse                 | 911 us                                                          | 933 us: 1.02x slower                                                |
| coverage                         | 57.4 ms                                                         | 59.1 ms: 1.03x slower                                               |
| argparse_subparsers              | 686 us                                                          | 707 us: 1.03x slower                                                |
| coroutines                       | 15.1 ms                                                         | 15.7 ms: 1.04x slower                                               |
| typing_runtime_protocols         | 112 us                                                          | 116 us: 1.04x slower                                                |
| deepcopy_reduce                  | 2.00 us                                                         | 2.08 us: 1.04x slower                                               |
| thrift                           | 1.86 ms                                                         | 1.95 ms: 1.04x slower                                               |
| django_template                  | 27.8 ms                                                         | 29.3 ms: 1.05x slower                                               |
| xdsl_constant_fold               | 34.7 ms                                                         | 36.7 ms: 1.06x slower                                               |
| comprehensions                   | 10.8 us                                                         | 11.4 us: 1.06x slower                                               |
| async_generators                 | 228 ms                                                          | 242 ms: 1.06x slower                                                |
| async_tree_eager                 | 81.3 ms                                                         | 86.5 ms: 1.06x slower                                               |
| raytrace                         | 194 ms                                                          | 207 ms: 1.07x slower                                                |
| chaos                            | 43.8 ms                                                         | 46.7 ms: 1.07x slower                                               |
| regex_v8                         | 14.8 ms                                                         | 15.8 ms: 1.07x slower                                               |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.23 ms: 1.07x slower                                               |
| nqueens                          | 56.8 ms                                                         | 60.8 ms: 1.07x slower                                               |
| regex_effbot                     | 1.95 ms                                                         | 2.08 ms: 1.07x slower                                               |
| genshi_text                      | 16.8 ms                                                         | 18.0 ms: 1.08x slower                                               |
| sympy_expand                     | 332 ms                                                          | 358 ms: 1.08x slower                                                |
| chameleon                        | 9.52 ms                                                         | 10.4 ms: 1.10x slower                                               |
| asyncio_websockets               | 296 ms                                                          | 325 ms: 1.10x slower                                                |
| deepcopy                         | 193 us                                                          | 216 us: 1.12x slower                                                |
| sympy_integrate                  | 15.4 ms                                                         | 17.5 ms: 1.14x slower                                               |
| pprint_pformat                   | 989 ms                                                          | 1.14 sec: 1.16x slower                                              |
| thread_montecarlo_naive          | 15.8 ms                                                         | 18.4 ms: 1.17x slower                                               |
| mypy2                            | 753 ms                                                          | 883 ms: 1.17x slower                                                |
| genshi_xml                       | 39.5 ms                                                         | 46.3 ms: 1.17x slower                                               |
| hexiom                           | 4.11 ms                                                         | 4.83 ms: 1.18x slower                                               |
| pprint_safe_repr                 | 474 ms                                                          | 561 ms: 1.18x slower                                                |
| sympy_sum                        | 106 ms                                                          | 126 ms: 1.19x slower                                                |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 95.4 ms: 1.22x slower                                               |
| sympy_str                        | 194 ms                                                          | 238 ms: 1.22x slower                                                |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 48.2 ms: 1.23x slower                                               |
| mdp                              | 946 ms                                                          | 1.17 sec: 1.24x slower                                              |
| pylint                           | 216 ms                                                          | 267 ms: 1.24x slower                                                |
| unpack_sequence                  | 25.8 ns                                                         | 54.4 ns: 2.11x slower                                               |
| Geometric mean                   | (ref)                                                           | 1.03x faster                                                        |

Benchmark hidden because not significant (4): async_tree_eager_memoization, html5lib, tornado_http, generators
Ignored benchmarks (7) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: async_tree_eager_memoization_tg, docutils, networkx_connected_components, networkx_k_core, networkx_shortest_path, quadtree_nbody, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.028x faster

# HPT report

- Reliability score: 99.88% likely to be faster
- 90% likely to have a speedup of 1.02x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.03x