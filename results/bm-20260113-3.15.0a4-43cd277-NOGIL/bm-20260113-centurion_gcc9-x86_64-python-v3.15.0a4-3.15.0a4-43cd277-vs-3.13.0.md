# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.080x faster
- HPT reliability: 73.70%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.57x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 11.0 ms: 1.11x slower                                               |
| docutils       | 1.89 sec                                                        | 2.11 sec: 1.12x slower                                              |
| fastapi_http   | 218 ms                                                          | 192 ms: 1.14x faster                                                |
| html5lib       | 51.7 ms                                                         | 47.8 ms: 1.08x faster                                               |
| tornado_http   | 101 ms                                                          | 96.2 ms: 1.05x faster                                               |
| Geometric mean | (ref)                                                           | 1.01x faster                                                        |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_io_tg                 | 778 ms                                                          | 469 ms: 1.66x faster                                                |
| async_tree_eager_io_tg           | 728 ms                                                          | 467 ms: 1.56x faster                                                |
| async_tree_memoization_tg        | 419 ms                                                          | 277 ms: 1.52x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 500 ms: 1.50x faster                                                |
| async_tree_io                    | 741 ms                                                          | 504 ms: 1.47x faster                                                |
| async_tree_none_tg               | 291 ms                                                          | 211 ms: 1.38x faster                                                |
| async_tree_none                  | 308 ms                                                          | 233 ms: 1.32x faster                                                |
| async_tree_memoization           | 388 ms                                                          | 301 ms: 1.29x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 394 ms: 1.24x faster                                                |
| asyncio_tcp                      | 318 ms                                                          | 274 ms: 1.16x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 189 ms: 1.16x faster                                                |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 421 ms: 1.13x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 312 ms: 1.04x faster                                                |
| asyncio_websockets               | 303 ms                                                          | 308 ms: 1.02x slower                                                |
| async_tree_eager                 | 89.6 ms                                                         | 93.0 ms: 1.04x slower                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.36 sec: 1.06x slower                                              |
| async_generators                 | 240 ms                                                          | 255 ms: 1.06x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 380 ms: 1.33x slower                                                |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 258 ms: 1.47x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                         | 188 ms: 3.22x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.08x faster                                                        |

Benchmark hidden because not significant (1): coroutines

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 20.5 ns                                                         | 22.7 ns: 1.11x slower                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                          | 188 ms: 1.07x slower                                                |
| decimal_pi        | 222 ms                                                          | 241 ms: 1.08x slower                                                |
| Geometric mean    | (ref)                                                           | 1.07x slower                                                        |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 53.4 ms: 1.07x faster                                               |
| pidigits       | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| quadtree_nbody | 626 ms                                                          | 668 ms: 1.07x slower                                                |
| nbody          | 65.9 ms                                                         | 83.5 ms: 1.27x slower                                               |
| Geometric mean | (ref)                                                           | 1.06x slower                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 2.02 ms: 1.14x faster                                               |
| regex_v8       | 15.2 ms                                                         | 14.6 ms: 1.04x faster                                               |
| regex_dna      | 162 ms                                                          | 157 ms: 1.03x faster                                                |
| regex_compile  | 98.5 ms                                                         | 102 ms: 1.04x slower                                                |
| Geometric mean | (ref)                                                           | 1.04x faster                                                        |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 4.65 ms: 7.95x faster                                               |
| base16_small         | 740 us                                                          | 292 us: 2.54x faster                                                |
| xml_etree_iterparse  | 79.9 ms                                                         | 64.6 ms: 1.24x faster                                               |
| xml_etree_parse      | 104 ms                                                          | 93.0 ms: 1.12x faster                                               |
| base64_small         | 177 us                                                          | 171 us: 1.04x faster                                                |
| base64_large         | 3.33 ms                                                         | 3.38 ms: 1.02x slower                                               |
| pickle_list          | 3.14 us                                                         | 3.22 us: 1.03x slower                                               |
| pickle_dict          | 22.0 us                                                         | 22.7 us: 1.03x slower                                               |
| unpickle_pure_python | 151 us                                                          | 155 us: 1.03x slower                                                |
| ascii85_small        | 13.6 ms                                                         | 14.2 ms: 1.04x slower                                               |
| tomli_loads          | 1.62 sec                                                        | 1.69 sec: 1.04x slower                                              |
| ascii85_large        | 717 ms                                                          | 755 ms: 1.05x slower                                                |
| xml_etree_generate   | 64.2 ms                                                         | 67.9 ms: 1.06x slower                                               |
| xml_etree_process    | 46.6 ms                                                         | 49.5 ms: 1.06x slower                                               |
| base85_large         | 252 ms                                                          | 269 ms: 1.07x slower                                                |
| base32_large         | 296 ms                                                          | 316 ms: 1.07x slower                                                |
| json_dumps           | 6.95 ms                                                         | 7.52 ms: 1.08x slower                                               |
| base32_small         | 5.79 ms                                                         | 6.32 ms: 1.09x slower                                               |
| pickle_pure_python   | 223 us                                                          | 245 us: 1.10x slower                                                |
| base85_small         | 4.59 ms                                                         | 5.04 ms: 1.10x slower                                               |
| unpickle             | 10.5 us                                                         | 12.1 us: 1.15x slower                                               |
| pickle               | 7.44 us                                                         | 8.83 us: 1.19x slower                                               |
| json_loads           | 16.2 us                                                         | 19.4 us: 1.20x slower                                               |
| unpickle_list        | 3.33 us                                                         | 3.99 us: 1.20x slower                                               |
| Geometric mean       | (ref)                                                           | 1.08x faster                                                        |

Benchmark hidden because not significant (1): urlsafe_base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                         | 11.7 ms: 1.23x slower                                               |
| python_startup_no_site | 6.46 ms                                                         | 8.20 ms: 1.27x slower                                               |
| Geometric mean         | (ref)                                                           | 1.25x slower                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| genshi_xml      | 41.3 ms                                                         | 43.6 ms: 1.06x slower                                               |
| django_template | 27.6 ms                                                         | 30.7 ms: 1.12x slower                                               |
| genshi_text     | 17.8 ms                                                         | 20.2 ms: 1.13x slower                                               |
| mako            | 7.16 ms                                                         | 11.6 ms: 1.62x slower                                               |
| Geometric mean  | (ref)                                                           | 1.21x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 210 ms                                                          | 59.3 ms: 3.54x faster                                               |
| thread_mandelbrot_optimized | 208 ms                                                          | 62.2 ms: 3.34x faster                                               |
| thread_pipeline_optimized   | 20.9 ms                                                         | 6.73 ms: 3.10x faster                                               |
| thread_accumulate_optimized | 32.3 ms                                                         | 10.7 ms: 3.02x faster                                               |
| thread_counter_optimized    | 16.5 ms                                                         | 5.52 ms: 2.99x faster                                               |
| thread_montecarlo_optimized | 14.5 ms                                                         | 4.94 ms: 2.93x faster                                               |
| thread_memo_optimized       | 15.3 ms                                                         | 5.80 ms: 2.63x faster                                               |
| thread_accumulate_naive     | 33.4 ms                                                         | 12.8 ms: 2.62x faster                                               |
| thread_pipeline_naive       | 47.3 ms                                                         | 24.1 ms: 1.96x faster                                               |
| thread_memo_naive           | 36.1 ms                                                         | 21.9 ms: 1.65x faster                                               |
| thread_counter_naive        | 20.6 ms                                                         | 20.5 ms: 1.01x faster                                               |
| thread_montecarlo_naive     | 19.0 ms                                                         | 32.4 ms: 1.70x slower                                               |
| Geometric mean              | (ref)                                                           | 2.20x faster                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 4.65 ms: 7.95x faster                                               |
| thread_mandelbrot_naive          | 210 ms                                                          | 59.3 ms: 3.54x faster                                               |
| thread_mandelbrot_optimized      | 208 ms                                                          | 62.2 ms: 3.34x faster                                               |
| thread_pipeline_optimized        | 20.9 ms                                                         | 6.73 ms: 3.10x faster                                               |
| thread_accumulate_optimized      | 32.3 ms                                                         | 10.7 ms: 3.02x faster                                               |
| thread_counter_optimized         | 16.5 ms                                                         | 5.52 ms: 2.99x faster                                               |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 4.94 ms: 2.93x faster                                               |
| thread_memo_optimized            | 15.3 ms                                                         | 5.80 ms: 2.63x faster                                               |
| thread_accumulate_naive          | 33.4 ms                                                         | 12.8 ms: 2.62x faster                                               |
| base16_small                     | 740 us                                                          | 292 us: 2.54x faster                                                |
| mdp                              | 2.15 sec                                                        | 1.01 sec: 2.12x faster                                              |
| thread_pipeline_naive            | 47.3 ms                                                         | 24.1 ms: 1.96x faster                                               |
| gc_traversal                     | 3.07 ms                                                         | 1.69 ms: 1.81x faster                                               |
| async_tree_io_tg                 | 778 ms                                                          | 469 ms: 1.66x faster                                                |
| thread_memo_naive                | 36.1 ms                                                         | 21.9 ms: 1.65x faster                                               |
| argparse_many_optionals          | 12.8 ms                                                         | 7.96 ms: 1.61x faster                                               |
| async_tree_eager_io_tg           | 728 ms                                                          | 467 ms: 1.56x faster                                                |
| async_tree_memoization_tg        | 419 ms                                                          | 277 ms: 1.52x faster                                                |
| async_tree_eager_io              | 749 ms                                                          | 500 ms: 1.50x faster                                                |
| async_tree_io                    | 741 ms                                                          | 504 ms: 1.47x faster                                                |
| deepcopy_memo                    | 26.5 us                                                         | 18.9 us: 1.40x faster                                               |
| async_tree_none_tg               | 291 ms                                                          | 211 ms: 1.38x faster                                                |
| async_tree_none                  | 308 ms                                                          | 233 ms: 1.32x faster                                                |
| create_gc_cycles                 | 1.75 ms                                                         | 1.36 ms: 1.29x faster                                               |
| async_tree_memoization           | 388 ms                                                          | 301 ms: 1.29x faster                                                |
| deepcopy                         | 269 us                                                          | 209 us: 1.29x faster                                                |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 394 ms: 1.24x faster                                                |
| xml_etree_iterparse              | 79.9 ms                                                         | 64.6 ms: 1.24x faster                                               |
| go                               | 117 ms                                                          | 95.6 ms: 1.22x faster                                               |
| asyncio_tcp                      | 318 ms                                                          | 274 ms: 1.16x faster                                                |
| async_tree_eager_memoization     | 219 ms                                                          | 189 ms: 1.16x faster                                                |
| fastapi_http                     | 218 ms                                                          | 192 ms: 1.14x faster                                                |
| regex_effbot                     | 2.30 ms                                                         | 2.02 ms: 1.14x faster                                               |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 421 ms: 1.13x faster                                                |
| xml_etree_parse                  | 104 ms                                                          | 93.0 ms: 1.12x faster                                               |
| pathlib                          | 12.8 ms                                                         | 11.7 ms: 1.09x faster                                               |
| html5lib                         | 51.7 ms                                                         | 47.8 ms: 1.08x faster                                               |
| telco                            | 5.83 ms                                                         | 5.45 ms: 1.07x faster                                               |
| float                            | 57.0 ms                                                         | 53.4 ms: 1.07x faster                                               |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.11 sec: 1.06x faster                                              |
| tornado_http                     | 101 ms                                                          | 96.2 ms: 1.05x faster                                               |
| deepcopy_reduce                  | 2.40 us                                                         | 2.30 us: 1.04x faster                                               |
| regex_v8                         | 15.2 ms                                                         | 14.6 ms: 1.04x faster                                               |
| richards                         | 37.8 ms                                                         | 36.4 ms: 1.04x faster                                               |
| pycparser                        | 860 ms                                                          | 827 ms: 1.04x faster                                                |
| base64_small                     | 177 us                                                          | 171 us: 1.04x faster                                                |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 312 ms: 1.04x faster                                                |
| regex_dna                        | 162 ms                                                          | 157 ms: 1.03x faster                                                |
| thrift                           | 2.02 ms                                                         | 1.98 ms: 1.02x faster                                               |
| pidigits                         | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| thread_counter_naive             | 20.6 ms                                                         | 20.5 ms: 1.01x faster                                               |
| pprint_pformat                   | 1.09 sec                                                        | 1.10 sec: 1.01x slower                                              |
| base64_large                     | 3.33 ms                                                         | 3.38 ms: 1.02x slower                                               |
| asyncio_websockets               | 303 ms                                                          | 308 ms: 1.02x slower                                                |
| pickle_list                      | 3.14 us                                                         | 3.22 us: 1.03x slower                                               |
| pickle_dict                      | 22.0 us                                                         | 22.7 us: 1.03x slower                                               |
| json                             | 3.51 ms                                                         | 3.62 ms: 1.03x slower                                               |
| unpickle_pure_python             | 151 us                                                          | 155 us: 1.03x slower                                                |
| scimark_fft                      | 226 ms                                                          | 234 ms: 1.03x slower                                                |
| regex_compile                    | 98.5 ms                                                         | 102 ms: 1.04x slower                                                |
| async_tree_eager                 | 89.6 ms                                                         | 93.0 ms: 1.04x slower                                               |
| ascii85_small                    | 13.6 ms                                                         | 14.2 ms: 1.04x slower                                               |
| tomli_loads                      | 1.62 sec                                                        | 1.69 sec: 1.04x slower                                              |
| sympy_integrate                  | 15.8 ms                                                         | 16.5 ms: 1.05x slower                                               |
| sympy_sum                        | 106 ms                                                          | 111 ms: 1.05x slower                                                |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 42.0 ms: 1.05x slower                                               |
| scimark_sor                      | 78.9 ms                                                         | 82.7 ms: 1.05x slower                                               |
| hexiom                           | 4.30 ms                                                         | 4.53 ms: 1.05x slower                                               |
| xdsl_constant_fold               | 36.7 ms                                                         | 38.7 ms: 1.05x slower                                               |
| ascii85_large                    | 717 ms                                                          | 755 ms: 1.05x slower                                                |
| genshi_xml                       | 41.3 ms                                                         | 43.6 ms: 1.06x slower                                               |
| xml_etree_generate               | 64.2 ms                                                         | 67.9 ms: 1.06x slower                                               |
| generators                       | 21.2 ms                                                         | 22.5 ms: 1.06x slower                                               |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.28 ms: 1.06x slower                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.36 sec: 1.06x slower                                              |
| xml_etree_process                | 46.6 ms                                                         | 49.5 ms: 1.06x slower                                               |
| async_generators                 | 240 ms                                                          | 255 ms: 1.06x slower                                                |
| decimal_factorial                | 177 ms                                                          | 188 ms: 1.07x slower                                                |
| quadtree_nbody                   | 626 ms                                                          | 668 ms: 1.07x slower                                                |
| sympy_expand                     | 336 ms                                                          | 360 ms: 1.07x slower                                                |
| base85_large                     | 252 ms                                                          | 269 ms: 1.07x slower                                                |
| base32_large                     | 296 ms                                                          | 316 ms: 1.07x slower                                                |
| sympy_str                        | 197 ms                                                          | 211 ms: 1.07x slower                                                |
| chaos                            | 45.1 ms                                                         | 48.5 ms: 1.07x slower                                               |
| sqlglot_v2_parse                 | 958 us                                                          | 1.04 ms: 1.08x slower                                               |
| json_dumps                       | 6.95 ms                                                         | 7.52 ms: 1.08x slower                                               |
| decimal_pi                       | 222 ms                                                          | 241 ms: 1.08x slower                                                |
| base32_small                     | 5.79 ms                                                         | 6.32 ms: 1.09x slower                                               |
| pickle_pure_python               | 223 us                                                          | 245 us: 1.10x slower                                                |
| base85_small                     | 4.59 ms                                                         | 5.04 ms: 1.10x slower                                               |
| scimark_monte_carlo              | 46.5 ms                                                         | 51.2 ms: 1.10x slower                                               |
| comprehensions                   | 10.9 us                                                         | 12.0 us: 1.10x slower                                               |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 89.1 ms: 1.11x slower                                               |
| noop                             | 20.5 ns                                                         | 22.7 ns: 1.11x slower                                               |
| chameleon                        | 9.95 ms                                                         | 11.0 ms: 1.11x slower                                               |
| scimark_lu                       | 74.5 ms                                                         | 82.8 ms: 1.11x slower                                               |
| django_template                  | 27.6 ms                                                         | 30.7 ms: 1.12x slower                                               |
| logging_silent                   | 61.0 ns                                                         | 68.0 ns: 1.12x slower                                               |
| docutils                         | 1.89 sec                                                        | 2.11 sec: 1.12x slower                                              |
| logging_simple                   | 4.71 us                                                         | 5.27 us: 1.12x slower                                               |
| deltablue                        | 2.41 ms                                                         | 2.70 ms: 1.12x slower                                               |
| argparse_subparsers              | 452 us                                                          | 508 us: 1.12x slower                                                |
| genshi_text                      | 17.8 ms                                                         | 20.2 ms: 1.13x slower                                               |
| logging_format                   | 5.25 us                                                         | 5.95 us: 1.13x slower                                               |
| mypy2                            | 724 ms                                                          | 830 ms: 1.15x slower                                                |
| spectral_norm                    | 65.9 ms                                                         | 75.8 ms: 1.15x slower                                               |
| unpickle                         | 10.5 us                                                         | 12.1 us: 1.15x slower                                               |
| unpack_sequence                  | 27.1 ns                                                         | 31.4 ns: 1.16x slower                                               |
| raytrace                         | 195 ms                                                          | 229 ms: 1.17x slower                                                |
| fannkuch                         | 246 ms                                                          | 290 ms: 1.18x slower                                                |
| meteor_contest                   | 84.4 ms                                                         | 99.7 ms: 1.18x slower                                               |
| pickle                           | 7.44 us                                                         | 8.83 us: 1.19x slower                                               |
| json_loads                       | 16.2 us                                                         | 19.4 us: 1.20x slower                                               |
| unpickle_list                    | 3.33 us                                                         | 3.99 us: 1.20x slower                                               |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.76 ms: 1.20x slower                                               |
| typing_runtime_protocols         | 113 us                                                          | 136 us: 1.20x slower                                                |
| networkx_shortest_path           | 437 ms                                                          | 526 ms: 1.20x slower                                                |
| python_startup                   | 9.51 ms                                                         | 11.7 ms: 1.23x slower                                               |
| crypto_pyaes                     | 50.9 ms                                                         | 63.6 ms: 1.25x slower                                               |
| nbody                            | 65.9 ms                                                         | 83.5 ms: 1.27x slower                                               |
| nqueens                          | 53.6 ms                                                         | 68.0 ms: 1.27x slower                                               |
| python_startup_no_site           | 6.46 ms                                                         | 8.20 ms: 1.27x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 380 ms: 1.33x slower                                                |
| networkx_connected_components    | 425 ms                                                          | 601 ms: 1.42x slower                                                |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 258 ms: 1.47x slower                                                |
| coverage                         | 55.8 ms                                                         | 82.8 ms: 1.48x slower                                               |
| mako                             | 7.16 ms                                                         | 11.6 ms: 1.62x slower                                               |
| thread_montecarlo_naive          | 19.0 ms                                                         | 32.4 ms: 1.70x slower                                               |
| async_tree_eager_tg              | 58.6 ms                                                         | 188 ms: 3.22x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.08x faster                                                        |

Benchmark hidden because not significant (7): pylint, networkx_k_core, coroutines, pyflate, richards_super, urlsafe_base64_small, pprint_safe_repr
Ignored benchmarks (1) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.080x faster

# HPT report

- Reliability score: 73.70% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.57x