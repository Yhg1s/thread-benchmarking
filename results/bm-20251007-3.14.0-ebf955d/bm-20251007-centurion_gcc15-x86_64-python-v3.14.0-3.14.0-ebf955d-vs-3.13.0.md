# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.078x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.02x faster
- Memory change: 1.09x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 10.6 ms: 1.03x faster                                            |
| docutils       | 1.98 sec                                                         | 2.02 sec: 1.02x slower                                           |
| html5lib       | 49.1 ms                                                          | 45.5 ms: 1.08x faster                                            |
| tornado_http   | 99.2 ms                                                          | 101 ms: 1.01x slower                                             |
| Geometric mean | (ref)                                                            | 1.01x faster                                                     |

Benchmark hidden because not significant (1): fastapi_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_memoization_tg        | 417 ms                                                           | 275 ms: 1.52x faster                                             |
| async_tree_io_tg                 | 777 ms                                                           | 529 ms: 1.47x faster                                             |
| async_tree_memoization           | 389 ms                                                           | 274 ms: 1.42x faster                                             |
| async_tree_io                    | 741 ms                                                           | 527 ms: 1.41x faster                                             |
| async_tree_none                  | 310 ms                                                           | 223 ms: 1.39x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 548 ms: 1.37x faster                                             |
| async_tree_eager_io_tg           | 724 ms                                                           | 549 ms: 1.32x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 221 ms: 1.31x faster                                             |
| async_tree_eager_memoization     | 215 ms                                                           | 175 ms: 1.23x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 436 ms: 1.21x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 430 ms: 1.20x faster                                             |
| coroutines                       | 17.6 ms                                                          | 15.4 ms: 1.15x faster                                            |
| async_tree_eager                 | 90.0 ms                                                          | 78.8 ms: 1.14x faster                                            |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 333 ms: 1.08x faster                                             |
| async_generators                 | 262 ms                                                           | 243 ms: 1.08x faster                                             |
| asyncio_tcp                      | 326 ms                                                           | 332 ms: 1.02x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 385 ms: 1.20x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 235 ms: 1.36x slower                                             |
| async_tree_eager_tg              | 58.6 ms                                                          | 179 ms: 3.06x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.10x faster                                                     |

Benchmark hidden because not significant (2): asyncio_tcp_ssl, asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 18.7 ns: 1.09x faster                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 201 ms: 1.04x faster                                             |
| decimal_factorial | 173 ms                                                           | 170 ms: 1.01x faster                                             |
| Geometric mean    | (ref)                                                            | 1.03x faster                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 48.1 ms: 1.18x faster                                            |
| quadtree_nbody | 620 ms                                                           | 602 ms: 1.03x faster                                             |
| Geometric mean | (ref)                                                            | 1.05x faster                                                     |

Benchmark hidden because not significant (2): pidigits, nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.80 ms: 1.11x faster                                            |
| regex_compile  | 97.7 ms                                                          | 91.6 ms: 1.07x faster                                            |
| regex_dna      | 144 ms                                                           | 141 ms: 1.02x faster                                             |
| regex_v8       | 14.7 ms                                                          | 15.0 ms: 1.02x slower                                            |
| Geometric mean | (ref)                                                            | 1.04x faster                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.41 ms: 5.83x faster                                            |
| base16_small         | 656 us                                                           | 298 us: 2.20x faster                                             |
| ascii85_large        | 814 ms                                                           | 651 ms: 1.25x faster                                             |
| ascii85_small        | 15.5 ms                                                          | 12.5 ms: 1.24x faster                                            |
| tomli_loads          | 1.63 sec                                                         | 1.41 sec: 1.16x faster                                           |
| xml_etree_parse      | 107 ms                                                           | 102 ms: 1.05x faster                                             |
| base32_small         | 5.69 ms                                                          | 5.43 ms: 1.05x faster                                            |
| base85_large         | 243 ms                                                           | 233 ms: 1.04x faster                                             |
| base32_large         | 286 ms                                                           | 276 ms: 1.03x faster                                             |
| pickle_dict          | 21.9 us                                                          | 21.3 us: 1.03x faster                                            |
| json_dumps           | 7.49 ms                                                          | 7.37 ms: 1.02x faster                                            |
| unpickle             | 10.3 us                                                          | 10.3 us: 1.01x slower                                            |
| base85_small         | 4.41 ms                                                          | 4.44 ms: 1.01x slower                                            |
| base64_small         | 228 us                                                           | 230 us: 1.01x slower                                             |
| urlsafe_base64_small | 379 us                                                           | 383 us: 1.01x slower                                             |
| unpickle_pure_python | 149 us                                                           | 153 us: 1.03x slower                                             |
| json_loads           | 16.7 us                                                          | 17.3 us: 1.04x slower                                            |
| xml_etree_process    | 48.1 ms                                                          | 50.0 ms: 1.04x slower                                            |
| pickle_pure_python   | 223 us                                                           | 234 us: 1.05x slower                                             |
| unpickle_list        | 3.45 us                                                          | 3.64 us: 1.06x slower                                            |
| xml_etree_generate   | 66.3 ms                                                          | 71.1 ms: 1.07x slower                                            |
| pickle_list          | 3.03 us                                                          | 3.26 us: 1.07x slower                                            |
| xml_etree_iterparse  | 69.6 ms                                                          | 76.5 ms: 1.10x slower                                            |
| pickle               | 8.22 us                                                          | 9.23 us: 1.12x slower                                            |
| Geometric mean       | (ref)                                                            | 1.12x faster                                                     |

Benchmark hidden because not significant (1): base64_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 6.29 ms: 1.01x faster                                            |
| python_startup         | 9.38 ms                                                          | 9.62 ms: 1.03x slower                                            |
| Geometric mean         | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| genshi_text     | 17.6 ms                                                          | 16.4 ms: 1.07x faster                                            |
| genshi_xml      | 39.7 ms                                                          | 38.4 ms: 1.03x faster                                            |
| mako            | 7.43 ms                                                          | 7.66 ms: 1.03x slower                                            |
| django_template | 27.3 ms                                                          | 28.4 ms: 1.04x slower                                            |
| Geometric mean  | (ref)                                                            | 1.01x faster                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 11.8 ms: 3.29x faster                                            |
| thread_pipeline_naive       | 52.1 ms                                                          | 35.4 ms: 1.47x faster                                            |
| thread_montecarlo_naive     | 17.8 ms                                                          | 14.6 ms: 1.22x faster                                            |
| thread_counter_naive        | 22.6 ms                                                          | 21.4 ms: 1.06x faster                                            |
| thread_montecarlo_optimized | 13.3 ms                                                          | 12.6 ms: 1.06x faster                                            |
| thread_memo_optimized       | 18.2 ms                                                          | 17.9 ms: 1.02x faster                                            |
| thread_mandelbrot_naive     | 220 ms                                                           | 217 ms: 1.01x faster                                             |
| thread_mandelbrot_optimized | 218 ms                                                           | 215 ms: 1.01x faster                                             |
| thread_accumulate_naive     | 40.9 ms                                                          | 41.6 ms: 1.02x slower                                            |
| thread_accumulate_optimized | 39.8 ms                                                          | 40.8 ms: 1.03x slower                                            |
| thread_pipeline_optimized   | 25.6 ms                                                          | 26.3 ms: 1.03x slower                                            |
| Geometric mean              | (ref)                                                            | 1.17x faster                                                     |

Benchmark hidden because not significant (1): thread_counter_optimized

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.41 ms: 5.83x faster                                            |
| thread_memo_naive                | 39.0 ms                                                          | 11.8 ms: 3.29x faster                                            |
| mdp                              | 2.11 sec                                                         | 935 ms: 2.26x faster                                             |
| base16_small                     | 656 us                                                           | 298 us: 2.20x faster                                             |
| async_tree_memoization_tg        | 417 ms                                                           | 275 ms: 1.52x faster                                             |
| thread_pipeline_naive            | 52.1 ms                                                          | 35.4 ms: 1.47x faster                                            |
| async_tree_io_tg                 | 777 ms                                                           | 529 ms: 1.47x faster                                             |
| go                               | 121 ms                                                           | 82.6 ms: 1.47x faster                                            |
| deepcopy_memo                    | 26.6 us                                                          | 18.2 us: 1.46x faster                                            |
| async_tree_memoization           | 389 ms                                                           | 274 ms: 1.42x faster                                             |
| async_tree_io                    | 741 ms                                                           | 527 ms: 1.41x faster                                             |
| async_tree_none                  | 310 ms                                                           | 223 ms: 1.39x faster                                             |
| deepcopy                         | 267 us                                                           | 195 us: 1.37x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 548 ms: 1.37x faster                                             |
| scimark_sor                      | 97.0 ms                                                          | 72.8 ms: 1.33x faster                                            |
| async_tree_eager_io_tg           | 724 ms                                                           | 549 ms: 1.32x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 221 ms: 1.31x faster                                             |
| ascii85_large                    | 814 ms                                                           | 651 ms: 1.25x faster                                             |
| ascii85_small                    | 15.5 ms                                                          | 12.5 ms: 1.24x faster                                            |
| async_tree_eager_memoization     | 215 ms                                                           | 175 ms: 1.23x faster                                             |
| thread_montecarlo_naive          | 17.8 ms                                                          | 14.6 ms: 1.22x faster                                            |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 436 ms: 1.21x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 430 ms: 1.20x faster                                             |
| pyflate                          | 358 ms                                                           | 300 ms: 1.19x faster                                             |
| scimark_monte_carlo              | 44.3 ms                                                          | 37.5 ms: 1.18x faster                                            |
| float                            | 56.6 ms                                                          | 48.1 ms: 1.18x faster                                            |
| deepcopy_reduce                  | 2.37 us                                                          | 2.05 us: 1.16x faster                                            |
| tomli_loads                      | 1.63 sec                                                         | 1.41 sec: 1.16x faster                                           |
| coroutines                       | 17.6 ms                                                          | 15.4 ms: 1.15x faster                                            |
| async_tree_eager                 | 90.0 ms                                                          | 78.8 ms: 1.14x faster                                            |
| fannkuch                         | 265 ms                                                           | 234 ms: 1.13x faster                                             |
| richards                         | 36.8 ms                                                          | 32.5 ms: 1.13x faster                                            |
| pprint_pformat                   | 1.11 sec                                                         | 982 ms: 1.13x faster                                             |
| thrift                           | 2.07 ms                                                          | 1.84 ms: 1.12x faster                                            |
| deltablue                        | 2.52 ms                                                          | 2.24 ms: 1.12x faster                                            |
| pprint_safe_repr                 | 541 ms                                                           | 484 ms: 1.12x faster                                             |
| richards_super                   | 41.3 ms                                                          | 37.2 ms: 1.11x faster                                            |
| regex_effbot                     | 1.99 ms                                                          | 1.80 ms: 1.11x faster                                            |
| hexiom                           | 4.42 ms                                                          | 4.00 ms: 1.11x faster                                            |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.10 sec: 1.10x faster                                           |
| unpack_sequence                  | 26.2 ns                                                          | 24.1 ns: 1.09x faster                                            |
| noop                             | 20.4 ns                                                          | 18.7 ns: 1.09x faster                                            |
| html5lib                         | 49.1 ms                                                          | 45.5 ms: 1.08x faster                                            |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 333 ms: 1.08x faster                                             |
| async_generators                 | 262 ms                                                           | 243 ms: 1.08x faster                                             |
| chaos                            | 45.0 ms                                                          | 41.9 ms: 1.08x faster                                            |
| spectral_norm                    | 64.1 ms                                                          | 59.6 ms: 1.07x faster                                            |
| genshi_text                      | 17.6 ms                                                          | 16.4 ms: 1.07x faster                                            |
| meteor_contest                   | 89.9 ms                                                          | 83.9 ms: 1.07x faster                                            |
| scimark_fft                      | 211 ms                                                           | 197 ms: 1.07x faster                                             |
| regex_compile                    | 97.7 ms                                                          | 91.6 ms: 1.07x faster                                            |
| generators                       | 22.0 ms                                                          | 20.7 ms: 1.06x faster                                            |
| thread_counter_naive             | 22.6 ms                                                          | 21.4 ms: 1.06x faster                                            |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 12.6 ms: 1.06x faster                                            |
| networkx_connected_components    | 460 ms                                                           | 435 ms: 1.06x faster                                             |
| pycparser                        | 884 ms                                                           | 837 ms: 1.06x faster                                             |
| scimark_lu                       | 70.2 ms                                                          | 66.7 ms: 1.05x faster                                            |
| xml_etree_parse                  | 107 ms                                                           | 102 ms: 1.05x faster                                             |
| pylint                           | 226 ms                                                           | 215 ms: 1.05x faster                                             |
| sqlglot_v2_parse                 | 953 us                                                           | 909 us: 1.05x faster                                             |
| sympy_integrate                  | 15.4 ms                                                          | 14.7 ms: 1.05x faster                                            |
| base32_small                     | 5.69 ms                                                          | 5.43 ms: 1.05x faster                                            |
| telco                            | 5.50 ms                                                          | 5.26 ms: 1.05x faster                                            |
| base85_large                     | 243 ms                                                           | 233 ms: 1.04x faster                                             |
| xdsl_constant_fold               | 36.7 ms                                                          | 35.1 ms: 1.04x faster                                            |
| decimal_pi                       | 210 ms                                                           | 201 ms: 1.04x faster                                             |
| networkx_shortest_path           | 464 ms                                                           | 445 ms: 1.04x faster                                             |
| networkx_k_core                  | 2.15 sec                                                         | 2.07 sec: 1.04x faster                                           |
| comprehensions                   | 11.6 us                                                          | 11.2 us: 1.04x faster                                            |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.15 ms: 1.04x faster                                            |
| base32_large                     | 286 ms                                                           | 276 ms: 1.03x faster                                             |
| genshi_xml                       | 39.7 ms                                                          | 38.4 ms: 1.03x faster                                            |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 38.7 ms: 1.03x faster                                            |
| chameleon                        | 10.9 ms                                                          | 10.6 ms: 1.03x faster                                            |
| quadtree_nbody                   | 620 ms                                                           | 602 ms: 1.03x faster                                             |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.58 ms: 1.03x faster                                            |
| pickle_dict                      | 21.9 us                                                          | 21.3 us: 1.03x faster                                            |
| raytrace                         | 199 ms                                                           | 194 ms: 1.02x faster                                             |
| json                             | 3.49 ms                                                          | 3.42 ms: 1.02x faster                                            |
| regex_dna                        | 144 ms                                                           | 141 ms: 1.02x faster                                             |
| nqueens                          | 57.3 ms                                                          | 56.3 ms: 1.02x faster                                            |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 77.8 ms: 1.02x faster                                            |
| json_dumps                       | 7.49 ms                                                          | 7.37 ms: 1.02x faster                                            |
| logging_silent                   | 60.6 ns                                                          | 59.7 ns: 1.02x faster                                            |
| thread_memo_optimized            | 18.2 ms                                                          | 17.9 ms: 1.02x faster                                            |
| decimal_factorial                | 173 ms                                                           | 170 ms: 1.01x faster                                             |
| thread_mandelbrot_naive          | 220 ms                                                           | 217 ms: 1.01x faster                                             |
| thread_mandelbrot_optimized      | 218 ms                                                           | 215 ms: 1.01x faster                                             |
| python_startup_no_site           | 6.36 ms                                                          | 6.29 ms: 1.01x faster                                            |
| sympy_str                        | 193 ms                                                           | 192 ms: 1.01x faster                                             |
| sympy_sum                        | 104 ms                                                           | 104 ms: 1.00x faster                                             |
| unpickle                         | 10.3 us                                                          | 10.3 us: 1.01x slower                                            |
| pathlib                          | 12.4 ms                                                          | 12.5 ms: 1.01x slower                                            |
| base85_small                     | 4.41 ms                                                          | 4.44 ms: 1.01x slower                                            |
| base64_small                     | 228 us                                                           | 230 us: 1.01x slower                                             |
| urlsafe_base64_small             | 379 us                                                           | 383 us: 1.01x slower                                             |
| tornado_http                     | 99.2 ms                                                          | 101 ms: 1.01x slower                                             |
| thread_accumulate_naive          | 40.9 ms                                                          | 41.6 ms: 1.02x slower                                            |
| asyncio_tcp                      | 326 ms                                                           | 332 ms: 1.02x slower                                             |
| docutils                         | 1.98 sec                                                         | 2.02 sec: 1.02x slower                                           |
| regex_v8                         | 14.7 ms                                                          | 15.0 ms: 1.02x slower                                            |
| logging_simple                   | 4.60 us                                                          | 4.72 us: 1.03x slower                                            |
| python_startup                   | 9.38 ms                                                          | 9.62 ms: 1.03x slower                                            |
| thread_accumulate_optimized      | 39.8 ms                                                          | 40.8 ms: 1.03x slower                                            |
| thread_pipeline_optimized        | 25.6 ms                                                          | 26.3 ms: 1.03x slower                                            |
| unpickle_pure_python             | 149 us                                                           | 153 us: 1.03x slower                                             |
| crypto_pyaes                     | 50.0 ms                                                          | 51.5 ms: 1.03x slower                                            |
| mako                             | 7.43 ms                                                          | 7.66 ms: 1.03x slower                                            |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.3 ms: 1.03x slower                                            |
| json_loads                       | 16.7 us                                                          | 17.3 us: 1.04x slower                                            |
| xml_etree_process                | 48.1 ms                                                          | 50.0 ms: 1.04x slower                                            |
| django_template                  | 27.3 ms                                                          | 28.4 ms: 1.04x slower                                            |
| mypy2                            | 726 ms                                                           | 756 ms: 1.04x slower                                             |
| pickle_pure_python               | 223 us                                                           | 234 us: 1.05x slower                                             |
| gc_traversal                     | 3.16 ms                                                          | 3.33 ms: 1.05x slower                                            |
| unpickle_list                    | 3.45 us                                                          | 3.64 us: 1.06x slower                                            |
| coverage                         | 52.2 ms                                                          | 55.4 ms: 1.06x slower                                            |
| xml_etree_generate               | 66.3 ms                                                          | 71.1 ms: 1.07x slower                                            |
| pickle_list                      | 3.03 us                                                          | 3.26 us: 1.07x slower                                            |
| xml_etree_iterparse              | 69.6 ms                                                          | 76.5 ms: 1.10x slower                                            |
| pickle                           | 8.22 us                                                          | 9.23 us: 1.12x slower                                            |
| create_gc_cycles                 | 1.70 ms                                                          | 1.93 ms: 1.14x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 385 ms: 1.20x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 235 ms: 1.36x slower                                             |
| argparse_subparsers              | 446 us                                                           | 665 us: 1.49x slower                                             |
| argparse_many_optionals          | 12.6 ms                                                          | 33.3 ms: 2.65x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                          | 179 ms: 3.06x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.08x faster                                                     |

Benchmark hidden because not significant (10): asyncio_tcp_ssl, base64_large, sympy_expand, typing_runtime_protocols, thread_counter_optimized, pidigits, logging_format, fastapi_http, asyncio_websockets, nbody

- Geometric mean (including insignificant results): 1.078x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.03x
- 95% likely to have a speedup of 1.03x
- 99% likely to have a speedup of 1.02x

# Memory
- memory change: 1.09x