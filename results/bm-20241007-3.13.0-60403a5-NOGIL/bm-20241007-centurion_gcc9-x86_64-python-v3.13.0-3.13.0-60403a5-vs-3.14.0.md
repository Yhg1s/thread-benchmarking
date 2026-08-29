# Results vs. 3.14.0

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.238x slower
- HPT reliability: 100.00%
- HPT 99th percentile: 1.25x slower
- Memory change: 1.35x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 16.3 ms: 1.71x slower                                           |
| docutils       | 1.95 sec                                                        | 2.32 sec: 1.19x slower                                          |
| fastapi_http   | 216 ms                                                          | 291 ms: 1.35x slower                                            |
| html5lib       | 46.9 ms                                                         | 70.5 ms: 1.50x slower                                           |
| tornado_http   | 101 ms                                                          | 116 ms: 1.15x slower                                            |
| Geometric mean | (ref)                                                           | 1.36x slower                                                    |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                          | 90.8 ms: 2.01x faster                                           |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 204 ms: 1.16x faster                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 325 ms: 1.12x faster                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.43 sec: 1.11x slower                                          |
| asyncio_tcp                      | 325 ms                                                          | 378 ms: 1.16x slower                                            |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 371 ms: 1.18x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 653 ms: 1.19x slower                                            |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 506 ms: 1.23x slower                                            |
| coroutines                       | 15.1 ms                                                         | 19.0 ms: 1.25x slower                                           |
| async_tree_eager_io              | 552 ms                                                          | 703 ms: 1.27x slower                                            |
| async_tree_io_tg                 | 539 ms                                                          | 703 ms: 1.30x slower                                            |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 544 ms: 1.33x slower                                            |
| async_generators                 | 228 ms                                                          | 312 ms: 1.37x slower                                            |
| async_tree_io                    | 531 ms                                                          | 739 ms: 1.39x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 313 ms: 1.40x slower                                            |
| async_tree_eager_memoization     | 180 ms                                                          | 257 ms: 1.43x slower                                            |
| async_tree_memoization_tg        | 277 ms                                                          | 404 ms: 1.46x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 436 ms: 1.55x slower                                            |
| async_tree_none                  | 228 ms                                                          | 355 ms: 1.56x slower                                            |
| async_tree_eager                 | 81.3 ms                                                         | 136 ms: 1.67x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.21x slower                                                    |

Benchmark hidden because not significant (1): asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 24.6 ns: 1.27x slower                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 190 ms: 1.10x slower                                            |
| decimal_pi        | 208 ms                                                          | 254 ms: 1.22x slower                                            |
| Geometric mean    | (ref)                                                           | 1.16x slower                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 185 ms: 1.02x faster                                            |
| float          | 47.3 ms                                                         | 97.8 ms: 2.07x slower                                           |
| nbody          | 67.9 ms                                                         | 142 ms: 2.09x slower                                            |
| quadtree_nbody | 596 ms                                                          | 1.36 sec: 2.28x slower                                          |
| Geometric mean | (ref)                                                           | 1.76x slower                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_v8       | 14.8 ms                                                         | 15.2 ms: 1.02x slower                                           |
| regex_dna      | 150 ms                                                          | 160 ms: 1.06x slower                                            |
| regex_effbot   | 1.95 ms                                                         | 2.21 ms: 1.14x slower                                           |
| regex_compile  | 93.9 ms                                                         | 147 ms: 1.56x slower                                            |
| Geometric mean | (ref)                                                           | 1.18x slower                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| pickle               | 8.20 us                                                         | 7.38 us: 1.11x faster                                           |
| base64_large         | 3.63 ms                                                         | 3.35 ms: 1.08x faster                                           |
| xml_etree_iterparse  | 76.2 ms                                                         | 71.0 ms: 1.07x faster                                           |
| xml_etree_parse      | 94.3 ms                                                         | 91.4 ms: 1.03x faster                                           |
| pickle_list          | 3.24 us                                                         | 3.17 us: 1.02x faster                                           |
| json_loads           | 17.5 us                                                         | 18.7 us: 1.07x slower                                           |
| unpickle_list        | 3.43 us                                                         | 3.77 us: 1.10x slower                                           |
| unpickle             | 10.2 us                                                         | 11.3 us: 1.11x slower                                           |
| base32_large         | 292 ms                                                          | 327 ms: 1.12x slower                                            |
| base32_small         | 5.71 ms                                                         | 6.56 ms: 1.15x slower                                           |
| xml_etree_generate   | 62.6 ms                                                         | 74.4 ms: 1.19x slower                                           |
| json_dumps           | 6.95 ms                                                         | 8.33 ms: 1.20x slower                                           |
| base85_small         | 4.69 ms                                                         | 5.96 ms: 1.27x slower                                           |
| base85_large         | 248 ms                                                          | 316 ms: 1.27x slower                                            |
| base64_small         | 186 us                                                          | 246 us: 1.32x slower                                            |
| xml_etree_process    | 44.7 ms                                                         | 60.6 ms: 1.36x slower                                           |
| urlsafe_base64_small | 329 us                                                          | 456 us: 1.39x slower                                            |
| ascii85_small        | 12.7 ms                                                         | 18.2 ms: 1.43x slower                                           |
| ascii85_large        | 667 ms                                                          | 973 ms: 1.46x slower                                            |
| tomli_loads          | 1.44 sec                                                        | 2.24 sec: 1.55x slower                                          |
| pickle_pure_python   | 240 us                                                          | 398 us: 1.66x slower                                            |
| unpickle_pure_python | 152 us                                                          | 264 us: 1.74x slower                                            |
| base16_small         | 305 us                                                          | 920 us: 3.01x slower                                            |
| base16_large         | 5.33 ms                                                         | 36.8 ms: 6.90x slower                                           |
| Geometric mean       | (ref)                                                           | 1.34x slower                                                    |

Benchmark hidden because not significant (1): pickle_dict

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 11.6 ms: 1.19x slower                                           |
| python_startup_no_site | 6.38 ms                                                         | 7.98 ms: 1.25x slower                                           |
| Geometric mean         | (ref)                                                           | 1.22x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| genshi_xml      | 39.5 ms                                                         | 59.7 ms: 1.51x slower                                           |
| django_template | 27.8 ms                                                         | 44.5 ms: 1.60x slower                                           |
| genshi_text     | 16.8 ms                                                         | 30.0 ms: 1.79x slower                                           |
| mako            | 7.40 ms                                                         | 13.7 ms: 1.85x slower                                           |
| Geometric mean  | (ref)                                                           | 1.68x slower                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_accumulate_optimized | 35.1 ms                                                         | 9.91 ms: 3.54x faster                                           |
| thread_mandelbrot_optimized | 233 ms                                                          | 66.8 ms: 3.49x faster                                           |
| thread_pipeline_optimized   | 22.5 ms                                                         | 6.47 ms: 3.47x faster                                           |
| thread_mandelbrot_naive     | 233 ms                                                          | 67.3 ms: 3.47x faster                                           |
| thread_accumulate_naive     | 35.8 ms                                                         | 11.4 ms: 3.14x faster                                           |
| thread_counter_optimized    | 17.1 ms                                                         | 6.01 ms: 2.85x faster                                           |
| thread_montecarlo_optimized | 13.9 ms                                                         | 5.31 ms: 2.62x faster                                           |
| thread_memo_optimized       | 15.9 ms                                                         | 6.25 ms: 2.55x faster                                           |
| thread_counter_naive        | 20.2 ms                                                         | 27.8 ms: 1.38x slower                                           |
| thread_pipeline_naive       | 32.0 ms                                                         | 52.9 ms: 1.65x slower                                           |
| thread_montecarlo_naive     | 15.8 ms                                                         | 63.7 ms: 4.03x slower                                           |
| thread_memo_naive           | 11.5 ms                                                         | 49.9 ms: 4.33x slower                                           |
| Geometric mean              | (ref)                                                           | 1.57x faster                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_accumulate_optimized      | 35.1 ms                                                         | 9.91 ms: 3.54x faster                                           |
| thread_mandelbrot_optimized      | 233 ms                                                          | 66.8 ms: 3.49x faster                                           |
| thread_pipeline_optimized        | 22.5 ms                                                         | 6.47 ms: 3.47x faster                                           |
| thread_mandelbrot_naive          | 233 ms                                                          | 67.3 ms: 3.47x faster                                           |
| thread_accumulate_naive          | 35.8 ms                                                         | 11.4 ms: 3.14x faster                                           |
| thread_counter_optimized         | 17.1 ms                                                         | 6.01 ms: 2.85x faster                                           |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 5.31 ms: 2.62x faster                                           |
| thread_memo_optimized            | 15.9 ms                                                         | 6.25 ms: 2.55x faster                                           |
| async_tree_eager_tg              | 182 ms                                                          | 90.8 ms: 2.01x faster                                           |
| argparse_many_optionals          | 34.4 ms                                                         | 18.4 ms: 1.87x faster                                           |
| argparse_subparsers              | 686 us                                                          | 558 us: 1.23x faster                                            |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 204 ms: 1.16x faster                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 325 ms: 1.12x faster                                            |
| pickle                           | 8.20 us                                                         | 7.38 us: 1.11x faster                                           |
| create_gc_cycles                 | 1.96 ms                                                         | 1.78 ms: 1.10x faster                                           |
| base64_large                     | 3.63 ms                                                         | 3.35 ms: 1.08x faster                                           |
| xml_etree_iterparse              | 76.2 ms                                                         | 71.0 ms: 1.07x faster                                           |
| gc_traversal                     | 3.26 ms                                                         | 3.15 ms: 1.04x faster                                           |
| xml_etree_parse                  | 94.3 ms                                                         | 91.4 ms: 1.03x faster                                           |
| pidigits                         | 189 ms                                                          | 185 ms: 1.02x faster                                            |
| pickle_list                      | 3.24 us                                                         | 3.17 us: 1.02x faster                                           |
| regex_v8                         | 14.8 ms                                                         | 15.2 ms: 1.02x slower                                           |
| regex_dna                        | 150 ms                                                          | 160 ms: 1.06x slower                                            |
| json_loads                       | 17.5 us                                                         | 18.7 us: 1.07x slower                                           |
| json                             | 3.42 ms                                                         | 3.72 ms: 1.09x slower                                           |
| decimal_factorial                | 173 ms                                                          | 190 ms: 1.10x slower                                            |
| unpickle_list                    | 3.43 us                                                         | 3.77 us: 1.10x slower                                           |
| unpickle                         | 10.2 us                                                         | 11.3 us: 1.11x slower                                           |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.43 sec: 1.11x slower                                          |
| base32_large                     | 292 ms                                                          | 327 ms: 1.12x slower                                            |
| regex_effbot                     | 1.95 ms                                                         | 2.21 ms: 1.14x slower                                           |
| tornado_http                     | 101 ms                                                          | 116 ms: 1.15x slower                                            |
| base32_small                     | 5.71 ms                                                         | 6.56 ms: 1.15x slower                                           |
| networkx_k_core                  | 2.07 sec                                                        | 2.38 sec: 1.15x slower                                          |
| networkx_connected_components    | 438 ms                                                          | 505 ms: 1.15x slower                                            |
| asyncio_tcp                      | 325 ms                                                          | 378 ms: 1.16x slower                                            |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 371 ms: 1.18x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 653 ms: 1.19x slower                                            |
| xml_etree_generate               | 62.6 ms                                                         | 74.4 ms: 1.19x slower                                           |
| python_startup                   | 9.73 ms                                                         | 11.6 ms: 1.19x slower                                           |
| docutils                         | 1.95 sec                                                        | 2.32 sec: 1.19x slower                                          |
| scimark_fft                      | 226 ms                                                          | 270 ms: 1.19x slower                                            |
| networkx_shortest_path           | 444 ms                                                          | 530 ms: 1.19x slower                                            |
| json_dumps                       | 6.95 ms                                                         | 8.33 ms: 1.20x slower                                           |
| pathlib                          | 13.0 ms                                                         | 15.6 ms: 1.20x slower                                           |
| generators                       | 20.3 ms                                                         | 24.5 ms: 1.21x slower                                           |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 3.85 ms: 1.21x slower                                           |
| coverage                         | 57.4 ms                                                         | 69.8 ms: 1.21x slower                                           |
| decimal_pi                       | 208 ms                                                          | 254 ms: 1.22x slower                                            |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 506 ms: 1.23x slower                                            |
| python_startup_no_site           | 6.38 ms                                                         | 7.98 ms: 1.25x slower                                           |
| coroutines                       | 15.1 ms                                                         | 19.0 ms: 1.25x slower                                           |
| base85_small                     | 4.69 ms                                                         | 5.96 ms: 1.27x slower                                           |
| noop                             | 19.4 ns                                                         | 24.6 ns: 1.27x slower                                           |
| async_tree_eager_io              | 552 ms                                                          | 703 ms: 1.27x slower                                            |
| base85_large                     | 248 ms                                                          | 316 ms: 1.27x slower                                            |
| pylint                           | 216 ms                                                          | 275 ms: 1.28x slower                                            |
| meteor_contest                   | 84.1 ms                                                         | 107 ms: 1.28x slower                                            |
| telco                            | 5.59 ms                                                         | 7.29 ms: 1.30x slower                                           |
| async_tree_io_tg                 | 539 ms                                                          | 703 ms: 1.30x slower                                            |
| nqueens                          | 56.8 ms                                                         | 74.9 ms: 1.32x slower                                           |
| pycparser                        | 851 ms                                                          | 1.12 sec: 1.32x slower                                          |
| base64_small                     | 186 us                                                          | 246 us: 1.32x slower                                            |
| xdsl_constant_fold               | 34.7 ms                                                         | 46.0 ms: 1.32x slower                                           |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 544 ms: 1.33x slower                                            |
| crypto_pyaes                     | 54.5 ms                                                         | 72.9 ms: 1.34x slower                                           |
| mypy2                            | 753 ms                                                          | 1.01 sec: 1.35x slower                                          |
| fastapi_http                     | 216 ms                                                          | 291 ms: 1.35x slower                                            |
| sympy_integrate                  | 15.4 ms                                                         | 20.8 ms: 1.35x slower                                           |
| xml_etree_process                | 44.7 ms                                                         | 60.6 ms: 1.36x slower                                           |
| async_generators                 | 228 ms                                                          | 312 ms: 1.37x slower                                            |
| thread_counter_naive             | 20.2 ms                                                         | 27.8 ms: 1.38x slower                                           |
| urlsafe_base64_small             | 329 us                                                          | 456 us: 1.39x slower                                            |
| async_tree_io                    | 531 ms                                                          | 739 ms: 1.39x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 313 ms: 1.40x slower                                            |
| fannkuch                         | 245 ms                                                          | 347 ms: 1.42x slower                                            |
| bpe_tokeniser                    | 3.00 sec                                                        | 4.27 sec: 1.42x slower                                          |
| async_tree_eager_memoization     | 180 ms                                                          | 257 ms: 1.43x slower                                            |
| ascii85_small                    | 12.7 ms                                                         | 18.2 ms: 1.43x slower                                           |
| async_tree_memoization_tg        | 277 ms                                                          | 404 ms: 1.46x slower                                            |
| ascii85_large                    | 667 ms                                                          | 973 ms: 1.46x slower                                            |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 57.6 ms: 1.48x slower                                           |
| html5lib                         | 46.9 ms                                                         | 70.5 ms: 1.50x slower                                           |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 118 ms: 1.51x slower                                            |
| genshi_xml                       | 39.5 ms                                                         | 59.7 ms: 1.51x slower                                           |
| typing_runtime_protocols         | 112 us                                                          | 169 us: 1.51x slower                                            |
| sympy_str                        | 194 ms                                                          | 296 ms: 1.53x slower                                            |
| spectral_norm                    | 65.6 ms                                                         | 102 ms: 1.55x slower                                            |
| tomli_loads                      | 1.44 sec                                                        | 2.24 sec: 1.55x slower                                          |
| async_tree_memoization           | 281 ms                                                          | 436 ms: 1.55x slower                                            |
| async_tree_none                  | 228 ms                                                          | 355 ms: 1.56x slower                                            |
| regex_compile                    | 93.9 ms                                                         | 147 ms: 1.56x slower                                            |
| django_template                  | 27.8 ms                                                         | 44.5 ms: 1.60x slower                                           |
| comprehensions                   | 10.8 us                                                         | 17.5 us: 1.62x slower                                           |
| logging_format                   | 5.35 us                                                         | 8.71 us: 1.63x slower                                           |
| pyflate                          | 299 ms                                                          | 490 ms: 1.64x slower                                            |
| sympy_expand                     | 332 ms                                                          | 547 ms: 1.65x slower                                            |
| thread_pipeline_naive            | 32.0 ms                                                         | 52.9 ms: 1.65x slower                                           |
| pickle_pure_python               | 240 us                                                          | 398 us: 1.66x slower                                            |
| logging_simple                   | 4.79 us                                                         | 7.96 us: 1.66x slower                                           |
| async_tree_eager                 | 81.3 ms                                                         | 136 ms: 1.67x slower                                            |
| sympy_sum                        | 106 ms                                                          | 178 ms: 1.67x slower                                            |
| richards                         | 32.6 ms                                                         | 55.0 ms: 1.69x slower                                           |
| chameleon                        | 9.52 ms                                                         | 16.3 ms: 1.71x slower                                           |
| richards_super                   | 37.4 ms                                                         | 64.6 ms: 1.73x slower                                           |
| unpickle_pure_python             | 152 us                                                          | 264 us: 1.74x slower                                            |
| logging_silent                   | 65.3 ns                                                         | 115 ns: 1.76x slower                                            |
| hexiom                           | 4.11 ms                                                         | 7.30 ms: 1.78x slower                                           |
| chaos                            | 43.8 ms                                                         | 78.0 ms: 1.78x slower                                           |
| deepcopy_reduce                  | 2.00 us                                                         | 3.57 us: 1.79x slower                                           |
| genshi_text                      | 16.8 ms                                                         | 30.0 ms: 1.79x slower                                           |
| thrift                           | 1.86 ms                                                         | 3.34 ms: 1.79x slower                                           |
| pprint_pformat                   | 989 ms                                                          | 1.78 sec: 1.80x slower                                          |
| pprint_safe_repr                 | 474 ms                                                          | 856 ms: 1.80x slower                                            |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 2.11 ms: 1.84x slower                                           |
| mako                             | 7.40 ms                                                         | 13.7 ms: 1.85x slower                                           |
| scimark_monte_carlo              | 40.7 ms                                                         | 76.1 ms: 1.87x slower                                           |
| raytrace                         | 194 ms                                                          | 373 ms: 1.92x slower                                            |
| sqlglot_v2_parse                 | 911 us                                                          | 1.83 ms: 2.01x slower                                           |
| deepcopy                         | 193 us                                                          | 392 us: 2.03x slower                                            |
| float                            | 47.3 ms                                                         | 97.8 ms: 2.07x slower                                           |
| scimark_sor                      | 75.7 ms                                                         | 158 ms: 2.09x slower                                            |
| nbody                            | 67.9 ms                                                         | 142 ms: 2.09x slower                                            |
| scimark_lu                       | 73.8 ms                                                         | 167 ms: 2.27x slower                                            |
| deepcopy_memo                    | 18.0 us                                                         | 41.0 us: 2.28x slower                                           |
| quadtree_nbody                   | 596 ms                                                          | 1.36 sec: 2.28x slower                                          |
| deltablue                        | 2.34 ms                                                         | 5.73 ms: 2.45x slower                                           |
| go                               | 84.7 ms                                                         | 209 ms: 2.46x slower                                            |
| mdp                              | 946 ms                                                          | 2.48 sec: 2.62x slower                                          |
| base16_small                     | 305 us                                                          | 920 us: 3.01x slower                                            |
| thread_montecarlo_naive          | 15.8 ms                                                         | 63.7 ms: 4.03x slower                                           |
| unpack_sequence                  | 25.8 ns                                                         | 107 ns: 4.15x slower                                            |
| thread_memo_naive                | 11.5 ms                                                         | 49.9 ms: 4.33x slower                                           |
| base16_large                     | 5.33 ms                                                         | 36.8 ms: 6.90x slower                                           |
| Geometric mean                   | (ref)                                                           | 1.31x slower                                                    |

Benchmark hidden because not significant (2): asyncio_websockets, pickle_dict
Ignored benchmarks (1) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.238x slower

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.29x
- 95% likely to have a slowdown of 1.28x
- 99% likely to have a slowdown of 1.25x

# Memory
- memory change: 1.35x