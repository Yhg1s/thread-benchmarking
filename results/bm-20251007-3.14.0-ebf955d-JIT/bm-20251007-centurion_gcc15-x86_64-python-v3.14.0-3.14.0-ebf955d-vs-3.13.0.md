# Results vs. 3.13.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.079x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.02x faster
- Memory change: 1.08x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 10.7 ms: 1.02x faster                                            |
| docutils       | 1.98 sec                                                         | 2.08 sec: 1.05x slower                                           |
| fastapi_http   | 215 ms                                                           | 209 ms: 1.03x faster                                             |
| html5lib       | 49.1 ms                                                          | 45.7 ms: 1.08x faster                                            |
| tornado_http   | 99.2 ms                                                          | 102 ms: 1.03x slower                                             |
| Geometric mean | (ref)                                                            | 1.01x faster                                                     |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| async_tree_memoization_tg        | 417 ms                                                           | 270 ms: 1.54x faster                                             |
| async_tree_io_tg                 | 777 ms                                                           | 525 ms: 1.48x faster                                             |
| async_tree_io                    | 741 ms                                                           | 517 ms: 1.43x faster                                             |
| async_tree_memoization           | 389 ms                                                           | 272 ms: 1.43x faster                                             |
| async_tree_eager_io              | 749 ms                                                           | 526 ms: 1.42x faster                                             |
| async_tree_none                  | 310 ms                                                           | 224 ms: 1.38x faster                                             |
| async_tree_eager_io_tg           | 724 ms                                                           | 542 ms: 1.34x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 222 ms: 1.30x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 421 ms: 1.25x faster                                             |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 422 ms: 1.22x faster                                             |
| async_tree_eager_memoization     | 215 ms                                                           | 177 ms: 1.21x faster                                             |
| coroutines                       | 17.6 ms                                                          | 15.2 ms: 1.16x faster                                            |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 331 ms: 1.09x faster                                             |
| asyncio_tcp                      | 326 ms                                                           | 302 ms: 1.08x faster                                             |
| async_tree_eager                 | 90.0 ms                                                          | 84.0 ms: 1.07x faster                                            |
| async_generators                 | 262 ms                                                           | 258 ms: 1.01x faster                                             |
| asyncio_websockets               | 304 ms                                                           | 300 ms: 1.01x faster                                             |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.29 sec: 1.00x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 383 ms: 1.19x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 239 ms: 1.38x slower                                             |
| async_tree_eager_tg              | 58.6 ms                                                          | 175 ms: 2.99x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.11x faster                                                     |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| noop      | 20.4 ns                                                          | 15.7 ns: 1.30x faster                                            |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| decimal_pi        | 210 ms                                                           | 194 ms: 1.08x faster                                             |
| decimal_factorial | 173 ms                                                           | 171 ms: 1.01x faster                                             |
| Geometric mean    | (ref)                                                            | 1.05x faster                                                     |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| float          | 56.6 ms                                                          | 39.8 ms: 1.42x faster                                            |
| quadtree_nbody | 620 ms                                                           | 559 ms: 1.11x faster                                             |
| nbody          | 66.8 ms                                                          | 63.4 ms: 1.05x faster                                            |
| pidigits       | 181 ms                                                           | 181 ms: 1.00x faster                                             |
| Geometric mean | (ref)                                                            | 1.14x faster                                                     |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 1.79 ms: 1.11x faster                                            |
| regex_compile  | 97.7 ms                                                          | 92.5 ms: 1.06x faster                                            |
| regex_dna      | 144 ms                                                           | 143 ms: 1.01x faster                                             |
| regex_v8       | 14.7 ms                                                          | 15.4 ms: 1.05x slower                                            |
| Geometric mean | (ref)                                                            | 1.03x faster                                                     |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large         | 31.6 ms                                                          | 5.35 ms: 5.90x faster                                            |
| base16_small         | 656 us                                                           | 300 us: 2.19x faster                                             |
| ascii85_large        | 814 ms                                                           | 592 ms: 1.38x faster                                             |
| ascii85_small        | 15.5 ms                                                          | 11.4 ms: 1.36x faster                                            |
| tomli_loads          | 1.63 sec                                                         | 1.30 sec: 1.26x faster                                           |
| unpickle_pure_python | 149 us                                                           | 133 us: 1.12x faster                                             |
| base85_large         | 243 ms                                                           | 221 ms: 1.10x faster                                             |
| xml_etree_parse      | 107 ms                                                           | 102 ms: 1.06x faster                                             |
| xml_etree_process    | 48.1 ms                                                          | 45.7 ms: 1.05x faster                                            |
| base85_small         | 4.41 ms                                                          | 4.21 ms: 1.05x faster                                            |
| base32_large         | 286 ms                                                           | 276 ms: 1.04x faster                                             |
| xml_etree_generate   | 66.3 ms                                                          | 64.1 ms: 1.03x faster                                            |
| pickle_dict          | 21.9 us                                                          | 21.3 us: 1.03x faster                                            |
| base32_small         | 5.69 ms                                                          | 5.55 ms: 1.03x faster                                            |
| json_dumps           | 7.49 ms                                                          | 7.42 ms: 1.01x faster                                            |
| urlsafe_base64_small | 379 us                                                           | 377 us: 1.00x faster                                             |
| unpickle             | 10.3 us                                                          | 10.3 us: 1.01x slower                                            |
| base64_small         | 228 us                                                           | 230 us: 1.01x slower                                             |
| unpickle_list        | 3.45 us                                                          | 3.54 us: 1.03x slower                                            |
| json_loads           | 16.7 us                                                          | 17.3 us: 1.03x slower                                            |
| pickle_pure_python   | 223 us                                                           | 237 us: 1.06x slower                                             |
| xml_etree_iterparse  | 69.6 ms                                                          | 76.6 ms: 1.10x slower                                            |
| pickle_list          | 3.03 us                                                          | 3.34 us: 1.10x slower                                            |
| pickle               | 8.22 us                                                          | 9.24 us: 1.12x slower                                            |
| Geometric mean       | (ref)                                                            | 1.15x faster                                                     |

Benchmark hidden because not significant (1): base64_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 6.30 ms: 1.01x faster                                            |
| python_startup         | 9.38 ms                                                          | 9.63 ms: 1.03x slower                                            |
| Geometric mean         | (ref)                                                            | 1.01x slower                                                     |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| genshi_text     | 17.6 ms                                                          | 16.0 ms: 1.10x faster                                            |
| mako            | 7.43 ms                                                          | 6.79 ms: 1.09x faster                                            |
| genshi_xml      | 39.7 ms                                                          | 40.0 ms: 1.01x slower                                            |
| django_template | 27.3 ms                                                          | 28.6 ms: 1.05x slower                                            |
| Geometric mean  | (ref)                                                            | 1.03x faster                                                     |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| thread_memo_naive           | 39.0 ms                                                          | 11.0 ms: 3.56x faster                                            |
| thread_pipeline_naive       | 52.1 ms                                                          | 34.2 ms: 1.52x faster                                            |
| thread_mandelbrot_naive     | 220 ms                                                           | 200 ms: 1.10x faster                                             |
| thread_counter_naive        | 22.6 ms                                                          | 20.8 ms: 1.09x faster                                            |
| thread_mandelbrot_optimized | 218 ms                                                           | 201 ms: 1.08x faster                                             |
| thread_memo_optimized       | 18.2 ms                                                          | 17.2 ms: 1.06x faster                                            |
| thread_counter_optimized    | 18.7 ms                                                          | 17.8 ms: 1.05x faster                                            |
| thread_pipeline_optimized   | 25.6 ms                                                          | 24.5 ms: 1.04x faster                                            |
| thread_accumulate_optimized | 39.8 ms                                                          | 39.0 ms: 1.02x faster                                            |
| thread_accumulate_naive     | 40.9 ms                                                          | 40.3 ms: 1.02x faster                                            |
| thread_montecarlo_naive     | 17.8 ms                                                          | 17.6 ms: 1.01x faster                                            |
| thread_montecarlo_optimized | 13.3 ms                                                          | 13.5 ms: 1.01x slower                                            |
| Geometric mean              | (ref)                                                            | 1.19x faster                                                     |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------:|
| base16_large                     | 31.6 ms                                                          | 5.35 ms: 5.90x faster                                            |
| thread_memo_naive                | 39.0 ms                                                          | 11.0 ms: 3.56x faster                                            |
| mdp                              | 2.11 sec                                                         | 925 ms: 2.28x faster                                             |
| base16_small                     | 656 us                                                           | 300 us: 2.19x faster                                             |
| async_tree_memoization_tg        | 417 ms                                                           | 270 ms: 1.54x faster                                             |
| thread_pipeline_naive            | 52.1 ms                                                          | 34.2 ms: 1.52x faster                                            |
| deepcopy_memo                    | 26.6 us                                                          | 17.8 us: 1.49x faster                                            |
| async_tree_io_tg                 | 777 ms                                                           | 525 ms: 1.48x faster                                             |
| async_tree_io                    | 741 ms                                                           | 517 ms: 1.43x faster                                             |
| async_tree_memoization           | 389 ms                                                           | 272 ms: 1.43x faster                                             |
| float                            | 56.6 ms                                                          | 39.8 ms: 1.42x faster                                            |
| async_tree_eager_io              | 749 ms                                                           | 526 ms: 1.42x faster                                             |
| async_tree_none                  | 310 ms                                                           | 224 ms: 1.38x faster                                             |
| deepcopy                         | 267 us                                                           | 194 us: 1.38x faster                                             |
| ascii85_large                    | 814 ms                                                           | 592 ms: 1.38x faster                                             |
| richards                         | 36.8 ms                                                          | 26.8 ms: 1.37x faster                                            |
| ascii85_small                    | 15.5 ms                                                          | 11.4 ms: 1.36x faster                                            |
| scimark_sor                      | 97.0 ms                                                          | 71.5 ms: 1.36x faster                                            |
| richards_super                   | 41.3 ms                                                          | 30.9 ms: 1.34x faster                                            |
| async_tree_eager_io_tg           | 724 ms                                                           | 542 ms: 1.34x faster                                             |
| async_tree_none_tg               | 289 ms                                                           | 222 ms: 1.30x faster                                             |
| noop                             | 20.4 ns                                                          | 15.7 ns: 1.30x faster                                            |
| tomli_loads                      | 1.63 sec                                                         | 1.30 sec: 1.26x faster                                           |
| deltablue                        | 2.52 ms                                                          | 2.00 ms: 1.26x faster                                            |
| scimark_fft                      | 211 ms                                                           | 168 ms: 1.26x faster                                             |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 421 ms: 1.25x faster                                             |
| go                               | 121 ms                                                           | 97.4 ms: 1.24x faster                                            |
| async_tree_cpu_io_mixed          | 514 ms                                                           | 422 ms: 1.22x faster                                             |
| pyflate                          | 358 ms                                                           | 294 ms: 1.22x faster                                             |
| spectral_norm                    | 64.1 ms                                                          | 52.7 ms: 1.22x faster                                            |
| async_tree_eager_memoization     | 215 ms                                                           | 177 ms: 1.21x faster                                             |
| scimark_monte_carlo              | 44.3 ms                                                          | 36.8 ms: 1.20x faster                                            |
| deepcopy_reduce                  | 2.37 us                                                          | 2.04 us: 1.16x faster                                            |
| fannkuch                         | 265 ms                                                           | 229 ms: 1.16x faster                                             |
| coroutines                       | 17.6 ms                                                          | 15.2 ms: 1.16x faster                                            |
| bpe_tokeniser                    | 3.40 sec                                                         | 2.97 sec: 1.15x faster                                           |
| unpickle_pure_python             | 149 us                                                           | 133 us: 1.12x faster                                             |
| regex_effbot                     | 1.99 ms                                                          | 1.79 ms: 1.11x faster                                            |
| quadtree_nbody                   | 620 ms                                                           | 559 ms: 1.11x faster                                             |
| base85_large                     | 243 ms                                                           | 221 ms: 1.10x faster                                             |
| thread_mandelbrot_naive          | 220 ms                                                           | 200 ms: 1.10x faster                                             |
| genshi_text                      | 17.6 ms                                                          | 16.0 ms: 1.10x faster                                            |
| mako                             | 7.43 ms                                                          | 6.79 ms: 1.09x faster                                            |
| thread_counter_naive             | 22.6 ms                                                          | 20.8 ms: 1.09x faster                                            |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 331 ms: 1.09x faster                                             |
| thread_mandelbrot_optimized      | 218 ms                                                           | 201 ms: 1.08x faster                                             |
| decimal_pi                       | 210 ms                                                           | 194 ms: 1.08x faster                                             |
| asyncio_tcp                      | 326 ms                                                           | 302 ms: 1.08x faster                                             |
| networkx_connected_components    | 460 ms                                                           | 427 ms: 1.08x faster                                             |
| html5lib                         | 49.1 ms                                                          | 45.7 ms: 1.08x faster                                            |
| networkx_shortest_path           | 464 ms                                                           | 433 ms: 1.07x faster                                             |
| thrift                           | 2.07 ms                                                          | 1.93 ms: 1.07x faster                                            |
| async_tree_eager                 | 90.0 ms                                                          | 84.0 ms: 1.07x faster                                            |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 2.48 ms: 1.07x faster                                            |
| scimark_lu                       | 70.2 ms                                                          | 65.7 ms: 1.07x faster                                            |
| generators                       | 22.0 ms                                                          | 20.7 ms: 1.06x faster                                            |
| thread_memo_optimized            | 18.2 ms                                                          | 17.2 ms: 1.06x faster                                            |
| xml_etree_parse                  | 107 ms                                                           | 102 ms: 1.06x faster                                             |
| regex_compile                    | 97.7 ms                                                          | 92.5 ms: 1.06x faster                                            |
| nbody                            | 66.8 ms                                                          | 63.4 ms: 1.05x faster                                            |
| networkx_k_core                  | 2.15 sec                                                         | 2.04 sec: 1.05x faster                                           |
| json                             | 3.49 ms                                                          | 3.32 ms: 1.05x faster                                            |
| xml_etree_process                | 48.1 ms                                                          | 45.7 ms: 1.05x faster                                            |
| thread_counter_optimized         | 18.7 ms                                                          | 17.8 ms: 1.05x faster                                            |
| base85_small                     | 4.41 ms                                                          | 4.21 ms: 1.05x faster                                            |
| thread_pipeline_optimized        | 25.6 ms                                                          | 24.5 ms: 1.04x faster                                            |
| chaos                            | 45.0 ms                                                          | 43.2 ms: 1.04x faster                                            |
| base32_large                     | 286 ms                                                           | 276 ms: 1.04x faster                                             |
| xml_etree_generate               | 66.3 ms                                                          | 64.1 ms: 1.03x faster                                            |
| meteor_contest                   | 89.9 ms                                                          | 87.2 ms: 1.03x faster                                            |
| pycparser                        | 884 ms                                                           | 859 ms: 1.03x faster                                             |
| fastapi_http                     | 215 ms                                                           | 209 ms: 1.03x faster                                             |
| pickle_dict                      | 21.9 us                                                          | 21.3 us: 1.03x faster                                            |
| base32_small                     | 5.69 ms                                                          | 5.55 ms: 1.03x faster                                            |
| sympy_integrate                  | 15.4 ms                                                          | 15.1 ms: 1.02x faster                                            |
| chameleon                        | 10.9 ms                                                          | 10.7 ms: 1.02x faster                                            |
| thread_accumulate_optimized      | 39.8 ms                                                          | 39.0 ms: 1.02x faster                                            |
| thread_accumulate_naive          | 40.9 ms                                                          | 40.3 ms: 1.02x faster                                            |
| async_generators                 | 262 ms                                                           | 258 ms: 1.01x faster                                             |
| thread_montecarlo_naive          | 17.8 ms                                                          | 17.6 ms: 1.01x faster                                            |
| nqueens                          | 57.3 ms                                                          | 56.6 ms: 1.01x faster                                            |
| asyncio_websockets               | 304 ms                                                           | 300 ms: 1.01x faster                                             |
| decimal_factorial                | 173 ms                                                           | 171 ms: 1.01x faster                                             |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 39.6 ms: 1.01x faster                                            |
| json_dumps                       | 7.49 ms                                                          | 7.42 ms: 1.01x faster                                            |
| python_startup_no_site           | 6.36 ms                                                          | 6.30 ms: 1.01x faster                                            |
| regex_dna                        | 144 ms                                                           | 143 ms: 1.01x faster                                             |
| raytrace                         | 199 ms                                                           | 198 ms: 1.01x faster                                             |
| urlsafe_base64_small             | 379 us                                                           | 377 us: 1.00x faster                                             |
| hexiom                           | 4.42 ms                                                          | 4.40 ms: 1.00x faster                                            |
| pidigits                         | 181 ms                                                           | 181 ms: 1.00x faster                                             |
| sympy_str                        | 193 ms                                                           | 194 ms: 1.00x slower                                             |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.29 sec: 1.00x slower                                           |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.20 ms: 1.01x slower                                            |
| unpickle                         | 10.3 us                                                          | 10.3 us: 1.01x slower                                            |
| base64_small                     | 228 us                                                           | 230 us: 1.01x slower                                             |
| genshi_xml                       | 39.7 ms                                                          | 40.0 ms: 1.01x slower                                            |
| sympy_sum                        | 104 ms                                                           | 105 ms: 1.01x slower                                             |
| pathlib                          | 12.4 ms                                                          | 12.5 ms: 1.01x slower                                            |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 13.5 ms: 1.01x slower                                            |
| telco                            | 5.50 ms                                                          | 5.58 ms: 1.01x slower                                            |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 80.2 ms: 1.01x slower                                            |
| python_startup                   | 9.38 ms                                                          | 9.63 ms: 1.03x slower                                            |
| tornado_http                     | 99.2 ms                                                          | 102 ms: 1.03x slower                                             |
| unpickle_list                    | 3.45 us                                                          | 3.54 us: 1.03x slower                                            |
| sympy_expand                     | 330 ms                                                           | 341 ms: 1.03x slower                                             |
| json_loads                       | 16.7 us                                                          | 17.3 us: 1.03x slower                                            |
| comprehensions                   | 11.6 us                                                          | 12.1 us: 1.04x slower                                            |
| gc_traversal                     | 3.16 ms                                                          | 3.29 ms: 1.04x slower                                            |
| mypy2                            | 726 ms                                                           | 758 ms: 1.04x slower                                             |
| regex_v8                         | 14.7 ms                                                          | 15.4 ms: 1.05x slower                                            |
| django_template                  | 27.3 ms                                                          | 28.6 ms: 1.05x slower                                            |
| docutils                         | 1.98 sec                                                         | 2.08 sec: 1.05x slower                                           |
| coverage                         | 52.2 ms                                                          | 55.3 ms: 1.06x slower                                            |
| pickle_pure_python               | 223 us                                                           | 237 us: 1.06x slower                                             |
| typing_runtime_protocols         | 106 us                                                           | 113 us: 1.07x slower                                             |
| sqlalchemy_imperative            | 13.8 ms                                                          | 14.8 ms: 1.07x slower                                            |
| crypto_pyaes                     | 50.0 ms                                                          | 53.7 ms: 1.07x slower                                            |
| xml_etree_iterparse              | 69.6 ms                                                          | 76.6 ms: 1.10x slower                                            |
| pickle_list                      | 3.03 us                                                          | 3.34 us: 1.10x slower                                            |
| pickle                           | 8.22 us                                                          | 9.24 us: 1.12x slower                                            |
| pprint_safe_repr                 | 541 ms                                                           | 610 ms: 1.13x slower                                             |
| create_gc_cycles                 | 1.70 ms                                                          | 1.92 ms: 1.13x slower                                            |
| pprint_pformat                   | 1.11 sec                                                         | 1.26 sec: 1.14x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 383 ms: 1.19x slower                                             |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 239 ms: 1.38x slower                                             |
| argparse_subparsers              | 446 us                                                           | 688 us: 1.54x slower                                             |
| argparse_many_optionals          | 12.6 ms                                                          | 33.0 ms: 2.63x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                          | 175 ms: 2.99x slower                                             |
| unpack_sequence                  | 26.2 ns                                                          | 102 ns: 3.90x slower                                             |
| Geometric mean                   | (ref)                                                            | 1.08x faster                                                     |

Benchmark hidden because not significant (7): pylint, logging_format, base64_large, logging_silent, logging_simple, sqlglot_v2_parse, xdsl_constant_fold

- Geometric mean (including insignificant results): 1.079x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.03x
- 95% likely to have a speedup of 1.03x
- 99% likely to have a speedup of 1.02x

# Memory
- memory change: 1.08x