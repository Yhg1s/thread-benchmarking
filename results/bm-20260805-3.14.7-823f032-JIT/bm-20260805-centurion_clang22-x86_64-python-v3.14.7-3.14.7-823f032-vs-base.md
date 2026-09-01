# Results vs. base

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.010x slower
- HPT reliability: 97.09%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.00x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| chameleon      | 10.5 ms                                                                                                    | 11.0 ms: 1.05x slower                                                                                          |
| docutils       | 1.89 sec                                                                                                   | 1.97 sec: 1.04x slower                                                                                         |
| tornado_http   | 103 ms                                                                                                     | 103 ms: 1.01x slower                                                                                           |
| Geometric mean | (ref)                                                                                                      | 1.02x slower                                                                                                   |

Benchmark hidden because not significant (2): fastapi_http, html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                     | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-------------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| async_tree_memoization        | 354 ms                                                                                                     | 340 ms: 1.04x faster                                                                                           |
| async_tree_cpu_io_mixed_tg    | 494 ms                                                                                                     | 483 ms: 1.02x faster                                                                                           |
| async_tree_eager_tg           | 215 ms                                                                                                     | 211 ms: 1.02x faster                                                                                           |
| coroutines                    | 15.6 ms                                                                                                    | 15.7 ms: 1.01x slower                                                                                          |
| async_tree_eager_cpu_io_mixed | 339 ms                                                                                                     | 345 ms: 1.02x slower                                                                                           |
| async_tree_io                 | 683 ms                                                                                                     | 705 ms: 1.03x slower                                                                                           |
| async_tree_eager              | 85.4 ms                                                                                                    | 88.6 ms: 1.04x slower                                                                                          |
| async_tree_eager_memoization  | 193 ms                                                                                                     | 201 ms: 1.04x slower                                                                                           |
| async_generators              | 239 ms                                                                                                     | 259 ms: 1.08x slower                                                                                           |
| asyncio_websockets            | 297 ms                                                                                                     | 328 ms: 1.10x slower                                                                                           |
| Geometric mean                | (ref)                                                                                                      | 1.01x slower                                                                                                   |

Benchmark hidden because not significant (11): async_tree_eager_io_tg, async_tree_none_tg, async_tree_eager_memoization_tg, async_tree_io_tg, async_tree_cpu_io_mixed, asyncio_tcp_ssl, asyncio_tcp, async_tree_none, async_tree_eager_cpu_io_mixed_tg, async_tree_eager_io, async_tree_memoization_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| noop      | 19.2 ns                                                                                                    | 17.6 ns: 1.09x faster                                                                                          |

Benchmarks with tag 'decimal':
==============================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| decimal_pi     | 212 ms                                                                                                     | 209 ms: 1.02x faster                                                                                           |
| Geometric mean | (ref)                                                                                                      | 1.01x faster                                                                                                   |

Benchmark hidden because not significant (1): decimal_factorial

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| float          | 54.3 ms                                                                                                    | 43.9 ms: 1.24x faster                                                                                          |
| quadtree_nbody | 631 ms                                                                                                     | 592 ms: 1.07x faster                                                                                           |
| nbody          | 74.6 ms                                                                                                    | 84.0 ms: 1.13x slower                                                                                          |
| Geometric mean | (ref)                                                                                                      | 1.04x faster                                                                                                   |

Benchmark hidden because not significant (1): pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| regex_dna      | 151 ms                                                                                                     | 146 ms: 1.04x faster                                                                                           |
| regex_compile  | 97.9 ms                                                                                                    | 99.9 ms: 1.02x slower                                                                                          |
| Geometric mean | (ref)                                                                                                      | 1.00x slower                                                                                                   |

Benchmark hidden because not significant (2): regex_v8, regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| unpickle_pure_python | 162 us                                                                                                     | 137 us: 1.18x faster                                                                                           |
| ascii85_large        | 699 ms                                                                                                     | 617 ms: 1.13x faster                                                                                           |
| ascii85_small        | 13.4 ms                                                                                                    | 11.9 ms: 1.13x faster                                                                                          |
| xml_etree_generate   | 67.5 ms                                                                                                    | 61.8 ms: 1.09x faster                                                                                          |
| xml_etree_process    | 48.9 ms                                                                                                    | 45.0 ms: 1.09x faster                                                                                          |
| base85_large         | 254 ms                                                                                                     | 238 ms: 1.07x faster                                                                                           |
| base85_small         | 4.72 ms                                                                                                    | 4.49 ms: 1.05x faster                                                                                          |
| tomli_loads          | 1.50 sec                                                                                                   | 1.44 sec: 1.04x faster                                                                                         |
| urlsafe_base64_small | 338 us                                                                                                     | 335 us: 1.01x faster                                                                                           |
| base16_large         | 6.33 ms                                                                                                    | 6.26 ms: 1.01x faster                                                                                          |
| pickle_list          | 3.20 us                                                                                                    | 3.19 us: 1.00x faster                                                                                          |
| pickle               | 8.05 us                                                                                                    | 8.03 us: 1.00x faster                                                                                          |
| base64_large         | 5.68 ms                                                                                                    | 5.68 ms: 1.00x slower                                                                                          |
| unpickle             | 10.5 us                                                                                                    | 10.6 us: 1.00x slower                                                                                          |
| json_loads           | 19.2 us                                                                                                    | 19.3 us: 1.00x slower                                                                                          |
| json_dumps           | 7.79 ms                                                                                                    | 7.83 ms: 1.01x slower                                                                                          |
| pickle_dict          | 19.4 us                                                                                                    | 19.5 us: 1.01x slower                                                                                          |
| base32_large         | 288 ms                                                                                                     | 293 ms: 1.02x slower                                                                                           |
| base64_small         | 223 us                                                                                                     | 227 us: 1.02x slower                                                                                           |
| xml_etree_iterparse  | 80.4 ms                                                                                                    | 82.2 ms: 1.02x slower                                                                                          |
| pickle_pure_python   | 249 us                                                                                                     | 258 us: 1.04x slower                                                                                           |
| base32_small         | 5.68 ms                                                                                                    | 5.96 ms: 1.05x slower                                                                                          |
| Geometric mean       | (ref)                                                                                                      | 1.02x faster                                                                                                   |

Benchmark hidden because not significant (3): unpickle_list, xml_etree_parse, base16_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| python_startup         | 10.0 ms                                                                                                    | 10.00 ms: 1.00x faster                                                                                         |
| python_startup_no_site | 6.53 ms                                                                                                    | 6.56 ms: 1.00x slower                                                                                          |
| Geometric mean         | (ref)                                                                                                      | 1.00x slower                                                                                                   |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| mako            | 8.64 ms                                                                                                    | 7.44 ms: 1.16x faster                                                                                          |
| genshi_xml      | 43.8 ms                                                                                                    | 45.1 ms: 1.03x slower                                                                                          |
| genshi_text     | 18.2 ms                                                                                                    | 18.9 ms: 1.04x slower                                                                                          |
| django_template | 30.3 ms                                                                                                    | 31.7 ms: 1.05x slower                                                                                          |
| Geometric mean  | (ref)                                                                                                      | 1.01x faster                                                                                                   |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_pipeline_optimized   | 25.5 ms                                                                                                    | 23.1 ms: 1.10x faster                                                                                          |
| thread_memo_naive           | 12.3 ms                                                                                                    | 11.2 ms: 1.10x faster                                                                                          |
| thread_accumulate_optimized | 39.0 ms                                                                                                    | 35.9 ms: 1.09x faster                                                                                          |
| thread_accumulate_naive     | 40.0 ms                                                                                                    | 36.8 ms: 1.09x faster                                                                                          |
| thread_memo_optimized       | 17.5 ms                                                                                                    | 16.2 ms: 1.08x faster                                                                                          |
| thread_pipeline_naive       | 35.3 ms                                                                                                    | 33.6 ms: 1.05x faster                                                                                          |
| thread_counter_optimized    | 18.4 ms                                                                                                    | 17.7 ms: 1.04x faster                                                                                          |
| thread_counter_naive        | 21.6 ms                                                                                                    | 20.8 ms: 1.04x faster                                                                                          |
| thread_mandelbrot_optimized | 201 ms                                                                                                     | 204 ms: 1.01x slower                                                                                           |
| thread_montecarlo_optimized | 12.9 ms                                                                                                    | 14.4 ms: 1.12x slower                                                                                          |
| thread_montecarlo_naive     | 14.8 ms                                                                                                    | 18.5 ms: 1.25x slower                                                                                          |
| Geometric mean              | (ref)                                                                                                      | 1.02x faster                                                                                                   |

Benchmark hidden because not significant (1): thread_mandelbrot_naive

All benchmarks:
===============

| Benchmark                     | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-------------------------------|:----------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| scimark_fft                   | 220 ms                                                                                                     | 177 ms: 1.25x faster                                                                                           |
| float                         | 54.3 ms                                                                                                    | 43.9 ms: 1.24x faster                                                                                          |
| deltablue                     | 2.61 ms                                                                                                    | 2.17 ms: 1.20x faster                                                                                          |
| richards                      | 35.0 ms                                                                                                    | 29.4 ms: 1.19x faster                                                                                          |
| unpickle_pure_python          | 162 us                                                                                                     | 137 us: 1.18x faster                                                                                           |
| mako                          | 8.64 ms                                                                                                    | 7.44 ms: 1.16x faster                                                                                          |
| richards_super                | 40.4 ms                                                                                                    | 34.8 ms: 1.16x faster                                                                                          |
| ascii85_large                 | 699 ms                                                                                                     | 617 ms: 1.13x faster                                                                                           |
| ascii85_small                 | 13.4 ms                                                                                                    | 11.9 ms: 1.13x faster                                                                                          |
| spectral_norm                 | 66.0 ms                                                                                                    | 59.2 ms: 1.11x faster                                                                                          |
| thread_pipeline_optimized     | 25.5 ms                                                                                                    | 23.1 ms: 1.10x faster                                                                                          |
| thread_memo_naive             | 12.3 ms                                                                                                    | 11.2 ms: 1.10x faster                                                                                          |
| xml_etree_generate            | 67.5 ms                                                                                                    | 61.8 ms: 1.09x faster                                                                                          |
| noop                          | 19.2 ns                                                                                                    | 17.6 ns: 1.09x faster                                                                                          |
| xml_etree_process             | 48.9 ms                                                                                                    | 45.0 ms: 1.09x faster                                                                                          |
| thread_accumulate_optimized   | 39.0 ms                                                                                                    | 35.9 ms: 1.09x faster                                                                                          |
| thread_accumulate_naive       | 40.0 ms                                                                                                    | 36.8 ms: 1.09x faster                                                                                          |
| thread_memo_optimized         | 17.5 ms                                                                                                    | 16.2 ms: 1.08x faster                                                                                          |
| quadtree_nbody                | 631 ms                                                                                                     | 592 ms: 1.07x faster                                                                                           |
| base85_large                  | 254 ms                                                                                                     | 238 ms: 1.07x faster                                                                                           |
| bpe_tokeniser                 | 3.20 sec                                                                                                   | 3.03 sec: 1.05x faster                                                                                         |
| thread_pipeline_naive         | 35.3 ms                                                                                                    | 33.6 ms: 1.05x faster                                                                                          |
| base85_small                  | 4.72 ms                                                                                                    | 4.49 ms: 1.05x faster                                                                                          |
| tomli_loads                   | 1.50 sec                                                                                                   | 1.44 sec: 1.04x faster                                                                                         |
| thread_counter_optimized      | 18.4 ms                                                                                                    | 17.7 ms: 1.04x faster                                                                                          |
| async_tree_memoization        | 354 ms                                                                                                     | 340 ms: 1.04x faster                                                                                           |
| thread_counter_naive          | 21.6 ms                                                                                                    | 20.8 ms: 1.04x faster                                                                                          |
| regex_dna                     | 151 ms                                                                                                     | 146 ms: 1.04x faster                                                                                           |
| nqueens                       | 62.7 ms                                                                                                    | 60.8 ms: 1.03x faster                                                                                          |
| async_tree_cpu_io_mixed_tg    | 494 ms                                                                                                     | 483 ms: 1.02x faster                                                                                           |
| pyflate                       | 312 ms                                                                                                     | 307 ms: 1.02x faster                                                                                           |
| async_tree_eager_tg           | 215 ms                                                                                                     | 211 ms: 1.02x faster                                                                                           |
| decimal_pi                    | 212 ms                                                                                                     | 209 ms: 1.02x faster                                                                                           |
| scimark_sparse_mat_mult       | 2.84 ms                                                                                                    | 2.80 ms: 1.02x faster                                                                                          |
| urlsafe_base64_small          | 338 us                                                                                                     | 335 us: 1.01x faster                                                                                           |
| base16_large                  | 6.33 ms                                                                                                    | 6.26 ms: 1.01x faster                                                                                          |
| pathlib                       | 12.7 ms                                                                                                    | 12.6 ms: 1.01x faster                                                                                          |
| pickle_list                   | 3.20 us                                                                                                    | 3.19 us: 1.00x faster                                                                                          |
| pickle                        | 8.05 us                                                                                                    | 8.03 us: 1.00x faster                                                                                          |
| python_startup                | 10.0 ms                                                                                                    | 10.00 ms: 1.00x faster                                                                                         |
| base64_large                  | 5.68 ms                                                                                                    | 5.68 ms: 1.00x slower                                                                                          |
| unpickle                      | 10.5 us                                                                                                    | 10.6 us: 1.00x slower                                                                                          |
| python_startup_no_site        | 6.53 ms                                                                                                    | 6.56 ms: 1.00x slower                                                                                          |
| json_loads                    | 19.2 us                                                                                                    | 19.3 us: 1.00x slower                                                                                          |
| json_dumps                    | 7.79 ms                                                                                                    | 7.83 ms: 1.01x slower                                                                                          |
| pickle_dict                   | 19.4 us                                                                                                    | 19.5 us: 1.01x slower                                                                                          |
| chaos                         | 42.5 ms                                                                                                    | 42.8 ms: 1.01x slower                                                                                          |
| mdp                           | 984 ms                                                                                                     | 991 ms: 1.01x slower                                                                                           |
| tornado_http                  | 103 ms                                                                                                     | 103 ms: 1.01x slower                                                                                           |
| deepcopy_reduce               | 2.06 us                                                                                                    | 2.07 us: 1.01x slower                                                                                          |
| networkx_connected_components | 430 ms                                                                                                     | 434 ms: 1.01x slower                                                                                           |
| coroutines                    | 15.6 ms                                                                                                    | 15.7 ms: 1.01x slower                                                                                          |
| logging_format                | 5.73 us                                                                                                    | 5.80 us: 1.01x slower                                                                                          |
| thread_mandelbrot_optimized   | 201 ms                                                                                                     | 204 ms: 1.01x slower                                                                                           |
| base32_large                  | 288 ms                                                                                                     | 293 ms: 1.02x slower                                                                                           |
| create_gc_cycles              | 1.87 ms                                                                                                    | 1.90 ms: 1.02x slower                                                                                          |
| meteor_contest                | 85.4 ms                                                                                                    | 86.8 ms: 1.02x slower                                                                                          |
| gc_traversal                  | 3.25 ms                                                                                                    | 3.30 ms: 1.02x slower                                                                                          |
| base64_small                  | 223 us                                                                                                     | 227 us: 1.02x slower                                                                                           |
| async_tree_eager_cpu_io_mixed | 339 ms                                                                                                     | 345 ms: 1.02x slower                                                                                           |
| crypto_pyaes                  | 56.9 ms                                                                                                    | 58.0 ms: 1.02x slower                                                                                          |
| regex_compile                 | 97.9 ms                                                                                                    | 99.9 ms: 1.02x slower                                                                                          |
| telco                         | 5.38 ms                                                                                                    | 5.49 ms: 1.02x slower                                                                                          |
| sympy_sum                     | 110 ms                                                                                                     | 113 ms: 1.02x slower                                                                                           |
| deepcopy_memo                 | 19.1 us                                                                                                    | 19.5 us: 1.02x slower                                                                                          |
| xml_etree_iterparse           | 80.4 ms                                                                                                    | 82.2 ms: 1.02x slower                                                                                          |
| logging_simple                | 5.09 us                                                                                                    | 5.21 us: 1.02x slower                                                                                          |
| networkx_shortest_path        | 440 ms                                                                                                     | 451 ms: 1.02x slower                                                                                           |
| fannkuch                      | 250 ms                                                                                                     | 256 ms: 1.03x slower                                                                                           |
| genshi_xml                    | 43.8 ms                                                                                                    | 45.1 ms: 1.03x slower                                                                                          |
| sympy_integrate               | 15.4 ms                                                                                                    | 15.9 ms: 1.03x slower                                                                                          |
| async_tree_io                 | 683 ms                                                                                                     | 705 ms: 1.03x slower                                                                                           |
| sqlglot_v2_optimize           | 41.6 ms                                                                                                    | 43.0 ms: 1.03x slower                                                                                          |
| raytrace                      | 201 ms                                                                                                     | 208 ms: 1.03x slower                                                                                           |
| sqlglot_v2_normalize          | 84.5 ms                                                                                                    | 87.4 ms: 1.04x slower                                                                                          |
| pickle_pure_python            | 249 us                                                                                                     | 258 us: 1.04x slower                                                                                           |
| pylint                        | 229 ms                                                                                                     | 237 ms: 1.04x slower                                                                                           |
| sympy_str                     | 201 ms                                                                                                     | 209 ms: 1.04x slower                                                                                           |
| async_tree_eager              | 85.4 ms                                                                                                    | 88.6 ms: 1.04x slower                                                                                          |
| docutils                      | 1.89 sec                                                                                                   | 1.97 sec: 1.04x slower                                                                                         |
| genshi_text                   | 18.2 ms                                                                                                    | 18.9 ms: 1.04x slower                                                                                          |
| async_tree_eager_memoization  | 193 ms                                                                                                     | 201 ms: 1.04x slower                                                                                           |
| sqlalchemy_imperative         | 15.0 ms                                                                                                    | 15.6 ms: 1.04x slower                                                                                          |
| sympy_expand                  | 344 ms                                                                                                     | 359 ms: 1.04x slower                                                                                           |
| deepcopy                      | 199 us                                                                                                     | 207 us: 1.04x slower                                                                                           |
| django_template               | 30.3 ms                                                                                                    | 31.7 ms: 1.05x slower                                                                                          |
| argparse_many_optionals       | 8.02 ms                                                                                                    | 8.38 ms: 1.05x slower                                                                                          |
| typing_runtime_protocols      | 113 us                                                                                                     | 118 us: 1.05x slower                                                                                           |
| base32_small                  | 5.68 ms                                                                                                    | 5.96 ms: 1.05x slower                                                                                          |
| chameleon                     | 10.5 ms                                                                                                    | 11.0 ms: 1.05x slower                                                                                          |
| thrift                        | 2.00 ms                                                                                                    | 2.11 ms: 1.05x slower                                                                                          |
| sqlglot_v2_parse              | 958 us                                                                                                     | 1.01 ms: 1.06x slower                                                                                          |
| networkx_k_core               | 2.05 sec                                                                                                   | 2.18 sec: 1.06x slower                                                                                         |
| argparse_subparsers           | 503 us                                                                                                     | 534 us: 1.06x slower                                                                                           |
| sqlglot_v2_transpile          | 1.19 ms                                                                                                    | 1.27 ms: 1.06x slower                                                                                          |
| pycparser                     | 937 ms                                                                                                     | 997 ms: 1.06x slower                                                                                           |
| async_generators              | 239 ms                                                                                                     | 259 ms: 1.08x slower                                                                                           |
| comprehensions                | 11.1 us                                                                                                    | 12.2 us: 1.09x slower                                                                                          |
| hexiom                        | 4.39 ms                                                                                                    | 4.81 ms: 1.10x slower                                                                                          |
| asyncio_websockets            | 297 ms                                                                                                     | 328 ms: 1.10x slower                                                                                           |
| thread_montecarlo_optimized   | 12.9 ms                                                                                                    | 14.4 ms: 1.12x slower                                                                                          |
| nbody                         | 74.6 ms                                                                                                    | 84.0 ms: 1.13x slower                                                                                          |
| go                            | 93.1 ms                                                                                                    | 105 ms: 1.13x slower                                                                                           |
| scimark_monte_carlo           | 46.0 ms                                                                                                    | 52.3 ms: 1.14x slower                                                                                          |
| thread_montecarlo_naive       | 14.8 ms                                                                                                    | 18.5 ms: 1.25x slower                                                                                          |
| pprint_safe_repr              | 531 ms                                                                                                     | 667 ms: 1.26x slower                                                                                           |
| pprint_pformat                | 1.10 sec                                                                                                   | 1.39 sec: 1.26x slower                                                                                         |
| mypy2                         | 753 ms                                                                                                     | 1.09 sec: 1.45x slower                                                                                         |
| unpack_sequence               | 36.4 ns                                                                                                    | 107 ns: 2.93x slower                                                                                           |
| Geometric mean                | (ref)                                                                                                      | 1.01x slower                                                                                                   |

Benchmark hidden because not significant (28): async_tree_eager_io_tg, async_tree_none_tg, async_tree_eager_memoization_tg, scimark_lu, async_tree_io_tg, html5lib, async_tree_cpu_io_mixed, logging_silent, coverage, generators, pidigits, xdsl_constant_fold, unpickle_list, regex_v8, thread_mandelbrot_naive, fastapi_http, decimal_factorial, json, asyncio_tcp_ssl, scimark_sor, asyncio_tcp, xml_etree_parse, base16_small, async_tree_none, async_tree_eager_cpu_io_mixed_tg, async_tree_eager_io, async_tree_memoization_tg, regex_effbot

- Geometric mean (including insignificant results): 1.010x slower

# HPT report

- Reliability score: 97.09% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.00x