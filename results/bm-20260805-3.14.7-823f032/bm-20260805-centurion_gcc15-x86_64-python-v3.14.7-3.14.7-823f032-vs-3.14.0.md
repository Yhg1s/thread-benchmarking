# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.004x slower
- HPT reliability: 99.96%
- HPT 99th percentile: 1.00x slower
- Memory change: 0.99x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 10.8 ms: 1.02x slower                                            |
| docutils       | 2.02 sec                                                         | 1.95 sec: 1.04x faster                                           |
| fastapi_http   | 215 ms                                                           | 211 ms: 1.02x faster                                             |
| Geometric mean | (ref)                                                            | 1.00x faster                                                     |

Benchmark hidden because not significant (2): html5lib, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| asyncio_tcp                      | 332 ms                                                           | 307 ms: 1.08x faster                                             |
| coroutines                       | 15.4 ms                                                          | 14.9 ms: 1.03x faster                                            |
| asyncio_websockets               | 305 ms                                                           | 299 ms: 1.02x faster                                             |
| async_generators                 | 243 ms                                                           | 247 ms: 1.02x slower                                             |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 345 ms: 1.03x slower                                             |
| async_tree_eager_memoization     | 175 ms                                                           | 182 ms: 1.04x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 428 ms: 1.11x slower                                             |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 479 ms: 1.12x slower                                             |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 496 ms: 1.14x slower                                             |
| async_tree_none                  | 223 ms                                                           | 255 ms: 1.14x slower                                             |
| async_tree_eager_tg              | 179 ms                                                           | 210 ms: 1.17x slower                                             |
| async_tree_eager_io              | 548 ms                                                           | 649 ms: 1.18x slower                                             |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 283 ms: 1.20x slower                                             |
| async_tree_memoization_tg        | 275 ms                                                           | 331 ms: 1.21x slower                                             |
| async_tree_none_tg               | 221 ms                                                           | 269 ms: 1.22x slower                                             |
| async_tree_memoization           | 274 ms                                                           | 335 ms: 1.22x slower                                             |
| async_tree_eager_io_tg           | 549 ms                                                           | 679 ms: 1.24x slower                                             |
| async_tree_io                    | 527 ms                                                           | 654 ms: 1.24x slower                                             |
| async_tree_io_tg                 | 529 ms                                                           | 694 ms: 1.31x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.11x slower                                                     |

Benchmark hidden because not significant (2): asyncio_tcp_ssl, async_tree_eager

Benchmarks with tag 'baseline':
===============================

Benchmark hidden because not significant (1): noop

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 170 ms: 1.00x slower                                             |
| decimal_pi        | 201 ms                                                           | 204 ms: 1.01x slower                                             |
| Geometric mean    | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| quadtree_nbody | 602 ms                                                           | 591 ms: 1.02x faster                                             |
| nbody          | 67.2 ms                                                          | 69.1 ms: 1.03x slower                                            |
| float          | 48.1 ms                                                          | 49.5 ms: 1.03x slower                                            |
| Geometric mean | (ref)                                                            | 1.01x slower                                                     |

Benchmark hidden because not significant (1): pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_effbot   | 1.80 ms                                                          | 1.77 ms: 1.01x faster                                            |
| regex_dna      | 141 ms                                                           | 139 ms: 1.01x faster                                             |
| regex_compile  | 91.6 ms                                                          | 92.0 ms: 1.00x slower                                            |
| regex_v8       | 15.0 ms                                                          | 15.7 ms: 1.04x slower                                            |
| Geometric mean | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base64_large         | 6.31 ms                                                          | 5.01 ms: 1.26x faster                                            |
| base64_small         | 230 us                                                           | 211 us: 1.09x faster                                             |
| urlsafe_base64_small | 383 us                                                           | 359 us: 1.07x faster                                             |
| pickle_pure_python   | 234 us                                                           | 228 us: 1.03x faster                                             |
| xml_etree_iterparse  | 76.5 ms                                                          | 74.5 ms: 1.03x faster                                            |
| base16_large         | 5.41 ms                                                          | 5.35 ms: 1.01x faster                                            |
| unpickle_list        | 3.64 us                                                          | 3.60 us: 1.01x faster                                            |
| unpickle_pure_python | 153 us                                                           | 152 us: 1.01x faster                                             |
| pickle_dict          | 21.3 us                                                          | 21.3 us: 1.00x slower                                            |
| base32_small         | 5.43 ms                                                          | 5.46 ms: 1.01x slower                                            |
| base85_large         | 233 ms                                                           | 235 ms: 1.01x slower                                             |
| ascii85_large        | 651 ms                                                           | 657 ms: 1.01x slower                                             |
| unpickle             | 10.3 us                                                          | 10.4 us: 1.01x slower                                            |
| xml_etree_generate   | 71.1 ms                                                          | 71.8 ms: 1.01x slower                                            |
| xml_etree_process    | 50.0 ms                                                          | 50.6 ms: 1.01x slower                                            |
| tomli_loads          | 1.41 sec                                                         | 1.43 sec: 1.01x slower                                           |
| base16_small         | 298 us                                                           | 303 us: 1.02x slower                                             |
| ascii85_small        | 12.5 ms                                                          | 12.7 ms: 1.02x slower                                            |
| json_dumps           | 7.37 ms                                                          | 7.59 ms: 1.03x slower                                            |
| pickle               | 9.23 us                                                          | 9.59 us: 1.04x slower                                            |
| xml_etree_parse      | 102 ms                                                           | 109 ms: 1.07x slower                                             |
| json_loads           | 17.3 us                                                          | 19.1 us: 1.10x slower                                            |
| pickle_list          | 3.26 us                                                          | 3.76 us: 1.15x slower                                            |
| Geometric mean       | (ref)                                                            | 1.00x slower                                                     |

Benchmark hidden because not significant (2): base85_small, base32_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup_no_site | 6.29 ms                                                          | 6.31 ms: 1.00x slower                                            |
| python_startup         | 9.62 ms                                                          | 9.71 ms: 1.01x slower                                            |
| Geometric mean         | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| django_template | 28.4 ms                                                          | 28.0 ms: 1.01x faster                                            |
| genshi_xml      | 38.4 ms                                                          | 39.3 ms: 1.02x slower                                            |
| mako            | 7.66 ms                                                          | 8.28 ms: 1.08x slower                                            |
| Geometric mean  | (ref)                                                            | 1.02x slower                                                     |

Benchmark hidden because not significant (1): genshi_text

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_memo_naive           | 11.8 ms                                                          | 11.7 ms: 1.01x faster                                            |
| thread_counter_naive        | 21.4 ms                                                          | 21.2 ms: 1.01x faster                                            |
| thread_counter_optimized    | 18.7 ms                                                          | 18.5 ms: 1.01x faster                                            |
| thread_pipeline_naive       | 35.4 ms                                                          | 35.1 ms: 1.01x faster                                            |
| thread_montecarlo_naive     | 14.6 ms                                                          | 14.7 ms: 1.01x slower                                            |
| thread_pipeline_optimized   | 26.3 ms                                                          | 26.7 ms: 1.01x slower                                            |
| thread_memo_optimized       | 17.9 ms                                                          | 18.2 ms: 1.02x slower                                            |
| thread_accumulate_naive     | 41.6 ms                                                          | 42.3 ms: 1.02x slower                                            |
| thread_accumulate_optimized | 40.8 ms                                                          | 41.5 ms: 1.02x slower                                            |
| thread_montecarlo_optimized | 12.6 ms                                                          | 12.8 ms: 1.02x slower                                            |
| thread_mandelbrot_naive     | 217 ms                                                           | 225 ms: 1.04x slower                                             |
| thread_mandelbrot_optimized | 215 ms                                                           | 225 ms: 1.04x slower                                             |
| Geometric mean              | (ref)                                                            | 1.01x slower                                                     |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| argparse_many_optionals          | 33.3 ms                                                          | 7.41 ms: 4.49x faster                                            |
| argparse_subparsers              | 665 us                                                           | 489 us: 1.36x faster                                             |
| base64_large                     | 6.31 ms                                                          | 5.01 ms: 1.26x faster                                            |
| base64_small                     | 230 us                                                           | 211 us: 1.09x faster                                             |
| asyncio_tcp                      | 332 ms                                                           | 307 ms: 1.08x faster                                             |
| gc_traversal                     | 3.33 ms                                                          | 3.11 ms: 1.07x faster                                            |
| urlsafe_base64_small             | 383 us                                                           | 359 us: 1.07x faster                                             |
| create_gc_cycles                 | 1.93 ms                                                          | 1.83 ms: 1.06x faster                                            |
| coverage                         | 55.4 ms                                                          | 52.8 ms: 1.05x faster                                            |
| mypy2                            | 756 ms                                                           | 725 ms: 1.04x faster                                             |
| docutils                         | 2.02 sec                                                         | 1.95 sec: 1.04x faster                                           |
| deepcopy_reduce                  | 2.05 us                                                          | 1.98 us: 1.04x faster                                            |
| logging_simple                   | 4.72 us                                                          | 4.57 us: 1.03x faster                                            |
| coroutines                       | 15.4 ms                                                          | 14.9 ms: 1.03x faster                                            |
| richards                         | 32.5 ms                                                          | 31.6 ms: 1.03x faster                                            |
| pickle_pure_python               | 234 us                                                           | 228 us: 1.03x faster                                             |
| xml_etree_iterparse              | 76.5 ms                                                          | 74.5 ms: 1.03x faster                                            |
| sqlglot_v2_parse                 | 909 us                                                           | 887 us: 1.02x faster                                             |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.13 ms: 1.02x faster                                            |
| quadtree_nbody                   | 602 ms                                                           | 591 ms: 1.02x faster                                             |
| fastapi_http                     | 215 ms                                                           | 211 ms: 1.02x faster                                             |
| asyncio_websockets               | 305 ms                                                           | 299 ms: 1.02x faster                                             |
| deepcopy                         | 195 us                                                           | 192 us: 1.02x faster                                             |
| deltablue                        | 2.24 ms                                                          | 2.21 ms: 1.02x faster                                            |
| regex_effbot                     | 1.80 ms                                                          | 1.77 ms: 1.01x faster                                            |
| scimark_sor                      | 72.8 ms                                                          | 71.8 ms: 1.01x faster                                            |
| django_template                  | 28.4 ms                                                          | 28.0 ms: 1.01x faster                                            |
| thread_memo_naive                | 11.8 ms                                                          | 11.7 ms: 1.01x faster                                            |
| base16_large                     | 5.41 ms                                                          | 5.35 ms: 1.01x faster                                            |
| raytrace                         | 194 ms                                                           | 192 ms: 1.01x faster                                             |
| unpickle_list                    | 3.64 us                                                          | 3.60 us: 1.01x faster                                            |
| thread_counter_naive             | 21.4 ms                                                          | 21.2 ms: 1.01x faster                                            |
| regex_dna                        | 141 ms                                                           | 139 ms: 1.01x faster                                             |
| richards_super                   | 37.2 ms                                                          | 36.8 ms: 1.01x faster                                            |
| pathlib                          | 12.5 ms                                                          | 12.4 ms: 1.01x faster                                            |
| thread_counter_optimized         | 18.7 ms                                                          | 18.5 ms: 1.01x faster                                            |
| unpickle_pure_python             | 153 us                                                           | 152 us: 1.01x faster                                             |
| thread_pipeline_naive            | 35.4 ms                                                          | 35.1 ms: 1.01x faster                                            |
| logging_format                   | 5.24 us                                                          | 5.20 us: 1.01x faster                                            |
| logging_silent                   | 59.7 ns                                                          | 59.2 ns: 1.01x faster                                            |
| networkx_shortest_path           | 445 ms                                                           | 442 ms: 1.01x faster                                             |
| pyflate                          | 300 ms                                                           | 298 ms: 1.01x faster                                             |
| comprehensions                   | 11.2 us                                                          | 11.1 us: 1.01x faster                                            |
| pprint_safe_repr                 | 484 ms                                                           | 481 ms: 1.01x faster                                             |
| pickle_dict                      | 21.3 us                                                          | 21.3 us: 1.00x slower                                            |
| decimal_factorial                | 170 ms                                                           | 170 ms: 1.00x slower                                             |
| hexiom                           | 4.00 ms                                                          | 4.02 ms: 1.00x slower                                            |
| python_startup_no_site           | 6.29 ms                                                          | 6.31 ms: 1.00x slower                                            |
| regex_compile                    | 91.6 ms                                                          | 92.0 ms: 1.00x slower                                            |
| base32_small                     | 5.43 ms                                                          | 5.46 ms: 1.01x slower                                            |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 39.0 ms: 1.01x slower                                            |
| thread_montecarlo_naive          | 14.6 ms                                                          | 14.7 ms: 1.01x slower                                            |
| crypto_pyaes                     | 51.5 ms                                                          | 51.9 ms: 1.01x slower                                            |
| sympy_expand                     | 330 ms                                                           | 333 ms: 1.01x slower                                             |
| base85_large                     | 233 ms                                                           | 235 ms: 1.01x slower                                             |
| ascii85_large                    | 651 ms                                                           | 657 ms: 1.01x slower                                             |
| unpickle                         | 10.3 us                                                          | 10.4 us: 1.01x slower                                            |
| typing_runtime_protocols         | 106 us                                                           | 107 us: 1.01x slower                                             |
| scimark_monte_carlo              | 37.5 ms                                                          | 37.8 ms: 1.01x slower                                            |
| python_startup                   | 9.62 ms                                                          | 9.71 ms: 1.01x slower                                            |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                             |
| xml_etree_generate               | 71.1 ms                                                          | 71.8 ms: 1.01x slower                                            |
| mdp                              | 935 ms                                                           | 945 ms: 1.01x slower                                             |
| decimal_pi                       | 201 ms                                                           | 204 ms: 1.01x slower                                             |
| xml_etree_process                | 50.0 ms                                                          | 50.6 ms: 1.01x slower                                            |
| pprint_pformat                   | 982 ms                                                           | 996 ms: 1.01x slower                                             |
| thread_pipeline_optimized        | 26.3 ms                                                          | 26.7 ms: 1.01x slower                                            |
| tomli_loads                      | 1.41 sec                                                         | 1.43 sec: 1.01x slower                                           |
| base16_small                     | 298 us                                                           | 303 us: 1.02x slower                                             |
| ascii85_small                    | 12.5 ms                                                          | 12.7 ms: 1.02x slower                                            |
| thread_memo_optimized            | 17.9 ms                                                          | 18.2 ms: 1.02x slower                                            |
| thread_accumulate_naive          | 41.6 ms                                                          | 42.3 ms: 1.02x slower                                            |
| thread_accumulate_optimized      | 40.8 ms                                                          | 41.5 ms: 1.02x slower                                            |
| async_generators                 | 243 ms                                                           | 247 ms: 1.02x slower                                             |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 12.8 ms: 1.02x slower                                            |
| spectral_norm                    | 59.6 ms                                                          | 60.6 ms: 1.02x slower                                            |
| telco                            | 5.26 ms                                                          | 5.37 ms: 1.02x slower                                            |
| chameleon                        | 10.6 ms                                                          | 10.8 ms: 1.02x slower                                            |
| genshi_xml                       | 38.4 ms                                                          | 39.3 ms: 1.02x slower                                            |
| scimark_fft                      | 197 ms                                                           | 202 ms: 1.02x slower                                             |
| meteor_contest                   | 83.9 ms                                                          | 86.1 ms: 1.03x slower                                            |
| pycparser                        | 837 ms                                                           | 859 ms: 1.03x slower                                             |
| nbody                            | 67.2 ms                                                          | 69.1 ms: 1.03x slower                                            |
| float                            | 48.1 ms                                                          | 49.5 ms: 1.03x slower                                            |
| json_dumps                       | 7.37 ms                                                          | 7.59 ms: 1.03x slower                                            |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.20 sec: 1.03x slower                                           |
| pylint                           | 215 ms                                                           | 223 ms: 1.03x slower                                             |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 345 ms: 1.03x slower                                             |
| thread_mandelbrot_naive          | 217 ms                                                           | 225 ms: 1.04x slower                                             |
| async_tree_eager_memoization     | 175 ms                                                           | 182 ms: 1.04x slower                                             |
| pickle                           | 9.23 us                                                          | 9.59 us: 1.04x slower                                            |
| unpack_sequence                  | 24.1 ns                                                          | 25.0 ns: 1.04x slower                                            |
| regex_v8                         | 15.0 ms                                                          | 15.7 ms: 1.04x slower                                            |
| thread_mandelbrot_optimized      | 215 ms                                                           | 225 ms: 1.04x slower                                             |
| xdsl_constant_fold               | 35.1 ms                                                          | 37.0 ms: 1.05x slower                                            |
| json                             | 3.42 ms                                                          | 3.65 ms: 1.06x slower                                            |
| xml_etree_parse                  | 102 ms                                                           | 109 ms: 1.07x slower                                             |
| mako                             | 7.66 ms                                                          | 8.28 ms: 1.08x slower                                            |
| json_loads                       | 17.3 us                                                          | 19.1 us: 1.10x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 428 ms: 1.11x slower                                             |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 479 ms: 1.12x slower                                             |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 496 ms: 1.14x slower                                             |
| async_tree_none                  | 223 ms                                                           | 255 ms: 1.14x slower                                             |
| pickle_list                      | 3.26 us                                                          | 3.76 us: 1.15x slower                                            |
| async_tree_eager_tg              | 179 ms                                                           | 210 ms: 1.17x slower                                             |
| async_tree_eager_io              | 548 ms                                                           | 649 ms: 1.18x slower                                             |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 283 ms: 1.20x slower                                             |
| async_tree_memoization_tg        | 275 ms                                                           | 331 ms: 1.21x slower                                             |
| async_tree_none_tg               | 221 ms                                                           | 269 ms: 1.22x slower                                             |
| async_tree_memoization           | 274 ms                                                           | 335 ms: 1.22x slower                                             |
| async_tree_eager_io_tg           | 549 ms                                                           | 679 ms: 1.24x slower                                             |
| async_tree_io                    | 527 ms                                                           | 654 ms: 1.24x slower                                             |
| async_tree_io_tg                 | 529 ms                                                           | 694 ms: 1.31x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.00x slower                                                     |

Benchmark hidden because not significant (24): go, thrift, genshi_text, sqlalchemy_imperative, deepcopy_memo, sympy_integrate, base85_small, chaos, asyncio_tcp_ssl, networkx_connected_components, networkx_k_core, nqueens, pidigits, sympy_str, async_tree_eager, base32_large, scimark_lu, fannkuch, scimark_sparse_mat_mult, tornado_http, sqlglot_v2_normalize, noop, generators, html5lib

- Geometric mean (including insignificant results): 1.004x slower

# HPT report

- Reliability score: 99.96% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 0.99x