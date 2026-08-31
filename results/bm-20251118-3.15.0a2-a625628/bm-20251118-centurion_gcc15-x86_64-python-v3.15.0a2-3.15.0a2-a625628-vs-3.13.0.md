# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.107x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.04x faster
- Memory change: 1.11x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 10.4 ms: 1.05x faster                                                |
| docutils       | 1.98 sec                                                         | 2.00 sec: 1.01x slower                                               |
| fastapi_http   | 215 ms                                                           | 210 ms: 1.02x faster                                                 |
| html5lib       | 49.1 ms                                                          | 44.2 ms: 1.11x faster                                                |
| tornado_http   | 99.2 ms                                                          | 97.0 ms: 1.02x faster                                                |
| Geometric mean | (ref)                                                            | 1.04x faster                                                         |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| async_tree_io_tg                 | 777 ms                                                           | 479 ms: 1.62x faster                                                 |
| async_tree_memoization_tg        | 417 ms                                                           | 259 ms: 1.61x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 467 ms: 1.60x faster                                                 |
| async_tree_io                    | 741 ms                                                           | 468 ms: 1.58x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 196 ms: 1.58x faster                                                 |
| async_tree_eager_io_tg           | 724 ms                                                           | 462 ms: 1.57x faster                                                 |
| async_tree_memoization           | 389 ms                                                           | 255 ms: 1.53x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 199 ms: 1.46x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 393 ms: 1.34x faster                                                 |
| async_tree_eager_memoization     | 215 ms                                                           | 163 ms: 1.32x faster                                                 |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 394 ms: 1.30x faster                                                 |
| async_tree_eager                 | 90.0 ms                                                          | 76.7 ms: 1.17x faster                                                |
| coroutines                       | 17.6 ms                                                          | 15.4 ms: 1.14x faster                                                |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 324 ms: 1.11x faster                                                 |
| async_generators                 | 262 ms                                                           | 240 ms: 1.09x faster                                                 |
| asyncio_tcp                      | 326 ms                                                           | 303 ms: 1.08x faster                                                 |
| asyncio_websockets               | 304 ms                                                           | 310 ms: 1.02x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 372 ms: 1.16x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 222 ms: 1.28x slower                                                 |
| async_tree_eager_tg              | 58.6 ms                                                          | 176 ms: 3.01x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.18x faster                                                         |

Benchmark hidden because not significant (1): asyncio_tcp_ssl

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 17.9 ns: 1.14x faster                                                |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 202 ms: 1.04x faster                                                 |
| decimal_factorial | 173 ms                                                           | 170 ms: 1.02x faster                                                 |
| Geometric mean    | (ref)                                                            | 1.03x faster                                                         |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 48.8 ms: 1.16x faster                                                |
| quadtree_nbody | 620 ms                                                           | 557 ms: 1.11x faster                                                 |
| nbody          | 66.8 ms                                                          | 62.3 ms: 1.07x faster                                                |
| pidigits       | 181 ms                                                           | 182 ms: 1.00x slower                                                 |
| Geometric mean | (ref)                                                            | 1.08x faster                                                         |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.82 ms: 1.10x faster                                                |
| regex_compile  | 97.7 ms                                                          | 91.3 ms: 1.07x faster                                                |
| regex_dna      | 144 ms                                                           | 144 ms: 1.00x slower                                                 |
| regex_v8       | 14.7 ms                                                          | 15.2 ms: 1.03x slower                                                |
| Geometric mean | (ref)                                                            | 1.03x faster                                                         |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.08 ms: 6.21x faster                                                |
| base16_small         | 656 us                                                           | 313 us: 2.09x faster                                                 |
| ascii85_large        | 814 ms                                                           | 642 ms: 1.27x faster                                                 |
| ascii85_small        | 15.5 ms                                                          | 12.4 ms: 1.25x faster                                                |
| tomli_loads          | 1.63 sec                                                         | 1.38 sec: 1.18x faster                                               |
| json_dumps           | 7.49 ms                                                          | 6.50 ms: 1.15x faster                                                |
| base64_large         | 6.32 ms                                                          | 5.82 ms: 1.08x faster                                                |
| xml_etree_parse      | 107 ms                                                           | 101 ms: 1.06x faster                                                 |
| base32_large         | 286 ms                                                           | 277 ms: 1.03x faster                                                 |
| pickle_dict          | 21.9 us                                                          | 21.2 us: 1.03x faster                                                |
| base85_large         | 243 ms                                                           | 237 ms: 1.03x faster                                                 |
| base64_small         | 228 us                                                           | 225 us: 1.01x faster                                                 |
| base32_small         | 5.69 ms                                                          | 5.64 ms: 1.01x faster                                                |
| urlsafe_base64_small | 379 us                                                           | 377 us: 1.00x faster                                                 |
| xml_etree_process    | 48.1 ms                                                          | 48.6 ms: 1.01x slower                                                |
| base85_small         | 4.41 ms                                                          | 4.48 ms: 1.02x slower                                                |
| json_loads           | 16.7 us                                                          | 17.2 us: 1.03x slower                                                |
| unpickle_list        | 3.45 us                                                          | 3.55 us: 1.03x slower                                                |
| xml_etree_generate   | 66.3 ms                                                          | 68.6 ms: 1.04x slower                                                |
| unpickle_pure_python | 149 us                                                           | 154 us: 1.04x slower                                                 |
| pickle_pure_python   | 223 us                                                           | 237 us: 1.06x slower                                                 |
| pickle_list          | 3.03 us                                                          | 3.29 us: 1.09x slower                                                |
| pickle               | 8.22 us                                                          | 9.48 us: 1.15x slower                                                |
| Geometric mean       | (ref)                                                            | 1.13x faster                                                         |

Benchmark hidden because not significant (2): unpickle, xml_etree_iterparse

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 6.18 ms: 1.03x faster                                                |
| python_startup         | 9.38 ms                                                          | 9.33 ms: 1.00x faster                                                |
| Geometric mean         | (ref)                                                            | 1.02x faster                                                         |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| genshi_text     | 17.6 ms                                                          | 16.0 ms: 1.10x faster                                                |
| genshi_xml      | 39.7 ms                                                          | 38.5 ms: 1.03x faster                                                |
| mako            | 7.43 ms                                                          | 7.39 ms: 1.01x faster                                                |
| django_template | 27.3 ms                                                          | 28.0 ms: 1.03x slower                                                |
| Geometric mean  | (ref)                                                            | 1.03x faster                                                         |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 9.79 ms: 3.98x faster                                                |
| thread_pipeline_naive       | 52.1 ms                                                          | 36.8 ms: 1.41x faster                                                |
| thread_montecarlo_naive     | 17.8 ms                                                          | 14.1 ms: 1.27x faster                                                |
| thread_mandelbrot_naive     | 220 ms                                                           | 202 ms: 1.09x faster                                                 |
| thread_montecarlo_optimized | 13.3 ms                                                          | 12.3 ms: 1.08x faster                                                |
| thread_mandelbrot_optimized | 218 ms                                                           | 202 ms: 1.08x faster                                                 |
| thread_counter_naive        | 22.6 ms                                                          | 22.6 ms: 1.00x faster                                                |
| thread_memo_optimized       | 18.2 ms                                                          | 19.0 ms: 1.04x slower                                                |
| thread_counter_optimized    | 18.7 ms                                                          | 20.5 ms: 1.09x slower                                                |
| thread_accumulate_optimized | 39.8 ms                                                          | 43.6 ms: 1.10x slower                                                |
| thread_accumulate_naive     | 40.9 ms                                                          | 45.3 ms: 1.11x slower                                                |
| thread_pipeline_optimized   | 25.6 ms                                                          | 29.0 ms: 1.13x slower                                                |
| Geometric mean              | (ref)                                                            | 1.16x faster                                                         |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:----------------------------------------------------------------:|:--------------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.08 ms: 6.21x faster                                                |
| thread_memo_naive                | 39.0 ms                                                          | 9.79 ms: 3.98x faster                                                |
| mdp                              | 2.11 sec                                                         | 905 ms: 2.33x faster                                                 |
| base16_small                     | 656 us                                                           | 313 us: 2.09x faster                                                 |
| async_tree_io_tg                 | 777 ms                                                           | 479 ms: 1.62x faster                                                 |
| async_tree_memoization_tg        | 417 ms                                                           | 259 ms: 1.61x faster                                                 |
| async_tree_eager_io              | 749 ms                                                           | 467 ms: 1.60x faster                                                 |
| deepcopy_memo                    | 26.6 us                                                          | 16.8 us: 1.58x faster                                                |
| async_tree_io                    | 741 ms                                                           | 468 ms: 1.58x faster                                                 |
| async_tree_none                  | 310 ms                                                           | 196 ms: 1.58x faster                                                 |
| async_tree_eager_io_tg           | 724 ms                                                           | 462 ms: 1.57x faster                                                 |
| async_tree_memoization           | 389 ms                                                           | 255 ms: 1.53x faster                                                 |
| go                               | 121 ms                                                           | 81.1 ms: 1.49x faster                                                |
| deepcopy                         | 267 us                                                           | 183 us: 1.46x faster                                                 |
| async_tree_none_tg               | 289 ms                                                           | 199 ms: 1.46x faster                                                 |
| thread_pipeline_naive            | 52.1 ms                                                          | 36.8 ms: 1.41x faster                                                |
| scimark_sor                      | 97.0 ms                                                          | 71.3 ms: 1.36x faster                                                |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 393 ms: 1.34x faster                                                 |
| async_tree_eager_memoization     | 215 ms                                                           | 163 ms: 1.32x faster                                                 |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 394 ms: 1.30x faster                                                 |
| thread_montecarlo_naive          | 17.8 ms                                                          | 14.1 ms: 1.27x faster                                                |
| ascii85_large                    | 814 ms                                                           | 642 ms: 1.27x faster                                                 |
| ascii85_small                    | 15.5 ms                                                          | 12.4 ms: 1.25x faster                                                |
| pyflate                          | 358 ms                                                           | 293 ms: 1.22x faster                                                 |
| scimark_monte_carlo              | 44.3 ms                                                          | 36.3 ms: 1.22x faster                                                |
| deepcopy_reduce                  | 2.37 us                                                          | 1.97 us: 1.20x faster                                                |
| tomli_loads                      | 1.63 sec                                                         | 1.38 sec: 1.18x faster                                               |
| pathlib                          | 12.4 ms                                                          | 10.6 ms: 1.18x faster                                                |
| richards                         | 36.8 ms                                                          | 31.3 ms: 1.18x faster                                                |
| async_tree_eager                 | 90.0 ms                                                          | 76.7 ms: 1.17x faster                                                |
| float                            | 56.6 ms                                                          | 48.8 ms: 1.16x faster                                                |
| pprint_safe_repr                 | 541 ms                                                           | 468 ms: 1.16x faster                                                 |
| pprint_pformat                   | 1.11 sec                                                         | 959 ms: 1.15x faster                                                 |
| json_dumps                       | 7.49 ms                                                          | 6.50 ms: 1.15x faster                                                |
| fannkuch                         | 265 ms                                                           | 231 ms: 1.15x faster                                                 |
| richards_super                   | 41.3 ms                                                          | 36.1 ms: 1.14x faster                                                |
| noop                             | 20.4 ns                                                          | 17.9 ns: 1.14x faster                                                |
| coroutines                       | 17.6 ms                                                          | 15.4 ms: 1.14x faster                                                |
| chaos                            | 45.0 ms                                                          | 39.6 ms: 1.14x faster                                                |
| scimark_fft                      | 211 ms                                                           | 187 ms: 1.13x faster                                                 |
| spectral_norm                    | 64.1 ms                                                          | 56.8 ms: 1.13x faster                                                |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.04 sec: 1.12x faster                                               |
| telco                            | 5.50 ms                                                          | 4.94 ms: 1.11x faster                                                |
| quadtree_nbody                   | 620 ms                                                           | 557 ms: 1.11x faster                                                 |
| hexiom                           | 4.42 ms                                                          | 3.97 ms: 1.11x faster                                                |
| html5lib                         | 49.1 ms                                                          | 44.2 ms: 1.11x faster                                                |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 324 ms: 1.11x faster                                                 |
| thrift                           | 2.07 ms                                                          | 1.86 ms: 1.11x faster                                                |
| deltablue                        | 2.52 ms                                                          | 2.28 ms: 1.11x faster                                                |
| comprehensions                   | 11.6 us                                                          | 10.5 us: 1.10x faster                                                |
| genshi_text                      | 17.6 ms                                                          | 16.0 ms: 1.10x faster                                                |
| regex_effbot                     | 1.99 ms                                                          | 1.82 ms: 1.10x faster                                                |
| async_generators                 | 262 ms                                                           | 240 ms: 1.09x faster                                                 |
| scimark_lu                       | 70.2 ms                                                          | 64.4 ms: 1.09x faster                                                |
| thread_mandelbrot_naive          | 220 ms                                                           | 202 ms: 1.09x faster                                                 |
| pylint                           | 226 ms                                                           | 208 ms: 1.09x faster                                                 |
| base64_large                     | 6.32 ms                                                          | 5.82 ms: 1.08x faster                                                |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 12.3 ms: 1.08x faster                                                |
| asyncio_tcp                      | 326 ms                                                           | 303 ms: 1.08x faster                                                 |
| thread_mandelbrot_optimized      | 218 ms                                                           | 202 ms: 1.08x faster                                                 |
| xdsl_constant_fold               | 36.7 ms                                                          | 34.1 ms: 1.08x faster                                                |
| nbody                            | 66.8 ms                                                          | 62.3 ms: 1.07x faster                                                |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.47 ms: 1.07x faster                                                |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.12 ms: 1.07x faster                                                |
| regex_compile                    | 97.7 ms                                                          | 91.3 ms: 1.07x faster                                                |
| meteor_contest                   | 89.9 ms                                                          | 84.5 ms: 1.06x faster                                                |
| pycparser                        | 884 ms                                                           | 831 ms: 1.06x faster                                                 |
| nqueens                          | 57.3 ms                                                          | 53.9 ms: 1.06x faster                                                |
| xml_etree_parse                  | 107 ms                                                           | 101 ms: 1.06x faster                                                 |
| chameleon                        | 10.9 ms                                                          | 10.4 ms: 1.05x faster                                                |
| raytrace                         | 199 ms                                                           | 189 ms: 1.05x faster                                                 |
| sqlglot_v2_parse                 | 953 us                                                           | 907 us: 1.05x faster                                                 |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 38.1 ms: 1.05x faster                                                |
| unpack_sequence                  | 26.2 ns                                                          | 25.0 ns: 1.05x faster                                                |
| logging_simple                   | 4.60 us                                                          | 4.38 us: 1.05x faster                                                |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 75.5 ms: 1.05x faster                                                |
| generators                       | 22.0 ms                                                          | 21.1 ms: 1.04x faster                                                |
| sympy_integrate                  | 15.4 ms                                                          | 14.8 ms: 1.04x faster                                                |
| decimal_pi                       | 210 ms                                                           | 202 ms: 1.04x faster                                                 |
| logging_format                   | 5.23 us                                                          | 5.03 us: 1.04x faster                                                |
| genshi_xml                       | 39.7 ms                                                          | 38.5 ms: 1.03x faster                                                |
| base32_large                     | 286 ms                                                           | 277 ms: 1.03x faster                                                 |
| typing_runtime_protocols         | 106 us                                                           | 103 us: 1.03x faster                                                 |
| pickle_dict                      | 21.9 us                                                          | 21.2 us: 1.03x faster                                                |
| python_startup_no_site           | 6.36 ms                                                          | 6.18 ms: 1.03x faster                                                |
| base85_large                     | 243 ms                                                           | 237 ms: 1.03x faster                                                 |
| tornado_http                     | 99.2 ms                                                          | 97.0 ms: 1.02x faster                                                |
| fastapi_http                     | 215 ms                                                           | 210 ms: 1.02x faster                                                 |
| decimal_factorial                | 173 ms                                                           | 170 ms: 1.02x faster                                                 |
| base64_small                     | 228 us                                                           | 225 us: 1.01x faster                                                 |
| json                             | 3.49 ms                                                          | 3.46 ms: 1.01x faster                                                |
| sympy_str                        | 193 ms                                                           | 191 ms: 1.01x faster                                                 |
| base32_small                     | 5.69 ms                                                          | 5.64 ms: 1.01x faster                                                |
| mako                             | 7.43 ms                                                          | 7.39 ms: 1.01x faster                                                |
| python_startup                   | 9.38 ms                                                          | 9.33 ms: 1.00x faster                                                |
| urlsafe_base64_small             | 379 us                                                           | 377 us: 1.00x faster                                                 |
| thread_counter_naive             | 22.6 ms                                                          | 22.6 ms: 1.00x faster                                                |
| pidigits                         | 181 ms                                                           | 182 ms: 1.00x slower                                                 |
| sympy_expand                     | 330 ms                                                           | 331 ms: 1.00x slower                                                 |
| regex_dna                        | 144 ms                                                           | 144 ms: 1.00x slower                                                 |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                                 |
| xml_etree_process                | 48.1 ms                                                          | 48.6 ms: 1.01x slower                                                |
| docutils                         | 1.98 sec                                                         | 2.00 sec: 1.01x slower                                               |
| crypto_pyaes                     | 50.0 ms                                                          | 50.5 ms: 1.01x slower                                                |
| logging_silent                   | 60.6 ns                                                          | 61.3 ns: 1.01x slower                                                |
| mypy2                            | 726 ms                                                           | 734 ms: 1.01x slower                                                 |
| base85_small                     | 4.41 ms                                                          | 4.48 ms: 1.02x slower                                                |
| asyncio_websockets               | 304 ms                                                           | 310 ms: 1.02x slower                                                 |
| django_template                  | 27.3 ms                                                          | 28.0 ms: 1.03x slower                                                |
| json_loads                       | 16.7 us                                                          | 17.2 us: 1.03x slower                                                |
| unpickle_list                    | 3.45 us                                                          | 3.55 us: 1.03x slower                                                |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.2 ms: 1.03x slower                                                |
| regex_v8                         | 14.7 ms                                                          | 15.2 ms: 1.03x slower                                                |
| xml_etree_generate               | 66.3 ms                                                          | 68.6 ms: 1.04x slower                                                |
| coverage                         | 52.2 ms                                                          | 54.1 ms: 1.04x slower                                                |
| unpickle_pure_python             | 149 us                                                           | 154 us: 1.04x slower                                                 |
| thread_memo_optimized            | 18.2 ms                                                          | 19.0 ms: 1.04x slower                                                |
| gc_traversal                     | 3.16 ms                                                          | 3.30 ms: 1.05x slower                                                |
| pickle_pure_python               | 223 us                                                           | 237 us: 1.06x slower                                                 |
| pickle_list                      | 3.03 us                                                          | 3.29 us: 1.09x slower                                                |
| thread_counter_optimized         | 18.7 ms                                                          | 20.5 ms: 1.09x slower                                                |
| thread_accumulate_optimized      | 39.8 ms                                                          | 43.6 ms: 1.10x slower                                                |
| thread_accumulate_naive          | 40.9 ms                                                          | 45.3 ms: 1.11x slower                                                |
| thread_pipeline_optimized        | 25.6 ms                                                          | 29.0 ms: 1.13x slower                                                |
| create_gc_cycles                 | 1.70 ms                                                          | 1.93 ms: 1.14x slower                                                |
| pickle                           | 8.22 us                                                          | 9.48 us: 1.15x slower                                                |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 372 ms: 1.16x slower                                                 |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 222 ms: 1.28x slower                                                 |
| argparse_subparsers              | 446 us                                                           | 665 us: 1.49x slower                                                 |
| argparse_many_optionals          | 12.6 ms                                                          | 33.8 ms: 2.69x slower                                                |
| async_tree_eager_tg              | 58.6 ms                                                          | 176 ms: 3.01x slower                                                 |
| Geometric mean                   | (ref)                                                            | 1.11x faster                                                         |

Benchmark hidden because not significant (3): unpickle, xml_etree_iterparse, asyncio_tcp_ssl
Ignored benchmarks (3) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json: networkx_connected_components, networkx_k_core, networkx_shortest_path

- Geometric mean (including insignificant results): 1.107x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.05x
- 95% likely to have a speedup of 1.05x
- 99% likely to have a speedup of 1.04x

# Memory
- memory change: 1.11x