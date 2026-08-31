# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.053x faster
- HPT reliability: 98.18%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.10x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 10.7 ms: 1.04x faster                                              |
| docutils       | 1.89 sec                                                           | 2.06 sec: 1.09x slower                                             |
| fastapi_http   | 215 ms                                                             | 223 ms: 1.03x slower                                               |
| html5lib       | 50.9 ms                                                            | 49.7 ms: 1.02x faster                                              |
| tornado_http   | 98.9 ms                                                            | 103 ms: 1.04x slower                                               |
| Geometric mean | (ref)                                                              | 1.02x slower                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 284 ms: 1.48x faster                                               |
| async_tree_io_tg                 | 781 ms                                                             | 549 ms: 1.42x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 556 ms: 1.35x faster                                               |
| async_tree_io                    | 743 ms                                                             | 555 ms: 1.34x faster                                               |
| async_tree_memoization           | 392 ms                                                             | 294 ms: 1.33x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 553 ms: 1.32x faster                                               |
| async_tree_none                  | 312 ms                                                             | 238 ms: 1.31x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 232 ms: 1.25x faster                                               |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 430 ms: 1.18x faster                                               |
| async_tree_eager_memoization     | 221 ms                                                             | 192 ms: 1.15x faster                                               |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 436 ms: 1.13x faster                                               |
| coroutines                       | 18.2 ms                                                            | 16.4 ms: 1.11x faster                                              |
| asyncio_websockets               | 313 ms                                                             | 294 ms: 1.07x faster                                               |
| asyncio_tcp                      | 316 ms                                                             | 302 ms: 1.05x faster                                               |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 335 ms: 1.02x faster                                               |
| async_generators                 | 251 ms                                                             | 249 ms: 1.01x faster                                               |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.29 sec: 1.01x slower                                             |
| async_tree_eager                 | 88.3 ms                                                            | 90.4 ms: 1.02x slower                                              |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 382 ms: 1.27x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 247 ms: 1.42x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 181 ms: 3.18x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.06x faster                                                       |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 17.0 ns: 1.26x faster                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 205 ms: 1.11x faster                                               |
| decimal_factorial | 177 ms                                                             | 178 ms: 1.01x slower                                               |
| Geometric mean    | (ref)                                                              | 1.05x faster                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 41.4 ms: 1.43x faster                                              |
| quadtree_nbody | 675 ms                                                             | 596 ms: 1.13x faster                                               |
| pidigits       | 216 ms                                                             | 216 ms: 1.00x faster                                               |
| nbody          | 75.8 ms                                                            | 83.5 ms: 1.10x slower                                              |
| Geometric mean | (ref)                                                              | 1.10x faster                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 1.92 ms: 1.21x faster                                              |
| regex_dna      | 159 ms                                                             | 147 ms: 1.08x faster                                               |
| regex_v8       | 15.0 ms                                                            | 14.3 ms: 1.05x faster                                              |
| regex_compile  | 102 ms                                                             | 102 ms: 1.00x faster                                               |
| Geometric mean | (ref)                                                              | 1.08x faster                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.29 ms: 6.79x faster                                              |
| base16_small         | 836 us                                                             | 271 us: 3.08x faster                                               |
| ascii85_large        | 824 ms                                                             | 617 ms: 1.33x faster                                               |
| ascii85_small        | 15.7 ms                                                            | 12.3 ms: 1.28x faster                                              |
| tomli_loads          | 1.77 sec                                                           | 1.46 sec: 1.21x faster                                             |
| unpickle_pure_python | 161 us                                                             | 137 us: 1.18x faster                                               |
| unpickle_list        | 3.42 us                                                            | 2.94 us: 1.17x faster                                              |
| xml_etree_generate   | 70.6 ms                                                            | 61.8 ms: 1.14x faster                                              |
| base32_large         | 325 ms                                                             | 293 ms: 1.11x faster                                               |
| xml_etree_process    | 49.9 ms                                                            | 45.1 ms: 1.11x faster                                              |
| base85_large         | 267 ms                                                             | 243 ms: 1.10x faster                                               |
| base85_small         | 4.85 ms                                                            | 4.47 ms: 1.08x faster                                              |
| base32_small         | 6.46 ms                                                            | 5.96 ms: 1.08x faster                                              |
| unpickle             | 10.8 us                                                            | 10.4 us: 1.04x faster                                              |
| xml_etree_parse      | 121 ms                                                             | 117 ms: 1.03x faster                                               |
| json_loads           | 18.2 us                                                            | 18.6 us: 1.02x slower                                              |
| base64_small         | 222 us                                                             | 228 us: 1.03x slower                                               |
| urlsafe_base64_small | 328 us                                                             | 338 us: 1.03x slower                                               |
| pickle_dict          | 19.0 us                                                            | 20.0 us: 1.05x slower                                              |
| json_dumps           | 7.26 ms                                                            | 7.65 ms: 1.05x slower                                              |
| pickle_pure_python   | 245 us                                                             | 265 us: 1.08x slower                                               |
| pickle               | 7.21 us                                                            | 8.11 us: 1.12x slower                                              |
| pickle_list          | 2.66 us                                                            | 3.06 us: 1.15x slower                                              |
| Geometric mean       | (ref)                                                              | 1.18x faster                                                       |

Benchmark hidden because not significant (2): xml_etree_iterparse, base64_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.53 ms: 1.01x slower                                              |
| python_startup         | 9.51 ms                                                            | 9.91 ms: 1.04x slower                                              |
| Geometric mean         | (ref)                                                              | 1.02x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 18.6 ms: 1.13x faster                                              |
| mako            | 8.30 ms                                                            | 7.35 ms: 1.13x faster                                              |
| genshi_xml      | 46.3 ms                                                            | 45.7 ms: 1.01x faster                                              |
| django_template | 28.8 ms                                                            | 31.1 ms: 1.08x slower                                              |
| Geometric mean  | (ref)                                                              | 1.05x faster                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 11.0 ms: 3.44x faster                                              |
| thread_pipeline_naive       | 49.8 ms                                                            | 33.7 ms: 1.48x faster                                              |
| thread_counter_naive        | 23.7 ms                                                            | 20.4 ms: 1.16x faster                                              |
| thread_counter_optimized    | 19.7 ms                                                            | 17.5 ms: 1.13x faster                                              |
| thread_memo_optimized       | 16.8 ms                                                            | 16.0 ms: 1.05x faster                                              |
| thread_pipeline_optimized   | 22.8 ms                                                            | 22.8 ms: 1.00x slower                                              |
| thread_accumulate_optimized | 35.3 ms                                                            | 35.6 ms: 1.01x slower                                              |
| thread_montecarlo_optimized | 14.2 ms                                                            | 14.4 ms: 1.01x slower                                              |
| thread_montecarlo_naive     | 18.1 ms                                                            | 18.6 ms: 1.03x slower                                              |
| thread_mandelbrot_naive     | 190 ms                                                             | 198 ms: 1.05x slower                                               |
| thread_mandelbrot_optimized | 189 ms                                                             | 200 ms: 1.06x slower                                               |
| Geometric mean              | (ref)                                                              | 1.16x faster                                                       |

Benchmark hidden because not significant (1): thread_accumulate_naive

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.29 ms: 6.79x faster                                              |
| thread_memo_naive                | 37.9 ms                                                            | 11.0 ms: 3.44x faster                                              |
| base16_small                     | 836 us                                                             | 271 us: 3.08x faster                                               |
| mdp                              | 2.05 sec                                                           | 983 ms: 2.09x faster                                               |
| thread_pipeline_naive            | 49.8 ms                                                            | 33.7 ms: 1.48x faster                                              |
| async_tree_memoization_tg        | 421 ms                                                             | 284 ms: 1.48x faster                                               |
| float                            | 59.2 ms                                                            | 41.4 ms: 1.43x faster                                              |
| deepcopy_memo                    | 27.8 us                                                            | 19.5 us: 1.43x faster                                              |
| async_tree_io_tg                 | 781 ms                                                             | 549 ms: 1.42x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 556 ms: 1.35x faster                                               |
| async_tree_io                    | 743 ms                                                             | 555 ms: 1.34x faster                                               |
| async_tree_memoization           | 392 ms                                                             | 294 ms: 1.33x faster                                               |
| ascii85_large                    | 824 ms                                                             | 617 ms: 1.33x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 553 ms: 1.32x faster                                               |
| async_tree_none                  | 312 ms                                                             | 238 ms: 1.31x faster                                               |
| deepcopy                         | 267 us                                                             | 207 us: 1.29x faster                                               |
| ascii85_small                    | 15.7 ms                                                            | 12.3 ms: 1.28x faster                                              |
| richards                         | 38.2 ms                                                            | 30.3 ms: 1.26x faster                                              |
| noop                             | 21.4 ns                                                            | 17.0 ns: 1.26x faster                                              |
| async_tree_none_tg               | 290 ms                                                             | 232 ms: 1.25x faster                                               |
| richards_super                   | 43.8 ms                                                            | 35.4 ms: 1.24x faster                                              |
| fannkuch                         | 287 ms                                                             | 234 ms: 1.22x faster                                               |
| go                               | 129 ms                                                             | 106 ms: 1.22x faster                                               |
| scimark_fft                      | 216 ms                                                             | 177 ms: 1.22x faster                                               |
| tomli_loads                      | 1.77 sec                                                           | 1.46 sec: 1.21x faster                                             |
| regex_effbot                     | 2.33 ms                                                            | 1.92 ms: 1.21x faster                                              |
| pyflate                          | 374 ms                                                             | 311 ms: 1.20x faster                                               |
| spectral_norm                    | 68.6 ms                                                            | 57.3 ms: 1.20x faster                                              |
| unpickle_pure_python             | 161 us                                                             | 137 us: 1.18x faster                                               |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 430 ms: 1.18x faster                                               |
| unpickle_list                    | 3.42 us                                                            | 2.94 us: 1.17x faster                                              |
| thread_counter_naive             | 23.7 ms                                                            | 20.4 ms: 1.16x faster                                              |
| bpe_tokeniser                    | 3.37 sec                                                           | 2.90 sec: 1.16x faster                                             |
| deltablue                        | 2.59 ms                                                            | 2.24 ms: 1.16x faster                                              |
| async_tree_eager_memoization     | 221 ms                                                             | 192 ms: 1.15x faster                                               |
| xml_etree_generate               | 70.6 ms                                                            | 61.8 ms: 1.14x faster                                              |
| genshi_text                      | 21.1 ms                                                            | 18.6 ms: 1.13x faster                                              |
| quadtree_nbody                   | 675 ms                                                             | 596 ms: 1.13x faster                                               |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 436 ms: 1.13x faster                                               |
| thread_counter_optimized         | 19.7 ms                                                            | 17.5 ms: 1.13x faster                                              |
| mako                             | 8.30 ms                                                            | 7.35 ms: 1.13x faster                                              |
| deepcopy_reduce                  | 2.36 us                                                            | 2.09 us: 1.13x faster                                              |
| decimal_pi                       | 228 ms                                                             | 205 ms: 1.11x faster                                               |
| base32_large                     | 325 ms                                                             | 293 ms: 1.11x faster                                               |
| coroutines                       | 18.2 ms                                                            | 16.4 ms: 1.11x faster                                              |
| xml_etree_process                | 49.9 ms                                                            | 45.1 ms: 1.11x faster                                              |
| base85_large                     | 267 ms                                                             | 243 ms: 1.10x faster                                               |
| scimark_monte_carlo              | 47.2 ms                                                            | 43.2 ms: 1.09x faster                                              |
| base85_small                     | 4.85 ms                                                            | 4.47 ms: 1.08x faster                                              |
| base32_small                     | 6.46 ms                                                            | 5.96 ms: 1.08x faster                                              |
| regex_dna                        | 159 ms                                                             | 147 ms: 1.08x faster                                               |
| asyncio_websockets               | 313 ms                                                             | 294 ms: 1.07x faster                                               |
| thread_memo_optimized            | 16.8 ms                                                            | 16.0 ms: 1.05x faster                                              |
| scimark_sor                      | 96.2 ms                                                            | 91.5 ms: 1.05x faster                                              |
| asyncio_tcp                      | 316 ms                                                             | 302 ms: 1.05x faster                                               |
| regex_v8                         | 15.0 ms                                                            | 14.3 ms: 1.05x faster                                              |
| chameleon                        | 11.1 ms                                                            | 10.7 ms: 1.04x faster                                              |
| unpickle                         | 10.8 us                                                            | 10.4 us: 1.04x faster                                              |
| networkx_k_core                  | 2.16 sec                                                           | 2.09 sec: 1.03x faster                                             |
| xml_etree_parse                  | 121 ms                                                             | 117 ms: 1.03x faster                                               |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.78 ms: 1.03x faster                                              |
| html5lib                         | 50.9 ms                                                            | 49.7 ms: 1.02x faster                                              |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 335 ms: 1.02x faster                                               |
| meteor_contest                   | 85.7 ms                                                            | 84.2 ms: 1.02x faster                                              |
| json                             | 3.50 ms                                                            | 3.45 ms: 1.01x faster                                              |
| genshi_xml                       | 46.3 ms                                                            | 45.7 ms: 1.01x faster                                              |
| chaos                            | 43.6 ms                                                            | 43.1 ms: 1.01x faster                                              |
| async_generators                 | 251 ms                                                             | 249 ms: 1.01x faster                                               |
| networkx_connected_components    | 443 ms                                                             | 441 ms: 1.00x faster                                               |
| regex_compile                    | 102 ms                                                             | 102 ms: 1.00x faster                                               |
| pidigits                         | 216 ms                                                             | 216 ms: 1.00x faster                                               |
| thread_pipeline_optimized        | 22.8 ms                                                            | 22.8 ms: 1.00x slower                                              |
| networkx_shortest_path           | 454 ms                                                             | 456 ms: 1.01x slower                                               |
| python_startup_no_site           | 6.49 ms                                                            | 6.53 ms: 1.01x slower                                              |
| decimal_factorial                | 177 ms                                                             | 178 ms: 1.01x slower                                               |
| thread_accumulate_optimized      | 35.3 ms                                                            | 35.6 ms: 1.01x slower                                              |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 14.4 ms: 1.01x slower                                              |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.29 sec: 1.01x slower                                             |
| json_loads                       | 18.2 us                                                            | 18.6 us: 1.02x slower                                              |
| async_tree_eager                 | 88.3 ms                                                            | 90.4 ms: 1.02x slower                                              |
| sympy_integrate                  | 15.4 ms                                                            | 15.8 ms: 1.02x slower                                              |
| crypto_pyaes                     | 55.6 ms                                                            | 57.1 ms: 1.03x slower                                              |
| thread_montecarlo_naive          | 18.1 ms                                                            | 18.6 ms: 1.03x slower                                              |
| hexiom                           | 4.75 ms                                                            | 4.88 ms: 1.03x slower                                              |
| base64_small                     | 222 us                                                             | 228 us: 1.03x slower                                               |
| urlsafe_base64_small             | 328 us                                                             | 338 us: 1.03x slower                                               |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 43.5 ms: 1.03x slower                                              |
| fastapi_http                     | 215 ms                                                             | 223 ms: 1.03x slower                                               |
| thrift                           | 2.07 ms                                                            | 2.15 ms: 1.04x slower                                              |
| pycparser                        | 901 ms                                                             | 937 ms: 1.04x slower                                               |
| pathlib                          | 12.2 ms                                                            | 12.7 ms: 1.04x slower                                              |
| python_startup                   | 9.51 ms                                                            | 9.91 ms: 1.04x slower                                              |
| logging_silent                   | 60.1 ns                                                            | 62.7 ns: 1.04x slower                                              |
| sqlglot_v2_parse                 | 979 us                                                             | 1.02 ms: 1.04x slower                                              |
| tornado_http                     | 98.9 ms                                                            | 103 ms: 1.04x slower                                               |
| thread_mandelbrot_naive          | 190 ms                                                             | 198 ms: 1.05x slower                                               |
| telco                            | 5.37 ms                                                            | 5.61 ms: 1.05x slower                                              |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.28 ms: 1.05x slower                                              |
| pickle_dict                      | 19.0 us                                                            | 20.0 us: 1.05x slower                                              |
| gc_traversal                     | 3.20 ms                                                            | 3.35 ms: 1.05x slower                                              |
| json_dumps                       | 7.26 ms                                                            | 7.65 ms: 1.05x slower                                              |
| thread_mandelbrot_optimized      | 189 ms                                                             | 200 ms: 1.06x slower                                               |
| logging_format                   | 5.62 us                                                            | 5.98 us: 1.06x slower                                              |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 89.2 ms: 1.07x slower                                              |
| xdsl_constant_fold               | 36.4 ms                                                            | 38.9 ms: 1.07x slower                                              |
| mypy2                            | 741 ms                                                             | 793 ms: 1.07x slower                                               |
| sympy_sum                        | 104 ms                                                             | 112 ms: 1.07x slower                                               |
| typing_runtime_protocols         | 112 us                                                             | 120 us: 1.07x slower                                               |
| nqueens                          | 58.3 ms                                                            | 62.7 ms: 1.07x slower                                              |
| generators                       | 22.2 ms                                                            | 23.9 ms: 1.08x slower                                              |
| logging_simple                   | 5.06 us                                                            | 5.44 us: 1.08x slower                                              |
| comprehensions                   | 11.4 us                                                            | 12.3 us: 1.08x slower                                              |
| pickle_pure_python               | 245 us                                                             | 265 us: 1.08x slower                                               |
| sympy_str                        | 193 ms                                                             | 208 ms: 1.08x slower                                               |
| django_template                  | 28.8 ms                                                            | 31.1 ms: 1.08x slower                                              |
| raytrace                         | 197 ms                                                             | 214 ms: 1.08x slower                                               |
| sympy_expand                     | 331 ms                                                             | 361 ms: 1.09x slower                                               |
| docutils                         | 1.89 sec                                                           | 2.06 sec: 1.09x slower                                             |
| nbody                            | 75.8 ms                                                            | 83.5 ms: 1.10x slower                                              |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.3 ms: 1.10x slower                                              |
| pickle                           | 7.21 us                                                            | 8.11 us: 1.12x slower                                              |
| scimark_lu                       | 70.2 ms                                                            | 79.2 ms: 1.13x slower                                              |
| create_gc_cycles                 | 1.77 ms                                                            | 2.01 ms: 1.13x slower                                              |
| pickle_list                      | 2.66 us                                                            | 3.06 us: 1.15x slower                                              |
| pprint_pformat                   | 1.13 sec                                                           | 1.33 sec: 1.18x slower                                             |
| pprint_safe_repr                 | 546 ms                                                             | 654 ms: 1.20x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 382 ms: 1.27x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 247 ms: 1.42x slower                                               |
| argparse_subparsers              | 449 us                                                             | 736 us: 1.64x slower                                               |
| argparse_many_optionals          | 12.9 ms                                                            | 36.1 ms: 2.79x slower                                              |
| async_tree_eager_tg              | 56.8 ms                                                            | 181 ms: 3.18x slower                                               |
| unpack_sequence                  | 26.4 ns                                                            | 106 ns: 4.02x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.05x faster                                                       |

Benchmark hidden because not significant (5): coverage, thread_accumulate_naive, xml_etree_iterparse, base64_large, pylint

- Geometric mean (including insignificant results): 1.053x faster

# HPT report

- Reliability score: 98.18% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.10x