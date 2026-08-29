# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.015x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.03x slower
- Memory change: 1.45x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 11.0 ms: 1.16x slower                                               |
| docutils       | 1.95 sec                                                        | 2.11 sec: 1.08x slower                                              |
| fastapi_http   | 216 ms                                                          | 192 ms: 1.13x faster                                                |
| html5lib       | 46.9 ms                                                         | 47.8 ms: 1.02x slower                                               |
| tornado_http   | 101 ms                                                          | 96.2 ms: 1.05x faster                                               |
| Geometric mean | (ref)                                                           | 1.02x slower                                                        |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| asyncio_tcp                      | 325 ms                                                          | 274 ms: 1.19x faster                                                |
| async_tree_eager_io_tg           | 550 ms                                                          | 467 ms: 1.18x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 469 ms: 1.15x faster                                                |
| async_tree_eager_io              | 552 ms                                                          | 500 ms: 1.10x faster                                                |
| async_tree_none_tg               | 223 ms                                                          | 211 ms: 1.06x faster                                                |
| async_tree_io                    | 531 ms                                                          | 504 ms: 1.05x faster                                                |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 394 ms: 1.04x faster                                                |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 312 ms: 1.01x faster                                                |
| coroutines                       | 15.1 ms                                                         | 15.3 ms: 1.01x slower                                               |
| async_tree_none                  | 228 ms                                                          | 233 ms: 1.02x slower                                                |
| async_tree_eager_tg              | 182 ms                                                          | 188 ms: 1.03x slower                                                |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 421 ms: 1.03x slower                                                |
| asyncio_websockets               | 296 ms                                                          | 308 ms: 1.04x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 380 ms: 1.05x slower                                                |
| async_tree_eager_memoization     | 180 ms                                                          | 189 ms: 1.05x slower                                                |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.36 sec: 1.06x slower                                              |
| async_tree_memoization           | 281 ms                                                          | 301 ms: 1.07x slower                                                |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 258 ms: 1.09x slower                                                |
| async_generators                 | 228 ms                                                          | 255 ms: 1.12x slower                                                |
| async_tree_eager                 | 81.3 ms                                                         | 93.0 ms: 1.14x slower                                               |
| Geometric mean                   | (ref)                                                           | 1.00x faster                                                        |

Benchmark hidden because not significant (1): async_tree_memoization_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 22.7 ns: 1.17x slower                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 188 ms: 1.09x slower                                                |
| decimal_pi        | 208 ms                                                          | 241 ms: 1.16x slower                                                |
| Geometric mean    | (ref)                                                           | 1.12x slower                                                        |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| quadtree_nbody | 596 ms                                                          | 668 ms: 1.12x slower                                                |
| float          | 47.3 ms                                                         | 53.4 ms: 1.13x slower                                               |
| nbody          | 67.9 ms                                                         | 83.5 ms: 1.23x slower                                               |
| Geometric mean | (ref)                                                           | 1.11x slower                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_v8       | 14.8 ms                                                         | 14.6 ms: 1.02x faster                                               |
| regex_effbot   | 1.95 ms                                                         | 2.02 ms: 1.04x slower                                               |
| regex_dna      | 150 ms                                                          | 157 ms: 1.04x slower                                                |
| regex_compile  | 93.9 ms                                                         | 102 ms: 1.09x slower                                                |
| Geometric mean | (ref)                                                           | 1.04x slower                                                        |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| xml_etree_iterparse  | 76.2 ms                                                         | 64.6 ms: 1.18x faster                                               |
| base16_large         | 5.33 ms                                                         | 4.65 ms: 1.15x faster                                               |
| base64_small         | 186 us                                                          | 171 us: 1.09x faster                                                |
| base64_large         | 3.63 ms                                                         | 3.38 ms: 1.07x faster                                               |
| base16_small         | 305 us                                                          | 292 us: 1.05x faster                                                |
| xml_etree_parse      | 94.3 ms                                                         | 93.0 ms: 1.01x faster                                               |
| urlsafe_base64_small | 329 us                                                          | 325 us: 1.01x faster                                                |
| pickle_pure_python   | 240 us                                                          | 245 us: 1.02x slower                                                |
| unpickle_pure_python | 152 us                                                          | 155 us: 1.02x slower                                                |
| pickle_dict          | 21.5 us                                                         | 22.7 us: 1.05x slower                                               |
| base85_small         | 4.69 ms                                                         | 5.04 ms: 1.07x slower                                               |
| pickle               | 8.20 us                                                         | 8.83 us: 1.08x slower                                               |
| base32_large         | 292 ms                                                          | 316 ms: 1.08x slower                                                |
| json_dumps           | 6.95 ms                                                         | 7.52 ms: 1.08x slower                                               |
| xml_etree_generate   | 62.6 ms                                                         | 67.9 ms: 1.08x slower                                               |
| base85_large         | 248 ms                                                          | 269 ms: 1.09x slower                                                |
| base32_small         | 5.71 ms                                                         | 6.32 ms: 1.11x slower                                               |
| xml_etree_process    | 44.7 ms                                                         | 49.5 ms: 1.11x slower                                               |
| json_loads           | 17.5 us                                                         | 19.4 us: 1.11x slower                                               |
| ascii85_small        | 12.7 ms                                                         | 14.2 ms: 1.12x slower                                               |
| ascii85_large        | 667 ms                                                          | 755 ms: 1.13x slower                                                |
| unpickle_list        | 3.43 us                                                         | 3.99 us: 1.16x slower                                               |
| tomli_loads          | 1.44 sec                                                        | 1.69 sec: 1.17x slower                                              |
| unpickle             | 10.2 us                                                         | 12.1 us: 1.19x slower                                               |
| Geometric mean       | (ref)                                                           | 1.04x slower                                                        |

Benchmark hidden because not significant (1): pickle_list

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 11.7 ms: 1.21x slower                                               |
| python_startup_no_site | 6.38 ms                                                         | 8.20 ms: 1.29x slower                                               |
| Geometric mean         | (ref)                                                           | 1.25x slower                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| django_template | 27.8 ms                                                         | 30.7 ms: 1.10x slower                                               |
| genshi_xml      | 39.5 ms                                                         | 43.6 ms: 1.10x slower                                               |
| genshi_text     | 16.8 ms                                                         | 20.2 ms: 1.20x slower                                               |
| mako            | 7.40 ms                                                         | 11.6 ms: 1.57x slower                                               |
| Geometric mean  | (ref)                                                           | 1.23x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 233 ms                                                          | 59.3 ms: 3.93x faster                                               |
| thread_mandelbrot_optimized | 233 ms                                                          | 62.2 ms: 3.74x faster                                               |
| thread_pipeline_optimized   | 22.5 ms                                                         | 6.73 ms: 3.34x faster                                               |
| thread_accumulate_optimized | 35.1 ms                                                         | 10.7 ms: 3.27x faster                                               |
| thread_counter_optimized    | 17.1 ms                                                         | 5.52 ms: 3.10x faster                                               |
| thread_montecarlo_optimized | 13.9 ms                                                         | 4.94 ms: 2.81x faster                                               |
| thread_accumulate_naive     | 35.8 ms                                                         | 12.8 ms: 2.80x faster                                               |
| thread_memo_optimized       | 15.9 ms                                                         | 5.80 ms: 2.74x faster                                               |
| thread_pipeline_naive       | 32.0 ms                                                         | 24.1 ms: 1.33x faster                                               |
| thread_counter_naive        | 20.2 ms                                                         | 20.5 ms: 1.01x slower                                               |
| thread_memo_naive           | 11.5 ms                                                         | 21.9 ms: 1.90x slower                                               |
| thread_montecarlo_naive     | 15.8 ms                                                         | 32.4 ms: 2.05x slower                                               |
| Geometric mean              | (ref)                                                           | 1.98x faster                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| argparse_many_optionals          | 34.4 ms                                                         | 7.96 ms: 4.32x faster                                               |
| thread_mandelbrot_naive          | 233 ms                                                          | 59.3 ms: 3.93x faster                                               |
| thread_mandelbrot_optimized      | 233 ms                                                          | 62.2 ms: 3.74x faster                                               |
| thread_pipeline_optimized        | 22.5 ms                                                         | 6.73 ms: 3.34x faster                                               |
| thread_accumulate_optimized      | 35.1 ms                                                         | 10.7 ms: 3.27x faster                                               |
| thread_counter_optimized         | 17.1 ms                                                         | 5.52 ms: 3.10x faster                                               |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 4.94 ms: 2.81x faster                                               |
| thread_accumulate_naive          | 35.8 ms                                                         | 12.8 ms: 2.80x faster                                               |
| thread_memo_optimized            | 15.9 ms                                                         | 5.80 ms: 2.74x faster                                               |
| gc_traversal                     | 3.26 ms                                                         | 1.69 ms: 1.92x faster                                               |
| create_gc_cycles                 | 1.96 ms                                                         | 1.36 ms: 1.45x faster                                               |
| argparse_subparsers              | 686 us                                                          | 508 us: 1.35x faster                                                |
| thread_pipeline_naive            | 32.0 ms                                                         | 24.1 ms: 1.33x faster                                               |
| asyncio_tcp                      | 325 ms                                                          | 274 ms: 1.19x faster                                                |
| xml_etree_iterparse              | 76.2 ms                                                         | 64.6 ms: 1.18x faster                                               |
| async_tree_eager_io_tg           | 550 ms                                                          | 467 ms: 1.18x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 469 ms: 1.15x faster                                                |
| base16_large                     | 5.33 ms                                                         | 4.65 ms: 1.15x faster                                               |
| fastapi_http                     | 216 ms                                                          | 192 ms: 1.13x faster                                                |
| pathlib                          | 13.0 ms                                                         | 11.7 ms: 1.11x faster                                               |
| async_tree_eager_io              | 552 ms                                                          | 500 ms: 1.10x faster                                                |
| base64_small                     | 186 us                                                          | 171 us: 1.09x faster                                                |
| base64_large                     | 3.63 ms                                                         | 3.38 ms: 1.07x faster                                               |
| async_tree_none_tg               | 223 ms                                                          | 211 ms: 1.06x faster                                                |
| tornado_http                     | 101 ms                                                          | 96.2 ms: 1.05x faster                                               |
| async_tree_io                    | 531 ms                                                          | 504 ms: 1.05x faster                                                |
| base16_small                     | 305 us                                                          | 292 us: 1.05x faster                                                |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 394 ms: 1.04x faster                                                |
| pycparser                        | 851 ms                                                          | 827 ms: 1.03x faster                                                |
| telco                            | 5.59 ms                                                         | 5.45 ms: 1.03x faster                                               |
| regex_v8                         | 14.8 ms                                                         | 14.6 ms: 1.02x faster                                               |
| xml_etree_parse                  | 94.3 ms                                                         | 93.0 ms: 1.01x faster                                               |
| pidigits                         | 189 ms                                                          | 187 ms: 1.01x faster                                                |
| urlsafe_base64_small             | 329 us                                                          | 325 us: 1.01x faster                                                |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 312 ms: 1.01x faster                                                |
| coroutines                       | 15.1 ms                                                         | 15.3 ms: 1.01x slower                                               |
| thread_counter_naive             | 20.2 ms                                                         | 20.5 ms: 1.01x slower                                               |
| html5lib                         | 46.9 ms                                                         | 47.8 ms: 1.02x slower                                               |
| async_tree_none                  | 228 ms                                                          | 233 ms: 1.02x slower                                                |
| pickle_pure_python               | 240 us                                                          | 245 us: 1.02x slower                                                |
| unpickle_pure_python             | 152 us                                                          | 155 us: 1.02x slower                                                |
| async_tree_eager_tg              | 182 ms                                                          | 188 ms: 1.03x slower                                                |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 421 ms: 1.03x slower                                                |
| scimark_fft                      | 226 ms                                                          | 234 ms: 1.03x slower                                                |
| pylint                           | 216 ms                                                          | 223 ms: 1.03x slower                                                |
| networkx_k_core                  | 2.07 sec                                                        | 2.14 sec: 1.04x slower                                              |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.11 sec: 1.04x slower                                              |
| regex_effbot                     | 1.95 ms                                                         | 2.02 ms: 1.04x slower                                               |
| logging_silent                   | 65.3 ns                                                         | 68.0 ns: 1.04x slower                                               |
| asyncio_websockets               | 296 ms                                                          | 308 ms: 1.04x slower                                                |
| regex_dna                        | 150 ms                                                          | 157 ms: 1.04x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 380 ms: 1.05x slower                                                |
| deepcopy_memo                    | 18.0 us                                                         | 18.9 us: 1.05x slower                                               |
| sympy_sum                        | 106 ms                                                          | 111 ms: 1.05x slower                                                |
| async_tree_eager_memoization     | 180 ms                                                          | 189 ms: 1.05x slower                                                |
| pickle_dict                      | 21.5 us                                                         | 22.7 us: 1.05x slower                                               |
| json                             | 3.42 ms                                                         | 3.62 ms: 1.06x slower                                               |
| thrift                           | 1.86 ms                                                         | 1.98 ms: 1.06x slower                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.36 sec: 1.06x slower                                              |
| async_tree_memoization           | 281 ms                                                          | 301 ms: 1.07x slower                                                |
| mdp                              | 946 ms                                                          | 1.01 sec: 1.07x slower                                              |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 42.0 ms: 1.07x slower                                               |
| base85_small                     | 4.69 ms                                                         | 5.04 ms: 1.07x slower                                               |
| sympy_integrate                  | 15.4 ms                                                         | 16.5 ms: 1.07x slower                                               |
| pickle                           | 8.20 us                                                         | 8.83 us: 1.08x slower                                               |
| base32_large                     | 292 ms                                                          | 316 ms: 1.08x slower                                                |
| json_dumps                       | 6.95 ms                                                         | 7.52 ms: 1.08x slower                                               |
| docutils                         | 1.95 sec                                                        | 2.11 sec: 1.08x slower                                              |
| sympy_expand                     | 332 ms                                                          | 360 ms: 1.08x slower                                                |
| xml_etree_generate               | 62.6 ms                                                         | 67.9 ms: 1.08x slower                                               |
| sympy_str                        | 194 ms                                                          | 211 ms: 1.09x slower                                                |
| regex_compile                    | 93.9 ms                                                         | 102 ms: 1.09x slower                                                |
| deepcopy                         | 193 us                                                          | 209 us: 1.09x slower                                                |
| base85_large                     | 248 ms                                                          | 269 ms: 1.09x slower                                                |
| decimal_factorial                | 173 ms                                                          | 188 ms: 1.09x slower                                                |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 258 ms: 1.09x slower                                                |
| scimark_sor                      | 75.7 ms                                                         | 82.7 ms: 1.09x slower                                               |
| logging_simple                   | 4.79 us                                                         | 5.27 us: 1.10x slower                                               |
| mypy2                            | 753 ms                                                          | 830 ms: 1.10x slower                                                |
| hexiom                           | 4.11 ms                                                         | 4.53 ms: 1.10x slower                                               |
| django_template                  | 27.8 ms                                                         | 30.7 ms: 1.10x slower                                               |
| genshi_xml                       | 39.5 ms                                                         | 43.6 ms: 1.10x slower                                               |
| base32_small                     | 5.71 ms                                                         | 6.32 ms: 1.11x slower                                               |
| generators                       | 20.3 ms                                                         | 22.5 ms: 1.11x slower                                               |
| xml_etree_process                | 44.7 ms                                                         | 49.5 ms: 1.11x slower                                               |
| chaos                            | 43.8 ms                                                         | 48.5 ms: 1.11x slower                                               |
| json_loads                       | 17.5 us                                                         | 19.4 us: 1.11x slower                                               |
| logging_format                   | 5.35 us                                                         | 5.95 us: 1.11x slower                                               |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.28 ms: 1.11x slower                                               |
| pprint_pformat                   | 989 ms                                                          | 1.10 sec: 1.11x slower                                              |
| xdsl_constant_fold               | 34.7 ms                                                         | 38.7 ms: 1.11x slower                                               |
| comprehensions                   | 10.8 us                                                         | 12.0 us: 1.11x slower                                               |
| richards                         | 32.6 ms                                                         | 36.4 ms: 1.12x slower                                               |
| ascii85_small                    | 12.7 ms                                                         | 14.2 ms: 1.12x slower                                               |
| pprint_safe_repr                 | 474 ms                                                          | 530 ms: 1.12x slower                                                |
| async_generators                 | 228 ms                                                          | 255 ms: 1.12x slower                                                |
| quadtree_nbody                   | 596 ms                                                          | 668 ms: 1.12x slower                                                |
| scimark_lu                       | 73.8 ms                                                         | 82.8 ms: 1.12x slower                                               |
| go                               | 84.7 ms                                                         | 95.6 ms: 1.13x slower                                               |
| float                            | 47.3 ms                                                         | 53.4 ms: 1.13x slower                                               |
| ascii85_large                    | 667 ms                                                          | 755 ms: 1.13x slower                                                |
| sqlglot_v2_parse                 | 911 us                                                          | 1.04 ms: 1.14x slower                                               |
| pyflate                          | 299 ms                                                          | 341 ms: 1.14x slower                                                |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 89.1 ms: 1.14x slower                                               |
| async_tree_eager                 | 81.3 ms                                                         | 93.0 ms: 1.14x slower                                               |
| richards_super                   | 37.4 ms                                                         | 42.8 ms: 1.14x slower                                               |
| deepcopy_reduce                  | 2.00 us                                                         | 2.30 us: 1.15x slower                                               |
| spectral_norm                    | 65.6 ms                                                         | 75.8 ms: 1.16x slower                                               |
| deltablue                        | 2.34 ms                                                         | 2.70 ms: 1.16x slower                                               |
| decimal_pi                       | 208 ms                                                          | 241 ms: 1.16x slower                                                |
| chameleon                        | 9.52 ms                                                         | 11.0 ms: 1.16x slower                                               |
| unpickle_list                    | 3.43 us                                                         | 3.99 us: 1.16x slower                                               |
| crypto_pyaes                     | 54.5 ms                                                         | 63.6 ms: 1.17x slower                                               |
| tomli_loads                      | 1.44 sec                                                        | 1.69 sec: 1.17x slower                                              |
| noop                             | 19.4 ns                                                         | 22.7 ns: 1.17x slower                                               |
| raytrace                         | 194 ms                                                          | 229 ms: 1.18x slower                                                |
| fannkuch                         | 245 ms                                                          | 290 ms: 1.18x slower                                                |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 3.76 ms: 1.18x slower                                               |
| networkx_shortest_path           | 444 ms                                                          | 526 ms: 1.18x slower                                                |
| meteor_contest                   | 84.1 ms                                                         | 99.7 ms: 1.19x slower                                               |
| unpickle                         | 10.2 us                                                         | 12.1 us: 1.19x slower                                               |
| nqueens                          | 56.8 ms                                                         | 68.0 ms: 1.20x slower                                               |
| genshi_text                      | 16.8 ms                                                         | 20.2 ms: 1.20x slower                                               |
| python_startup                   | 9.73 ms                                                         | 11.7 ms: 1.21x slower                                               |
| typing_runtime_protocols         | 112 us                                                          | 136 us: 1.21x slower                                                |
| unpack_sequence                  | 25.8 ns                                                         | 31.4 ns: 1.22x slower                                               |
| nbody                            | 67.9 ms                                                         | 83.5 ms: 1.23x slower                                               |
| scimark_monte_carlo              | 40.7 ms                                                         | 51.2 ms: 1.26x slower                                               |
| python_startup_no_site           | 6.38 ms                                                         | 8.20 ms: 1.29x slower                                               |
| networkx_connected_components    | 438 ms                                                          | 601 ms: 1.37x slower                                                |
| coverage                         | 57.4 ms                                                         | 82.8 ms: 1.44x slower                                               |
| mako                             | 7.40 ms                                                         | 11.6 ms: 1.57x slower                                               |
| thread_memo_naive                | 11.5 ms                                                         | 21.9 ms: 1.90x slower                                               |
| thread_montecarlo_naive          | 15.8 ms                                                         | 32.4 ms: 2.05x slower                                               |
| Geometric mean                   | (ref)                                                           | 1.01x faster                                                        |

Benchmark hidden because not significant (2): pickle_list, async_tree_memoization_tg
Ignored benchmarks (1) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.015x faster

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.04x
- 95% likely to have a slowdown of 1.03x
- 99% likely to have a slowdown of 1.03x

# Memory
- memory change: 1.45x