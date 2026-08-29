# Results vs. 3.14.0

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.072x slower
- HPT reliability: 100.00%
- HPT 99th percentile: 1.02x slower
- Memory change: 0.93x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 10.9 ms: 1.03x slower                                            |
| docutils       | 2.02 sec                                                         | 1.98 sec: 1.02x faster                                           |
| html5lib       | 45.5 ms                                                          | 49.1 ms: 1.08x slower                                            |
| tornado_http   | 101 ms                                                           | 99.2 ms: 1.01x faster                                            |
| Geometric mean | (ref)                                                            | 1.01x slower                                                     |

Benchmark hidden because not significant (1): fastapi_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_eager_tg              | 179 ms                                                           | 58.6 ms: 3.06x faster                                            |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 173 ms: 1.36x faster                                             |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 321 ms: 1.20x faster                                             |
| asyncio_tcp                      | 332 ms                                                           | 326 ms: 1.02x faster                                             |
| async_generators                 | 243 ms                                                           | 262 ms: 1.08x slower                                             |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 360 ms: 1.08x slower                                             |
| async_tree_eager                 | 78.8 ms                                                          | 90.0 ms: 1.14x slower                                            |
| coroutines                       | 15.4 ms                                                          | 17.6 ms: 1.15x slower                                            |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 514 ms: 1.20x slower                                             |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 527 ms: 1.21x slower                                             |
| async_tree_eager_memoization     | 175 ms                                                           | 215 ms: 1.23x slower                                             |
| async_tree_none_tg               | 221 ms                                                           | 289 ms: 1.31x slower                                             |
| async_tree_eager_io_tg           | 549 ms                                                           | 724 ms: 1.32x slower                                             |
| async_tree_eager_io              | 548 ms                                                           | 749 ms: 1.37x slower                                             |
| async_tree_none                  | 223 ms                                                           | 310 ms: 1.39x slower                                             |
| async_tree_io                    | 527 ms                                                           | 741 ms: 1.41x slower                                             |
| async_tree_memoization           | 274 ms                                                           | 389 ms: 1.42x slower                                             |
| async_tree_io_tg                 | 529 ms                                                           | 777 ms: 1.47x slower                                             |
| async_tree_memoization_tg        | 275 ms                                                           | 417 ms: 1.52x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.10x slower                                                     |

Benchmark hidden because not significant (2): asyncio_websockets, asyncio_tcp_ssl

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 20.4 ns: 1.09x slower                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 173 ms: 1.01x slower                                             |
| decimal_pi        | 201 ms                                                           | 210 ms: 1.04x slower                                             |
| Geometric mean    | (ref)                                                            | 1.03x slower                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| quadtree_nbody | 602 ms                                                           | 620 ms: 1.03x slower                                             |
| float          | 48.1 ms                                                          | 56.6 ms: 1.18x slower                                            |
| Geometric mean | (ref)                                                            | 1.05x slower                                                     |

Benchmark hidden because not significant (2): nbody, pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                          | 14.7 ms: 1.02x faster                                            |
| regex_dna      | 141 ms                                                           | 144 ms: 1.02x slower                                             |
| regex_compile  | 91.6 ms                                                          | 97.7 ms: 1.07x slower                                            |
| regex_effbot   | 1.80 ms                                                          | 1.99 ms: 1.11x slower                                            |
| Geometric mean | (ref)                                                            | 1.04x slower                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| pickle               | 9.23 us                                                          | 8.22 us: 1.12x faster                                            |
| xml_etree_iterparse  | 76.5 ms                                                          | 69.6 ms: 1.10x faster                                            |
| pickle_list          | 3.26 us                                                          | 3.03 us: 1.07x faster                                            |
| xml_etree_generate   | 71.1 ms                                                          | 66.3 ms: 1.07x faster                                            |
| unpickle_list        | 3.64 us                                                          | 3.45 us: 1.06x faster                                            |
| pickle_pure_python   | 234 us                                                           | 223 us: 1.05x faster                                             |
| xml_etree_process    | 50.0 ms                                                          | 48.1 ms: 1.04x faster                                            |
| json_loads           | 17.3 us                                                          | 16.7 us: 1.04x faster                                            |
| unpickle_pure_python | 153 us                                                           | 149 us: 1.03x faster                                             |
| urlsafe_base64_small | 383 us                                                           | 379 us: 1.01x faster                                             |
| base64_small         | 230 us                                                           | 228 us: 1.01x faster                                             |
| base85_small         | 4.44 ms                                                          | 4.41 ms: 1.01x faster                                            |
| unpickle             | 10.3 us                                                          | 10.3 us: 1.01x faster                                            |
| json_dumps           | 7.37 ms                                                          | 7.49 ms: 1.02x slower                                            |
| pickle_dict          | 21.3 us                                                          | 21.9 us: 1.03x slower                                            |
| base32_large         | 276 ms                                                           | 286 ms: 1.03x slower                                             |
| base85_large         | 233 ms                                                           | 243 ms: 1.04x slower                                             |
| base32_small         | 5.43 ms                                                          | 5.69 ms: 1.05x slower                                            |
| xml_etree_parse      | 102 ms                                                           | 107 ms: 1.05x slower                                             |
| tomli_loads          | 1.41 sec                                                         | 1.63 sec: 1.16x slower                                           |
| ascii85_small        | 12.5 ms                                                          | 15.5 ms: 1.24x slower                                            |
| ascii85_large        | 651 ms                                                           | 814 ms: 1.25x slower                                             |
| base16_small         | 298 us                                                           | 656 us: 2.20x slower                                             |
| base16_large         | 5.41 ms                                                          | 31.6 ms: 5.83x slower                                            |
| Geometric mean       | (ref)                                                            | 1.12x slower                                                     |

Benchmark hidden because not significant (1): base64_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 9.38 ms: 1.03x faster                                            |
| python_startup_no_site | 6.29 ms                                                          | 6.36 ms: 1.01x slower                                            |
| Geometric mean         | (ref)                                                            | 1.01x faster                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| django_template | 28.4 ms                                                          | 27.3 ms: 1.04x faster                                            |
| mako            | 7.66 ms                                                          | 7.43 ms: 1.03x faster                                            |
| genshi_xml      | 38.4 ms                                                          | 39.7 ms: 1.03x slower                                            |
| genshi_text     | 16.4 ms                                                          | 17.6 ms: 1.07x slower                                            |
| Geometric mean  | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_pipeline_optimized   | 26.3 ms                                                          | 25.6 ms: 1.03x faster                                            |
| thread_accumulate_optimized | 40.8 ms                                                          | 39.8 ms: 1.03x faster                                            |
| thread_accumulate_naive     | 41.6 ms                                                          | 40.9 ms: 1.02x faster                                            |
| thread_mandelbrot_optimized | 215 ms                                                           | 218 ms: 1.01x slower                                             |
| thread_mandelbrot_naive     | 217 ms                                                           | 220 ms: 1.01x slower                                             |
| thread_memo_optimized       | 17.9 ms                                                          | 18.2 ms: 1.02x slower                                            |
| thread_montecarlo_optimized | 12.6 ms                                                          | 13.3 ms: 1.06x slower                                            |
| thread_counter_naive        | 21.4 ms                                                          | 22.6 ms: 1.06x slower                                            |
| thread_montecarlo_naive     | 14.6 ms                                                          | 17.8 ms: 1.22x slower                                            |
| thread_pipeline_naive       | 35.4 ms                                                          | 52.1 ms: 1.47x slower                                            |
| thread_memo_naive           | 11.8 ms                                                          | 39.0 ms: 3.29x slower                                            |
| Geometric mean              | (ref)                                                            | 1.17x slower                                                     |

Benchmark hidden because not significant (1): thread_counter_optimized

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_eager_tg              | 179 ms                                                           | 58.6 ms: 3.06x faster                                            |
| argparse_many_optionals          | 33.3 ms                                                          | 12.6 ms: 2.65x faster                                            |
| argparse_subparsers              | 665 us                                                           | 446 us: 1.49x faster                                             |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 173 ms: 1.36x faster                                             |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 321 ms: 1.20x faster                                             |
| create_gc_cycles                 | 1.93 ms                                                          | 1.70 ms: 1.14x faster                                            |
| pickle                           | 9.23 us                                                          | 8.22 us: 1.12x faster                                            |
| xml_etree_iterparse              | 76.5 ms                                                          | 69.6 ms: 1.10x faster                                            |
| pickle_list                      | 3.26 us                                                          | 3.03 us: 1.07x faster                                            |
| xml_etree_generate               | 71.1 ms                                                          | 66.3 ms: 1.07x faster                                            |
| coverage                         | 55.4 ms                                                          | 52.2 ms: 1.06x faster                                            |
| unpickle_list                    | 3.64 us                                                          | 3.45 us: 1.06x faster                                            |
| gc_traversal                     | 3.33 ms                                                          | 3.16 ms: 1.05x faster                                            |
| pickle_pure_python               | 234 us                                                           | 223 us: 1.05x faster                                             |
| mypy2                            | 756 ms                                                           | 726 ms: 1.04x faster                                             |
| django_template                  | 28.4 ms                                                          | 27.3 ms: 1.04x faster                                            |
| xml_etree_process                | 50.0 ms                                                          | 48.1 ms: 1.04x faster                                            |
| json_loads                       | 17.3 us                                                          | 16.7 us: 1.04x faster                                            |
| sqlalchemy_imperative            | 14.3 ms                                                          | 13.8 ms: 1.03x faster                                            |
| mako                             | 7.66 ms                                                          | 7.43 ms: 1.03x faster                                            |
| crypto_pyaes                     | 51.5 ms                                                          | 50.0 ms: 1.03x faster                                            |
| unpickle_pure_python             | 153 us                                                           | 149 us: 1.03x faster                                             |
| thread_pipeline_optimized        | 26.3 ms                                                          | 25.6 ms: 1.03x faster                                            |
| thread_accumulate_optimized      | 40.8 ms                                                          | 39.8 ms: 1.03x faster                                            |
| python_startup                   | 9.62 ms                                                          | 9.38 ms: 1.03x faster                                            |
| logging_simple                   | 4.72 us                                                          | 4.60 us: 1.03x faster                                            |
| regex_v8                         | 15.0 ms                                                          | 14.7 ms: 1.02x faster                                            |
| docutils                         | 2.02 sec                                                         | 1.98 sec: 1.02x faster                                           |
| asyncio_tcp                      | 332 ms                                                           | 326 ms: 1.02x faster                                             |
| thread_accumulate_naive          | 41.6 ms                                                          | 40.9 ms: 1.02x faster                                            |
| tornado_http                     | 101 ms                                                           | 99.2 ms: 1.01x faster                                            |
| urlsafe_base64_small             | 383 us                                                           | 379 us: 1.01x faster                                             |
| base64_small                     | 230 us                                                           | 228 us: 1.01x faster                                             |
| base85_small                     | 4.44 ms                                                          | 4.41 ms: 1.01x faster                                            |
| pathlib                          | 12.5 ms                                                          | 12.4 ms: 1.01x faster                                            |
| unpickle                         | 10.3 us                                                          | 10.3 us: 1.01x faster                                            |
| sympy_sum                        | 104 ms                                                           | 104 ms: 1.00x slower                                             |
| sympy_str                        | 192 ms                                                           | 193 ms: 1.01x slower                                             |
| python_startup_no_site           | 6.29 ms                                                          | 6.36 ms: 1.01x slower                                            |
| thread_mandelbrot_optimized      | 215 ms                                                           | 218 ms: 1.01x slower                                             |
| thread_mandelbrot_naive          | 217 ms                                                           | 220 ms: 1.01x slower                                             |
| decimal_factorial                | 170 ms                                                           | 173 ms: 1.01x slower                                             |
| thread_memo_optimized            | 17.9 ms                                                          | 18.2 ms: 1.02x slower                                            |
| logging_silent                   | 59.7 ns                                                          | 60.6 ns: 1.02x slower                                            |
| json_dumps                       | 7.37 ms                                                          | 7.49 ms: 1.02x slower                                            |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 79.1 ms: 1.02x slower                                            |
| nqueens                          | 56.3 ms                                                          | 57.3 ms: 1.02x slower                                            |
| regex_dna                        | 141 ms                                                           | 144 ms: 1.02x slower                                             |
| json                             | 3.42 ms                                                          | 3.49 ms: 1.02x slower                                            |
| raytrace                         | 194 ms                                                           | 199 ms: 1.02x slower                                             |
| pickle_dict                      | 21.3 us                                                          | 21.9 us: 1.03x slower                                            |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 2.66 ms: 1.03x slower                                            |
| quadtree_nbody                   | 602 ms                                                           | 620 ms: 1.03x slower                                             |
| chameleon                        | 10.6 ms                                                          | 10.9 ms: 1.03x slower                                            |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 40.0 ms: 1.03x slower                                            |
| genshi_xml                       | 38.4 ms                                                          | 39.7 ms: 1.03x slower                                            |
| base32_large                     | 276 ms                                                           | 286 ms: 1.03x slower                                             |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.20 ms: 1.04x slower                                            |
| comprehensions                   | 11.2 us                                                          | 11.6 us: 1.04x slower                                            |
| networkx_k_core                  | 2.07 sec                                                         | 2.15 sec: 1.04x slower                                           |
| networkx_shortest_path           | 445 ms                                                           | 464 ms: 1.04x slower                                             |
| decimal_pi                       | 201 ms                                                           | 210 ms: 1.04x slower                                             |
| xdsl_constant_fold               | 35.1 ms                                                          | 36.7 ms: 1.04x slower                                            |
| base85_large                     | 233 ms                                                           | 243 ms: 1.04x slower                                             |
| telco                            | 5.26 ms                                                          | 5.50 ms: 1.05x slower                                            |
| base32_small                     | 5.43 ms                                                          | 5.69 ms: 1.05x slower                                            |
| sympy_integrate                  | 14.7 ms                                                          | 15.4 ms: 1.05x slower                                            |
| sqlglot_v2_parse                 | 909 us                                                           | 953 us: 1.05x slower                                             |
| pylint                           | 215 ms                                                           | 226 ms: 1.05x slower                                             |
| xml_etree_parse                  | 102 ms                                                           | 107 ms: 1.05x slower                                             |
| scimark_lu                       | 66.7 ms                                                          | 70.2 ms: 1.05x slower                                            |
| pycparser                        | 837 ms                                                           | 884 ms: 1.06x slower                                             |
| networkx_connected_components    | 435 ms                                                           | 460 ms: 1.06x slower                                             |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 13.3 ms: 1.06x slower                                            |
| thread_counter_naive             | 21.4 ms                                                          | 22.6 ms: 1.06x slower                                            |
| generators                       | 20.7 ms                                                          | 22.0 ms: 1.06x slower                                            |
| regex_compile                    | 91.6 ms                                                          | 97.7 ms: 1.07x slower                                            |
| scimark_fft                      | 197 ms                                                           | 211 ms: 1.07x slower                                             |
| meteor_contest                   | 83.9 ms                                                          | 89.9 ms: 1.07x slower                                            |
| genshi_text                      | 16.4 ms                                                          | 17.6 ms: 1.07x slower                                            |
| spectral_norm                    | 59.6 ms                                                          | 64.1 ms: 1.07x slower                                            |
| chaos                            | 41.9 ms                                                          | 45.0 ms: 1.08x slower                                            |
| async_generators                 | 243 ms                                                           | 262 ms: 1.08x slower                                             |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 360 ms: 1.08x slower                                             |
| html5lib                         | 45.5 ms                                                          | 49.1 ms: 1.08x slower                                            |
| noop                             | 18.7 ns                                                          | 20.4 ns: 1.09x slower                                            |
| unpack_sequence                  | 24.1 ns                                                          | 26.2 ns: 1.09x slower                                            |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.40 sec: 1.10x slower                                           |
| hexiom                           | 4.00 ms                                                          | 4.42 ms: 1.11x slower                                            |
| regex_effbot                     | 1.80 ms                                                          | 1.99 ms: 1.11x slower                                            |
| richards_super                   | 37.2 ms                                                          | 41.3 ms: 1.11x slower                                            |
| pprint_safe_repr                 | 484 ms                                                           | 541 ms: 1.12x slower                                             |
| deltablue                        | 2.24 ms                                                          | 2.52 ms: 1.12x slower                                            |
| thrift                           | 1.84 ms                                                          | 2.07 ms: 1.12x slower                                            |
| pprint_pformat                   | 982 ms                                                           | 1.11 sec: 1.13x slower                                           |
| richards                         | 32.5 ms                                                          | 36.8 ms: 1.13x slower                                            |
| fannkuch                         | 234 ms                                                           | 265 ms: 1.13x slower                                             |
| async_tree_eager                 | 78.8 ms                                                          | 90.0 ms: 1.14x slower                                            |
| coroutines                       | 15.4 ms                                                          | 17.6 ms: 1.15x slower                                            |
| tomli_loads                      | 1.41 sec                                                         | 1.63 sec: 1.16x slower                                           |
| deepcopy_reduce                  | 2.05 us                                                          | 2.37 us: 1.16x slower                                            |
| float                            | 48.1 ms                                                          | 56.6 ms: 1.18x slower                                            |
| scimark_monte_carlo              | 37.5 ms                                                          | 44.3 ms: 1.18x slower                                            |
| pyflate                          | 300 ms                                                           | 358 ms: 1.19x slower                                             |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 514 ms: 1.20x slower                                             |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 527 ms: 1.21x slower                                             |
| thread_montecarlo_naive          | 14.6 ms                                                          | 17.8 ms: 1.22x slower                                            |
| async_tree_eager_memoization     | 175 ms                                                           | 215 ms: 1.23x slower                                             |
| ascii85_small                    | 12.5 ms                                                          | 15.5 ms: 1.24x slower                                            |
| ascii85_large                    | 651 ms                                                           | 814 ms: 1.25x slower                                             |
| async_tree_none_tg               | 221 ms                                                           | 289 ms: 1.31x slower                                             |
| async_tree_eager_io_tg           | 549 ms                                                           | 724 ms: 1.32x slower                                             |
| scimark_sor                      | 72.8 ms                                                          | 97.0 ms: 1.33x slower                                            |
| async_tree_eager_io              | 548 ms                                                           | 749 ms: 1.37x slower                                             |
| deepcopy                         | 195 us                                                           | 267 us: 1.37x slower                                             |
| async_tree_none                  | 223 ms                                                           | 310 ms: 1.39x slower                                             |
| async_tree_io                    | 527 ms                                                           | 741 ms: 1.41x slower                                             |
| async_tree_memoization           | 274 ms                                                           | 389 ms: 1.42x slower                                             |
| deepcopy_memo                    | 18.2 us                                                          | 26.6 us: 1.46x slower                                            |
| go                               | 82.6 ms                                                          | 121 ms: 1.47x slower                                             |
| async_tree_io_tg                 | 529 ms                                                           | 777 ms: 1.47x slower                                             |
| thread_pipeline_naive            | 35.4 ms                                                          | 52.1 ms: 1.47x slower                                            |
| async_tree_memoization_tg        | 275 ms                                                           | 417 ms: 1.52x slower                                             |
| base16_small                     | 298 us                                                           | 656 us: 2.20x slower                                             |
| mdp                              | 935 ms                                                           | 2.11 sec: 2.26x slower                                           |
| thread_memo_naive                | 11.8 ms                                                          | 39.0 ms: 3.29x slower                                            |
| base16_large                     | 5.41 ms                                                          | 31.6 ms: 5.83x slower                                            |
| Geometric mean                   | (ref)                                                            | 1.08x slower                                                     |

Benchmark hidden because not significant (10): nbody, asyncio_websockets, fastapi_http, logging_format, pidigits, thread_counter_optimized, typing_runtime_protocols, sympy_expand, base64_large, asyncio_tcp_ssl

- Geometric mean (including insignificant results): 1.072x slower

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.03x
- 95% likely to have a slowdown of 1.03x
- 99% likely to have a slowdown of 1.02x

# Memory
- memory change: 0.93x