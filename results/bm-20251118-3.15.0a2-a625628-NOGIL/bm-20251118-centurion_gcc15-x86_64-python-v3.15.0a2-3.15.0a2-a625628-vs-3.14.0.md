# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.039x faster
- HPT reliability: 94.59%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.49x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 11.7 ms: 1.10x slower                                                |
| docutils       | 2.02 sec                                                         | 2.05 sec: 1.02x slower                                               |
| fastapi_http   | 215 ms                                                           | 181 ms: 1.19x faster                                                 |
| html5lib       | 45.5 ms                                                          | 44.9 ms: 1.01x faster                                                |
| tornado_http   | 101 ms                                                           | 91.8 ms: 1.10x faster                                                |
| Geometric mean | (ref)                                                            | 1.03x faster                                                         |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 549 ms                                                           | 384 ms: 1.43x faster                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 392 ms: 1.35x faster                                                 |
| async_tree_eager_io              | 548 ms                                                           | 417 ms: 1.31x faster                                                 |
| async_tree_none_tg               | 221 ms                                                           | 170 ms: 1.29x faster                                                 |
| async_tree_io                    | 527 ms                                                           | 425 ms: 1.24x faster                                                 |
| async_tree_memoization_tg        | 275 ms                                                           | 226 ms: 1.22x faster                                                 |
| async_tree_eager_tg              | 179 ms                                                           | 149 ms: 1.20x faster                                                 |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 203 ms: 1.16x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 379 ms: 1.15x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 198 ms: 1.13x faster                                                 |
| asyncio_tcp                      | 332 ms                                                           | 299 ms: 1.11x faster                                                 |
| async_tree_memoization           | 274 ms                                                           | 249 ms: 1.10x faster                                                 |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 357 ms: 1.08x faster                                                 |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 401 ms: 1.07x faster                                                 |
| async_tree_eager_memoization     | 175 ms                                                           | 166 ms: 1.05x faster                                                 |
| asyncio_websockets               | 305 ms                                                           | 291 ms: 1.05x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 331 ms: 1.01x faster                                                 |
| coroutines                       | 15.4 ms                                                          | 15.2 ms: 1.01x faster                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.37 sec: 1.07x slower                                               |
| async_generators                 | 243 ms                                                           | 264 ms: 1.08x slower                                                 |
| async_tree_eager                 | 78.8 ms                                                          | 88.4 ms: 1.12x slower                                                |
| Geometric mean                   | (ref)                                                            | 1.12x faster                                                         |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 21.4 ns: 1.14x slower                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 184 ms: 1.09x slower                                                 |
| decimal_pi        | 201 ms                                                           | 231 ms: 1.15x slower                                                 |
| Geometric mean    | (ref)                                                            | 1.12x slower                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| pidigits       | 181 ms                                                           | 179 ms: 1.01x faster                                                 |
| quadtree_nbody | 602 ms                                                           | 615 ms: 1.02x slower                                                 |
| float          | 48.1 ms                                                          | 49.3 ms: 1.03x slower                                                |
| nbody          | 67.2 ms                                                          | 83.1 ms: 1.24x slower                                                |
| Geometric mean | (ref)                                                            | 1.06x slower                                                         |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                          | 14.6 ms: 1.03x faster                                                |
| regex_effbot   | 1.80 ms                                                          | 1.79 ms: 1.01x faster                                                |
| regex_dna      | 141 ms                                                           | 142 ms: 1.01x slower                                                 |
| regex_compile  | 91.6 ms                                                          | 100 ms: 1.09x slower                                                 |
| Geometric mean | (ref)                                                            | 1.02x slower                                                         |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| xml_etree_iterparse  | 76.5 ms                                                          | 63.8 ms: 1.20x faster                                                |
| base64_large         | 6.31 ms                                                          | 5.63 ms: 1.12x faster                                                |
| base16_large         | 5.41 ms                                                          | 5.09 ms: 1.06x faster                                                |
| base64_small         | 230 us                                                           | 217 us: 1.06x faster                                                 |
| xml_etree_parse      | 102 ms                                                           | 98.9 ms: 1.03x faster                                                |
| urlsafe_base64_small | 383 us                                                           | 371 us: 1.03x faster                                                 |
| json_dumps           | 7.37 ms                                                          | 7.23 ms: 1.02x faster                                                |
| pickle               | 9.23 us                                                          | 9.11 us: 1.01x faster                                                |
| pickle_list          | 3.26 us                                                          | 3.24 us: 1.01x faster                                                |
| base16_small         | 298 us                                                           | 299 us: 1.00x slower                                                 |
| tomli_loads          | 1.41 sec                                                         | 1.44 sec: 1.02x slower                                               |
| xml_etree_generate   | 71.1 ms                                                          | 73.8 ms: 1.04x slower                                                |
| unpickle_pure_python | 153 us                                                           | 160 us: 1.05x slower                                                 |
| xml_etree_process    | 50.0 ms                                                          | 52.9 ms: 1.06x slower                                                |
| unpickle             | 10.3 us                                                          | 11.1 us: 1.08x slower                                                |
| base85_small         | 4.44 ms                                                          | 4.95 ms: 1.11x slower                                                |
| base32_large         | 276 ms                                                           | 309 ms: 1.12x slower                                                 |
| json_loads           | 17.3 us                                                          | 19.5 us: 1.12x slower                                                |
| base32_small         | 5.43 ms                                                          | 6.13 ms: 1.13x slower                                                |
| pickle_pure_python   | 234 us                                                           | 265 us: 1.13x slower                                                 |
| ascii85_large        | 651 ms                                                           | 739 ms: 1.13x slower                                                 |
| ascii85_small        | 12.5 ms                                                          | 14.2 ms: 1.14x slower                                                |
| base85_large         | 233 ms                                                           | 266 ms: 1.14x slower                                                 |
| unpickle_list        | 3.64 us                                                          | 4.46 us: 1.23x slower                                                |
| Geometric mean       | (ref)                                                            | 1.04x slower                                                         |

Benchmark hidden because not significant (1): pickle_dict

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 11.5 ms: 1.20x slower                                                |
| python_startup_no_site | 6.29 ms                                                          | 8.04 ms: 1.28x slower                                                |
| Geometric mean         | (ref)                                                            | 1.24x slower                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| django_template | 28.4 ms                                                          | 29.9 ms: 1.05x slower                                                |
| genshi_xml      | 38.4 ms                                                          | 41.5 ms: 1.08x slower                                                |
| genshi_text     | 16.4 ms                                                          | 18.9 ms: 1.15x slower                                                |
| mako            | 7.66 ms                                                          | 11.0 ms: 1.44x slower                                                |
| Geometric mean  | (ref)                                                            | 1.17x slower                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_pipeline_optimized   | 26.3 ms                                                          | 7.32 ms: 3.60x faster                                                |
| thread_mandelbrot_optimized | 215 ms                                                           | 60.5 ms: 3.56x faster                                                |
| thread_mandelbrot_naive     | 217 ms                                                           | 61.0 ms: 3.56x faster                                                |
| thread_accumulate_optimized | 40.8 ms                                                          | 11.7 ms: 3.49x faster                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 5.73 ms: 3.26x faster                                                |
| thread_accumulate_naive     | 41.6 ms                                                          | 13.8 ms: 3.02x faster                                                |
| thread_memo_optimized       | 17.9 ms                                                          | 6.11 ms: 2.94x faster                                                |
| thread_montecarlo_optimized | 12.6 ms                                                          | 4.75 ms: 2.65x faster                                                |
| thread_pipeline_naive       | 35.4 ms                                                          | 24.5 ms: 1.44x faster                                                |
| thread_counter_naive        | 21.4 ms                                                          | 20.8 ms: 1.03x faster                                                |
| thread_montecarlo_naive     | 14.6 ms                                                          | 24.9 ms: 1.71x slower                                                |
| thread_memo_naive           | 11.8 ms                                                          | 21.1 ms: 1.78x slower                                                |
| Geometric mean              | (ref)                                                            | 2.06x faster                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_pipeline_optimized        | 26.3 ms                                                          | 7.32 ms: 3.60x faster                                                |
| thread_mandelbrot_optimized      | 215 ms                                                           | 60.5 ms: 3.56x faster                                                |
| thread_mandelbrot_naive          | 217 ms                                                           | 61.0 ms: 3.56x faster                                                |
| thread_accumulate_optimized      | 40.8 ms                                                          | 11.7 ms: 3.49x faster                                                |
| thread_counter_optimized         | 18.7 ms                                                          | 5.73 ms: 3.26x faster                                                |
| thread_accumulate_naive          | 41.6 ms                                                          | 13.8 ms: 3.02x faster                                                |
| thread_memo_optimized            | 17.9 ms                                                          | 6.11 ms: 2.94x faster                                                |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 4.75 ms: 2.65x faster                                                |
| gc_traversal                     | 3.33 ms                                                          | 1.48 ms: 2.25x faster                                                |
| create_gc_cycles                 | 1.93 ms                                                          | 1.31 ms: 1.47x faster                                                |
| thread_pipeline_naive            | 35.4 ms                                                          | 24.5 ms: 1.44x faster                                                |
| async_tree_eager_io_tg           | 549 ms                                                           | 384 ms: 1.43x faster                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 392 ms: 1.35x faster                                                 |
| async_tree_eager_io              | 548 ms                                                           | 417 ms: 1.31x faster                                                 |
| async_tree_none_tg               | 221 ms                                                           | 170 ms: 1.29x faster                                                 |
| async_tree_io                    | 527 ms                                                           | 425 ms: 1.24x faster                                                 |
| async_tree_memoization_tg        | 275 ms                                                           | 226 ms: 1.22x faster                                                 |
| async_tree_eager_tg              | 179 ms                                                           | 149 ms: 1.20x faster                                                 |
| xml_etree_iterparse              | 76.5 ms                                                          | 63.8 ms: 1.20x faster                                                |
| fastapi_http                     | 215 ms                                                           | 181 ms: 1.19x faster                                                 |
| pathlib                          | 12.5 ms                                                          | 10.8 ms: 1.16x faster                                                |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 203 ms: 1.16x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 379 ms: 1.15x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 198 ms: 1.13x faster                                                 |
| base64_large                     | 6.31 ms                                                          | 5.63 ms: 1.12x faster                                                |
| asyncio_tcp                      | 332 ms                                                           | 299 ms: 1.11x faster                                                 |
| async_tree_memoization           | 274 ms                                                           | 249 ms: 1.10x faster                                                 |
| tornado_http                     | 101 ms                                                           | 91.8 ms: 1.10x faster                                                |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 357 ms: 1.08x faster                                                 |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 401 ms: 1.07x faster                                                 |
| base16_large                     | 5.41 ms                                                          | 5.09 ms: 1.06x faster                                                |
| base64_small                     | 230 us                                                           | 217 us: 1.06x faster                                                 |
| async_tree_eager_memoization     | 175 ms                                                           | 166 ms: 1.05x faster                                                 |
| pycparser                        | 837 ms                                                           | 796 ms: 1.05x faster                                                 |
| asyncio_websockets               | 305 ms                                                           | 291 ms: 1.05x faster                                                 |
| xml_etree_parse                  | 102 ms                                                           | 98.9 ms: 1.03x faster                                                |
| urlsafe_base64_small             | 383 us                                                           | 371 us: 1.03x faster                                                 |
| thread_counter_naive             | 21.4 ms                                                          | 20.8 ms: 1.03x faster                                                |
| regex_v8                         | 15.0 ms                                                          | 14.6 ms: 1.03x faster                                                |
| json_dumps                       | 7.37 ms                                                          | 7.23 ms: 1.02x faster                                                |
| pidigits                         | 181 ms                                                           | 179 ms: 1.01x faster                                                 |
| pickle                           | 9.23 us                                                          | 9.11 us: 1.01x faster                                                |
| html5lib                         | 45.5 ms                                                          | 44.9 ms: 1.01x faster                                                |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 331 ms: 1.01x faster                                                 |
| coroutines                       | 15.4 ms                                                          | 15.2 ms: 1.01x faster                                                |
| regex_effbot                     | 1.80 ms                                                          | 1.79 ms: 1.01x faster                                                |
| pickle_list                      | 3.26 us                                                          | 3.24 us: 1.01x faster                                                |
| base16_small                     | 298 us                                                           | 299 us: 1.00x slower                                                 |
| regex_dna                        | 141 ms                                                           | 142 ms: 1.01x slower                                                 |
| mypy2                            | 756 ms                                                           | 766 ms: 1.01x slower                                                 |
| docutils                         | 2.02 sec                                                         | 2.05 sec: 1.02x slower                                               |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.16 sec: 1.02x slower                                               |
| quadtree_nbody                   | 602 ms                                                           | 615 ms: 1.02x slower                                                 |
| tomli_loads                      | 1.41 sec                                                         | 1.44 sec: 1.02x slower                                               |
| pylint                           | 215 ms                                                           | 220 ms: 1.02x slower                                                 |
| mdp                              | 935 ms                                                           | 959 ms: 1.03x slower                                                 |
| float                            | 48.1 ms                                                          | 49.3 ms: 1.03x slower                                                |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 80.4 ms: 1.03x slower                                                |
| deepcopy                         | 195 us                                                           | 202 us: 1.03x slower                                                 |
| xml_etree_generate               | 71.1 ms                                                          | 73.8 ms: 1.04x slower                                                |
| thrift                           | 1.84 ms                                                          | 1.91 ms: 1.04x slower                                                |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 40.3 ms: 1.04x slower                                                |
| comprehensions                   | 11.2 us                                                          | 11.7 us: 1.04x slower                                                |
| generators                       | 20.7 ms                                                          | 21.7 ms: 1.05x slower                                                |
| telco                            | 5.26 ms                                                          | 5.51 ms: 1.05x slower                                                |
| unpickle_pure_python             | 153 us                                                           | 160 us: 1.05x slower                                                 |
| logging_simple                   | 4.72 us                                                          | 4.97 us: 1.05x slower                                                |
| sympy_sum                        | 104 ms                                                           | 109 ms: 1.05x slower                                                 |
| django_template                  | 28.4 ms                                                          | 29.9 ms: 1.05x slower                                                |
| argparse_subparsers              | 665 us                                                           | 701 us: 1.05x slower                                                 |
| xml_etree_process                | 50.0 ms                                                          | 52.9 ms: 1.06x slower                                                |
| json                             | 3.42 ms                                                          | 3.63 ms: 1.06x slower                                                |
| logging_silent                   | 59.7 ns                                                          | 63.3 ns: 1.06x slower                                                |
| sympy_expand                     | 330 ms                                                           | 351 ms: 1.06x slower                                                 |
| logging_format                   | 5.24 us                                                          | 5.58 us: 1.06x slower                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.37 sec: 1.07x slower                                               |
| sympy_str                        | 192 ms                                                           | 205 ms: 1.07x slower                                                 |
| sympy_integrate                  | 14.7 ms                                                          | 15.8 ms: 1.07x slower                                                |
| pprint_safe_repr                 | 484 ms                                                           | 520 ms: 1.08x slower                                                 |
| hexiom                           | 4.00 ms                                                          | 4.31 ms: 1.08x slower                                                |
| pyflate                          | 300 ms                                                           | 323 ms: 1.08x slower                                                 |
| unpickle                         | 10.3 us                                                          | 11.1 us: 1.08x slower                                                |
| genshi_xml                       | 38.4 ms                                                          | 41.5 ms: 1.08x slower                                                |
| scimark_fft                      | 197 ms                                                           | 213 ms: 1.08x slower                                                 |
| async_generators                 | 243 ms                                                           | 264 ms: 1.08x slower                                                 |
| decimal_factorial                | 170 ms                                                           | 184 ms: 1.09x slower                                                 |
| sqlalchemy_imperative            | 14.3 ms                                                          | 15.5 ms: 1.09x slower                                                |
| go                               | 82.6 ms                                                          | 90.0 ms: 1.09x slower                                                |
| argparse_many_optionals          | 33.3 ms                                                          | 36.4 ms: 1.09x slower                                                |
| xdsl_constant_fold               | 35.1 ms                                                          | 38.5 ms: 1.09x slower                                                |
| regex_compile                    | 91.6 ms                                                          | 100 ms: 1.09x slower                                                 |
| chaos                            | 41.9 ms                                                          | 45.9 ms: 1.10x slower                                                |
| chameleon                        | 10.6 ms                                                          | 11.7 ms: 1.10x slower                                                |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.26 ms: 1.10x slower                                                |
| nqueens                          | 56.3 ms                                                          | 61.8 ms: 1.10x slower                                                |
| deepcopy_memo                    | 18.2 us                                                          | 20.0 us: 1.10x slower                                                |
| deepcopy_reduce                  | 2.05 us                                                          | 2.25 us: 1.10x slower                                                |
| pprint_pformat                   | 982 ms                                                           | 1.09 sec: 1.11x slower                                               |
| deltablue                        | 2.24 ms                                                          | 2.49 ms: 1.11x slower                                                |
| scimark_sor                      | 72.8 ms                                                          | 81.1 ms: 1.11x slower                                                |
| base85_small                     | 4.44 ms                                                          | 4.95 ms: 1.11x slower                                                |
| base32_large                     | 276 ms                                                           | 309 ms: 1.12x slower                                                 |
| async_tree_eager                 | 78.8 ms                                                          | 88.4 ms: 1.12x slower                                                |
| json_loads                       | 17.3 us                                                          | 19.5 us: 1.12x slower                                                |
| sqlglot_v2_parse                 | 909 us                                                           | 1.03 ms: 1.13x slower                                                |
| base32_small                     | 5.43 ms                                                          | 6.13 ms: 1.13x slower                                                |
| pickle_pure_python               | 234 us                                                           | 265 us: 1.13x slower                                                 |
| meteor_contest                   | 83.9 ms                                                          | 95.1 ms: 1.13x slower                                                |
| ascii85_large                    | 651 ms                                                           | 739 ms: 1.13x slower                                                 |
| ascii85_small                    | 12.5 ms                                                          | 14.2 ms: 1.14x slower                                                |
| scimark_lu                       | 66.7 ms                                                          | 76.0 ms: 1.14x slower                                                |
| noop                             | 18.7 ns                                                          | 21.4 ns: 1.14x slower                                                |
| base85_large                     | 233 ms                                                           | 266 ms: 1.14x slower                                                 |
| richards                         | 32.5 ms                                                          | 37.4 ms: 1.15x slower                                                |
| decimal_pi                       | 201 ms                                                           | 231 ms: 1.15x slower                                                 |
| genshi_text                      | 16.4 ms                                                          | 18.9 ms: 1.15x slower                                                |
| raytrace                         | 194 ms                                                           | 224 ms: 1.15x slower                                                 |
| richards_super                   | 37.2 ms                                                          | 43.8 ms: 1.18x slower                                                |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 3.08 ms: 1.19x slower                                                |
| spectral_norm                    | 59.6 ms                                                          | 71.2 ms: 1.19x slower                                                |
| typing_runtime_protocols         | 106 us                                                           | 126 us: 1.19x slower                                                 |
| python_startup                   | 9.62 ms                                                          | 11.5 ms: 1.20x slower                                                |
| unpickle_list                    | 3.64 us                                                          | 4.46 us: 1.23x slower                                                |
| crypto_pyaes                     | 51.5 ms                                                          | 63.2 ms: 1.23x slower                                                |
| scimark_monte_carlo              | 37.5 ms                                                          | 46.3 ms: 1.24x slower                                                |
| nbody                            | 67.2 ms                                                          | 83.1 ms: 1.24x slower                                                |
| fannkuch                         | 234 ms                                                           | 290 ms: 1.24x slower                                                 |
| python_startup_no_site           | 6.29 ms                                                          | 8.04 ms: 1.28x slower                                                |
| unpack_sequence                  | 24.1 ns                                                          | 31.8 ns: 1.32x slower                                                |
| coverage                         | 55.4 ms                                                          | 75.1 ms: 1.36x slower                                                |
| mako                             | 7.66 ms                                                          | 11.0 ms: 1.44x slower                                                |
| thread_montecarlo_naive          | 14.6 ms                                                          | 24.9 ms: 1.71x slower                                                |
| thread_memo_naive                | 11.8 ms                                                          | 21.1 ms: 1.78x slower                                                |
| Geometric mean                   | (ref)                                                            | 1.04x faster                                                         |

Benchmark hidden because not significant (1): pickle_dict
Ignored benchmarks (3) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json: networkx_connected_components, networkx_k_core, networkx_shortest_path

- Geometric mean (including insignificant results): 1.039x faster

# HPT report

- Reliability score: 94.59% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.49x