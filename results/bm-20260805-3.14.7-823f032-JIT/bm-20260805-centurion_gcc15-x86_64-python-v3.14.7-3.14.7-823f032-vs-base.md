# Results vs. base

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.004x slower
- HPT reliability: 99.86%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| docutils       | 1.95 sec                                                                                                 | 1.99 sec: 1.02x slower                                                                                       |
| fastapi_http   | 211 ms                                                                                                   | 205 ms: 1.03x faster                                                                                         |
| Geometric mean | (ref)                                                                                                    | 1.01x faster                                                                                                 |

Benchmark hidden because not significant (3): chameleon, html5lib, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| async_tree_memoization           | 335 ms                                                                                                   | 321 ms: 1.04x faster                                                                                         |
| async_tree_cpu_io_mixed_tg       | 496 ms                                                                                                   | 476 ms: 1.04x faster                                                                                         |
| async_tree_cpu_io_mixed          | 479 ms                                                                                                   | 464 ms: 1.03x faster                                                                                         |
| async_tree_eager_cpu_io_mixed_tg | 428 ms                                                                                                   | 419 ms: 1.02x faster                                                                                         |
| async_tree_eager_tg              | 210 ms                                                                                                   | 206 ms: 1.02x faster                                                                                         |
| async_tree_eager_io              | 649 ms                                                                                                   | 638 ms: 1.02x faster                                                                                         |
| async_tree_eager_cpu_io_mixed    | 345 ms                                                                                                   | 340 ms: 1.01x faster                                                                                         |
| async_tree_io                    | 654 ms                                                                                                   | 665 ms: 1.02x slower                                                                                         |
| async_tree_eager_memoization     | 182 ms                                                                                                   | 189 ms: 1.04x slower                                                                                         |
| async_tree_eager                 | 78.9 ms                                                                                                  | 84.4 ms: 1.07x slower                                                                                        |
| async_generators                 | 247 ms                                                                                                   | 264 ms: 1.07x slower                                                                                         |
| Geometric mean                   | (ref)                                                                                                    | 1.00x faster                                                                                                 |

Benchmark hidden because not significant (10): async_tree_eager_io_tg, async_tree_none_tg, async_tree_eager_memoization_tg, async_tree_io_tg, asyncio_tcp, coroutines, asyncio_tcp_ssl, async_tree_none, async_tree_memoization_tg, asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| noop      | 18.8 ns                                                                                                  | 15.7 ns: 1.20x faster                                                                                        |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| decimal_pi        | 204 ms                                                                                                   | 198 ms: 1.03x faster                                                                                         |
| decimal_factorial | 170 ms                                                                                                   | 170 ms: 1.00x faster                                                                                         |
| Geometric mean    | (ref)                                                                                                    | 1.01x faster                                                                                                 |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| float          | 49.5 ms                                                                                                  | 42.2 ms: 1.17x faster                                                                                        |
| nbody          | 69.1 ms                                                                                                  | 62.7 ms: 1.10x faster                                                                                        |
| quadtree_nbody | 591 ms                                                                                                   | 557 ms: 1.06x faster                                                                                         |
| pidigits       | 181 ms                                                                                                   | 181 ms: 1.00x faster                                                                                         |
| Geometric mean | (ref)                                                                                                    | 1.08x faster                                                                                                 |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| regex_v8       | 15.7 ms                                                                                                  | 15.4 ms: 1.02x faster                                                                                        |
| Geometric mean | (ref)                                                                                                    | 1.00x faster                                                                                                 |

Benchmark hidden because not significant (3): regex_effbot, regex_compile, regex_dna

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| unpickle_pure_python | 152 us                                                                                                   | 131 us: 1.16x faster                                                                                         |
| xml_etree_generate   | 71.8 ms                                                                                                  | 65.0 ms: 1.10x faster                                                                                        |
| ascii85_small        | 12.7 ms                                                                                                  | 11.6 ms: 1.10x faster                                                                                        |
| xml_etree_process    | 50.6 ms                                                                                                  | 46.7 ms: 1.08x faster                                                                                        |
| base85_large         | 235 ms                                                                                                   | 220 ms: 1.07x faster                                                                                         |
| base85_small         | 4.44 ms                                                                                                  | 4.17 ms: 1.06x faster                                                                                        |
| tomli_loads          | 1.43 sec                                                                                                 | 1.34 sec: 1.06x faster                                                                                       |
| pickle               | 9.59 us                                                                                                  | 9.29 us: 1.03x faster                                                                                        |
| ascii85_large        | 657 ms                                                                                                   | 647 ms: 1.02x faster                                                                                         |
| xml_etree_parse      | 109 ms                                                                                                   | 107 ms: 1.02x faster                                                                                         |
| json_dumps           | 7.59 ms                                                                                                  | 7.48 ms: 1.02x faster                                                                                        |
| json_loads           | 19.1 us                                                                                                  | 18.8 us: 1.01x faster                                                                                        |
| xml_etree_iterparse  | 74.5 ms                                                                                                  | 74.1 ms: 1.01x faster                                                                                        |
| pickle_dict          | 21.3 us                                                                                                  | 21.2 us: 1.01x faster                                                                                        |
| base32_large         | 277 ms                                                                                                   | 278 ms: 1.01x slower                                                                                         |
| base64_small         | 211 us                                                                                                   | 213 us: 1.01x slower                                                                                         |
| base64_large         | 5.01 ms                                                                                                  | 5.04 ms: 1.01x slower                                                                                        |
| unpickle             | 10.4 us                                                                                                  | 10.5 us: 1.01x slower                                                                                        |
| unpickle_list        | 3.60 us                                                                                                  | 3.66 us: 1.02x slower                                                                                        |
| base32_small         | 5.46 ms                                                                                                  | 5.56 ms: 1.02x slower                                                                                        |
| pickle_pure_python   | 228 us                                                                                                   | 234 us: 1.03x slower                                                                                         |
| pickle_list          | 3.76 us                                                                                                  | 3.87 us: 1.03x slower                                                                                        |
| base16_small         | 303 us                                                                                                   | 334 us: 1.10x slower                                                                                         |
| base16_large         | 5.35 ms                                                                                                  | 7.44 ms: 1.39x slower                                                                                        |
| Geometric mean       | (ref)                                                                                                    | 1.01x faster                                                                                                 |

Benchmark hidden because not significant (1): urlsafe_base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|------------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| python_startup_no_site | 6.31 ms                                                                                                  | 6.35 ms: 1.00x slower                                                                                        |
| python_startup         | 9.71 ms                                                                                                  | 9.77 ms: 1.01x slower                                                                                        |
| Geometric mean         | (ref)                                                                                                    | 1.01x slower                                                                                                 |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| mako            | 8.28 ms                                                                                                  | 7.44 ms: 1.11x faster                                                                                        |
| genshi_text     | 16.4 ms                                                                                                  | 16.2 ms: 1.01x faster                                                                                        |
| django_template | 28.0 ms                                                                                                  | 28.5 ms: 1.02x slower                                                                                        |
| Geometric mean  | (ref)                                                                                                    | 1.03x faster                                                                                                 |

Benchmark hidden because not significant (1): genshi_xml

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 225 ms                                                                                                   | 208 ms: 1.08x faster                                                                                         |
| thread_mandelbrot_optimized | 225 ms                                                                                                   | 209 ms: 1.07x faster                                                                                         |
| thread_memo_naive           | 11.7 ms                                                                                                  | 11.0 ms: 1.07x faster                                                                                        |
| thread_pipeline_optimized   | 26.7 ms                                                                                                  | 25.0 ms: 1.07x faster                                                                                        |
| thread_memo_optimized       | 18.2 ms                                                                                                  | 17.1 ms: 1.06x faster                                                                                        |
| thread_accumulate_optimized | 41.5 ms                                                                                                  | 39.2 ms: 1.06x faster                                                                                        |
| thread_counter_optimized    | 18.5 ms                                                                                                  | 17.5 ms: 1.06x faster                                                                                        |
| thread_accumulate_naive     | 42.3 ms                                                                                                  | 40.1 ms: 1.05x faster                                                                                        |
| thread_counter_naive        | 21.2 ms                                                                                                  | 20.3 ms: 1.04x faster                                                                                        |
| thread_pipeline_naive       | 35.1 ms                                                                                                  | 34.6 ms: 1.01x faster                                                                                        |
| thread_montecarlo_optimized | 12.8 ms                                                                                                  | 13.5 ms: 1.06x slower                                                                                        |
| thread_montecarlo_naive     | 14.7 ms                                                                                                  | 18.2 ms: 1.24x slower                                                                                        |
| Geometric mean              | (ref)                                                                                                    | 1.02x faster                                                                                                 |

All benchmarks:
===============

| Benchmark                        | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| scimark_fft                      | 202 ms                                                                                                   | 168 ms: 1.20x faster                                                                                         |
| noop                             | 18.8 ns                                                                                                  | 15.7 ns: 1.20x faster                                                                                        |
| float                            | 49.5 ms                                                                                                  | 42.2 ms: 1.17x faster                                                                                        |
| unpickle_pure_python             | 152 us                                                                                                   | 131 us: 1.16x faster                                                                                         |
| richards_super                   | 36.8 ms                                                                                                  | 32.0 ms: 1.15x faster                                                                                        |
| richards                         | 31.6 ms                                                                                                  | 27.7 ms: 1.14x faster                                                                                        |
| deltablue                        | 2.21 ms                                                                                                  | 1.97 ms: 1.12x faster                                                                                        |
| mako                             | 8.28 ms                                                                                                  | 7.44 ms: 1.11x faster                                                                                        |
| xml_etree_generate               | 71.8 ms                                                                                                  | 65.0 ms: 1.10x faster                                                                                        |
| nbody                            | 69.1 ms                                                                                                  | 62.7 ms: 1.10x faster                                                                                        |
| ascii85_small                    | 12.7 ms                                                                                                  | 11.6 ms: 1.10x faster                                                                                        |
| spectral_norm                    | 60.6 ms                                                                                                  | 55.5 ms: 1.09x faster                                                                                        |
| thread_mandelbrot_naive          | 225 ms                                                                                                   | 208 ms: 1.08x faster                                                                                         |
| xml_etree_process                | 50.6 ms                                                                                                  | 46.7 ms: 1.08x faster                                                                                        |
| thread_mandelbrot_optimized      | 225 ms                                                                                                   | 209 ms: 1.07x faster                                                                                         |
| base85_large                     | 235 ms                                                                                                   | 220 ms: 1.07x faster                                                                                         |
| thread_memo_naive                | 11.7 ms                                                                                                  | 11.0 ms: 1.07x faster                                                                                        |
| thread_pipeline_optimized        | 26.7 ms                                                                                                  | 25.0 ms: 1.07x faster                                                                                        |
| base85_small                     | 4.44 ms                                                                                                  | 4.17 ms: 1.06x faster                                                                                        |
| tomli_loads                      | 1.43 sec                                                                                                 | 1.34 sec: 1.06x faster                                                                                       |
| thread_memo_optimized            | 18.2 ms                                                                                                  | 17.1 ms: 1.06x faster                                                                                        |
| quadtree_nbody                   | 591 ms                                                                                                   | 557 ms: 1.06x faster                                                                                         |
| thread_accumulate_optimized      | 41.5 ms                                                                                                  | 39.2 ms: 1.06x faster                                                                                        |
| thread_counter_optimized         | 18.5 ms                                                                                                  | 17.5 ms: 1.06x faster                                                                                        |
| thread_accumulate_naive          | 42.3 ms                                                                                                  | 40.1 ms: 1.05x faster                                                                                        |
| bpe_tokeniser                    | 3.20 sec                                                                                                 | 3.05 sec: 1.05x faster                                                                                       |
| scimark_sparse_mat_mult          | 2.59 ms                                                                                                  | 2.48 ms: 1.04x faster                                                                                        |
| async_tree_memoization           | 335 ms                                                                                                   | 321 ms: 1.04x faster                                                                                         |
| async_tree_cpu_io_mixed_tg       | 496 ms                                                                                                   | 476 ms: 1.04x faster                                                                                         |
| thread_counter_naive             | 21.2 ms                                                                                                  | 20.3 ms: 1.04x faster                                                                                        |
| generators                       | 21.0 ms                                                                                                  | 20.2 ms: 1.04x faster                                                                                        |
| fannkuch                         | 234 ms                                                                                                   | 227 ms: 1.03x faster                                                                                         |
| async_tree_cpu_io_mixed          | 479 ms                                                                                                   | 464 ms: 1.03x faster                                                                                         |
| pickle                           | 9.59 us                                                                                                  | 9.29 us: 1.03x faster                                                                                        |
| fastapi_http                     | 211 ms                                                                                                   | 205 ms: 1.03x faster                                                                                         |
| nqueens                          | 56.3 ms                                                                                                  | 54.7 ms: 1.03x faster                                                                                        |
| decimal_pi                       | 204 ms                                                                                                   | 198 ms: 1.03x faster                                                                                         |
| json                             | 3.65 ms                                                                                                  | 3.56 ms: 1.02x faster                                                                                        |
| deepcopy_reduce                  | 1.98 us                                                                                                  | 1.93 us: 1.02x faster                                                                                        |
| async_tree_eager_cpu_io_mixed_tg | 428 ms                                                                                                   | 419 ms: 1.02x faster                                                                                         |
| async_tree_eager_tg              | 210 ms                                                                                                   | 206 ms: 1.02x faster                                                                                         |
| networkx_connected_components    | 435 ms                                                                                                   | 427 ms: 1.02x faster                                                                                         |
| scimark_sor                      | 71.8 ms                                                                                                  | 70.4 ms: 1.02x faster                                                                                        |
| networkx_shortest_path           | 442 ms                                                                                                   | 433 ms: 1.02x faster                                                                                         |
| chaos                            | 41.8 ms                                                                                                  | 41.1 ms: 1.02x faster                                                                                        |
| async_tree_eager_io              | 649 ms                                                                                                   | 638 ms: 1.02x faster                                                                                         |
| ascii85_large                    | 657 ms                                                                                                   | 647 ms: 1.02x faster                                                                                         |
| xml_etree_parse                  | 109 ms                                                                                                   | 107 ms: 1.02x faster                                                                                         |
| regex_v8                         | 15.7 ms                                                                                                  | 15.4 ms: 1.02x faster                                                                                        |
| json_dumps                       | 7.59 ms                                                                                                  | 7.48 ms: 1.02x faster                                                                                        |
| mdp                              | 945 ms                                                                                                   | 931 ms: 1.02x faster                                                                                         |
| async_tree_eager_cpu_io_mixed    | 345 ms                                                                                                   | 340 ms: 1.01x faster                                                                                         |
| thread_pipeline_naive            | 35.1 ms                                                                                                  | 34.6 ms: 1.01x faster                                                                                        |
| json_loads                       | 19.1 us                                                                                                  | 18.8 us: 1.01x faster                                                                                        |
| genshi_text                      | 16.4 ms                                                                                                  | 16.2 ms: 1.01x faster                                                                                        |
| deepcopy                         | 192 us                                                                                                   | 189 us: 1.01x faster                                                                                         |
| logging_format                   | 5.20 us                                                                                                  | 5.15 us: 1.01x faster                                                                                        |
| logging_simple                   | 4.57 us                                                                                                  | 4.53 us: 1.01x faster                                                                                        |
| scimark_lu                       | 66.8 ms                                                                                                  | 66.3 ms: 1.01x faster                                                                                        |
| deepcopy_memo                    | 18.2 us                                                                                                  | 18.1 us: 1.01x faster                                                                                        |
| xml_etree_iterparse              | 74.5 ms                                                                                                  | 74.1 ms: 1.01x faster                                                                                        |
| create_gc_cycles                 | 1.83 ms                                                                                                  | 1.82 ms: 1.01x faster                                                                                        |
| pickle_dict                      | 21.3 us                                                                                                  | 21.2 us: 1.01x faster                                                                                        |
| sympy_sum                        | 105 ms                                                                                                   | 105 ms: 1.00x faster                                                                                         |
| decimal_factorial                | 170 ms                                                                                                   | 170 ms: 1.00x faster                                                                                         |
| meteor_contest                   | 86.1 ms                                                                                                  | 85.8 ms: 1.00x faster                                                                                        |
| pidigits                         | 181 ms                                                                                                   | 181 ms: 1.00x faster                                                                                         |
| sympy_str                        | 192 ms                                                                                                   | 192 ms: 1.00x slower                                                                                         |
| python_startup_no_site           | 6.31 ms                                                                                                  | 6.35 ms: 1.00x slower                                                                                        |
| base32_large                     | 277 ms                                                                                                   | 278 ms: 1.01x slower                                                                                         |
| python_startup                   | 9.71 ms                                                                                                  | 9.77 ms: 1.01x slower                                                                                        |
| base64_small                     | 211 us                                                                                                   | 213 us: 1.01x slower                                                                                         |
| base64_large                     | 5.01 ms                                                                                                  | 5.04 ms: 1.01x slower                                                                                        |
| sqlglot_v2_normalize             | 78.2 ms                                                                                                  | 78.8 ms: 1.01x slower                                                                                        |
| argparse_many_optionals          | 7.41 ms                                                                                                  | 7.47 ms: 1.01x slower                                                                                        |
| unpickle                         | 10.4 us                                                                                                  | 10.5 us: 1.01x slower                                                                                        |
| sqlglot_v2_optimize              | 39.0 ms                                                                                                  | 39.4 ms: 1.01x slower                                                                                        |
| logging_silent                   | 59.2 ns                                                                                                  | 60.1 ns: 1.01x slower                                                                                        |
| sympy_expand                     | 333 ms                                                                                                   | 338 ms: 1.01x slower                                                                                         |
| sympy_integrate                  | 14.7 ms                                                                                                  | 14.9 ms: 1.02x slower                                                                                        |
| pathlib                          | 12.4 ms                                                                                                  | 12.6 ms: 1.02x slower                                                                                        |
| unpickle_list                    | 3.60 us                                                                                                  | 3.66 us: 1.02x slower                                                                                        |
| async_tree_io                    | 654 ms                                                                                                   | 665 ms: 1.02x slower                                                                                         |
| raytrace                         | 192 ms                                                                                                   | 195 ms: 1.02x slower                                                                                         |
| typing_runtime_protocols         | 107 us                                                                                                   | 109 us: 1.02x slower                                                                                         |
| thrift                           | 1.83 ms                                                                                                  | 1.86 ms: 1.02x slower                                                                                        |
| base32_small                     | 5.46 ms                                                                                                  | 5.56 ms: 1.02x slower                                                                                        |
| django_template                  | 28.0 ms                                                                                                  | 28.5 ms: 1.02x slower                                                                                        |
| coverage                         | 52.8 ms                                                                                                  | 53.9 ms: 1.02x slower                                                                                        |
| docutils                         | 1.95 sec                                                                                                 | 1.99 sec: 1.02x slower                                                                                       |
| pickle_pure_python               | 228 us                                                                                                   | 234 us: 1.03x slower                                                                                         |
| pickle_list                      | 3.76 us                                                                                                  | 3.87 us: 1.03x slower                                                                                        |
| argparse_subparsers              | 489 us                                                                                                   | 505 us: 1.03x slower                                                                                         |
| sqlalchemy_imperative            | 14.2 ms                                                                                                  | 14.7 ms: 1.03x slower                                                                                        |
| pycparser                        | 859 ms                                                                                                   | 890 ms: 1.04x slower                                                                                         |
| async_tree_eager_memoization     | 182 ms                                                                                                   | 189 ms: 1.04x slower                                                                                         |
| crypto_pyaes                     | 51.9 ms                                                                                                  | 54.4 ms: 1.05x slower                                                                                        |
| sqlglot_v2_transpile             | 1.13 ms                                                                                                  | 1.18 ms: 1.05x slower                                                                                        |
| sqlglot_v2_parse                 | 887 us                                                                                                   | 933 us: 1.05x slower                                                                                         |
| thread_montecarlo_optimized      | 12.8 ms                                                                                                  | 13.5 ms: 1.06x slower                                                                                        |
| async_tree_eager                 | 78.9 ms                                                                                                  | 84.4 ms: 1.07x slower                                                                                        |
| async_generators                 | 247 ms                                                                                                   | 264 ms: 1.07x slower                                                                                         |
| comprehensions                   | 11.1 us                                                                                                  | 12.0 us: 1.09x slower                                                                                        |
| hexiom                           | 4.02 ms                                                                                                  | 4.40 ms: 1.10x slower                                                                                        |
| base16_small                     | 303 us                                                                                                   | 334 us: 1.10x slower                                                                                         |
| go                               | 82.3 ms                                                                                                  | 96.6 ms: 1.17x slower                                                                                        |
| thread_montecarlo_naive          | 14.7 ms                                                                                                  | 18.2 ms: 1.24x slower                                                                                        |
| pprint_pformat                   | 996 ms                                                                                                   | 1.27 sec: 1.28x slower                                                                                       |
| pprint_safe_repr                 | 481 ms                                                                                                   | 620 ms: 1.29x slower                                                                                         |
| base16_large                     | 5.35 ms                                                                                                  | 7.44 ms: 1.39x slower                                                                                        |
| mypy2                            | 725 ms                                                                                                   | 1.04 sec: 1.44x slower                                                                                       |
| unpack_sequence                  | 25.0 ns                                                                                                  | 102 ns: 4.07x slower                                                                                         |
| Geometric mean                   | (ref)                                                                                                    | 1.01x slower                                                                                                 |

Benchmark hidden because not significant (25): html5lib, async_tree_eager_io_tg, async_tree_none_tg, async_tree_eager_memoization_tg, async_tree_io_tg, xdsl_constant_fold, asyncio_tcp, tornado_http, coroutines, scimark_monte_carlo, telco, urlsafe_base64_small, genshi_xml, chameleon, asyncio_tcp_ssl, gc_traversal, pyflate, regex_effbot, regex_compile, regex_dna, async_tree_none, async_tree_memoization_tg, networkx_k_core, asyncio_websockets, pylint

- Geometric mean (including insignificant results): 1.004x slower

# HPT report

- Reliability score: 99.86% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.01x