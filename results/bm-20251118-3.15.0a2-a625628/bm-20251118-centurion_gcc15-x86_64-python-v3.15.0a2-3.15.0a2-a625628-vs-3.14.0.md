# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.026x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 10.4 ms: 1.02x faster                                                |
| docutils       | 2.02 sec                                                         | 2.00 sec: 1.01x faster                                               |
| fastapi_http   | 215 ms                                                           | 210 ms: 1.02x faster                                                 |
| html5lib       | 45.5 ms                                                          | 44.2 ms: 1.03x faster                                                |
| tornado_http   | 101 ms                                                           | 97.0 ms: 1.04x faster                                                |
| Geometric mean | (ref)                                                            | 1.02x faster                                                         |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 549 ms                                                           | 462 ms: 1.19x faster                                                 |
| async_tree_eager_io              | 548 ms                                                           | 467 ms: 1.17x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 196 ms: 1.14x faster                                                 |
| async_tree_io                    | 527 ms                                                           | 468 ms: 1.13x faster                                                 |
| async_tree_none_tg               | 221 ms                                                           | 199 ms: 1.11x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 393 ms: 1.11x faster                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 479 ms: 1.10x faster                                                 |
| asyncio_tcp                      | 332 ms                                                           | 303 ms: 1.10x faster                                                 |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 394 ms: 1.09x faster                                                 |
| async_tree_memoization           | 274 ms                                                           | 255 ms: 1.08x faster                                                 |
| async_tree_eager_memoization     | 175 ms                                                           | 163 ms: 1.07x faster                                                 |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 222 ms: 1.06x faster                                                 |
| async_tree_memoization_tg        | 275 ms                                                           | 259 ms: 1.06x faster                                                 |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 372 ms: 1.03x faster                                                 |
| async_tree_eager                 | 78.8 ms                                                          | 76.7 ms: 1.03x faster                                                |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 324 ms: 1.03x faster                                                 |
| async_tree_eager_tg              | 179 ms                                                           | 176 ms: 1.02x faster                                                 |
| async_generators                 | 243 ms                                                           | 240 ms: 1.01x faster                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.29 sec: 1.00x slower                                               |
| asyncio_websockets               | 305 ms                                                           | 310 ms: 1.02x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.07x faster                                                         |

Benchmark hidden because not significant (1): coroutines

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 17.9 ns: 1.05x faster                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 170 ms: 1.00x faster                                                 |
| decimal_pi        | 201 ms                                                           | 202 ms: 1.00x slower                                                 |
| Geometric mean    | (ref)                                                            | 1.00x faster                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| quadtree_nbody | 602 ms                                                           | 557 ms: 1.08x faster                                                 |
| nbody          | 67.2 ms                                                          | 62.3 ms: 1.08x faster                                                |
| pidigits       | 181 ms                                                           | 182 ms: 1.00x slower                                                 |
| float          | 48.1 ms                                                          | 48.8 ms: 1.01x slower                                                |
| Geometric mean | (ref)                                                            | 1.04x faster                                                         |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_compile  | 91.6 ms                                                          | 91.3 ms: 1.00x faster                                                |
| regex_effbot   | 1.80 ms                                                          | 1.82 ms: 1.01x slower                                                |
| regex_v8       | 15.0 ms                                                          | 15.2 ms: 1.01x slower                                                |
| regex_dna      | 141 ms                                                           | 144 ms: 1.02x slower                                                 |
| Geometric mean | (ref)                                                            | 1.01x slower                                                         |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| json_dumps           | 7.37 ms                                                          | 6.50 ms: 1.13x faster                                                |
| xml_etree_iterparse  | 76.5 ms                                                          | 69.5 ms: 1.10x faster                                                |
| base64_large         | 6.31 ms                                                          | 5.82 ms: 1.08x faster                                                |
| base16_large         | 5.41 ms                                                          | 5.08 ms: 1.06x faster                                                |
| xml_etree_generate   | 71.1 ms                                                          | 68.6 ms: 1.04x faster                                                |
| xml_etree_process    | 50.0 ms                                                          | 48.6 ms: 1.03x faster                                                |
| unpickle_list        | 3.64 us                                                          | 3.55 us: 1.03x faster                                                |
| base64_small         | 230 us                                                           | 225 us: 1.02x faster                                                 |
| tomli_loads          | 1.41 sec                                                         | 1.38 sec: 1.02x faster                                               |
| urlsafe_base64_small | 383 us                                                           | 377 us: 1.01x faster                                                 |
| ascii85_large        | 651 ms                                                           | 642 ms: 1.01x faster                                                 |
| xml_etree_parse      | 102 ms                                                           | 101 ms: 1.01x faster                                                 |
| unpickle             | 10.3 us                                                          | 10.2 us: 1.01x faster                                                |
| json_loads           | 17.3 us                                                          | 17.2 us: 1.01x faster                                                |
| ascii85_small        | 12.5 ms                                                          | 12.4 ms: 1.01x faster                                                |
| base32_large         | 276 ms                                                           | 277 ms: 1.00x slower                                                 |
| base85_small         | 4.44 ms                                                          | 4.48 ms: 1.01x slower                                                |
| unpickle_pure_python | 153 us                                                           | 154 us: 1.01x slower                                                 |
| pickle_list          | 3.26 us                                                          | 3.29 us: 1.01x slower                                                |
| pickle_pure_python   | 234 us                                                           | 237 us: 1.01x slower                                                 |
| base85_large         | 233 ms                                                           | 237 ms: 1.02x slower                                                 |
| pickle               | 9.23 us                                                          | 9.48 us: 1.03x slower                                                |
| base32_small         | 5.43 ms                                                          | 5.64 ms: 1.04x slower                                                |
| base16_small         | 298 us                                                           | 313 us: 1.05x slower                                                 |
| Geometric mean       | (ref)                                                            | 1.02x faster                                                         |

Benchmark hidden because not significant (1): pickle_dict

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 9.33 ms: 1.03x faster                                                |
| python_startup_no_site | 6.29 ms                                                          | 6.18 ms: 1.02x faster                                                |
| Geometric mean         | (ref)                                                            | 1.02x faster                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| mako            | 7.66 ms                                                          | 7.39 ms: 1.04x faster                                                |
| genshi_text     | 16.4 ms                                                          | 16.0 ms: 1.03x faster                                                |
| django_template | 28.4 ms                                                          | 28.0 ms: 1.01x faster                                                |
| Geometric mean  | (ref)                                                            | 1.02x faster                                                         |

Benchmark hidden because not significant (1): genshi_xml

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_memo_naive           | 11.8 ms                                                          | 9.79 ms: 1.21x faster                                                |
| thread_mandelbrot_naive     | 217 ms                                                           | 202 ms: 1.07x faster                                                 |
| thread_mandelbrot_optimized | 215 ms                                                           | 202 ms: 1.06x faster                                                 |
| thread_montecarlo_naive     | 14.6 ms                                                          | 14.1 ms: 1.04x faster                                                |
| thread_montecarlo_optimized | 12.6 ms                                                          | 12.3 ms: 1.03x faster                                                |
| thread_pipeline_naive       | 35.4 ms                                                          | 36.8 ms: 1.04x slower                                                |
| thread_counter_naive        | 21.4 ms                                                          | 22.6 ms: 1.05x slower                                                |
| thread_memo_optimized       | 17.9 ms                                                          | 19.0 ms: 1.06x slower                                                |
| thread_accumulate_optimized | 40.8 ms                                                          | 43.6 ms: 1.07x slower                                                |
| thread_accumulate_naive     | 41.6 ms                                                          | 45.3 ms: 1.09x slower                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 20.5 ms: 1.09x slower                                                |
| thread_pipeline_optimized   | 26.3 ms                                                          | 29.0 ms: 1.10x slower                                                |
| Geometric mean              | (ref)                                                            | 1.01x slower                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_memo_naive                | 11.8 ms                                                          | 9.79 ms: 1.21x faster                                                |
| async_tree_eager_io_tg           | 549 ms                                                           | 462 ms: 1.19x faster                                                 |
| pathlib                          | 12.5 ms                                                          | 10.6 ms: 1.19x faster                                                |
| async_tree_eager_io              | 548 ms                                                           | 467 ms: 1.17x faster                                                 |
| async_tree_none                  | 223 ms                                                           | 196 ms: 1.14x faster                                                 |
| json_dumps                       | 7.37 ms                                                          | 6.50 ms: 1.13x faster                                                |
| async_tree_io                    | 527 ms                                                           | 468 ms: 1.13x faster                                                 |
| async_tree_none_tg               | 221 ms                                                           | 199 ms: 1.11x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 393 ms: 1.11x faster                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 479 ms: 1.10x faster                                                 |
| xml_etree_iterparse              | 76.5 ms                                                          | 69.5 ms: 1.10x faster                                                |
| asyncio_tcp                      | 332 ms                                                           | 303 ms: 1.10x faster                                                 |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 394 ms: 1.09x faster                                                 |
| deepcopy_memo                    | 18.2 us                                                          | 16.8 us: 1.09x faster                                                |
| base64_large                     | 6.31 ms                                                          | 5.82 ms: 1.08x faster                                                |
| quadtree_nbody                   | 602 ms                                                           | 557 ms: 1.08x faster                                                 |
| nbody                            | 67.2 ms                                                          | 62.3 ms: 1.08x faster                                                |
| logging_simple                   | 4.72 us                                                          | 4.38 us: 1.08x faster                                                |
| async_tree_memoization           | 274 ms                                                           | 255 ms: 1.08x faster                                                 |
| async_tree_eager_memoization     | 175 ms                                                           | 163 ms: 1.07x faster                                                 |
| thread_mandelbrot_naive          | 217 ms                                                           | 202 ms: 1.07x faster                                                 |
| deepcopy                         | 195 us                                                           | 183 us: 1.07x faster                                                 |
| telco                            | 5.26 ms                                                          | 4.94 ms: 1.06x faster                                                |
| base16_large                     | 5.41 ms                                                          | 5.08 ms: 1.06x faster                                                |
| thread_mandelbrot_optimized      | 215 ms                                                           | 202 ms: 1.06x faster                                                 |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 222 ms: 1.06x faster                                                 |
| async_tree_memoization_tg        | 275 ms                                                           | 259 ms: 1.06x faster                                                 |
| comprehensions                   | 11.2 us                                                          | 10.5 us: 1.06x faster                                                |
| chaos                            | 41.9 ms                                                          | 39.6 ms: 1.06x faster                                                |
| scimark_fft                      | 197 ms                                                           | 187 ms: 1.06x faster                                                 |
| spectral_norm                    | 59.6 ms                                                          | 56.8 ms: 1.05x faster                                                |
| noop                             | 18.7 ns                                                          | 17.9 ns: 1.05x faster                                                |
| nqueens                          | 56.3 ms                                                          | 53.9 ms: 1.04x faster                                                |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 2.47 ms: 1.04x faster                                                |
| logging_format                   | 5.24 us                                                          | 5.03 us: 1.04x faster                                                |
| thread_montecarlo_naive          | 14.6 ms                                                          | 14.1 ms: 1.04x faster                                                |
| richards                         | 32.5 ms                                                          | 31.3 ms: 1.04x faster                                                |
| tornado_http                     | 101 ms                                                           | 97.0 ms: 1.04x faster                                                |
| mako                             | 7.66 ms                                                          | 7.39 ms: 1.04x faster                                                |
| deepcopy_reduce                  | 2.05 us                                                          | 1.97 us: 1.04x faster                                                |
| xml_etree_generate               | 71.1 ms                                                          | 68.6 ms: 1.04x faster                                                |
| pylint                           | 215 ms                                                           | 208 ms: 1.04x faster                                                 |
| scimark_lu                       | 66.7 ms                                                          | 64.4 ms: 1.04x faster                                                |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 372 ms: 1.03x faster                                                 |
| mdp                              | 935 ms                                                           | 905 ms: 1.03x faster                                                 |
| pprint_safe_repr                 | 484 ms                                                           | 468 ms: 1.03x faster                                                 |
| scimark_monte_carlo              | 37.5 ms                                                          | 36.3 ms: 1.03x faster                                                |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 75.5 ms: 1.03x faster                                                |
| richards_super                   | 37.2 ms                                                          | 36.1 ms: 1.03x faster                                                |
| python_startup                   | 9.62 ms                                                          | 9.33 ms: 1.03x faster                                                |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.12 ms: 1.03x faster                                                |
| xdsl_constant_fold               | 35.1 ms                                                          | 34.1 ms: 1.03x faster                                                |
| typing_runtime_protocols         | 106 us                                                           | 103 us: 1.03x faster                                                 |
| mypy2                            | 756 ms                                                           | 734 ms: 1.03x faster                                                 |
| xml_etree_process                | 50.0 ms                                                          | 48.6 ms: 1.03x faster                                                |
| html5lib                         | 45.5 ms                                                          | 44.2 ms: 1.03x faster                                                |
| async_tree_eager                 | 78.8 ms                                                          | 76.7 ms: 1.03x faster                                                |
| raytrace                         | 194 ms                                                           | 189 ms: 1.03x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 324 ms: 1.03x faster                                                 |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 12.3 ms: 1.03x faster                                                |
| unpickle_list                    | 3.64 us                                                          | 3.55 us: 1.03x faster                                                |
| genshi_text                      | 16.4 ms                                                          | 16.0 ms: 1.03x faster                                                |
| pyflate                          | 300 ms                                                           | 293 ms: 1.02x faster                                                 |
| pprint_pformat                   | 982 ms                                                           | 959 ms: 1.02x faster                                                 |
| coverage                         | 55.4 ms                                                          | 54.1 ms: 1.02x faster                                                |
| chameleon                        | 10.6 ms                                                          | 10.4 ms: 1.02x faster                                                |
| base64_small                     | 230 us                                                           | 225 us: 1.02x faster                                                 |
| fastapi_http                     | 215 ms                                                           | 210 ms: 1.02x faster                                                 |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.04 sec: 1.02x faster                                               |
| scimark_sor                      | 72.8 ms                                                          | 71.3 ms: 1.02x faster                                                |
| crypto_pyaes                     | 51.5 ms                                                          | 50.5 ms: 1.02x faster                                                |
| go                               | 82.6 ms                                                          | 81.1 ms: 1.02x faster                                                |
| python_startup_no_site           | 6.29 ms                                                          | 6.18 ms: 1.02x faster                                                |
| tomli_loads                      | 1.41 sec                                                         | 1.38 sec: 1.02x faster                                               |
| async_tree_eager_tg              | 179 ms                                                           | 176 ms: 1.02x faster                                                 |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 38.1 ms: 1.02x faster                                                |
| urlsafe_base64_small             | 383 us                                                           | 377 us: 1.01x faster                                                 |
| django_template                  | 28.4 ms                                                          | 28.0 ms: 1.01x faster                                                |
| ascii85_large                    | 651 ms                                                           | 642 ms: 1.01x faster                                                 |
| async_generators                 | 243 ms                                                           | 240 ms: 1.01x faster                                                 |
| fannkuch                         | 234 ms                                                           | 231 ms: 1.01x faster                                                 |
| xml_etree_parse                  | 102 ms                                                           | 101 ms: 1.01x faster                                                 |
| docutils                         | 2.02 sec                                                         | 2.00 sec: 1.01x faster                                               |
| unpickle                         | 10.3 us                                                          | 10.2 us: 1.01x faster                                                |
| json_loads                       | 17.3 us                                                          | 17.2 us: 1.01x faster                                                |
| gc_traversal                     | 3.33 ms                                                          | 3.30 ms: 1.01x faster                                                |
| hexiom                           | 4.00 ms                                                          | 3.97 ms: 1.01x faster                                                |
| pycparser                        | 837 ms                                                           | 831 ms: 1.01x faster                                                 |
| ascii85_small                    | 12.5 ms                                                          | 12.4 ms: 1.01x faster                                                |
| regex_compile                    | 91.6 ms                                                          | 91.3 ms: 1.00x faster                                                |
| decimal_factorial                | 170 ms                                                           | 170 ms: 1.00x faster                                                 |
| sympy_str                        | 192 ms                                                           | 191 ms: 1.00x faster                                                 |
| pidigits                         | 181 ms                                                           | 182 ms: 1.00x slower                                                 |
| decimal_pi                       | 201 ms                                                           | 202 ms: 1.00x slower                                                 |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.29 sec: 1.00x slower                                               |
| sympy_expand                     | 330 ms                                                           | 331 ms: 1.00x slower                                                 |
| base32_large                     | 276 ms                                                           | 277 ms: 1.00x slower                                                 |
| sympy_integrate                  | 14.7 ms                                                          | 14.8 ms: 1.01x slower                                                |
| meteor_contest                   | 83.9 ms                                                          | 84.5 ms: 1.01x slower                                                |
| base85_small                     | 4.44 ms                                                          | 4.48 ms: 1.01x slower                                                |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                                 |
| unpickle_pure_python             | 153 us                                                           | 154 us: 1.01x slower                                                 |
| json                             | 3.42 ms                                                          | 3.46 ms: 1.01x slower                                                |
| regex_effbot                     | 1.80 ms                                                          | 1.82 ms: 1.01x slower                                                |
| pickle_list                      | 3.26 us                                                          | 3.29 us: 1.01x slower                                                |
| regex_v8                         | 15.0 ms                                                          | 15.2 ms: 1.01x slower                                                |
| pickle_pure_python               | 234 us                                                           | 237 us: 1.01x slower                                                 |
| thrift                           | 1.84 ms                                                          | 1.86 ms: 1.01x slower                                                |
| float                            | 48.1 ms                                                          | 48.8 ms: 1.01x slower                                                |
| deltablue                        | 2.24 ms                                                          | 2.28 ms: 1.02x slower                                                |
| argparse_many_optionals          | 33.3 ms                                                          | 33.8 ms: 1.02x slower                                                |
| base85_large                     | 233 ms                                                           | 237 ms: 1.02x slower                                                 |
| asyncio_websockets               | 305 ms                                                           | 310 ms: 1.02x slower                                                 |
| regex_dna                        | 141 ms                                                           | 144 ms: 1.02x slower                                                 |
| pickle                           | 9.23 us                                                          | 9.48 us: 1.03x slower                                                |
| logging_silent                   | 59.7 ns                                                          | 61.3 ns: 1.03x slower                                                |
| unpack_sequence                  | 24.1 ns                                                          | 25.0 ns: 1.04x slower                                                |
| base32_small                     | 5.43 ms                                                          | 5.64 ms: 1.04x slower                                                |
| thread_pipeline_naive            | 35.4 ms                                                          | 36.8 ms: 1.04x slower                                                |
| base16_small                     | 298 us                                                           | 313 us: 1.05x slower                                                 |
| thread_counter_naive             | 21.4 ms                                                          | 22.6 ms: 1.05x slower                                                |
| thread_memo_optimized            | 17.9 ms                                                          | 19.0 ms: 1.06x slower                                                |
| thread_accumulate_optimized      | 40.8 ms                                                          | 43.6 ms: 1.07x slower                                                |
| thread_accumulate_naive          | 41.6 ms                                                          | 45.3 ms: 1.09x slower                                                |
| thread_counter_optimized         | 18.7 ms                                                          | 20.5 ms: 1.09x slower                                                |
| thread_pipeline_optimized        | 26.3 ms                                                          | 29.0 ms: 1.10x slower                                                |
| Geometric mean                   | (ref)                                                            | 1.03x faster                                                         |

Benchmark hidden because not significant (8): sqlalchemy_imperative, sqlglot_v2_parse, pickle_dict, argparse_subparsers, create_gc_cycles, genshi_xml, coroutines, generators
Ignored benchmarks (3) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json: networkx_connected_components, networkx_k_core, networkx_shortest_path

- Geometric mean (including insignificant results): 1.026x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.01x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.01x