# Results vs. base

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.007x faster
- HPT reliability: 75.51%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.06x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                                                                    | 11.1 ms: 1.01x faster                                                                                          |
| docutils       | 1.89 sec                                                                                                   | 1.99 sec: 1.06x slower                                                                                         |
| fastapi_http   | 215 ms                                                                                                     | 219 ms: 1.02x slower                                                                                           |
| tornado_http   | 98.9 ms                                                                                                    | 101 ms: 1.02x slower                                                                                           |
| Geometric mean | (ref)                                                                                                      | 1.02x slower                                                                                                   |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| asyncio_tcp                      | 316 ms                                                                                                     | 301 ms: 1.05x faster                                                                                           |
| asyncio_websockets               | 313 ms                                                                                                     | 300 ms: 1.04x faster                                                                                           |
| async_tree_memoization_tg        | 421 ms                                                                                                     | 419 ms: 1.00x faster                                                                                           |
| async_tree_cpu_io_mixed          | 494 ms                                                                                                     | 498 ms: 1.01x slower                                                                                           |
| asyncio_tcp_ssl                  | 1.28 sec                                                                                                   | 1.29 sec: 1.01x slower                                                                                         |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                                                                     | 305 ms: 1.01x slower                                                                                           |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                                                                     | 349 ms: 1.02x slower                                                                                           |
| async_tree_eager_tg              | 56.8 ms                                                                                                    | 58.4 ms: 1.03x slower                                                                                          |
| async_tree_eager_memoization     | 221 ms                                                                                                     | 228 ms: 1.03x slower                                                                                           |
| async_generators                 | 251 ms                                                                                                     | 272 ms: 1.08x slower                                                                                           |
| async_tree_eager                 | 88.3 ms                                                                                                    | 96.3 ms: 1.09x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                      | 1.01x slower                                                                                                   |

Benchmark hidden because not significant (10): async_tree_eager_io_tg, coroutines, async_tree_none_tg, async_tree_io_tg, async_tree_none, async_tree_memoization, async_tree_cpu_io_mixed_tg, async_tree_eager_io, async_tree_io, async_tree_eager_memoization_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| noop      | 21.4 ns                                                                                                    | 20.3 ns: 1.05x faster                                                                                          |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                                                                     | 213 ms: 1.07x faster                                                                                           |
| decimal_factorial | 177 ms                                                                                                     | 177 ms: 1.00x slower                                                                                           |
| Geometric mean    | (ref)                                                                                                      | 1.03x faster                                                                                                   |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| nbody          | 75.8 ms                                                                                                    | 61.7 ms: 1.23x faster                                                                                          |
| quadtree_nbody | 675 ms                                                                                                     | 554 ms: 1.22x faster                                                                                           |
| float          | 59.2 ms                                                                                                    | 53.4 ms: 1.11x faster                                                                                          |
| pidigits       | 216 ms                                                                                                     | 213 ms: 1.01x faster                                                                                           |
| Geometric mean | (ref)                                                                                                      | 1.14x faster                                                                                                   |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                                                                    | 14.7 ms: 1.02x faster                                                                                          |
| regex_dna      | 159 ms                                                                                                     | 155 ms: 1.02x faster                                                                                           |
| regex_compile  | 102 ms                                                                                                     | 103 ms: 1.01x slower                                                                                           |
| Geometric mean | (ref)                                                                                                      | 1.01x faster                                                                                                   |

Benchmark hidden because not significant (1): regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| ascii85_large        | 824 ms                                                                                                     | 563 ms: 1.46x faster                                                                                           |
| ascii85_small        | 15.7 ms                                                                                                    | 11.3 ms: 1.40x faster                                                                                          |
| tomli_loads          | 1.77 sec                                                                                                   | 1.52 sec: 1.16x faster                                                                                         |
| unpickle_list        | 3.42 us                                                                                                    | 3.09 us: 1.11x faster                                                                                          |
| xml_etree_generate   | 70.6 ms                                                                                                    | 63.8 ms: 1.11x faster                                                                                          |
| pickle_pure_python   | 245 us                                                                                                     | 222 us: 1.11x faster                                                                                           |
| unpickle_pure_python | 161 us                                                                                                     | 147 us: 1.10x faster                                                                                           |
| base85_small         | 4.85 ms                                                                                                    | 4.46 ms: 1.09x faster                                                                                          |
| base85_large         | 267 ms                                                                                                     | 246 ms: 1.09x faster                                                                                           |
| xml_etree_process    | 49.9 ms                                                                                                    | 46.1 ms: 1.08x faster                                                                                          |
| base32_small         | 6.46 ms                                                                                                    | 6.11 ms: 1.06x faster                                                                                          |
| base32_large         | 325 ms                                                                                                     | 310 ms: 1.05x faster                                                                                           |
| json_dumps           | 7.26 ms                                                                                                    | 6.97 ms: 1.04x faster                                                                                          |
| unpickle             | 10.8 us                                                                                                    | 10.5 us: 1.03x faster                                                                                          |
| xml_etree_iterparse  | 86.8 ms                                                                                                    | 85.0 ms: 1.02x faster                                                                                          |
| json_loads           | 18.2 us                                                                                                    | 18.1 us: 1.01x faster                                                                                          |
| xml_etree_parse      | 121 ms                                                                                                     | 120 ms: 1.01x faster                                                                                           |
| base16_large         | 42.7 ms                                                                                                    | 42.6 ms: 1.00x faster                                                                                          |
| base16_small         | 836 us                                                                                                     | 839 us: 1.00x slower                                                                                           |
| urlsafe_base64_small | 328 us                                                                                                     | 331 us: 1.01x slower                                                                                           |
| pickle               | 7.21 us                                                                                                    | 7.33 us: 1.02x slower                                                                                          |
| pickle_dict          | 19.0 us                                                                                                    | 19.6 us: 1.03x slower                                                                                          |
| pickle_list          | 2.66 us                                                                                                    | 2.78 us: 1.05x slower                                                                                          |
| Geometric mean       | (ref)                                                                                                      | 1.07x faster                                                                                                   |

Benchmark hidden because not significant (2): base64_small, base64_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                                                                    | 10.3 ms: 1.08x slower                                                                                          |
| python_startup_no_site | 6.49 ms                                                                                                    | 7.29 ms: 1.12x slower                                                                                          |
| Geometric mean         | (ref)                                                                                                      | 1.10x slower                                                                                                   |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| mako            | 8.30 ms                                                                                                    | 6.61 ms: 1.26x faster                                                                                          |
| genshi_xml      | 46.3 ms                                                                                                    | 51.9 ms: 1.12x slower                                                                                          |
| django_template | 28.8 ms                                                                                                    | 33.4 ms: 1.16x slower                                                                                          |
| Geometric mean  | (ref)                                                                                                      | 1.01x slower                                                                                                   |

Benchmark hidden because not significant (1): genshi_text

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_counter_optimized    | 19.7 ms                                                                                                    | 17.7 ms: 1.12x faster                                                                                          |
| thread_memo_optimized       | 16.8 ms                                                                                                    | 15.2 ms: 1.11x faster                                                                                          |
| thread_counter_naive        | 23.7 ms                                                                                                    | 21.6 ms: 1.10x faster                                                                                          |
| thread_mandelbrot_naive     | 190 ms                                                                                                     | 175 ms: 1.08x faster                                                                                           |
| thread_mandelbrot_optimized | 189 ms                                                                                                     | 175 ms: 1.08x faster                                                                                           |
| thread_montecarlo_optimized | 14.2 ms                                                                                                    | 13.5 ms: 1.05x faster                                                                                          |
| thread_accumulate_optimized | 35.3 ms                                                                                                    | 33.6 ms: 1.05x faster                                                                                          |
| thread_accumulate_naive     | 36.5 ms                                                                                                    | 34.7 ms: 1.05x faster                                                                                          |
| thread_pipeline_optimized   | 22.8 ms                                                                                                    | 22.2 ms: 1.03x faster                                                                                          |
| thread_montecarlo_naive     | 18.1 ms                                                                                                    | 19.9 ms: 1.10x slower                                                                                          |
| Geometric mean              | (ref)                                                                                                      | 1.05x faster                                                                                                   |

Benchmark hidden because not significant (2): thread_pipeline_naive, thread_memo_naive

All benchmarks:
===============

| Benchmark                        | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| ascii85_large                    | 824 ms                                                                                                     | 563 ms: 1.46x faster                                                                                           |
| ascii85_small                    | 15.7 ms                                                                                                    | 11.3 ms: 1.40x faster                                                                                          |
| fannkuch                         | 287 ms                                                                                                     | 216 ms: 1.33x faster                                                                                           |
| mako                             | 8.30 ms                                                                                                    | 6.61 ms: 1.26x faster                                                                                          |
| nbody                            | 75.8 ms                                                                                                    | 61.7 ms: 1.23x faster                                                                                          |
| quadtree_nbody                   | 675 ms                                                                                                     | 554 ms: 1.22x faster                                                                                           |
| scimark_fft                      | 216 ms                                                                                                     | 178 ms: 1.21x faster                                                                                           |
| deepcopy_memo                    | 27.8 us                                                                                                    | 23.4 us: 1.19x faster                                                                                          |
| richards                         | 38.2 ms                                                                                                    | 32.5 ms: 1.17x faster                                                                                          |
| richards_super                   | 43.8 ms                                                                                                    | 37.4 ms: 1.17x faster                                                                                          |
| tomli_loads                      | 1.77 sec                                                                                                   | 1.52 sec: 1.16x faster                                                                                         |
| pyflate                          | 374 ms                                                                                                     | 322 ms: 1.16x faster                                                                                           |
| scimark_monte_carlo              | 47.2 ms                                                                                                    | 41.0 ms: 1.15x faster                                                                                          |
| thread_counter_optimized         | 19.7 ms                                                                                                    | 17.7 ms: 1.12x faster                                                                                          |
| thread_memo_optimized            | 16.8 ms                                                                                                    | 15.2 ms: 1.11x faster                                                                                          |
| float                            | 59.2 ms                                                                                                    | 53.4 ms: 1.11x faster                                                                                          |
| unpickle_list                    | 3.42 us                                                                                                    | 3.09 us: 1.11x faster                                                                                          |
| xml_etree_generate               | 70.6 ms                                                                                                    | 63.8 ms: 1.11x faster                                                                                          |
| crypto_pyaes                     | 55.6 ms                                                                                                    | 50.3 ms: 1.11x faster                                                                                          |
| pickle_pure_python               | 245 us                                                                                                     | 222 us: 1.11x faster                                                                                           |
| spectral_norm                    | 68.6 ms                                                                                                    | 62.0 ms: 1.11x faster                                                                                          |
| thread_counter_naive             | 23.7 ms                                                                                                    | 21.6 ms: 1.10x faster                                                                                          |
| unpickle_pure_python             | 161 us                                                                                                     | 147 us: 1.10x faster                                                                                           |
| base85_small                     | 4.85 ms                                                                                                    | 4.46 ms: 1.09x faster                                                                                          |
| base85_large                     | 267 ms                                                                                                     | 246 ms: 1.09x faster                                                                                           |
| xml_etree_process                | 49.9 ms                                                                                                    | 46.1 ms: 1.08x faster                                                                                          |
| thread_mandelbrot_naive          | 190 ms                                                                                                     | 175 ms: 1.08x faster                                                                                           |
| thread_mandelbrot_optimized      | 189 ms                                                                                                     | 175 ms: 1.08x faster                                                                                           |
| decimal_pi                       | 228 ms                                                                                                     | 213 ms: 1.07x faster                                                                                           |
| scimark_sparse_mat_mult          | 2.86 ms                                                                                                    | 2.68 ms: 1.06x faster                                                                                          |
| base32_small                     | 6.46 ms                                                                                                    | 6.11 ms: 1.06x faster                                                                                          |
| noop                             | 21.4 ns                                                                                                    | 20.3 ns: 1.05x faster                                                                                          |
| thread_montecarlo_optimized      | 14.2 ms                                                                                                    | 13.5 ms: 1.05x faster                                                                                          |
| thread_accumulate_optimized      | 35.3 ms                                                                                                    | 33.6 ms: 1.05x faster                                                                                          |
| thread_accumulate_naive          | 36.5 ms                                                                                                    | 34.7 ms: 1.05x faster                                                                                          |
| asyncio_tcp                      | 316 ms                                                                                                     | 301 ms: 1.05x faster                                                                                           |
| base32_large                     | 325 ms                                                                                                     | 310 ms: 1.05x faster                                                                                           |
| asyncio_websockets               | 313 ms                                                                                                     | 300 ms: 1.04x faster                                                                                           |
| json_dumps                       | 7.26 ms                                                                                                    | 6.97 ms: 1.04x faster                                                                                          |
| bpe_tokeniser                    | 3.37 sec                                                                                                   | 3.27 sec: 1.03x faster                                                                                         |
| deepcopy                         | 267 us                                                                                                     | 259 us: 1.03x faster                                                                                           |
| unpickle                         | 10.8 us                                                                                                    | 10.5 us: 1.03x faster                                                                                          |
| go                               | 129 ms                                                                                                     | 126 ms: 1.03x faster                                                                                           |
| thread_pipeline_optimized        | 22.8 ms                                                                                                    | 22.2 ms: 1.03x faster                                                                                          |
| json                             | 3.50 ms                                                                                                    | 3.42 ms: 1.02x faster                                                                                          |
| regex_v8                         | 15.0 ms                                                                                                    | 14.7 ms: 1.02x faster                                                                                          |
| networkx_k_core                  | 2.16 sec                                                                                                   | 2.11 sec: 1.02x faster                                                                                         |
| networkx_connected_components    | 443 ms                                                                                                     | 433 ms: 1.02x faster                                                                                           |
| xml_etree_iterparse              | 86.8 ms                                                                                                    | 85.0 ms: 1.02x faster                                                                                          |
| regex_dna                        | 159 ms                                                                                                     | 155 ms: 1.02x faster                                                                                           |
| networkx_shortest_path           | 454 ms                                                                                                     | 447 ms: 1.02x faster                                                                                           |
| sqlglot_v2_parse                 | 979 us                                                                                                     | 965 us: 1.01x faster                                                                                           |
| pidigits                         | 216 ms                                                                                                     | 213 ms: 1.01x faster                                                                                           |
| scimark_sor                      | 96.2 ms                                                                                                    | 95.3 ms: 1.01x faster                                                                                          |
| json_loads                       | 18.2 us                                                                                                    | 18.1 us: 1.01x faster                                                                                          |
| hexiom                           | 4.75 ms                                                                                                    | 4.72 ms: 1.01x faster                                                                                          |
| xml_etree_parse                  | 121 ms                                                                                                     | 120 ms: 1.01x faster                                                                                           |
| chameleon                        | 11.1 ms                                                                                                    | 11.1 ms: 1.01x faster                                                                                          |
| async_tree_memoization_tg        | 421 ms                                                                                                     | 419 ms: 1.00x faster                                                                                           |
| create_gc_cycles                 | 1.77 ms                                                                                                    | 1.77 ms: 1.00x faster                                                                                          |
| gc_traversal                     | 3.20 ms                                                                                                    | 3.19 ms: 1.00x faster                                                                                          |
| base16_large                     | 42.7 ms                                                                                                    | 42.6 ms: 1.00x faster                                                                                          |
| base16_small                     | 836 us                                                                                                     | 839 us: 1.00x slower                                                                                           |
| decimal_factorial                | 177 ms                                                                                                     | 177 ms: 1.00x slower                                                                                           |
| regex_compile                    | 102 ms                                                                                                     | 103 ms: 1.01x slower                                                                                           |
| meteor_contest                   | 85.7 ms                                                                                                    | 86.4 ms: 1.01x slower                                                                                          |
| async_tree_cpu_io_mixed          | 494 ms                                                                                                     | 498 ms: 1.01x slower                                                                                           |
| mdp                              | 2.05 sec                                                                                                   | 2.08 sec: 1.01x slower                                                                                         |
| asyncio_tcp_ssl                  | 1.28 sec                                                                                                   | 1.29 sec: 1.01x slower                                                                                         |
| urlsafe_base64_small             | 328 us                                                                                                     | 331 us: 1.01x slower                                                                                           |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                                                                     | 305 ms: 1.01x slower                                                                                           |
| logging_format                   | 5.62 us                                                                                                    | 5.70 us: 1.01x slower                                                                                          |
| fastapi_http                     | 215 ms                                                                                                     | 219 ms: 1.02x slower                                                                                           |
| comprehensions                   | 11.4 us                                                                                                    | 11.6 us: 1.02x slower                                                                                          |
| pickle                           | 7.21 us                                                                                                    | 7.33 us: 1.02x slower                                                                                          |
| logging_simple                   | 5.06 us                                                                                                    | 5.15 us: 1.02x slower                                                                                          |
| sqlglot_v2_transpile             | 1.22 ms                                                                                                    | 1.24 ms: 1.02x slower                                                                                          |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                                                                     | 349 ms: 1.02x slower                                                                                           |
| tornado_http                     | 98.9 ms                                                                                                    | 101 ms: 1.02x slower                                                                                           |
| pickle_dict                      | 19.0 us                                                                                                    | 19.6 us: 1.03x slower                                                                                          |
| async_tree_eager_tg              | 56.8 ms                                                                                                    | 58.4 ms: 1.03x slower                                                                                          |
| argparse_many_optionals          | 12.9 ms                                                                                                    | 13.3 ms: 1.03x slower                                                                                          |
| pathlib                          | 12.2 ms                                                                                                    | 12.6 ms: 1.03x slower                                                                                          |
| async_tree_eager_memoization     | 221 ms                                                                                                     | 228 ms: 1.03x slower                                                                                           |
| sqlalchemy_imperative            | 13.9 ms                                                                                                    | 14.3 ms: 1.03x slower                                                                                          |
| raytrace                         | 197 ms                                                                                                     | 204 ms: 1.03x slower                                                                                           |
| pycparser                        | 901 ms                                                                                                     | 933 ms: 1.03x slower                                                                                           |
| sqlglot_v2_optimize              | 42.1 ms                                                                                                    | 43.7 ms: 1.04x slower                                                                                          |
| telco                            | 5.37 ms                                                                                                    | 5.58 ms: 1.04x slower                                                                                          |
| argparse_subparsers              | 449 us                                                                                                     | 468 us: 1.04x slower                                                                                           |
| generators                       | 22.2 ms                                                                                                    | 23.2 ms: 1.04x slower                                                                                          |
| pickle_list                      | 2.66 us                                                                                                    | 2.78 us: 1.05x slower                                                                                          |
| xdsl_constant_fold               | 36.4 ms                                                                                                    | 38.1 ms: 1.05x slower                                                                                          |
| nqueens                          | 58.3 ms                                                                                                    | 61.4 ms: 1.05x slower                                                                                          |
| chaos                            | 43.6 ms                                                                                                    | 45.9 ms: 1.05x slower                                                                                          |
| docutils                         | 1.89 sec                                                                                                   | 1.99 sec: 1.06x slower                                                                                         |
| typing_runtime_protocols         | 112 us                                                                                                     | 119 us: 1.06x slower                                                                                           |
| sympy_str                        | 193 ms                                                                                                     | 209 ms: 1.08x slower                                                                                           |
| python_startup                   | 9.51 ms                                                                                                    | 10.3 ms: 1.08x slower                                                                                          |
| mypy2                            | 741 ms                                                                                                     | 803 ms: 1.08x slower                                                                                           |
| sqlglot_v2_normalize             | 83.6 ms                                                                                                    | 90.7 ms: 1.08x slower                                                                                          |
| async_generators                 | 251 ms                                                                                                     | 272 ms: 1.08x slower                                                                                           |
| sympy_sum                        | 104 ms                                                                                                     | 114 ms: 1.09x slower                                                                                           |
| thrift                           | 2.07 ms                                                                                                    | 2.26 ms: 1.09x slower                                                                                          |
| async_tree_eager                 | 88.3 ms                                                                                                    | 96.3 ms: 1.09x slower                                                                                          |
| deltablue                        | 2.59 ms                                                                                                    | 2.83 ms: 1.09x slower                                                                                          |
| sympy_expand                     | 331 ms                                                                                                     | 363 ms: 1.10x slower                                                                                           |
| thread_montecarlo_naive          | 18.1 ms                                                                                                    | 19.9 ms: 1.10x slower                                                                                          |
| pprint_safe_repr                 | 546 ms                                                                                                     | 600 ms: 1.10x slower                                                                                           |
| pprint_pformat                   | 1.13 sec                                                                                                   | 1.24 sec: 1.10x slower                                                                                         |
| sympy_integrate                  | 15.4 ms                                                                                                    | 17.1 ms: 1.11x slower                                                                                          |
| genshi_xml                       | 46.3 ms                                                                                                    | 51.9 ms: 1.12x slower                                                                                          |
| python_startup_no_site           | 6.49 ms                                                                                                    | 7.29 ms: 1.12x slower                                                                                          |
| pylint                           | 226 ms                                                                                                     | 255 ms: 1.13x slower                                                                                           |
| django_template                  | 28.8 ms                                                                                                    | 33.4 ms: 1.16x slower                                                                                          |
| scimark_lu                       | 70.2 ms                                                                                                    | 99.8 ms: 1.42x slower                                                                                          |
| unpack_sequence                  | 26.4 ns                                                                                                    | 82.2 ns: 3.11x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                      | 1.01x faster                                                                                                   |

Benchmark hidden because not significant (20): thread_pipeline_naive, async_tree_eager_io_tg, regex_effbot, coroutines, base64_small, genshi_text, html5lib, base64_large, async_tree_none_tg, async_tree_io_tg, deepcopy_reduce, coverage, async_tree_none, async_tree_memoization, async_tree_cpu_io_mixed_tg, thread_memo_naive, async_tree_eager_io, logging_silent, async_tree_io, async_tree_eager_memoization_tg

- Geometric mean (including insignificant results): 1.007x faster

# HPT report

- Reliability score: 75.51% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.06x