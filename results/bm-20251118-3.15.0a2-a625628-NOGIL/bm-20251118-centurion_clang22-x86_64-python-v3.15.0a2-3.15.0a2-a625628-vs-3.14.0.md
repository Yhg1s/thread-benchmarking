# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.014x faster
- HPT reliability: 99.71%
- HPT 99th percentile: 1.01x slower
- Memory change: 1.47x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 12.4 ms: 1.21x slower                                                  |
| docutils       | 1.98 sec                                                           | 2.05 sec: 1.04x slower                                                 |
| fastapi_http   | 222 ms                                                             | 203 ms: 1.09x faster                                                   |
| html5lib       | 45.3 ms                                                            | 49.4 ms: 1.09x slower                                                  |
| tornado_http   | 101 ms                                                             | 95.4 ms: 1.06x faster                                                  |
| Geometric mean | (ref)                                                              | 1.03x slower                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 565 ms                                                             | 414 ms: 1.36x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 419 ms: 1.30x faster                                                   |
| async_tree_eager_io              | 568 ms                                                             | 448 ms: 1.27x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 180 ms: 1.24x faster                                                   |
| async_tree_io                    | 549 ms                                                             | 452 ms: 1.21x faster                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 240 ms: 1.16x faster                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 158 ms: 1.15x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 378 ms: 1.13x faster                                                   |
| async_tree_none                  | 233 ms                                                             | 214 ms: 1.09x faster                                                   |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 218 ms: 1.09x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 302 ms: 1.07x faster                                                   |
| asyncio_websockets               | 305 ms                                                             | 286 ms: 1.07x faster                                                   |
| async_tree_memoization           | 285 ms                                                             | 268 ms: 1.06x faster                                                   |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 406 ms: 1.05x faster                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 360 ms: 1.04x faster                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 338 ms: 1.03x slower                                                   |
| coroutines                       | 15.1 ms                                                            | 16.2 ms: 1.07x slower                                                  |
| async_generators                 | 231 ms                                                             | 248 ms: 1.07x slower                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.39 sec: 1.07x slower                                                 |
| async_tree_eager                 | 83.0 ms                                                            | 100 ms: 1.21x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.08x faster                                                           |

Benchmark hidden because not significant (1): async_tree_eager_memoization

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 22.3 ns: 1.16x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 187 ms: 1.07x slower                                                   |
| decimal_pi        | 209 ms                                                             | 242 ms: 1.15x slower                                                   |
| Geometric mean    | (ref)                                                              | 1.11x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| pidigits       | 216 ms                                                             | 214 ms: 1.01x faster                                                   |
| float          | 51.2 ms                                                            | 53.1 ms: 1.04x slower                                                  |
| quadtree_nbody | 654 ms                                                             | 712 ms: 1.09x slower                                                   |
| nbody          | 74.2 ms                                                            | 89.2 ms: 1.20x slower                                                  |
| Geometric mean | (ref)                                                              | 1.08x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_effbot   | 1.98 ms                                                            | 1.95 ms: 1.01x faster                                                  |
| regex_v8       | 15.0 ms                                                            | 14.9 ms: 1.01x faster                                                  |
| regex_dna      | 147 ms                                                             | 150 ms: 1.02x slower                                                   |
| regex_compile  | 97.0 ms                                                            | 116 ms: 1.20x slower                                                   |
| Geometric mean | (ref)                                                              | 1.05x slower                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| xml_etree_iterparse  | 85.5 ms                                                            | 71.5 ms: 1.20x faster                                                  |
| json_dumps           | 7.52 ms                                                            | 6.91 ms: 1.09x faster                                                  |
| pickle_list          | 3.03 us                                                            | 2.83 us: 1.07x faster                                                  |
| base16_large         | 6.35 ms                                                            | 5.97 ms: 1.06x faster                                                  |
| xml_etree_parse      | 118 ms                                                             | 111 ms: 1.06x faster                                                   |
| pickle_dict          | 20.0 us                                                            | 19.0 us: 1.05x faster                                                  |
| pickle               | 8.04 us                                                            | 7.72 us: 1.04x faster                                                  |
| base16_small         | 265 us                                                             | 255 us: 1.04x faster                                                   |
| base64_large         | 5.70 ms                                                            | 5.50 ms: 1.04x faster                                                  |
| base64_small         | 227 us                                                             | 221 us: 1.03x faster                                                   |
| unpickle             | 10.5 us                                                            | 10.6 us: 1.01x slower                                                  |
| json_loads           | 18.6 us                                                            | 19.0 us: 1.02x slower                                                  |
| xml_etree_process    | 50.0 ms                                                            | 52.4 ms: 1.05x slower                                                  |
| xml_etree_generate   | 68.1 ms                                                            | 72.1 ms: 1.06x slower                                                  |
| unpickle_list        | 3.03 us                                                            | 3.27 us: 1.08x slower                                                  |
| tomli_loads          | 1.49 sec                                                           | 1.64 sec: 1.10x slower                                                 |
| base32_small         | 5.71 ms                                                            | 6.39 ms: 1.12x slower                                                  |
| base32_large         | 289 ms                                                             | 325 ms: 1.12x slower                                                   |
| pickle_pure_python   | 251 us                                                             | 283 us: 1.13x slower                                                   |
| base85_large         | 249 ms                                                             | 285 ms: 1.14x slower                                                   |
| base85_small         | 4.66 ms                                                            | 5.39 ms: 1.16x slower                                                  |
| unpickle_pure_python | 163 us                                                             | 189 us: 1.16x slower                                                   |
| ascii85_small        | 13.0 ms                                                            | 16.1 ms: 1.24x slower                                                  |
| ascii85_large        | 681 ms                                                             | 852 ms: 1.25x slower                                                   |
| Geometric mean       | (ref)                                                              | 1.04x slower                                                           |

Benchmark hidden because not significant (1): urlsafe_base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 11.5 ms: 1.16x slower                                                  |
| python_startup_no_site | 6.52 ms                                                            | 8.11 ms: 1.24x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.20x slower                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 35.6 ms: 1.17x slower                                                  |
| genshi_xml      | 43.2 ms                                                            | 51.2 ms: 1.18x slower                                                  |
| genshi_text     | 18.0 ms                                                            | 21.7 ms: 1.20x slower                                                  |
| mako            | 8.69 ms                                                            | 11.9 ms: 1.37x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.23x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 207 ms                                                             | 52.9 ms: 3.91x faster                                                  |
| thread_mandelbrot_optimized | 205 ms                                                             | 52.8 ms: 3.89x faster                                                  |
| thread_pipeline_optimized   | 25.8 ms                                                            | 7.08 ms: 3.64x faster                                                  |
| thread_accumulate_optimized | 39.5 ms                                                            | 11.2 ms: 3.52x faster                                                  |
| thread_counter_optimized    | 18.3 ms                                                            | 5.79 ms: 3.17x faster                                                  |
| thread_accumulate_naive     | 40.4 ms                                                            | 13.2 ms: 3.06x faster                                                  |
| thread_memo_optimized       | 17.5 ms                                                            | 5.86 ms: 2.99x faster                                                  |
| thread_montecarlo_optimized | 12.9 ms                                                            | 4.72 ms: 2.73x faster                                                  |
| thread_pipeline_naive       | 34.9 ms                                                            | 24.7 ms: 1.41x faster                                                  |
| thread_counter_naive        | 21.2 ms                                                            | 20.6 ms: 1.03x faster                                                  |
| thread_memo_naive           | 12.4 ms                                                            | 21.3 ms: 1.72x slower                                                  |
| thread_montecarlo_naive     | 14.3 ms                                                            | 25.4 ms: 1.78x slower                                                  |
| Geometric mean              | (ref)                                                              | 2.10x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_naive          | 207 ms                                                             | 52.9 ms: 3.91x faster                                                  |
| thread_mandelbrot_optimized      | 205 ms                                                             | 52.8 ms: 3.89x faster                                                  |
| thread_pipeline_optimized        | 25.8 ms                                                            | 7.08 ms: 3.64x faster                                                  |
| thread_accumulate_optimized      | 39.5 ms                                                            | 11.2 ms: 3.52x faster                                                  |
| thread_counter_optimized         | 18.3 ms                                                            | 5.79 ms: 3.17x faster                                                  |
| thread_accumulate_naive          | 40.4 ms                                                            | 13.2 ms: 3.06x faster                                                  |
| thread_memo_optimized            | 17.5 ms                                                            | 5.86 ms: 2.99x faster                                                  |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 4.72 ms: 2.73x faster                                                  |
| gc_traversal                     | 3.36 ms                                                            | 1.55 ms: 2.17x faster                                                  |
| create_gc_cycles                 | 2.02 ms                                                            | 1.24 ms: 1.63x faster                                                  |
| thread_pipeline_naive            | 34.9 ms                                                            | 24.7 ms: 1.41x faster                                                  |
| async_tree_eager_io_tg           | 565 ms                                                             | 414 ms: 1.36x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 419 ms: 1.30x faster                                                   |
| async_tree_eager_io              | 568 ms                                                             | 448 ms: 1.27x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 180 ms: 1.24x faster                                                   |
| async_tree_io                    | 549 ms                                                             | 452 ms: 1.21x faster                                                   |
| xml_etree_iterparse              | 85.5 ms                                                            | 71.5 ms: 1.20x faster                                                  |
| async_tree_memoization_tg        | 279 ms                                                             | 240 ms: 1.16x faster                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 158 ms: 1.15x faster                                                   |
| pathlib                          | 12.7 ms                                                            | 11.1 ms: 1.14x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 378 ms: 1.13x faster                                                   |
| fastapi_http                     | 222 ms                                                             | 203 ms: 1.09x faster                                                   |
| async_tree_none                  | 233 ms                                                             | 214 ms: 1.09x faster                                                   |
| json_dumps                       | 7.52 ms                                                            | 6.91 ms: 1.09x faster                                                  |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 218 ms: 1.09x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 302 ms: 1.07x faster                                                   |
| pickle_list                      | 3.03 us                                                            | 2.83 us: 1.07x faster                                                  |
| asyncio_websockets               | 305 ms                                                             | 286 ms: 1.07x faster                                                   |
| base16_large                     | 6.35 ms                                                            | 5.97 ms: 1.06x faster                                                  |
| async_tree_memoization           | 285 ms                                                             | 268 ms: 1.06x faster                                                   |
| xml_etree_parse                  | 118 ms                                                             | 111 ms: 1.06x faster                                                   |
| tornado_http                     | 101 ms                                                             | 95.4 ms: 1.06x faster                                                  |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 406 ms: 1.05x faster                                                   |
| pickle_dict                      | 20.0 us                                                            | 19.0 us: 1.05x faster                                                  |
| pickle                           | 8.04 us                                                            | 7.72 us: 1.04x faster                                                  |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 360 ms: 1.04x faster                                                   |
| base16_small                     | 265 us                                                             | 255 us: 1.04x faster                                                   |
| base64_large                     | 5.70 ms                                                            | 5.50 ms: 1.04x faster                                                  |
| thread_counter_naive             | 21.2 ms                                                            | 20.6 ms: 1.03x faster                                                  |
| base64_small                     | 227 us                                                             | 221 us: 1.03x faster                                                   |
| regex_effbot                     | 1.98 ms                                                            | 1.95 ms: 1.01x faster                                                  |
| pidigits                         | 216 ms                                                             | 214 ms: 1.01x faster                                                   |
| json                             | 3.46 ms                                                            | 3.43 ms: 1.01x faster                                                  |
| regex_v8                         | 15.0 ms                                                            | 14.9 ms: 1.01x faster                                                  |
| unpickle                         | 10.5 us                                                            | 10.6 us: 1.01x slower                                                  |
| regex_dna                        | 147 ms                                                             | 150 ms: 1.02x slower                                                   |
| json_loads                       | 18.6 us                                                            | 19.0 us: 1.02x slower                                                  |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 338 ms: 1.03x slower                                                   |
| docutils                         | 1.98 sec                                                           | 2.05 sec: 1.04x slower                                                 |
| pycparser                        | 878 ms                                                             | 910 ms: 1.04x slower                                                   |
| float                            | 51.2 ms                                                            | 53.1 ms: 1.04x slower                                                  |
| pylint                           | 222 ms                                                             | 231 ms: 1.04x slower                                                   |
| xml_etree_process                | 50.0 ms                                                            | 52.4 ms: 1.05x slower                                                  |
| mypy2                            | 780 ms                                                             | 821 ms: 1.05x slower                                                   |
| telco                            | 5.39 ms                                                            | 5.68 ms: 1.05x slower                                                  |
| xml_etree_generate               | 68.1 ms                                                            | 72.1 ms: 1.06x slower                                                  |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 44.4 ms: 1.06x slower                                                  |
| coroutines                       | 15.1 ms                                                            | 16.2 ms: 1.07x slower                                                  |
| decimal_factorial                | 174 ms                                                             | 187 ms: 1.07x slower                                                   |
| async_generators                 | 231 ms                                                             | 248 ms: 1.07x slower                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.39 sec: 1.07x slower                                                 |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.9 ms: 1.08x slower                                                  |
| unpickle_list                    | 3.03 us                                                            | 3.27 us: 1.08x slower                                                  |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.36 sec: 1.08x slower                                                 |
| sympy_sum                        | 109 ms                                                             | 118 ms: 1.09x slower                                                   |
| quadtree_nbody                   | 654 ms                                                             | 712 ms: 1.09x slower                                                   |
| html5lib                         | 45.3 ms                                                            | 49.4 ms: 1.09x slower                                                  |
| generators                       | 24.2 ms                                                            | 26.4 ms: 1.09x slower                                                  |
| unpack_sequence                  | 35.6 ns                                                            | 38.9 ns: 1.09x slower                                                  |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 92.9 ms: 1.10x slower                                                  |
| tomli_loads                      | 1.49 sec                                                           | 1.64 sec: 1.10x slower                                                 |
| mdp                              | 971 ms                                                             | 1.07 sec: 1.10x slower                                                 |
| logging_format                   | 6.00 us                                                            | 6.62 us: 1.10x slower                                                  |
| argparse_subparsers              | 687 us                                                             | 758 us: 1.10x slower                                                   |
| scimark_fft                      | 211 ms                                                             | 234 ms: 1.11x slower                                                   |
| thrift                           | 2.00 ms                                                            | 2.22 ms: 1.11x slower                                                  |
| spectral_norm                    | 64.1 ms                                                            | 71.7 ms: 1.12x slower                                                  |
| sympy_integrate                  | 15.1 ms                                                            | 16.9 ms: 1.12x slower                                                  |
| base32_small                     | 5.71 ms                                                            | 6.39 ms: 1.12x slower                                                  |
| base32_large                     | 289 ms                                                             | 325 ms: 1.12x slower                                                   |
| pickle_pure_python               | 251 us                                                             | 283 us: 1.13x slower                                                   |
| deltablue                        | 2.76 ms                                                            | 3.13 ms: 1.13x slower                                                  |
| sympy_str                        | 200 ms                                                             | 228 ms: 1.14x slower                                                   |
| crypto_pyaes                     | 56.7 ms                                                            | 64.6 ms: 1.14x slower                                                  |
| base85_large                     | 249 ms                                                             | 285 ms: 1.14x slower                                                   |
| meteor_contest                   | 85.4 ms                                                            | 97.7 ms: 1.14x slower                                                  |
| sympy_expand                     | 344 ms                                                             | 393 ms: 1.14x slower                                                   |
| pyflate                          | 309 ms                                                             | 355 ms: 1.15x slower                                                   |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 3.32 ms: 1.15x slower                                                  |
| xdsl_constant_fold               | 36.0 ms                                                            | 41.5 ms: 1.15x slower                                                  |
| argparse_many_optionals          | 34.5 ms                                                            | 39.8 ms: 1.15x slower                                                  |
| decimal_pi                       | 209 ms                                                             | 242 ms: 1.15x slower                                                   |
| deepcopy_memo                    | 19.1 us                                                            | 22.1 us: 1.16x slower                                                  |
| deepcopy                         | 198 us                                                             | 229 us: 1.16x slower                                                   |
| base85_small                     | 4.66 ms                                                            | 5.39 ms: 1.16x slower                                                  |
| python_startup                   | 9.93 ms                                                            | 11.5 ms: 1.16x slower                                                  |
| go                               | 91.1 ms                                                            | 106 ms: 1.16x slower                                                   |
| unpickle_pure_python             | 163 us                                                             | 189 us: 1.16x slower                                                   |
| noop                             | 19.2 ns                                                            | 22.3 ns: 1.16x slower                                                  |
| django_template                  | 30.5 ms                                                            | 35.6 ms: 1.17x slower                                                  |
| logging_simple                   | 5.02 us                                                            | 5.86 us: 1.17x slower                                                  |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.42 ms: 1.17x slower                                                  |
| chaos                            | 42.9 ms                                                            | 50.2 ms: 1.17x slower                                                  |
| raytrace                         | 201 ms                                                             | 235 ms: 1.17x slower                                                   |
| comprehensions                   | 11.4 us                                                            | 13.3 us: 1.17x slower                                                  |
| genshi_xml                       | 43.2 ms                                                            | 51.2 ms: 1.18x slower                                                  |
| pprint_safe_repr                 | 534 ms                                                             | 634 ms: 1.19x slower                                                   |
| nqueens                          | 59.8 ms                                                            | 70.9 ms: 1.19x slower                                                  |
| typing_runtime_protocols         | 115 us                                                             | 137 us: 1.19x slower                                                   |
| pprint_pformat                   | 1.10 sec                                                           | 1.31 sec: 1.20x slower                                                 |
| scimark_lu                       | 74.7 ms                                                            | 89.6 ms: 1.20x slower                                                  |
| regex_compile                    | 97.0 ms                                                            | 116 ms: 1.20x slower                                                   |
| nbody                            | 74.2 ms                                                            | 89.2 ms: 1.20x slower                                                  |
| genshi_text                      | 18.0 ms                                                            | 21.7 ms: 1.20x slower                                                  |
| async_tree_eager                 | 83.0 ms                                                            | 100 ms: 1.21x slower                                                   |
| chameleon                        | 10.3 ms                                                            | 12.4 ms: 1.21x slower                                                  |
| sqlglot_v2_parse                 | 954 us                                                             | 1.16 ms: 1.21x slower                                                  |
| hexiom                           | 4.50 ms                                                            | 5.47 ms: 1.22x slower                                                  |
| scimark_monte_carlo              | 42.3 ms                                                            | 51.7 ms: 1.22x slower                                                  |
| deepcopy_reduce                  | 2.02 us                                                            | 2.48 us: 1.23x slower                                                  |
| ascii85_small                    | 13.0 ms                                                            | 16.1 ms: 1.24x slower                                                  |
| logging_silent                   | 59.2 ns                                                            | 73.4 ns: 1.24x slower                                                  |
| python_startup_no_site           | 6.52 ms                                                            | 8.11 ms: 1.24x slower                                                  |
| ascii85_large                    | 681 ms                                                             | 852 ms: 1.25x slower                                                   |
| scimark_sor                      | 78.2 ms                                                            | 99.2 ms: 1.27x slower                                                  |
| richards                         | 34.7 ms                                                            | 44.4 ms: 1.28x slower                                                  |
| fannkuch                         | 246 ms                                                             | 316 ms: 1.28x slower                                                   |
| coverage                         | 54.5 ms                                                            | 73.4 ms: 1.35x slower                                                  |
| richards_super                   | 40.3 ms                                                            | 54.6 ms: 1.35x slower                                                  |
| mako                             | 8.69 ms                                                            | 11.9 ms: 1.37x slower                                                  |
| thread_memo_naive                | 12.4 ms                                                            | 21.3 ms: 1.72x slower                                                  |
| thread_montecarlo_naive          | 14.3 ms                                                            | 25.4 ms: 1.78x slower                                                  |
| Geometric mean                   | (ref)                                                              | 1.01x faster                                                           |

Benchmark hidden because not significant (2): urlsafe_base64_small, async_tree_eager_memoization
Ignored benchmarks (3) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json: networkx_connected_components, networkx_k_core, networkx_shortest_path

- Geometric mean (including insignificant results): 1.014x faster

# HPT report

- Reliability score: 99.71% likely to be slow
- 90% likely to have a slowdown of 1.04x
- 95% likely to have a slowdown of 1.03x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 1.47x