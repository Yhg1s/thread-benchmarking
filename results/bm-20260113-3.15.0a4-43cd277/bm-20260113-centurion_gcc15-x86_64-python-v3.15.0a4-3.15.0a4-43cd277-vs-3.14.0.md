# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.022x faster
- HPT reliability: 98.55%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 10.6 ms: 1.00x faster                                                |
| docutils       | 2.02 sec                                                         | 2.01 sec: 1.00x faster                                               |
| fastapi_http   | 215 ms                                                           | 208 ms: 1.04x faster                                                 |
| html5lib       | 45.5 ms                                                          | 43.4 ms: 1.05x faster                                                |
| tornado_http   | 101 ms                                                           | 97.8 ms: 1.03x faster                                                |
| Geometric mean | (ref)                                                            | 1.02x faster                                                         |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| asyncio_tcp                      | 332 ms                                                           | 279 ms: 1.19x faster                                                 |
| async_tree_eager_io_tg           | 549 ms                                                           | 468 ms: 1.17x faster                                                 |
| async_tree_eager_io              | 548 ms                                                           | 469 ms: 1.17x faster                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 485 ms: 1.09x faster                                                 |
| async_tree_none_tg               | 221 ms                                                           | 203 ms: 1.09x faster                                                 |
| async_tree_io                    | 527 ms                                                           | 485 ms: 1.09x faster                                                 |
| async_tree_eager_memoization     | 175 ms                                                           | 166 ms: 1.05x faster                                                 |
| async_tree_memoization_tg        | 275 ms                                                           | 262 ms: 1.05x faster                                                 |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 227 ms: 1.04x faster                                                 |
| async_tree_memoization           | 274 ms                                                           | 265 ms: 1.03x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 217 ms: 1.03x faster                                                 |
| async_tree_eager                 | 78.8 ms                                                          | 77.5 ms: 1.02x faster                                                |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.27 sec: 1.02x faster                                               |
| async_generators                 | 243 ms                                                           | 240 ms: 1.01x faster                                                 |
| async_tree_eager_tg              | 179 ms                                                           | 178 ms: 1.01x faster                                                 |
| asyncio_websockets               | 305 ms                                                           | 309 ms: 1.01x slower                                                 |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 439 ms: 1.02x slower                                                 |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 353 ms: 1.06x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 410 ms: 1.06x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.04x faster                                                         |

Benchmark hidden because not significant (2): coroutines, async_tree_cpu_io_mixed_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 19.4 ns: 1.04x slower                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 171 ms: 1.01x slower                                                 |
| decimal_pi        | 201 ms                                                           | 207 ms: 1.03x slower                                                 |
| Geometric mean    | (ref)                                                            | 1.02x slower                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| nbody          | 67.2 ms                                                          | 65.8 ms: 1.02x faster                                                |
| quadtree_nbody | 602 ms                                                           | 593 ms: 1.02x faster                                                 |
| pidigits       | 181 ms                                                           | 182 ms: 1.00x slower                                                 |
| Geometric mean | (ref)                                                            | 1.01x faster                                                         |

Benchmark hidden because not significant (1): float

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_compile  | 91.6 ms                                                          | 90.8 ms: 1.01x faster                                                |
| regex_dna      | 141 ms                                                           | 140 ms: 1.01x faster                                                 |
| regex_v8       | 15.0 ms                                                          | 15.2 ms: 1.01x slower                                                |
| Geometric mean | (ref)                                                            | 1.00x faster                                                         |

Benchmark hidden because not significant (1): regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| xml_etree_iterparse  | 76.5 ms                                                          | 69.5 ms: 1.10x faster                                                |
| json_dumps           | 7.37 ms                                                          | 6.72 ms: 1.10x faster                                                |
| base64_large         | 6.31 ms                                                          | 5.87 ms: 1.08x faster                                                |
| base16_large         | 5.41 ms                                                          | 5.09 ms: 1.06x faster                                                |
| base64_small         | 230 us                                                           | 221 us: 1.04x faster                                                 |
| unpickle_list        | 3.64 us                                                          | 3.51 us: 1.04x faster                                                |
| xml_etree_generate   | 71.1 ms                                                          | 68.8 ms: 1.03x faster                                                |
| urlsafe_base64_small | 383 us                                                           | 372 us: 1.03x faster                                                 |
| xml_etree_parse      | 102 ms                                                           | 99.3 ms: 1.03x faster                                                |
| xml_etree_process    | 50.0 ms                                                          | 49.3 ms: 1.01x faster                                                |
| unpickle_pure_python | 153 us                                                           | 151 us: 1.01x faster                                                 |
| pickle_pure_python   | 234 us                                                           | 233 us: 1.01x faster                                                 |
| pickle_dict          | 21.3 us                                                          | 21.3 us: 1.00x slower                                                |
| ascii85_large        | 651 ms                                                           | 653 ms: 1.00x slower                                                 |
| base32_large         | 276 ms                                                           | 279 ms: 1.01x slower                                                 |
| pickle               | 9.23 us                                                          | 9.36 us: 1.01x slower                                                |
| unpickle             | 10.3 us                                                          | 10.5 us: 1.01x slower                                                |
| ascii85_small        | 12.5 ms                                                          | 12.7 ms: 1.02x slower                                                |
| pickle_list          | 3.26 us                                                          | 3.33 us: 1.02x slower                                                |
| base16_small         | 298 us                                                           | 307 us: 1.03x slower                                                 |
| base85_small         | 4.44 ms                                                          | 4.60 ms: 1.04x slower                                                |
| base85_large         | 233 ms                                                           | 242 ms: 1.04x slower                                                 |
| base32_small         | 5.43 ms                                                          | 5.67 ms: 1.04x slower                                                |
| tomli_loads          | 1.41 sec                                                         | 1.53 sec: 1.09x slower                                               |
| Geometric mean       | (ref)                                                            | 1.01x faster                                                         |

Benchmark hidden because not significant (1): json_loads

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 9.27 ms: 1.04x faster                                                |
| python_startup_no_site | 6.29 ms                                                          | 6.09 ms: 1.03x faster                                                |
| Geometric mean         | (ref)                                                            | 1.04x faster                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| genshi_text     | 16.4 ms                                                          | 16.2 ms: 1.01x faster                                                |
| django_template | 28.4 ms                                                          | 28.8 ms: 1.02x slower                                                |
| genshi_xml      | 38.4 ms                                                          | 39.5 ms: 1.03x slower                                                |
| mako            | 7.66 ms                                                          | 9.06 ms: 1.18x slower                                                |
| Geometric mean  | (ref)                                                            | 1.05x slower                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_memo_naive           | 11.8 ms                                                          | 9.85 ms: 1.20x faster                                                |
| thread_mandelbrot_naive     | 217 ms                                                           | 219 ms: 1.01x slower                                                 |
| thread_mandelbrot_optimized | 215 ms                                                           | 219 ms: 1.02x slower                                                 |
| thread_montecarlo_optimized | 12.6 ms                                                          | 13.3 ms: 1.05x slower                                                |
| thread_pipeline_naive       | 35.4 ms                                                          | 37.3 ms: 1.05x slower                                                |
| thread_montecarlo_naive     | 14.6 ms                                                          | 15.4 ms: 1.05x slower                                                |
| thread_counter_naive        | 21.4 ms                                                          | 22.8 ms: 1.07x slower                                                |
| thread_memo_optimized       | 17.9 ms                                                          | 19.3 ms: 1.08x slower                                                |
| thread_accumulate_naive     | 41.6 ms                                                          | 45.4 ms: 1.09x slower                                                |
| thread_accumulate_optimized | 40.8 ms                                                          | 45.4 ms: 1.11x slower                                                |
| thread_pipeline_optimized   | 26.3 ms                                                          | 29.5 ms: 1.12x slower                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 20.9 ms: 1.12x slower                                                |
| Geometric mean              | (ref)                                                            | 1.05x slower                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| argparse_many_optionals          | 33.3 ms                                                          | 7.44 ms: 4.47x faster                                                |
| argparse_subparsers              | 665 us                                                           | 472 us: 1.41x faster                                                 |
| thread_memo_naive                | 11.8 ms                                                          | 9.85 ms: 1.20x faster                                                |
| asyncio_tcp                      | 332 ms                                                           | 279 ms: 1.19x faster                                                 |
| pathlib                          | 12.5 ms                                                          | 10.7 ms: 1.17x faster                                                |
| async_tree_eager_io_tg           | 549 ms                                                           | 468 ms: 1.17x faster                                                 |
| async_tree_eager_io              | 548 ms                                                           | 469 ms: 1.17x faster                                                 |
| xml_etree_iterparse              | 76.5 ms                                                          | 69.5 ms: 1.10x faster                                                |
| json_dumps                       | 7.37 ms                                                          | 6.72 ms: 1.10x faster                                                |
| deepcopy_memo                    | 18.2 us                                                          | 16.7 us: 1.09x faster                                                |
| async_tree_io_tg                 | 529 ms                                                           | 485 ms: 1.09x faster                                                 |
| async_tree_none_tg               | 221 ms                                                           | 203 ms: 1.09x faster                                                 |
| async_tree_io                    | 527 ms                                                           | 485 ms: 1.09x faster                                                 |
| base64_large                     | 6.31 ms                                                          | 5.87 ms: 1.08x faster                                                |
| base16_large                     | 5.41 ms                                                          | 5.09 ms: 1.06x faster                                                |
| networkx_k_core                  | 2.07 sec                                                         | 1.94 sec: 1.06x faster                                               |
| telco                            | 5.26 ms                                                          | 4.98 ms: 1.06x faster                                                |
| chaos                            | 41.9 ms                                                          | 39.7 ms: 1.05x faster                                                |
| async_tree_eager_memoization     | 175 ms                                                           | 166 ms: 1.05x faster                                                 |
| deepcopy                         | 195 us                                                           | 186 us: 1.05x faster                                                 |
| async_tree_memoization_tg        | 275 ms                                                           | 262 ms: 1.05x faster                                                 |
| html5lib                         | 45.5 ms                                                          | 43.4 ms: 1.05x faster                                                |
| coverage                         | 55.4 ms                                                          | 53.0 ms: 1.04x faster                                                |
| base64_small                     | 230 us                                                           | 221 us: 1.04x faster                                                 |
| python_startup                   | 9.62 ms                                                          | 9.27 ms: 1.04x faster                                                |
| fastapi_http                     | 215 ms                                                           | 208 ms: 1.04x faster                                                 |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 227 ms: 1.04x faster                                                 |
| unpickle_list                    | 3.64 us                                                          | 3.51 us: 1.04x faster                                                |
| async_tree_memoization           | 274 ms                                                           | 265 ms: 1.03x faster                                                 |
| comprehensions                   | 11.2 us                                                          | 10.8 us: 1.03x faster                                                |
| xml_etree_generate               | 71.1 ms                                                          | 68.8 ms: 1.03x faster                                                |
| logging_simple                   | 4.72 us                                                          | 4.57 us: 1.03x faster                                                |
| python_startup_no_site           | 6.29 ms                                                          | 6.09 ms: 1.03x faster                                                |
| pylint                           | 215 ms                                                           | 209 ms: 1.03x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 217 ms: 1.03x faster                                                 |
| urlsafe_base64_small             | 383 us                                                           | 372 us: 1.03x faster                                                 |
| scimark_sor                      | 72.8 ms                                                          | 70.6 ms: 1.03x faster                                                |
| tornado_http                     | 101 ms                                                           | 97.8 ms: 1.03x faster                                                |
| xml_etree_parse                  | 102 ms                                                           | 99.3 ms: 1.03x faster                                                |
| go                               | 82.6 ms                                                          | 80.6 ms: 1.03x faster                                                |
| mdp                              | 935 ms                                                           | 914 ms: 1.02x faster                                                 |
| nqueens                          | 56.3 ms                                                          | 55.0 ms: 1.02x faster                                                |
| scimark_lu                       | 66.7 ms                                                          | 65.2 ms: 1.02x faster                                                |
| nbody                            | 67.2 ms                                                          | 65.8 ms: 1.02x faster                                                |
| hexiom                           | 4.00 ms                                                          | 3.92 ms: 1.02x faster                                                |
| mypy2                            | 756 ms                                                           | 740 ms: 1.02x faster                                                 |
| deepcopy_reduce                  | 2.05 us                                                          | 2.00 us: 1.02x faster                                                |
| xdsl_constant_fold               | 35.1 ms                                                          | 34.5 ms: 1.02x faster                                                |
| fannkuch                         | 234 ms                                                           | 229 ms: 1.02x faster                                                 |
| async_tree_eager                 | 78.8 ms                                                          | 77.5 ms: 1.02x faster                                                |
| quadtree_nbody                   | 602 ms                                                           | 593 ms: 1.02x faster                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.27 sec: 1.02x faster                                               |
| pycparser                        | 837 ms                                                           | 824 ms: 1.02x faster                                                 |
| raytrace                         | 194 ms                                                           | 191 ms: 1.02x faster                                                 |
| xml_etree_process                | 50.0 ms                                                          | 49.3 ms: 1.01x faster                                                |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.14 ms: 1.01x faster                                                |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 2.55 ms: 1.01x faster                                                |
| genshi_text                      | 16.4 ms                                                          | 16.2 ms: 1.01x faster                                                |
| pyflate                          | 300 ms                                                           | 297 ms: 1.01x faster                                                 |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.06 sec: 1.01x faster                                               |
| async_generators                 | 243 ms                                                           | 240 ms: 1.01x faster                                                 |
| scimark_monte_carlo              | 37.5 ms                                                          | 37.0 ms: 1.01x faster                                                |
| scimark_fft                      | 197 ms                                                           | 195 ms: 1.01x faster                                                 |
| unpickle_pure_python             | 153 us                                                           | 151 us: 1.01x faster                                                 |
| async_tree_eager_tg              | 179 ms                                                           | 178 ms: 1.01x faster                                                 |
| sqlalchemy_imperative            | 14.3 ms                                                          | 14.1 ms: 1.01x faster                                                |
| logging_format                   | 5.24 us                                                          | 5.20 us: 1.01x faster                                                |
| crypto_pyaes                     | 51.5 ms                                                          | 51.0 ms: 1.01x faster                                                |
| gc_traversal                     | 3.33 ms                                                          | 3.30 ms: 1.01x faster                                                |
| regex_compile                    | 91.6 ms                                                          | 90.8 ms: 1.01x faster                                                |
| regex_dna                        | 141 ms                                                           | 140 ms: 1.01x faster                                                 |
| json                             | 3.42 ms                                                          | 3.40 ms: 1.01x faster                                                |
| richards_super                   | 37.2 ms                                                          | 37.0 ms: 1.01x faster                                                |
| typing_runtime_protocols         | 106 us                                                           | 105 us: 1.01x faster                                                 |
| pickle_pure_python               | 234 us                                                           | 233 us: 1.01x faster                                                 |
| chameleon                        | 10.6 ms                                                          | 10.6 ms: 1.00x faster                                                |
| docutils                         | 2.02 sec                                                         | 2.01 sec: 1.00x faster                                               |
| meteor_contest                   | 83.9 ms                                                          | 84.1 ms: 1.00x slower                                                |
| pidigits                         | 181 ms                                                           | 182 ms: 1.00x slower                                                 |
| pickle_dict                      | 21.3 us                                                          | 21.3 us: 1.00x slower                                                |
| ascii85_large                    | 651 ms                                                           | 653 ms: 1.00x slower                                                 |
| create_gc_cycles                 | 1.93 ms                                                          | 1.94 ms: 1.01x slower                                                |
| decimal_factorial                | 170 ms                                                           | 171 ms: 1.01x slower                                                 |
| sympy_str                        | 192 ms                                                           | 194 ms: 1.01x slower                                                 |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 78.7 ms: 1.01x slower                                                |
| thread_mandelbrot_naive          | 217 ms                                                           | 219 ms: 1.01x slower                                                 |
| thrift                           | 1.84 ms                                                          | 1.86 ms: 1.01x slower                                                |
| base32_large                     | 276 ms                                                           | 279 ms: 1.01x slower                                                 |
| regex_v8                         | 15.0 ms                                                          | 15.2 ms: 1.01x slower                                                |
| pickle                           | 9.23 us                                                          | 9.36 us: 1.01x slower                                                |
| unpickle                         | 10.3 us                                                          | 10.5 us: 1.01x slower                                                |
| asyncio_websockets               | 305 ms                                                           | 309 ms: 1.01x slower                                                 |
| networkx_connected_components    | 435 ms                                                           | 442 ms: 1.01x slower                                                 |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.02x slower                                                 |
| spectral_norm                    | 59.6 ms                                                          | 60.5 ms: 1.02x slower                                                |
| ascii85_small                    | 12.5 ms                                                          | 12.7 ms: 1.02x slower                                                |
| django_template                  | 28.4 ms                                                          | 28.8 ms: 1.02x slower                                                |
| sympy_expand                     | 330 ms                                                           | 335 ms: 1.02x slower                                                 |
| thread_mandelbrot_optimized      | 215 ms                                                           | 219 ms: 1.02x slower                                                 |
| pprint_safe_repr                 | 484 ms                                                           | 493 ms: 1.02x slower                                                 |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 439 ms: 1.02x slower                                                 |
| pickle_list                      | 3.26 us                                                          | 3.33 us: 1.02x slower                                                |
| decimal_pi                       | 201 ms                                                           | 207 ms: 1.03x slower                                                 |
| genshi_xml                       | 38.4 ms                                                          | 39.5 ms: 1.03x slower                                                |
| base16_small                     | 298 us                                                           | 307 us: 1.03x slower                                                 |
| base85_small                     | 4.44 ms                                                          | 4.60 ms: 1.04x slower                                                |
| noop                             | 18.7 ns                                                          | 19.4 ns: 1.04x slower                                                |
| base85_large                     | 233 ms                                                           | 242 ms: 1.04x slower                                                 |
| base32_small                     | 5.43 ms                                                          | 5.67 ms: 1.04x slower                                                |
| pprint_pformat                   | 982 ms                                                           | 1.03 sec: 1.04x slower                                               |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 13.3 ms: 1.05x slower                                                |
| thread_pipeline_naive            | 35.4 ms                                                          | 37.3 ms: 1.05x slower                                                |
| thread_montecarlo_naive          | 14.6 ms                                                          | 15.4 ms: 1.05x slower                                                |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 353 ms: 1.06x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 410 ms: 1.06x slower                                                 |
| thread_counter_naive             | 21.4 ms                                                          | 22.8 ms: 1.07x slower                                                |
| deltablue                        | 2.24 ms                                                          | 2.39 ms: 1.07x slower                                                |
| thread_memo_optimized            | 17.9 ms                                                          | 19.3 ms: 1.08x slower                                                |
| tomli_loads                      | 1.41 sec                                                         | 1.53 sec: 1.09x slower                                               |
| thread_accumulate_naive          | 41.6 ms                                                          | 45.4 ms: 1.09x slower                                                |
| unpack_sequence                  | 24.1 ns                                                          | 26.4 ns: 1.10x slower                                                |
| thread_accumulate_optimized      | 40.8 ms                                                          | 45.4 ms: 1.11x slower                                                |
| thread_pipeline_optimized        | 26.3 ms                                                          | 29.5 ms: 1.12x slower                                                |
| thread_counter_optimized         | 18.7 ms                                                          | 20.9 ms: 1.12x slower                                                |
| mako                             | 7.66 ms                                                          | 9.06 ms: 1.18x slower                                                |
| Geometric mean                   | (ref)                                                            | 1.02x faster                                                         |

Benchmark hidden because not significant (12): generators, richards, float, regex_effbot, json_loads, coroutines, networkx_shortest_path, sympy_integrate, sqlglot_v2_optimize, async_tree_cpu_io_mixed_tg, logging_silent, sqlglot_v2_parse

- Geometric mean (including insignificant results): 1.022x faster

# HPT report

- Reliability score: 98.55% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.01x