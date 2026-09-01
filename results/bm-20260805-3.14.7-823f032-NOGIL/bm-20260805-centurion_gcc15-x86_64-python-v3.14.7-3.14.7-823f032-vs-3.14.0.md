# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.014x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.03x slower
- Memory change: 1.46x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 11.8 ms: 1.11x slower                                            |
| docutils       | 2.02 sec                                                         | 2.09 sec: 1.04x slower                                           |
| fastapi_http   | 215 ms                                                           | 183 ms: 1.17x faster                                             |
| tornado_http   | 101 ms                                                           | 94.9 ms: 1.06x faster                                            |
| Geometric mean | (ref)                                                            | 1.02x faster                                                     |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_eager_io_tg           | 549 ms                                                           | 477 ms: 1.15x faster                                             |
| asyncio_tcp                      | 332 ms                                                           | 300 ms: 1.11x faster                                             |
| async_tree_io_tg                 | 529 ms                                                           | 484 ms: 1.09x faster                                             |
| async_tree_eager_io              | 548 ms                                                           | 518 ms: 1.06x faster                                             |
| asyncio_websockets               | 305 ms                                                           | 289 ms: 1.05x faster                                             |
| async_tree_none_tg               | 221 ms                                                           | 210 ms: 1.05x faster                                             |
| coroutines                       | 15.4 ms                                                          | 14.7 ms: 1.05x faster                                            |
| async_tree_io                    | 527 ms                                                           | 507 ms: 1.04x faster                                             |
| async_tree_eager_memoization     | 175 ms                                                           | 182 ms: 1.04x slower                                             |
| async_tree_eager_tg              | 179 ms                                                           | 188 ms: 1.05x slower                                             |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 461 ms: 1.06x slower                                             |
| async_tree_none                  | 223 ms                                                           | 236 ms: 1.06x slower                                             |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 252 ms: 1.07x slower                                             |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.39 sec: 1.08x slower                                           |
| async_generators                 | 243 ms                                                           | 264 ms: 1.09x slower                                             |
| async_tree_memoization           | 274 ms                                                           | 299 ms: 1.09x slower                                             |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 372 ms: 1.12x slower                                             |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 486 ms: 1.13x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 442 ms: 1.15x slower                                             |
| async_tree_eager                 | 78.8 ms                                                          | 93.0 ms: 1.18x slower                                            |
| Geometric mean                   | (ref)                                                            | 1.02x slower                                                     |

Benchmark hidden because not significant (1): async_tree_memoization_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 20.1 ns: 1.07x slower                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 186 ms: 1.10x slower                                             |
| decimal_pi        | 201 ms                                                           | 238 ms: 1.18x slower                                             |
| Geometric mean    | (ref)                                                            | 1.14x slower                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| pidigits       | 181 ms                                                           | 178 ms: 1.02x faster                                             |
| quadtree_nbody | 602 ms                                                           | 616 ms: 1.02x slower                                             |
| float          | 48.1 ms                                                          | 53.5 ms: 1.11x slower                                            |
| nbody          | 67.2 ms                                                          | 82.4 ms: 1.23x slower                                            |
| Geometric mean | (ref)                                                            | 1.08x slower                                                     |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                          | 14.8 ms: 1.01x faster                                            |
| regex_dna      | 141 ms                                                           | 144 ms: 1.03x slower                                             |
| regex_effbot   | 1.80 ms                                                          | 1.91 ms: 1.06x slower                                            |
| regex_compile  | 91.6 ms                                                          | 101 ms: 1.10x slower                                             |
| Geometric mean | (ref)                                                            | 1.04x slower                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base64_large         | 6.31 ms                                                          | 4.97 ms: 1.27x faster                                            |
| xml_etree_iterparse  | 76.5 ms                                                          | 65.8 ms: 1.16x faster                                            |
| base64_small         | 230 us                                                           | 210 us: 1.09x faster                                             |
| urlsafe_base64_small | 383 us                                                           | 361 us: 1.06x faster                                             |
| base16_small         | 298 us                                                           | 295 us: 1.01x faster                                             |
| base16_large         | 5.41 ms                                                          | 5.35 ms: 1.01x faster                                            |
| pickle               | 9.23 us                                                          | 9.13 us: 1.01x faster                                            |
| pickle_dict          | 21.3 us                                                          | 21.5 us: 1.01x slower                                            |
| pickle_pure_python   | 234 us                                                           | 239 us: 1.02x slower                                             |
| xml_etree_parse      | 102 ms                                                           | 106 ms: 1.03x slower                                             |
| unpickle_pure_python | 153 us                                                           | 158 us: 1.03x slower                                             |
| xml_etree_generate   | 71.1 ms                                                          | 75.1 ms: 1.06x slower                                            |
| base85_small         | 4.44 ms                                                          | 4.70 ms: 1.06x slower                                            |
| tomli_loads          | 1.41 sec                                                         | 1.51 sec: 1.08x slower                                           |
| json_dumps           | 7.37 ms                                                          | 8.00 ms: 1.09x slower                                            |
| xml_etree_process    | 50.0 ms                                                          | 54.3 ms: 1.09x slower                                            |
| unpickle             | 10.3 us                                                          | 11.3 us: 1.10x slower                                            |
| base32_large         | 276 ms                                                           | 307 ms: 1.11x slower                                             |
| base32_small         | 5.43 ms                                                          | 6.10 ms: 1.12x slower                                            |
| base85_large         | 233 ms                                                           | 264 ms: 1.13x slower                                             |
| ascii85_small        | 12.5 ms                                                          | 14.2 ms: 1.14x slower                                            |
| ascii85_large        | 651 ms                                                           | 743 ms: 1.14x slower                                             |
| pickle_list          | 3.26 us                                                          | 3.91 us: 1.20x slower                                            |
| unpickle_list        | 3.64 us                                                          | 4.54 us: 1.25x slower                                            |
| json_loads           | 17.3 us                                                          | 24.9 us: 1.44x slower                                            |
| Geometric mean       | (ref)                                                            | 1.06x slower                                                     |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 11.7 ms: 1.22x slower                                            |
| python_startup_no_site | 6.29 ms                                                          | 8.17 ms: 1.30x slower                                            |
| Geometric mean         | (ref)                                                            | 1.26x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| genshi_xml      | 38.4 ms                                                          | 41.8 ms: 1.09x slower                                            |
| django_template | 28.4 ms                                                          | 31.2 ms: 1.10x slower                                            |
| genshi_text     | 16.4 ms                                                          | 19.4 ms: 1.18x slower                                            |
| mako            | 7.66 ms                                                          | 11.9 ms: 1.55x slower                                            |
| Geometric mean  | (ref)                                                            | 1.22x slower                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_pipeline_optimized   | 26.3 ms                                                          | 7.14 ms: 3.69x faster                                            |
| thread_accumulate_optimized | 40.8 ms                                                          | 11.2 ms: 3.63x faster                                            |
| thread_counter_optimized    | 18.7 ms                                                          | 5.21 ms: 3.59x faster                                            |
| thread_mandelbrot_naive     | 217 ms                                                           | 61.6 ms: 3.53x faster                                            |
| thread_mandelbrot_optimized | 215 ms                                                           | 62.2 ms: 3.46x faster                                            |
| thread_accumulate_naive     | 41.6 ms                                                          | 13.7 ms: 3.03x faster                                            |
| thread_memo_optimized       | 17.9 ms                                                          | 6.05 ms: 2.97x faster                                            |
| thread_montecarlo_optimized | 12.6 ms                                                          | 4.46 ms: 2.82x faster                                            |
| thread_pipeline_naive       | 35.4 ms                                                          | 26.9 ms: 1.32x faster                                            |
| thread_counter_naive        | 21.4 ms                                                          | 21.0 ms: 1.02x faster                                            |
| thread_montecarlo_naive     | 14.6 ms                                                          | 25.3 ms: 1.73x slower                                            |
| thread_memo_naive           | 11.8 ms                                                          | 23.9 ms: 2.02x slower                                            |
| Geometric mean              | (ref)                                                            | 2.06x faster                                                     |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| argparse_many_optionals          | 33.3 ms                                                          | 7.63 ms: 4.36x faster                                            |
| thread_pipeline_optimized        | 26.3 ms                                                          | 7.14 ms: 3.69x faster                                            |
| thread_accumulate_optimized      | 40.8 ms                                                          | 11.2 ms: 3.63x faster                                            |
| thread_counter_optimized         | 18.7 ms                                                          | 5.21 ms: 3.59x faster                                            |
| thread_mandelbrot_naive          | 217 ms                                                           | 61.6 ms: 3.53x faster                                            |
| thread_mandelbrot_optimized      | 215 ms                                                           | 62.2 ms: 3.46x faster                                            |
| thread_accumulate_naive          | 41.6 ms                                                          | 13.7 ms: 3.03x faster                                            |
| thread_memo_optimized            | 17.9 ms                                                          | 6.05 ms: 2.97x faster                                            |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 4.46 ms: 2.82x faster                                            |
| gc_traversal                     | 3.33 ms                                                          | 1.46 ms: 2.28x faster                                            |
| create_gc_cycles                 | 1.93 ms                                                          | 1.29 ms: 1.49x faster                                            |
| thread_pipeline_naive            | 35.4 ms                                                          | 26.9 ms: 1.32x faster                                            |
| argparse_subparsers              | 665 us                                                           | 523 us: 1.27x faster                                             |
| base64_large                     | 6.31 ms                                                          | 4.97 ms: 1.27x faster                                            |
| fastapi_http                     | 215 ms                                                           | 183 ms: 1.17x faster                                             |
| xml_etree_iterparse              | 76.5 ms                                                          | 65.8 ms: 1.16x faster                                            |
| async_tree_eager_io_tg           | 549 ms                                                           | 477 ms: 1.15x faster                                             |
| asyncio_tcp                      | 332 ms                                                           | 300 ms: 1.11x faster                                             |
| base64_small                     | 230 us                                                           | 210 us: 1.09x faster                                             |
| async_tree_io_tg                 | 529 ms                                                           | 484 ms: 1.09x faster                                             |
| urlsafe_base64_small             | 383 us                                                           | 361 us: 1.06x faster                                             |
| tornado_http                     | 101 ms                                                           | 94.9 ms: 1.06x faster                                            |
| async_tree_eager_io              | 548 ms                                                           | 518 ms: 1.06x faster                                             |
| asyncio_websockets               | 305 ms                                                           | 289 ms: 1.05x faster                                             |
| async_tree_none_tg               | 221 ms                                                           | 210 ms: 1.05x faster                                             |
| coroutines                       | 15.4 ms                                                          | 14.7 ms: 1.05x faster                                            |
| async_tree_io                    | 527 ms                                                           | 507 ms: 1.04x faster                                             |
| pycparser                        | 837 ms                                                           | 812 ms: 1.03x faster                                             |
| pathlib                          | 12.5 ms                                                          | 12.2 ms: 1.03x faster                                            |
| thread_counter_naive             | 21.4 ms                                                          | 21.0 ms: 1.02x faster                                            |
| pidigits                         | 181 ms                                                           | 178 ms: 1.02x faster                                             |
| regex_v8                         | 15.0 ms                                                          | 14.8 ms: 1.01x faster                                            |
| base16_small                     | 298 us                                                           | 295 us: 1.01x faster                                             |
| base16_large                     | 5.41 ms                                                          | 5.35 ms: 1.01x faster                                            |
| pickle                           | 9.23 us                                                          | 9.13 us: 1.01x faster                                            |
| pickle_dict                      | 21.3 us                                                          | 21.5 us: 1.01x slower                                            |
| pylint                           | 215 ms                                                           | 219 ms: 1.02x slower                                             |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.16 sec: 1.02x slower                                           |
| generators                       | 20.7 ms                                                          | 21.2 ms: 1.02x slower                                            |
| pickle_pure_python               | 234 us                                                           | 239 us: 1.02x slower                                             |
| quadtree_nbody                   | 602 ms                                                           | 616 ms: 1.02x slower                                             |
| thrift                           | 1.84 ms                                                          | 1.89 ms: 1.03x slower                                            |
| regex_dna                        | 141 ms                                                           | 144 ms: 1.03x slower                                             |
| xml_etree_parse                  | 102 ms                                                           | 106 ms: 1.03x slower                                             |
| unpickle_pure_python             | 153 us                                                           | 158 us: 1.03x slower                                             |
| docutils                         | 2.02 sec                                                         | 2.09 sec: 1.04x slower                                           |
| async_tree_eager_memoization     | 175 ms                                                           | 182 ms: 1.04x slower                                             |
| mdp                              | 935 ms                                                           | 974 ms: 1.04x slower                                             |
| logging_silent                   | 59.7 ns                                                          | 62.2 ns: 1.04x slower                                            |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 40.5 ms: 1.05x slower                                            |
| async_tree_eager_tg              | 179 ms                                                           | 188 ms: 1.05x slower                                             |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 81.9 ms: 1.05x slower                                            |
| xml_etree_generate               | 71.1 ms                                                          | 75.1 ms: 1.06x slower                                            |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 461 ms: 1.06x slower                                             |
| async_tree_none                  | 223 ms                                                           | 236 ms: 1.06x slower                                             |
| base85_small                     | 4.44 ms                                                          | 4.70 ms: 1.06x slower                                            |
| sympy_sum                        | 104 ms                                                           | 110 ms: 1.06x slower                                             |
| regex_effbot                     | 1.80 ms                                                          | 1.91 ms: 1.06x slower                                            |
| sqlalchemy_imperative            | 14.3 ms                                                          | 15.2 ms: 1.06x slower                                            |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 252 ms: 1.07x slower                                             |
| noop                             | 18.7 ns                                                          | 20.1 ns: 1.07x slower                                            |
| sympy_str                        | 192 ms                                                           | 206 ms: 1.07x slower                                             |
| tomli_loads                      | 1.41 sec                                                         | 1.51 sec: 1.08x slower                                           |
| pprint_safe_repr                 | 484 ms                                                           | 521 ms: 1.08x slower                                             |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.39 sec: 1.08x slower                                           |
| sympy_expand                     | 330 ms                                                           | 356 ms: 1.08x slower                                             |
| sympy_integrate                  | 14.7 ms                                                          | 15.9 ms: 1.08x slower                                            |
| json_dumps                       | 7.37 ms                                                          | 8.00 ms: 1.09x slower                                            |
| xml_etree_process                | 50.0 ms                                                          | 54.3 ms: 1.09x slower                                            |
| genshi_xml                       | 38.4 ms                                                          | 41.8 ms: 1.09x slower                                            |
| async_generators                 | 243 ms                                                           | 264 ms: 1.09x slower                                             |
| logging_simple                   | 4.72 us                                                          | 5.14 us: 1.09x slower                                            |
| async_tree_memoization           | 274 ms                                                           | 299 ms: 1.09x slower                                             |
| chaos                            | 41.9 ms                                                          | 45.6 ms: 1.09x slower                                            |
| nqueens                          | 56.3 ms                                                          | 61.5 ms: 1.09x slower                                            |
| deepcopy                         | 195 us                                                           | 213 us: 1.09x slower                                             |
| go                               | 82.6 ms                                                          | 90.5 ms: 1.10x slower                                            |
| decimal_factorial                | 170 ms                                                           | 186 ms: 1.10x slower                                             |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.26 ms: 1.10x slower                                            |
| unpickle                         | 10.3 us                                                          | 11.3 us: 1.10x slower                                            |
| django_template                  | 28.4 ms                                                          | 31.2 ms: 1.10x slower                                            |
| hexiom                           | 4.00 ms                                                          | 4.40 ms: 1.10x slower                                            |
| pprint_pformat                   | 982 ms                                                           | 1.08 sec: 1.10x slower                                           |
| regex_compile                    | 91.6 ms                                                          | 101 ms: 1.10x slower                                             |
| xdsl_constant_fold               | 35.1 ms                                                          | 38.8 ms: 1.11x slower                                            |
| logging_format                   | 5.24 us                                                          | 5.80 us: 1.11x slower                                            |
| raytrace                         | 194 ms                                                           | 215 ms: 1.11x slower                                             |
| base32_large                     | 276 ms                                                           | 307 ms: 1.11x slower                                             |
| chameleon                        | 10.6 ms                                                          | 11.8 ms: 1.11x slower                                            |
| scimark_sor                      | 72.8 ms                                                          | 80.9 ms: 1.11x slower                                            |
| float                            | 48.1 ms                                                          | 53.5 ms: 1.11x slower                                            |
| deltablue                        | 2.24 ms                                                          | 2.49 ms: 1.11x slower                                            |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 372 ms: 1.12x slower                                             |
| pyflate                          | 300 ms                                                           | 336 ms: 1.12x slower                                             |
| deepcopy_reduce                  | 2.05 us                                                          | 2.29 us: 1.12x slower                                            |
| base32_small                     | 5.43 ms                                                          | 6.10 ms: 1.12x slower                                            |
| richards                         | 32.5 ms                                                          | 36.6 ms: 1.13x slower                                            |
| scimark_fft                      | 197 ms                                                           | 222 ms: 1.13x slower                                             |
| networkx_k_core                  | 2.07 sec                                                         | 2.33 sec: 1.13x slower                                           |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 486 ms: 1.13x slower                                             |
| spectral_norm                    | 59.6 ms                                                          | 67.6 ms: 1.13x slower                                            |
| base85_large                     | 233 ms                                                           | 264 ms: 1.13x slower                                             |
| ascii85_small                    | 12.5 ms                                                          | 14.2 ms: 1.14x slower                                            |
| sqlglot_v2_parse                 | 909 us                                                           | 1.03 ms: 1.14x slower                                            |
| ascii85_large                    | 651 ms                                                           | 743 ms: 1.14x slower                                             |
| richards_super                   | 37.2 ms                                                          | 42.7 ms: 1.15x slower                                            |
| comprehensions                   | 11.2 us                                                          | 12.8 us: 1.15x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 442 ms: 1.15x slower                                             |
| mypy2                            | 756 ms                                                           | 868 ms: 1.15x slower                                             |
| meteor_contest                   | 83.9 ms                                                          | 97.5 ms: 1.16x slower                                            |
| scimark_lu                       | 66.7 ms                                                          | 77.7 ms: 1.16x slower                                            |
| async_tree_eager                 | 78.8 ms                                                          | 93.0 ms: 1.18x slower                                            |
| genshi_text                      | 16.4 ms                                                          | 19.4 ms: 1.18x slower                                            |
| decimal_pi                       | 201 ms                                                           | 238 ms: 1.18x slower                                             |
| deepcopy_memo                    | 18.2 us                                                          | 21.6 us: 1.18x slower                                            |
| pickle_list                      | 3.26 us                                                          | 3.91 us: 1.20x slower                                            |
| typing_runtime_protocols         | 106 us                                                           | 128 us: 1.21x slower                                             |
| scimark_monte_carlo              | 37.5 ms                                                          | 45.5 ms: 1.21x slower                                            |
| crypto_pyaes                     | 51.5 ms                                                          | 62.6 ms: 1.21x slower                                            |
| python_startup                   | 9.62 ms                                                          | 11.7 ms: 1.22x slower                                            |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 3.16 ms: 1.22x slower                                            |
| nbody                            | 67.2 ms                                                          | 82.4 ms: 1.23x slower                                            |
| json                             | 3.42 ms                                                          | 4.20 ms: 1.23x slower                                            |
| networkx_connected_components    | 435 ms                                                           | 535 ms: 1.23x slower                                             |
| telco                            | 5.26 ms                                                          | 6.49 ms: 1.23x slower                                            |
| fannkuch                         | 234 ms                                                           | 291 ms: 1.24x slower                                             |
| unpickle_list                    | 3.64 us                                                          | 4.54 us: 1.25x slower                                            |
| networkx_shortest_path           | 445 ms                                                           | 555 ms: 1.25x slower                                             |
| python_startup_no_site           | 6.29 ms                                                          | 8.17 ms: 1.30x slower                                            |
| unpack_sequence                  | 24.1 ns                                                          | 31.4 ns: 1.31x slower                                            |
| coverage                         | 55.4 ms                                                          | 73.6 ms: 1.33x slower                                            |
| json_loads                       | 17.3 us                                                          | 24.9 us: 1.44x slower                                            |
| mako                             | 7.66 ms                                                          | 11.9 ms: 1.55x slower                                            |
| thread_montecarlo_naive          | 14.6 ms                                                          | 25.3 ms: 1.73x slower                                            |
| thread_memo_naive                | 11.8 ms                                                          | 23.9 ms: 2.02x slower                                            |
| Geometric mean                   | (ref)                                                            | 1.01x faster                                                     |

Benchmark hidden because not significant (2): async_tree_memoization_tg, html5lib

- Geometric mean (including insignificant results): 1.014x faster

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.05x
- 95% likely to have a slowdown of 1.04x
- 99% likely to have a slowdown of 1.03x

# Memory
- memory change: 1.46x