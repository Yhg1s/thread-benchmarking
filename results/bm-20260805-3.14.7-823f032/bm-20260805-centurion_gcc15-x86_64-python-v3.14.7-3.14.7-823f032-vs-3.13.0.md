# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.074x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.02x faster
- Memory change: 1.08x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 10.8 ms: 1.01x faster                                            |
| docutils       | 1.98 sec                                                         | 1.95 sec: 1.01x faster                                           |
| fastapi_http   | 215 ms                                                           | 211 ms: 1.02x faster                                             |
| html5lib       | 49.1 ms                                                          | 46.5 ms: 1.06x faster                                            |
| tornado_http   | 99.2 ms                                                          | 101 ms: 1.02x slower                                             |
| Geometric mean | (ref)                                                            | 1.02x faster                                                     |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_memoization_tg        | 417 ms                                                           | 331 ms: 1.26x faster                                             |
| async_tree_none                  | 310 ms                                                           | 255 ms: 1.22x faster                                             |
| async_tree_eager_memoization     | 215 ms                                                           | 182 ms: 1.18x faster                                             |
| coroutines                       | 17.6 ms                                                          | 14.9 ms: 1.18x faster                                            |
| async_tree_memoization           | 389 ms                                                           | 335 ms: 1.16x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 649 ms: 1.15x faster                                             |
| async_tree_eager                 | 90.0 ms                                                          | 78.9 ms: 1.14x faster                                            |
| async_tree_io                    | 741 ms                                                           | 654 ms: 1.13x faster                                             |
| async_tree_io_tg                 | 777 ms                                                           | 694 ms: 1.12x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 269 ms: 1.08x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 479 ms: 1.07x faster                                             |
| async_tree_eager_io_tg           | 724 ms                                                           | 679 ms: 1.07x faster                                             |
| asyncio_tcp                      | 326 ms                                                           | 307 ms: 1.06x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 496 ms: 1.06x faster                                             |
| async_generators                 | 262 ms                                                           | 247 ms: 1.06x faster                                             |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 345 ms: 1.04x faster                                             |
| asyncio_websockets               | 304 ms                                                           | 299 ms: 1.01x faster                                             |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.29 sec: 1.00x faster                                           |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 428 ms: 1.33x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 283 ms: 1.64x slower                                             |
| async_tree_eager_tg              | 58.6 ms                                                          | 210 ms: 3.59x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 18.8 ns: 1.08x faster                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 204 ms: 1.03x faster                                             |
| decimal_factorial | 173 ms                                                           | 170 ms: 1.01x faster                                             |
| Geometric mean    | (ref)                                                            | 1.02x faster                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 49.5 ms: 1.14x faster                                            |
| quadtree_nbody | 620 ms                                                           | 591 ms: 1.05x faster                                             |
| nbody          | 66.8 ms                                                          | 69.1 ms: 1.03x slower                                            |
| Geometric mean | (ref)                                                            | 1.04x faster                                                     |

Benchmark hidden because not significant (1): pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.77 ms: 1.12x faster                                            |
| regex_compile  | 97.7 ms                                                          | 92.0 ms: 1.06x faster                                            |
| regex_dna      | 144 ms                                                           | 139 ms: 1.03x faster                                             |
| regex_v8       | 14.7 ms                                                          | 15.7 ms: 1.07x slower                                            |
| Geometric mean | (ref)                                                            | 1.04x faster                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.35 ms: 5.90x faster                                            |
| base16_small         | 656 us                                                           | 303 us: 2.17x faster                                             |
| base64_large         | 6.32 ms                                                          | 5.01 ms: 1.26x faster                                            |
| ascii85_large        | 814 ms                                                           | 657 ms: 1.24x faster                                             |
| ascii85_small        | 15.5 ms                                                          | 12.7 ms: 1.22x faster                                            |
| tomli_loads          | 1.63 sec                                                         | 1.43 sec: 1.14x faster                                           |
| base64_small         | 228 us                                                           | 211 us: 1.08x faster                                             |
| urlsafe_base64_small | 379 us                                                           | 359 us: 1.05x faster                                             |
| base32_small         | 5.69 ms                                                          | 5.46 ms: 1.04x faster                                            |
| base85_large         | 243 ms                                                           | 235 ms: 1.04x faster                                             |
| base32_large         | 286 ms                                                           | 277 ms: 1.03x faster                                             |
| pickle_dict          | 21.9 us                                                          | 21.3 us: 1.03x faster                                            |
| base85_small         | 4.41 ms                                                          | 4.44 ms: 1.01x slower                                            |
| json_dumps           | 7.49 ms                                                          | 7.59 ms: 1.01x slower                                            |
| unpickle             | 10.3 us                                                          | 10.4 us: 1.02x slower                                            |
| xml_etree_parse      | 107 ms                                                           | 109 ms: 1.02x slower                                             |
| unpickle_pure_python | 149 us                                                           | 152 us: 1.02x slower                                             |
| pickle_pure_python   | 223 us                                                           | 228 us: 1.02x slower                                             |
| unpickle_list        | 3.45 us                                                          | 3.60 us: 1.04x slower                                            |
| xml_etree_process    | 48.1 ms                                                          | 50.6 ms: 1.05x slower                                            |
| xml_etree_iterparse  | 69.6 ms                                                          | 74.5 ms: 1.07x slower                                            |
| xml_etree_generate   | 66.3 ms                                                          | 71.8 ms: 1.08x slower                                            |
| json_loads           | 16.7 us                                                          | 19.1 us: 1.14x slower                                            |
| pickle               | 8.22 us                                                          | 9.59 us: 1.17x slower                                            |
| pickle_list          | 3.03 us                                                          | 3.76 us: 1.24x slower                                            |
| Geometric mean       | (ref)                                                            | 1.12x faster                                                     |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 6.31 ms: 1.01x faster                                            |
| python_startup         | 9.38 ms                                                          | 9.71 ms: 1.04x slower                                            |
| Geometric mean         | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| genshi_text     | 17.6 ms                                                          | 16.4 ms: 1.07x faster                                            |
| genshi_xml      | 39.7 ms                                                          | 39.3 ms: 1.01x faster                                            |
| django_template | 27.3 ms                                                          | 28.0 ms: 1.03x slower                                            |
| mako            | 7.43 ms                                                          | 8.28 ms: 1.11x slower                                            |
| Geometric mean  | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 11.7 ms: 3.34x faster                                            |
| thread_pipeline_naive       | 52.1 ms                                                          | 35.1 ms: 1.48x faster                                            |
| thread_montecarlo_naive     | 17.8 ms                                                          | 14.7 ms: 1.21x faster                                            |
| thread_counter_naive        | 22.6 ms                                                          | 21.2 ms: 1.07x faster                                            |
| thread_montecarlo_optimized | 13.3 ms                                                          | 12.8 ms: 1.04x faster                                            |
| thread_counter_optimized    | 18.7 ms                                                          | 18.5 ms: 1.01x faster                                            |
| thread_mandelbrot_naive     | 220 ms                                                           | 225 ms: 1.03x slower                                             |
| thread_mandelbrot_optimized | 218 ms                                                           | 225 ms: 1.03x slower                                             |
| thread_accumulate_naive     | 40.9 ms                                                          | 42.3 ms: 1.03x slower                                            |
| thread_pipeline_optimized   | 25.6 ms                                                          | 26.7 ms: 1.04x slower                                            |
| thread_accumulate_optimized | 39.8 ms                                                          | 41.5 ms: 1.04x slower                                            |
| Geometric mean              | (ref)                                                            | 1.16x faster                                                     |

Benchmark hidden because not significant (1): thread_memo_optimized

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.35 ms: 5.90x faster                                            |
| thread_memo_naive                | 39.0 ms                                                          | 11.7 ms: 3.34x faster                                            |
| mdp                              | 2.11 sec                                                         | 945 ms: 2.23x faster                                             |
| base16_small                     | 656 us                                                           | 303 us: 2.17x faster                                             |
| argparse_many_optionals          | 12.6 ms                                                          | 7.41 ms: 1.69x faster                                            |
| thread_pipeline_naive            | 52.1 ms                                                          | 35.1 ms: 1.48x faster                                            |
| go                               | 121 ms                                                           | 82.3 ms: 1.47x faster                                            |
| deepcopy_memo                    | 26.6 us                                                          | 18.2 us: 1.46x faster                                            |
| deepcopy                         | 267 us                                                           | 192 us: 1.39x faster                                             |
| scimark_sor                      | 97.0 ms                                                          | 71.8 ms: 1.35x faster                                            |
| base64_large                     | 6.32 ms                                                          | 5.01 ms: 1.26x faster                                            |
| async_tree_memoization_tg        | 417 ms                                                           | 331 ms: 1.26x faster                                             |
| ascii85_large                    | 814 ms                                                           | 657 ms: 1.24x faster                                             |
| ascii85_small                    | 15.5 ms                                                          | 12.7 ms: 1.22x faster                                            |
| async_tree_none                  | 310 ms                                                           | 255 ms: 1.22x faster                                             |
| thread_montecarlo_naive          | 17.8 ms                                                          | 14.7 ms: 1.21x faster                                            |
| pyflate                          | 358 ms                                                           | 298 ms: 1.20x faster                                             |
| deepcopy_reduce                  | 2.37 us                                                          | 1.98 us: 1.20x faster                                            |
| async_tree_eager_memoization     | 215 ms                                                           | 182 ms: 1.18x faster                                             |
| coroutines                       | 17.6 ms                                                          | 14.9 ms: 1.18x faster                                            |
| scimark_monte_carlo              | 44.3 ms                                                          | 37.8 ms: 1.17x faster                                            |
| richards                         | 36.8 ms                                                          | 31.6 ms: 1.17x faster                                            |
| async_tree_memoization           | 389 ms                                                           | 335 ms: 1.16x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 649 ms: 1.15x faster                                             |
| float                            | 56.6 ms                                                          | 49.5 ms: 1.14x faster                                            |
| tomli_loads                      | 1.63 sec                                                         | 1.43 sec: 1.14x faster                                           |
| deltablue                        | 2.52 ms                                                          | 2.21 ms: 1.14x faster                                            |
| async_tree_eager                 | 90.0 ms                                                          | 78.9 ms: 1.14x faster                                            |
| async_tree_io                    | 741 ms                                                           | 654 ms: 1.13x faster                                             |
| fannkuch                         | 265 ms                                                           | 234 ms: 1.13x faster                                             |
| thrift                           | 2.07 ms                                                          | 1.83 ms: 1.13x faster                                            |
| pprint_safe_repr                 | 541 ms                                                           | 481 ms: 1.13x faster                                             |
| regex_effbot                     | 1.99 ms                                                          | 1.77 ms: 1.12x faster                                            |
| richards_super                   | 41.3 ms                                                          | 36.8 ms: 1.12x faster                                            |
| async_tree_io_tg                 | 777 ms                                                           | 694 ms: 1.12x faster                                             |
| pprint_pformat                   | 1.11 sec                                                         | 996 ms: 1.11x faster                                             |
| hexiom                           | 4.42 ms                                                          | 4.02 ms: 1.10x faster                                            |
| noop                             | 20.4 ns                                                          | 18.8 ns: 1.08x faster                                            |
| base64_small                     | 228 us                                                           | 211 us: 1.08x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 269 ms: 1.08x faster                                             |
| chaos                            | 45.0 ms                                                          | 41.8 ms: 1.08x faster                                            |
| genshi_text                      | 17.6 ms                                                          | 16.4 ms: 1.07x faster                                            |
| sqlglot_v2_parse                 | 953 us                                                           | 887 us: 1.07x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 479 ms: 1.07x faster                                             |
| thread_counter_naive             | 22.6 ms                                                          | 21.2 ms: 1.07x faster                                            |
| async_tree_eager_io_tg           | 724 ms                                                           | 679 ms: 1.07x faster                                             |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.20 sec: 1.06x faster                                           |
| asyncio_tcp                      | 326 ms                                                           | 307 ms: 1.06x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 496 ms: 1.06x faster                                             |
| regex_compile                    | 97.7 ms                                                          | 92.0 ms: 1.06x faster                                            |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.13 ms: 1.06x faster                                            |
| async_generators                 | 262 ms                                                           | 247 ms: 1.06x faster                                             |
| html5lib                         | 49.1 ms                                                          | 46.5 ms: 1.06x faster                                            |
| spectral_norm                    | 64.1 ms                                                          | 60.6 ms: 1.06x faster                                            |
| networkx_connected_components    | 460 ms                                                           | 435 ms: 1.06x faster                                             |
| urlsafe_base64_small             | 379 us                                                           | 359 us: 1.05x faster                                             |
| networkx_shortest_path           | 464 ms                                                           | 442 ms: 1.05x faster                                             |
| scimark_lu                       | 70.2 ms                                                          | 66.8 ms: 1.05x faster                                            |
| quadtree_nbody                   | 620 ms                                                           | 591 ms: 1.05x faster                                             |
| sympy_integrate                  | 15.4 ms                                                          | 14.7 ms: 1.05x faster                                            |
| unpack_sequence                  | 26.2 ns                                                          | 25.0 ns: 1.05x faster                                            |
| generators                       | 22.0 ms                                                          | 21.0 ms: 1.05x faster                                            |
| comprehensions                   | 11.6 us                                                          | 11.1 us: 1.05x faster                                            |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 345 ms: 1.04x faster                                             |
| meteor_contest                   | 89.9 ms                                                          | 86.1 ms: 1.04x faster                                            |
| scimark_fft                      | 211 ms                                                           | 202 ms: 1.04x faster                                             |
| networkx_k_core                  | 2.15 sec                                                         | 2.07 sec: 1.04x faster                                           |
| base32_small                     | 5.69 ms                                                          | 5.46 ms: 1.04x faster                                            |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 12.8 ms: 1.04x faster                                            |
| raytrace                         | 199 ms                                                           | 192 ms: 1.04x faster                                             |
| base85_large                     | 243 ms                                                           | 235 ms: 1.04x faster                                             |
| base32_large                     | 286 ms                                                           | 277 ms: 1.03x faster                                             |
| decimal_pi                       | 210 ms                                                           | 204 ms: 1.03x faster                                             |
| regex_dna                        | 144 ms                                                           | 139 ms: 1.03x faster                                             |
| pycparser                        | 884 ms                                                           | 859 ms: 1.03x faster                                             |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 39.0 ms: 1.03x faster                                            |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.59 ms: 1.03x faster                                            |
| pickle_dict                      | 21.9 us                                                          | 21.3 us: 1.03x faster                                            |
| telco                            | 5.50 ms                                                          | 5.37 ms: 1.03x faster                                            |
| logging_silent                   | 60.6 ns                                                          | 59.2 ns: 1.02x faster                                            |
| nqueens                          | 57.3 ms                                                          | 56.3 ms: 1.02x faster                                            |
| gc_traversal                     | 3.16 ms                                                          | 3.11 ms: 1.02x faster                                            |
| fastapi_http                     | 215 ms                                                           | 211 ms: 1.02x faster                                             |
| docutils                         | 1.98 sec                                                         | 1.95 sec: 1.01x faster                                           |
| asyncio_websockets               | 304 ms                                                           | 299 ms: 1.01x faster                                             |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 78.2 ms: 1.01x faster                                            |
| decimal_factorial                | 173 ms                                                           | 170 ms: 1.01x faster                                             |
| genshi_xml                       | 39.7 ms                                                          | 39.3 ms: 1.01x faster                                            |
| thread_counter_optimized         | 18.7 ms                                                          | 18.5 ms: 1.01x faster                                            |
| chameleon                        | 10.9 ms                                                          | 10.8 ms: 1.01x faster                                            |
| python_startup_no_site           | 6.36 ms                                                          | 6.31 ms: 1.01x faster                                            |
| sympy_str                        | 193 ms                                                           | 192 ms: 1.01x faster                                             |
| logging_simple                   | 4.60 us                                                          | 4.57 us: 1.01x faster                                            |
| logging_format                   | 5.23 us                                                          | 5.20 us: 1.01x faster                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.29 sec: 1.00x faster                                           |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                             |
| base85_small                     | 4.41 ms                                                          | 4.44 ms: 1.01x slower                                            |
| sympy_expand                     | 330 ms                                                           | 333 ms: 1.01x slower                                             |
| typing_runtime_protocols         | 106 us                                                           | 107 us: 1.01x slower                                             |
| coverage                         | 52.2 ms                                                          | 52.8 ms: 1.01x slower                                            |
| json_dumps                       | 7.49 ms                                                          | 7.59 ms: 1.01x slower                                            |
| unpickle                         | 10.3 us                                                          | 10.4 us: 1.02x slower                                            |
| xml_etree_parse                  | 107 ms                                                           | 109 ms: 1.02x slower                                             |
| tornado_http                     | 99.2 ms                                                          | 101 ms: 1.02x slower                                             |
| unpickle_pure_python             | 149 us                                                           | 152 us: 1.02x slower                                             |
| pickle_pure_python               | 223 us                                                           | 228 us: 1.02x slower                                             |
| thread_mandelbrot_naive          | 220 ms                                                           | 225 ms: 1.03x slower                                             |
| django_template                  | 27.3 ms                                                          | 28.0 ms: 1.03x slower                                            |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.2 ms: 1.03x slower                                            |
| thread_mandelbrot_optimized      | 218 ms                                                           | 225 ms: 1.03x slower                                             |
| thread_accumulate_naive          | 40.9 ms                                                          | 42.3 ms: 1.03x slower                                            |
| nbody                            | 66.8 ms                                                          | 69.1 ms: 1.03x slower                                            |
| python_startup                   | 9.38 ms                                                          | 9.71 ms: 1.04x slower                                            |
| crypto_pyaes                     | 50.0 ms                                                          | 51.9 ms: 1.04x slower                                            |
| thread_pipeline_optimized        | 25.6 ms                                                          | 26.7 ms: 1.04x slower                                            |
| json                             | 3.49 ms                                                          | 3.65 ms: 1.04x slower                                            |
| thread_accumulate_optimized      | 39.8 ms                                                          | 41.5 ms: 1.04x slower                                            |
| unpickle_list                    | 3.45 us                                                          | 3.60 us: 1.04x slower                                            |
| xml_etree_process                | 48.1 ms                                                          | 50.6 ms: 1.05x slower                                            |
| regex_v8                         | 14.7 ms                                                          | 15.7 ms: 1.07x slower                                            |
| xml_etree_iterparse              | 69.6 ms                                                          | 74.5 ms: 1.07x slower                                            |
| create_gc_cycles                 | 1.70 ms                                                          | 1.83 ms: 1.08x slower                                            |
| xml_etree_generate               | 66.3 ms                                                          | 71.8 ms: 1.08x slower                                            |
| argparse_subparsers              | 446 us                                                           | 489 us: 1.10x slower                                             |
| mako                             | 7.43 ms                                                          | 8.28 ms: 1.11x slower                                            |
| json_loads                       | 16.7 us                                                          | 19.1 us: 1.14x slower                                            |
| pickle                           | 8.22 us                                                          | 9.59 us: 1.17x slower                                            |
| pickle_list                      | 3.03 us                                                          | 3.76 us: 1.24x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 428 ms: 1.33x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 283 ms: 1.64x slower                                             |
| async_tree_eager_tg              | 58.6 ms                                                          | 210 ms: 3.59x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.07x faster                                                     |

Benchmark hidden because not significant (6): pylint, pathlib, mypy2, thread_memo_optimized, pidigits, xdsl_constant_fold

- Geometric mean (including insignificant results): 1.074x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.03x
- 95% likely to have a speedup of 1.03x
- 99% likely to have a speedup of 1.02x

# Memory
- memory change: 1.08x