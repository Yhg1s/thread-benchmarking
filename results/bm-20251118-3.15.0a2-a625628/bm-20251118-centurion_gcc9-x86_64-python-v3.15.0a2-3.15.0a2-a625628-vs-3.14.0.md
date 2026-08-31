# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.007x faster
- HPT reliability: 68.50%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 9.74 ms: 1.02x slower                                               |
| docutils       | 1.95 sec                                                        | 1.96 sec: 1.01x slower                                              |
| fastapi_http   | 216 ms                                                          | 220 ms: 1.02x slower                                                |
| html5lib       | 46.9 ms                                                         | 45.1 ms: 1.04x faster                                               |
| tornado_http   | 101 ms                                                          | 98.7 ms: 1.03x faster                                               |
| Geometric mean | (ref)                                                           | 1.00x faster                                                        |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 550 ms                                                          | 464 ms: 1.19x faster                                                |
| async_tree_eager_io              | 552 ms                                                          | 472 ms: 1.17x faster                                                |
| async_tree_none                  | 228 ms                                                          | 200 ms: 1.14x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 479 ms: 1.13x faster                                                |
| async_tree_io                    | 531 ms                                                          | 472 ms: 1.12x faster                                                |
| async_tree_none_tg               | 223 ms                                                          | 199 ms: 1.12x faster                                                |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 369 ms: 1.11x faster                                                |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 372 ms: 1.10x faster                                                |
| asyncio_tcp                      | 325 ms                                                          | 298 ms: 1.09x faster                                                |
| async_tree_memoization           | 281 ms                                                          | 259 ms: 1.09x faster                                                |
| async_tree_eager_memoization     | 180 ms                                                          | 166 ms: 1.08x faster                                                |
| async_tree_memoization_tg        | 277 ms                                                          | 262 ms: 1.06x faster                                                |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 225 ms: 1.05x faster                                                |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 349 ms: 1.04x faster                                                |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 304 ms: 1.03x faster                                                |
| async_tree_eager                 | 81.3 ms                                                         | 79.0 ms: 1.03x faster                                               |
| async_generators                 | 228 ms                                                          | 223 ms: 1.02x faster                                                |
| async_tree_eager_tg              | 182 ms                                                          | 179 ms: 1.02x faster                                                |
| coroutines                       | 15.1 ms                                                         | 15.8 ms: 1.05x slower                                               |
| asyncio_websockets               | 296 ms                                                          | 309 ms: 1.05x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.07x faster                                                        |

Benchmark hidden because not significant (1): asyncio_tcp_ssl

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 21.7 ns: 1.12x slower                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 174 ms: 1.00x slower                                                |
| Geometric mean    | (ref)                                                           | 1.00x slower                                                        |

Benchmark hidden because not significant (1): decimal_pi

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 188 ms: 1.01x faster                                                |
| float          | 47.3 ms                                                         | 49.5 ms: 1.05x slower                                               |
| nbody          | 67.9 ms                                                         | 75.3 ms: 1.11x slower                                               |
| Geometric mean | (ref)                                                           | 1.04x slower                                                        |

Benchmark hidden because not significant (1): quadtree_nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_compile  | 93.9 ms                                                         | 95.0 ms: 1.01x slower                                               |
| regex_dna      | 150 ms                                                          | 153 ms: 1.02x slower                                                |
| regex_effbot   | 1.95 ms                                                         | 1.99 ms: 1.02x slower                                               |
| regex_v8       | 14.8 ms                                                         | 15.4 ms: 1.04x slower                                               |
| Geometric mean | (ref)                                                           | 1.02x slower                                                        |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| base16_large         | 5.33 ms                                                         | 4.80 ms: 1.11x faster                                               |
| xml_etree_iterparse  | 76.2 ms                                                         | 70.0 ms: 1.09x faster                                               |
| json_loads           | 17.5 us                                                         | 16.2 us: 1.08x faster                                               |
| base64_small         | 186 us                                                          | 177 us: 1.05x faster                                                |
| base64_large         | 3.63 ms                                                         | 3.49 ms: 1.04x faster                                               |
| pickle_list          | 3.24 us                                                         | 3.17 us: 1.02x faster                                               |
| base16_small         | 305 us                                                          | 299 us: 1.02x faster                                                |
| urlsafe_base64_small | 329 us                                                          | 322 us: 1.02x faster                                                |
| json_dumps           | 6.95 ms                                                         | 6.82 ms: 1.02x faster                                               |
| pickle_dict          | 21.5 us                                                         | 21.3 us: 1.01x faster                                               |
| xml_etree_generate   | 62.6 ms                                                         | 62.2 ms: 1.01x faster                                               |
| xml_etree_parse      | 94.3 ms                                                         | 93.9 ms: 1.00x faster                                               |
| ascii85_large        | 667 ms                                                          | 669 ms: 1.00x slower                                                |
| pickle               | 8.20 us                                                         | 8.24 us: 1.00x slower                                               |
| xml_etree_process    | 44.7 ms                                                         | 45.1 ms: 1.01x slower                                               |
| pickle_pure_python   | 240 us                                                          | 242 us: 1.01x slower                                                |
| base85_small         | 4.69 ms                                                         | 4.77 ms: 1.02x slower                                               |
| ascii85_small        | 12.7 ms                                                         | 12.9 ms: 1.02x slower                                               |
| base85_large         | 248 ms                                                          | 254 ms: 1.03x slower                                                |
| unpickle             | 10.2 us                                                         | 10.5 us: 1.03x slower                                               |
| base32_large         | 292 ms                                                          | 305 ms: 1.04x slower                                                |
| unpickle_pure_python | 152 us                                                          | 159 us: 1.05x slower                                                |
| tomli_loads          | 1.44 sec                                                        | 1.53 sec: 1.06x slower                                              |
| base32_small         | 5.71 ms                                                         | 6.06 ms: 1.06x slower                                               |
| Geometric mean       | (ref)                                                           | 1.01x faster                                                        |

Benchmark hidden because not significant (1): unpickle_list

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 9.41 ms: 1.03x faster                                               |
| python_startup_no_site | 6.38 ms                                                         | 6.26 ms: 1.02x faster                                               |
| Geometric mean         | (ref)                                                           | 1.03x faster                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| mako            | 7.40 ms                                                         | 7.47 ms: 1.01x slower                                               |
| genshi_xml      | 39.5 ms                                                         | 40.3 ms: 1.02x slower                                               |
| django_template | 27.8 ms                                                         | 29.1 ms: 1.05x slower                                               |
| Geometric mean  | (ref)                                                           | 1.02x slower                                                        |

Benchmark hidden because not significant (1): genshi_text

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_memo_naive           | 11.5 ms                                                         | 9.82 ms: 1.17x faster                                               |
| thread_mandelbrot_naive     | 233 ms                                                          | 225 ms: 1.04x faster                                                |
| thread_montecarlo_optimized | 13.9 ms                                                         | 13.6 ms: 1.02x faster                                               |
| thread_montecarlo_naive     | 15.8 ms                                                         | 15.6 ms: 1.01x faster                                               |
| thread_mandelbrot_optimized | 233 ms                                                          | 232 ms: 1.01x faster                                                |
| thread_counter_naive        | 20.2 ms                                                         | 21.5 ms: 1.06x slower                                               |
| thread_accumulate_naive     | 35.8 ms                                                         | 38.7 ms: 1.08x slower                                               |
| thread_memo_optimized       | 15.9 ms                                                         | 17.4 ms: 1.09x slower                                               |
| thread_pipeline_naive       | 32.0 ms                                                         | 35.1 ms: 1.10x slower                                               |
| thread_accumulate_optimized | 35.1 ms                                                         | 38.7 ms: 1.10x slower                                               |
| thread_counter_optimized    | 17.1 ms                                                         | 19.7 ms: 1.15x slower                                               |
| thread_pipeline_optimized   | 22.5 ms                                                         | 26.3 ms: 1.17x slower                                               |
| Geometric mean              | (ref)                                                           | 1.04x slower                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 550 ms                                                          | 464 ms: 1.19x faster                                                |
| thread_memo_naive                | 11.5 ms                                                         | 9.82 ms: 1.17x faster                                               |
| async_tree_eager_io              | 552 ms                                                          | 472 ms: 1.17x faster                                                |
| pathlib                          | 13.0 ms                                                         | 11.3 ms: 1.15x faster                                               |
| async_tree_none                  | 228 ms                                                          | 200 ms: 1.14x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 479 ms: 1.13x faster                                                |
| async_tree_io                    | 531 ms                                                          | 472 ms: 1.12x faster                                                |
| async_tree_none_tg               | 223 ms                                                          | 199 ms: 1.12x faster                                                |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 369 ms: 1.11x faster                                                |
| base16_large                     | 5.33 ms                                                         | 4.80 ms: 1.11x faster                                               |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 372 ms: 1.10x faster                                                |
| asyncio_tcp                      | 325 ms                                                          | 298 ms: 1.09x faster                                                |
| xml_etree_iterparse              | 76.2 ms                                                         | 70.0 ms: 1.09x faster                                               |
| async_tree_memoization           | 281 ms                                                          | 259 ms: 1.09x faster                                                |
| async_tree_eager_memoization     | 180 ms                                                          | 166 ms: 1.08x faster                                                |
| telco                            | 5.59 ms                                                         | 5.18 ms: 1.08x faster                                               |
| json_loads                       | 17.5 us                                                         | 16.2 us: 1.08x faster                                               |
| async_tree_memoization_tg        | 277 ms                                                          | 262 ms: 1.06x faster                                                |
| deepcopy_memo                    | 18.0 us                                                         | 17.0 us: 1.06x faster                                               |
| scimark_fft                      | 226 ms                                                          | 215 ms: 1.05x faster                                                |
| base64_small                     | 186 us                                                          | 177 us: 1.05x faster                                                |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 225 ms: 1.05x faster                                                |
| logging_silent                   | 65.3 ns                                                         | 62.6 ns: 1.04x faster                                               |
| base64_large                     | 3.63 ms                                                         | 3.49 ms: 1.04x faster                                               |
| html5lib                         | 46.9 ms                                                         | 45.1 ms: 1.04x faster                                               |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 349 ms: 1.04x faster                                                |
| deepcopy                         | 193 us                                                          | 185 us: 1.04x faster                                                |
| thread_mandelbrot_naive          | 233 ms                                                          | 225 ms: 1.04x faster                                                |
| fannkuch                         | 245 ms                                                          | 237 ms: 1.04x faster                                                |
| logging_simple                   | 4.79 us                                                         | 4.63 us: 1.03x faster                                               |
| python_startup                   | 9.73 ms                                                         | 9.41 ms: 1.03x faster                                               |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 304 ms: 1.03x faster                                                |
| async_tree_eager                 | 81.3 ms                                                         | 79.0 ms: 1.03x faster                                               |
| scimark_sor                      | 75.7 ms                                                         | 73.6 ms: 1.03x faster                                               |
| tornado_http                     | 101 ms                                                          | 98.7 ms: 1.03x faster                                               |
| pickle_list                      | 3.24 us                                                         | 3.17 us: 1.02x faster                                               |
| base16_small                     | 305 us                                                          | 299 us: 1.02x faster                                                |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 13.6 ms: 1.02x faster                                               |
| async_generators                 | 228 ms                                                          | 223 ms: 1.02x faster                                                |
| argparse_subparsers              | 686 us                                                          | 672 us: 1.02x faster                                                |
| urlsafe_base64_small             | 329 us                                                          | 322 us: 1.02x faster                                                |
| deepcopy_reduce                  | 2.00 us                                                         | 1.96 us: 1.02x faster                                               |
| json                             | 3.42 ms                                                         | 3.36 ms: 1.02x faster                                               |
| python_startup_no_site           | 6.38 ms                                                         | 6.26 ms: 1.02x faster                                               |
| async_tree_eager_tg              | 182 ms                                                          | 179 ms: 1.02x faster                                                |
| json_dumps                       | 6.95 ms                                                         | 6.82 ms: 1.02x faster                                               |
| logging_format                   | 5.35 us                                                         | 5.25 us: 1.02x faster                                               |
| mypy2                            | 753 ms                                                          | 742 ms: 1.01x faster                                                |
| gc_traversal                     | 3.26 ms                                                         | 3.22 ms: 1.01x faster                                               |
| thread_montecarlo_naive          | 15.8 ms                                                         | 15.6 ms: 1.01x faster                                               |
| chaos                            | 43.8 ms                                                         | 43.2 ms: 1.01x faster                                               |
| argparse_many_optionals          | 34.4 ms                                                         | 34.0 ms: 1.01x faster                                               |
| unpack_sequence                  | 25.8 ns                                                         | 25.5 ns: 1.01x faster                                               |
| richards                         | 32.6 ms                                                         | 32.3 ms: 1.01x faster                                               |
| comprehensions                   | 10.8 us                                                         | 10.7 us: 1.01x faster                                               |
| pprint_pformat                   | 989 ms                                                          | 978 ms: 1.01x faster                                                |
| pickle_dict                      | 21.5 us                                                         | 21.3 us: 1.01x faster                                               |
| xml_etree_generate               | 62.6 ms                                                         | 62.2 ms: 1.01x faster                                               |
| xdsl_constant_fold               | 34.7 ms                                                         | 34.5 ms: 1.01x faster                                               |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.14 ms: 1.01x faster                                               |
| pidigits                         | 189 ms                                                          | 188 ms: 1.01x faster                                                |
| thread_mandelbrot_optimized      | 233 ms                                                          | 232 ms: 1.01x faster                                                |
| crypto_pyaes                     | 54.5 ms                                                         | 54.2 ms: 1.00x faster                                               |
| xml_etree_parse                  | 94.3 ms                                                         | 93.9 ms: 1.00x faster                                               |
| ascii85_large                    | 667 ms                                                          | 669 ms: 1.00x slower                                                |
| decimal_factorial                | 173 ms                                                          | 174 ms: 1.00x slower                                                |
| mdp                              | 946 ms                                                          | 949 ms: 1.00x slower                                                |
| pickle                           | 8.20 us                                                         | 8.24 us: 1.00x slower                                               |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.02 sec: 1.01x slower                                              |
| sympy_integrate                  | 15.4 ms                                                         | 15.5 ms: 1.01x slower                                               |
| sympy_sum                        | 106 ms                                                          | 107 ms: 1.01x slower                                                |
| xml_etree_process                | 44.7 ms                                                         | 45.1 ms: 1.01x slower                                               |
| nqueens                          | 56.8 ms                                                         | 57.3 ms: 1.01x slower                                               |
| pickle_pure_python               | 240 us                                                          | 242 us: 1.01x slower                                                |
| docutils                         | 1.95 sec                                                        | 1.96 sec: 1.01x slower                                              |
| mako                             | 7.40 ms                                                         | 7.47 ms: 1.01x slower                                               |
| scimark_lu                       | 73.8 ms                                                         | 74.7 ms: 1.01x slower                                               |
| regex_compile                    | 93.9 ms                                                         | 95.0 ms: 1.01x slower                                               |
| go                               | 84.7 ms                                                         | 85.7 ms: 1.01x slower                                               |
| sympy_expand                     | 332 ms                                                          | 336 ms: 1.01x slower                                                |
| spectral_norm                    | 65.6 ms                                                         | 66.6 ms: 1.02x slower                                               |
| regex_dna                        | 150 ms                                                          | 153 ms: 1.02x slower                                                |
| sympy_str                        | 194 ms                                                          | 197 ms: 1.02x slower                                                |
| base85_small                     | 4.69 ms                                                         | 4.77 ms: 1.02x slower                                               |
| ascii85_small                    | 12.7 ms                                                         | 12.9 ms: 1.02x slower                                               |
| fastapi_http                     | 216 ms                                                          | 220 ms: 1.02x slower                                                |
| genshi_xml                       | 39.5 ms                                                         | 40.3 ms: 1.02x slower                                               |
| chameleon                        | 9.52 ms                                                         | 9.74 ms: 1.02x slower                                               |
| regex_effbot                     | 1.95 ms                                                         | 1.99 ms: 1.02x slower                                               |
| scimark_monte_carlo              | 40.7 ms                                                         | 41.7 ms: 1.02x slower                                               |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 40.0 ms: 1.02x slower                                               |
| raytrace                         | 194 ms                                                          | 199 ms: 1.03x slower                                                |
| base85_large                     | 248 ms                                                          | 254 ms: 1.03x slower                                                |
| pyflate                          | 299 ms                                                          | 309 ms: 1.03x slower                                                |
| unpickle                         | 10.2 us                                                         | 10.5 us: 1.03x slower                                               |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 80.8 ms: 1.03x slower                                               |
| thrift                           | 1.86 ms                                                         | 1.93 ms: 1.03x slower                                               |
| generators                       | 20.3 ms                                                         | 21.0 ms: 1.03x slower                                               |
| regex_v8                         | 14.8 ms                                                         | 15.4 ms: 1.04x slower                                               |
| meteor_contest                   | 84.1 ms                                                         | 87.6 ms: 1.04x slower                                               |
| pprint_safe_repr                 | 474 ms                                                          | 494 ms: 1.04x slower                                                |
| base32_large                     | 292 ms                                                          | 305 ms: 1.04x slower                                                |
| unpickle_pure_python             | 152 us                                                          | 159 us: 1.05x slower                                                |
| django_template                  | 27.8 ms                                                         | 29.1 ms: 1.05x slower                                               |
| coroutines                       | 15.1 ms                                                         | 15.8 ms: 1.05x slower                                               |
| asyncio_websockets               | 296 ms                                                          | 309 ms: 1.05x slower                                                |
| float                            | 47.3 ms                                                         | 49.5 ms: 1.05x slower                                               |
| deltablue                        | 2.34 ms                                                         | 2.45 ms: 1.05x slower                                               |
| tomli_loads                      | 1.44 sec                                                        | 1.53 sec: 1.06x slower                                              |
| thread_counter_naive             | 20.2 ms                                                         | 21.5 ms: 1.06x slower                                               |
| base32_small                     | 5.71 ms                                                         | 6.06 ms: 1.06x slower                                               |
| thread_accumulate_naive          | 35.8 ms                                                         | 38.7 ms: 1.08x slower                                               |
| thread_memo_optimized            | 15.9 ms                                                         | 17.4 ms: 1.09x slower                                               |
| thread_pipeline_naive            | 32.0 ms                                                         | 35.1 ms: 1.10x slower                                               |
| coverage                         | 57.4 ms                                                         | 63.1 ms: 1.10x slower                                               |
| thread_accumulate_optimized      | 35.1 ms                                                         | 38.7 ms: 1.10x slower                                               |
| nbody                            | 67.9 ms                                                         | 75.3 ms: 1.11x slower                                               |
| noop                             | 19.4 ns                                                         | 21.7 ns: 1.12x slower                                               |
| thread_counter_optimized         | 17.1 ms                                                         | 19.7 ms: 1.15x slower                                               |
| thread_pipeline_optimized        | 22.5 ms                                                         | 26.3 ms: 1.17x slower                                               |
| Geometric mean                   | (ref)                                                           | 1.01x faster                                                        |

Benchmark hidden because not significant (13): pylint, scimark_sparse_mat_mult, typing_runtime_protocols, decimal_pi, sqlglot_v2_parse, unpickle_list, asyncio_tcp_ssl, pycparser, create_gc_cycles, richards_super, hexiom, genshi_text, quadtree_nbody
Ignored benchmarks (4) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: networkx_connected_components, networkx_k_core, networkx_shortest_path, sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.007x faster

# HPT report

- Reliability score: 68.50% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.01x