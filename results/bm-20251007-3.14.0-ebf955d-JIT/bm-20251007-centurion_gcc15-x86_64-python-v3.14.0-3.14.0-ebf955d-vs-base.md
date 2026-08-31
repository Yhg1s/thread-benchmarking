# Results vs. base

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.001x slower
- HPT reliability: 98.80%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                                                                  | 10.7 ms: 1.01x slower                                                                                        |
| docutils       | 2.02 sec                                                                                                 | 2.08 sec: 1.03x slower                                                                                       |
| fastapi_http   | 215 ms                                                                                                   | 209 ms: 1.03x faster                                                                                         |
| tornado_http   | 101 ms                                                                                                   | 102 ms: 1.01x slower                                                                                         |
| Geometric mean | (ref)                                                                                                    | 1.00x slower                                                                                                 |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|---------------------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| asyncio_tcp                     | 332 ms                                                                                                   | 302 ms: 1.10x faster                                                                                         |
| async_tree_eager_io             | 548 ms                                                                                                   | 526 ms: 1.04x faster                                                                                         |
| async_tree_cpu_io_mixed_tg      | 436 ms                                                                                                   | 421 ms: 1.04x faster                                                                                         |
| async_tree_eager_tg             | 179 ms                                                                                                   | 175 ms: 1.02x faster                                                                                         |
| async_tree_cpu_io_mixed         | 430 ms                                                                                                   | 422 ms: 1.02x faster                                                                                         |
| async_tree_io                   | 527 ms                                                                                                   | 517 ms: 1.02x faster                                                                                         |
| async_tree_memoization_tg       | 275 ms                                                                                                   | 270 ms: 1.02x faster                                                                                         |
| asyncio_websockets              | 305 ms                                                                                                   | 300 ms: 1.01x faster                                                                                         |
| coroutines                      | 15.4 ms                                                                                                  | 15.2 ms: 1.01x faster                                                                                        |
| async_tree_eager_cpu_io_mixed   | 333 ms                                                                                                   | 331 ms: 1.01x faster                                                                                         |
| asyncio_tcp_ssl                 | 1.29 sec                                                                                                 | 1.29 sec: 1.01x slower                                                                                       |
| async_tree_eager_memoization_tg | 235 ms                                                                                                   | 239 ms: 1.01x slower                                                                                         |
| async_tree_eager_memoization    | 175 ms                                                                                                   | 177 ms: 1.01x slower                                                                                         |
| async_generators                | 243 ms                                                                                                   | 258 ms: 1.06x slower                                                                                         |
| async_tree_eager                | 78.8 ms                                                                                                  | 84.0 ms: 1.07x slower                                                                                        |
| Geometric mean                  | (ref)                                                                                                    | 1.01x faster                                                                                                 |

Benchmark hidden because not significant (6): async_tree_eager_io_tg, async_tree_io_tg, async_tree_memoization, async_tree_eager_cpu_io_mixed_tg, async_tree_none, async_tree_none_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| noop      | 18.7 ns                                                                                                  | 15.7 ns: 1.19x faster                                                                                        |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| decimal_pi        | 201 ms                                                                                                   | 194 ms: 1.04x faster                                                                                         |
| decimal_factorial | 170 ms                                                                                                   | 171 ms: 1.00x slower                                                                                         |
| Geometric mean    | (ref)                                                                                                    | 1.02x faster                                                                                                 |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| float          | 48.1 ms                                                                                                  | 39.8 ms: 1.21x faster                                                                                        |
| quadtree_nbody | 602 ms                                                                                                   | 559 ms: 1.08x faster                                                                                         |
| nbody          | 67.2 ms                                                                                                  | 63.4 ms: 1.06x faster                                                                                        |
| pidigits       | 181 ms                                                                                                   | 181 ms: 1.00x faster                                                                                         |
| Geometric mean | (ref)                                                                                                    | 1.09x faster                                                                                                 |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| regex_compile  | 91.6 ms                                                                                                  | 92.5 ms: 1.01x slower                                                                                        |
| regex_dna      | 141 ms                                                                                                   | 143 ms: 1.01x slower                                                                                         |
| regex_v8       | 15.0 ms                                                                                                  | 15.4 ms: 1.02x slower                                                                                        |
| Geometric mean | (ref)                                                                                                    | 1.01x slower                                                                                                 |

Benchmark hidden because not significant (1): regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| unpickle_pure_python | 153 us                                                                                                   | 133 us: 1.15x faster                                                                                         |
| xml_etree_generate   | 71.1 ms                                                                                                  | 64.1 ms: 1.11x faster                                                                                        |
| ascii85_large        | 651 ms                                                                                                   | 592 ms: 1.10x faster                                                                                         |
| ascii85_small        | 12.5 ms                                                                                                  | 11.4 ms: 1.10x faster                                                                                        |
| xml_etree_process    | 50.0 ms                                                                                                  | 45.7 ms: 1.09x faster                                                                                        |
| tomli_loads          | 1.41 sec                                                                                                 | 1.30 sec: 1.09x faster                                                                                       |
| base85_small         | 4.44 ms                                                                                                  | 4.21 ms: 1.06x faster                                                                                        |
| base85_large         | 233 ms                                                                                                   | 221 ms: 1.05x faster                                                                                         |
| unpickle_list        | 3.64 us                                                                                                  | 3.54 us: 1.03x faster                                                                                        |
| urlsafe_base64_small | 383 us                                                                                                   | 377 us: 1.02x faster                                                                                         |
| base16_large         | 5.41 ms                                                                                                  | 5.35 ms: 1.01x faster                                                                                        |
| xml_etree_parse      | 102 ms                                                                                                   | 102 ms: 1.01x faster                                                                                         |
| json_loads           | 17.3 us                                                                                                  | 17.3 us: 1.00x faster                                                                                        |
| pickle               | 9.23 us                                                                                                  | 9.24 us: 1.00x slower                                                                                        |
| xml_etree_iterparse  | 76.5 ms                                                                                                  | 76.6 ms: 1.00x slower                                                                                        |
| base16_small         | 298 us                                                                                                   | 300 us: 1.01x slower                                                                                         |
| json_dumps           | 7.37 ms                                                                                                  | 7.42 ms: 1.01x slower                                                                                        |
| pickle_pure_python   | 234 us                                                                                                   | 237 us: 1.01x slower                                                                                         |
| base32_small         | 5.43 ms                                                                                                  | 5.55 ms: 1.02x slower                                                                                        |
| pickle_list          | 3.26 us                                                                                                  | 3.34 us: 1.03x slower                                                                                        |
| Geometric mean       | (ref)                                                                                                    | 1.03x faster                                                                                                 |

Benchmark hidden because not significant (5): base64_small, base32_large, unpickle, pickle_dict, base64_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|------------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                                                                  | 9.63 ms: 1.00x slower                                                                                        |
| python_startup_no_site | 6.29 ms                                                                                                  | 6.30 ms: 1.00x slower                                                                                        |
| Geometric mean         | (ref)                                                                                                    | 1.00x slower                                                                                                 |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| mako            | 7.66 ms                                                                                                  | 6.79 ms: 1.13x faster                                                                                        |
| genshi_text     | 16.4 ms                                                                                                  | 16.0 ms: 1.02x faster                                                                                        |
| django_template | 28.4 ms                                                                                                  | 28.6 ms: 1.01x slower                                                                                        |
| genshi_xml      | 38.4 ms                                                                                                  | 40.0 ms: 1.04x slower                                                                                        |
| Geometric mean  | (ref)                                                                                                    | 1.02x faster                                                                                                 |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 217 ms                                                                                                   | 200 ms: 1.08x faster                                                                                         |
| thread_memo_naive           | 11.8 ms                                                                                                  | 11.0 ms: 1.08x faster                                                                                        |
| thread_pipeline_optimized   | 26.3 ms                                                                                                  | 24.5 ms: 1.07x faster                                                                                        |
| thread_mandelbrot_optimized | 215 ms                                                                                                   | 201 ms: 1.07x faster                                                                                         |
| thread_counter_optimized    | 18.7 ms                                                                                                  | 17.8 ms: 1.05x faster                                                                                        |
| thread_accumulate_optimized | 40.8 ms                                                                                                  | 39.0 ms: 1.05x faster                                                                                        |
| thread_memo_optimized       | 17.9 ms                                                                                                  | 17.2 ms: 1.04x faster                                                                                        |
| thread_pipeline_naive       | 35.4 ms                                                                                                  | 34.2 ms: 1.04x faster                                                                                        |
| thread_accumulate_naive     | 41.6 ms                                                                                                  | 40.3 ms: 1.03x faster                                                                                        |
| thread_counter_naive        | 21.4 ms                                                                                                  | 20.8 ms: 1.03x faster                                                                                        |
| thread_montecarlo_optimized | 12.6 ms                                                                                                  | 13.5 ms: 1.07x slower                                                                                        |
| thread_montecarlo_naive     | 14.6 ms                                                                                                  | 17.6 ms: 1.20x slower                                                                                        |
| Geometric mean              | (ref)                                                                                                    | 1.02x faster                                                                                                 |

All benchmarks:
===============

| Benchmark                       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|---------------------------------|:--------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
| richards                        | 32.5 ms                                                                                                  | 26.8 ms: 1.21x faster                                                                                        |
| float                           | 48.1 ms                                                                                                  | 39.8 ms: 1.21x faster                                                                                        |
| richards_super                  | 37.2 ms                                                                                                  | 30.9 ms: 1.21x faster                                                                                        |
| noop                            | 18.7 ns                                                                                                  | 15.7 ns: 1.19x faster                                                                                        |
| scimark_fft                     | 197 ms                                                                                                   | 168 ms: 1.17x faster                                                                                         |
| unpickle_pure_python            | 153 us                                                                                                   | 133 us: 1.15x faster                                                                                         |
| spectral_norm                   | 59.6 ms                                                                                                  | 52.7 ms: 1.13x faster                                                                                        |
| mako                            | 7.66 ms                                                                                                  | 6.79 ms: 1.13x faster                                                                                        |
| deltablue                       | 2.24 ms                                                                                                  | 2.00 ms: 1.12x faster                                                                                        |
| xml_etree_generate              | 71.1 ms                                                                                                  | 64.1 ms: 1.11x faster                                                                                        |
| ascii85_large                   | 651 ms                                                                                                   | 592 ms: 1.10x faster                                                                                         |
| asyncio_tcp                     | 332 ms                                                                                                   | 302 ms: 1.10x faster                                                                                         |
| ascii85_small                   | 12.5 ms                                                                                                  | 11.4 ms: 1.10x faster                                                                                        |
| xml_etree_process               | 50.0 ms                                                                                                  | 45.7 ms: 1.09x faster                                                                                        |
| tomli_loads                     | 1.41 sec                                                                                                 | 1.30 sec: 1.09x faster                                                                                       |
| thread_mandelbrot_naive         | 217 ms                                                                                                   | 200 ms: 1.08x faster                                                                                         |
| thread_memo_naive               | 11.8 ms                                                                                                  | 11.0 ms: 1.08x faster                                                                                        |
| quadtree_nbody                  | 602 ms                                                                                                   | 559 ms: 1.08x faster                                                                                         |
| thread_pipeline_optimized       | 26.3 ms                                                                                                  | 24.5 ms: 1.07x faster                                                                                        |
| thread_mandelbrot_optimized     | 215 ms                                                                                                   | 201 ms: 1.07x faster                                                                                         |
| nbody                           | 67.2 ms                                                                                                  | 63.4 ms: 1.06x faster                                                                                        |
| base85_small                    | 4.44 ms                                                                                                  | 4.21 ms: 1.06x faster                                                                                        |
| base85_large                    | 233 ms                                                                                                   | 221 ms: 1.05x faster                                                                                         |
| thread_counter_optimized        | 18.7 ms                                                                                                  | 17.8 ms: 1.05x faster                                                                                        |
| thread_accumulate_optimized     | 40.8 ms                                                                                                  | 39.0 ms: 1.05x faster                                                                                        |
| thread_memo_optimized           | 17.9 ms                                                                                                  | 17.2 ms: 1.04x faster                                                                                        |
| bpe_tokeniser                   | 3.10 sec                                                                                                 | 2.97 sec: 1.04x faster                                                                                       |
| async_tree_eager_io             | 548 ms                                                                                                   | 526 ms: 1.04x faster                                                                                         |
| decimal_pi                      | 201 ms                                                                                                   | 194 ms: 1.04x faster                                                                                         |
| scimark_sparse_mat_mult         | 2.58 ms                                                                                                  | 2.48 ms: 1.04x faster                                                                                        |
| async_tree_cpu_io_mixed_tg      | 436 ms                                                                                                   | 421 ms: 1.04x faster                                                                                         |
| thread_pipeline_naive           | 35.4 ms                                                                                                  | 34.2 ms: 1.04x faster                                                                                        |
| thread_accumulate_naive         | 41.6 ms                                                                                                  | 40.3 ms: 1.03x faster                                                                                        |
| json                            | 3.42 ms                                                                                                  | 3.32 ms: 1.03x faster                                                                                        |
| fastapi_http                    | 215 ms                                                                                                   | 209 ms: 1.03x faster                                                                                         |
| thread_counter_naive            | 21.4 ms                                                                                                  | 20.8 ms: 1.03x faster                                                                                        |
| networkx_shortest_path          | 445 ms                                                                                                   | 433 ms: 1.03x faster                                                                                         |
| unpickle_list                   | 3.64 us                                                                                                  | 3.54 us: 1.03x faster                                                                                        |
| deepcopy_memo                   | 18.2 us                                                                                                  | 17.8 us: 1.03x faster                                                                                        |
| logging_simple                  | 4.72 us                                                                                                  | 4.61 us: 1.02x faster                                                                                        |
| genshi_text                     | 16.4 ms                                                                                                  | 16.0 ms: 1.02x faster                                                                                        |
| async_tree_eager_tg             | 179 ms                                                                                                   | 175 ms: 1.02x faster                                                                                         |
| pyflate                         | 300 ms                                                                                                   | 294 ms: 1.02x faster                                                                                         |
| async_tree_cpu_io_mixed         | 430 ms                                                                                                   | 422 ms: 1.02x faster                                                                                         |
| async_tree_io                   | 527 ms                                                                                                   | 517 ms: 1.02x faster                                                                                         |
| fannkuch                        | 234 ms                                                                                                   | 229 ms: 1.02x faster                                                                                         |
| networkx_connected_components   | 435 ms                                                                                                   | 427 ms: 1.02x faster                                                                                         |
| scimark_monte_carlo             | 37.5 ms                                                                                                  | 36.8 ms: 1.02x faster                                                                                        |
| scimark_sor                     | 72.8 ms                                                                                                  | 71.5 ms: 1.02x faster                                                                                        |
| urlsafe_base64_small            | 383 us                                                                                                   | 377 us: 1.02x faster                                                                                         |
| async_tree_memoization_tg       | 275 ms                                                                                                   | 270 ms: 1.02x faster                                                                                         |
| scimark_lu                      | 66.7 ms                                                                                                  | 65.7 ms: 1.02x faster                                                                                        |
| asyncio_websockets              | 305 ms                                                                                                   | 300 ms: 1.01x faster                                                                                         |
| gc_traversal                    | 3.33 ms                                                                                                  | 3.29 ms: 1.01x faster                                                                                        |
| base16_large                    | 5.41 ms                                                                                                  | 5.35 ms: 1.01x faster                                                                                        |
| mdp                             | 935 ms                                                                                                   | 925 ms: 1.01x faster                                                                                         |
| coroutines                      | 15.4 ms                                                                                                  | 15.2 ms: 1.01x faster                                                                                        |
| argparse_many_optionals         | 33.3 ms                                                                                                  | 33.0 ms: 1.01x faster                                                                                        |
| xml_etree_parse                 | 102 ms                                                                                                   | 102 ms: 1.01x faster                                                                                         |
| async_tree_eager_cpu_io_mixed   | 333 ms                                                                                                   | 331 ms: 1.01x faster                                                                                         |
| logging_format                  | 5.24 us                                                                                                  | 5.21 us: 1.01x faster                                                                                        |
| deepcopy                        | 195 us                                                                                                   | 194 us: 1.01x faster                                                                                         |
| create_gc_cycles                | 1.93 ms                                                                                                  | 1.92 ms: 1.01x faster                                                                                        |
| json_loads                      | 17.3 us                                                                                                  | 17.3 us: 1.00x faster                                                                                        |
| pidigits                        | 181 ms                                                                                                   | 181 ms: 1.00x faster                                                                                         |
| python_startup                  | 9.62 ms                                                                                                  | 9.63 ms: 1.00x slower                                                                                        |
| pickle                          | 9.23 us                                                                                                  | 9.24 us: 1.00x slower                                                                                        |
| xml_etree_iterparse             | 76.5 ms                                                                                                  | 76.6 ms: 1.00x slower                                                                                        |
| python_startup_no_site          | 6.29 ms                                                                                                  | 6.30 ms: 1.00x slower                                                                                        |
| decimal_factorial               | 170 ms                                                                                                   | 171 ms: 1.00x slower                                                                                         |
| nqueens                         | 56.3 ms                                                                                                  | 56.6 ms: 1.01x slower                                                                                        |
| base16_small                    | 298 us                                                                                                   | 300 us: 1.01x slower                                                                                         |
| chameleon                       | 10.6 ms                                                                                                  | 10.7 ms: 1.01x slower                                                                                        |
| json_dumps                      | 7.37 ms                                                                                                  | 7.42 ms: 1.01x slower                                                                                        |
| asyncio_tcp_ssl                 | 1.29 sec                                                                                                 | 1.29 sec: 1.01x slower                                                                                       |
| django_template                 | 28.4 ms                                                                                                  | 28.6 ms: 1.01x slower                                                                                        |
| regex_compile                   | 91.6 ms                                                                                                  | 92.5 ms: 1.01x slower                                                                                        |
| sympy_sum                       | 104 ms                                                                                                   | 105 ms: 1.01x slower                                                                                         |
| sympy_str                       | 192 ms                                                                                                   | 194 ms: 1.01x slower                                                                                         |
| pickle_pure_python              | 234 us                                                                                                   | 237 us: 1.01x slower                                                                                         |
| tornado_http                    | 101 ms                                                                                                   | 102 ms: 1.01x slower                                                                                         |
| regex_dna                       | 141 ms                                                                                                   | 143 ms: 1.01x slower                                                                                         |
| async_tree_eager_memoization_tg | 235 ms                                                                                                   | 239 ms: 1.01x slower                                                                                         |
| async_tree_eager_memoization    | 175 ms                                                                                                   | 177 ms: 1.01x slower                                                                                         |
| logging_silent                  | 59.7 ns                                                                                                  | 60.7 ns: 1.02x slower                                                                                        |
| raytrace                        | 194 ms                                                                                                   | 198 ms: 1.02x slower                                                                                         |
| base32_small                    | 5.43 ms                                                                                                  | 5.55 ms: 1.02x slower                                                                                        |
| sqlglot_v2_optimize             | 38.7 ms                                                                                                  | 39.6 ms: 1.02x slower                                                                                        |
| sympy_integrate                 | 14.7 ms                                                                                                  | 15.1 ms: 1.02x slower                                                                                        |
| regex_v8                        | 15.0 ms                                                                                                  | 15.4 ms: 1.02x slower                                                                                        |
| pycparser                       | 837 ms                                                                                                   | 859 ms: 1.03x slower                                                                                         |
| pickle_list                     | 3.26 us                                                                                                  | 3.34 us: 1.03x slower                                                                                        |
| docutils                        | 2.02 sec                                                                                                 | 2.08 sec: 1.03x slower                                                                                       |
| sqlglot_v2_normalize            | 77.8 ms                                                                                                  | 80.2 ms: 1.03x slower                                                                                        |
| chaos                           | 41.9 ms                                                                                                  | 43.2 ms: 1.03x slower                                                                                        |
| sympy_expand                    | 330 ms                                                                                                   | 341 ms: 1.03x slower                                                                                         |
| argparse_subparsers             | 665 us                                                                                                   | 688 us: 1.03x slower                                                                                         |
| pylint                          | 215 ms                                                                                                   | 223 ms: 1.03x slower                                                                                         |
| sqlalchemy_imperative           | 14.3 ms                                                                                                  | 14.8 ms: 1.03x slower                                                                                        |
| meteor_contest                  | 83.9 ms                                                                                                  | 87.2 ms: 1.04x slower                                                                                        |
| genshi_xml                      | 38.4 ms                                                                                                  | 40.0 ms: 1.04x slower                                                                                        |
| crypto_pyaes                    | 51.5 ms                                                                                                  | 53.7 ms: 1.04x slower                                                                                        |
| sqlglot_v2_transpile            | 1.15 ms                                                                                                  | 1.20 ms: 1.04x slower                                                                                        |
| thrift                          | 1.84 ms                                                                                                  | 1.93 ms: 1.05x slower                                                                                        |
| xdsl_constant_fold              | 35.1 ms                                                                                                  | 36.9 ms: 1.05x slower                                                                                        |
| sqlglot_v2_parse                | 909 us                                                                                                   | 956 us: 1.05x slower                                                                                         |
| telco                           | 5.26 ms                                                                                                  | 5.58 ms: 1.06x slower                                                                                        |
| async_generators                | 243 ms                                                                                                   | 258 ms: 1.06x slower                                                                                         |
| async_tree_eager                | 78.8 ms                                                                                                  | 84.0 ms: 1.07x slower                                                                                        |
| typing_runtime_protocols        | 106 us                                                                                                   | 113 us: 1.07x slower                                                                                         |
| thread_montecarlo_optimized     | 12.6 ms                                                                                                  | 13.5 ms: 1.07x slower                                                                                        |
| comprehensions                  | 11.2 us                                                                                                  | 12.1 us: 1.08x slower                                                                                        |
| hexiom                          | 4.00 ms                                                                                                  | 4.40 ms: 1.10x slower                                                                                        |
| go                              | 82.6 ms                                                                                                  | 97.4 ms: 1.18x slower                                                                                        |
| thread_montecarlo_naive         | 14.6 ms                                                                                                  | 17.6 ms: 1.20x slower                                                                                        |
| pprint_safe_repr                | 484 ms                                                                                                   | 610 ms: 1.26x slower                                                                                         |
| pprint_pformat                  | 982 ms                                                                                                   | 1.26 sec: 1.29x slower                                                                                       |
| unpack_sequence                 | 24.1 ns                                                                                                  | 102 ns: 4.25x slower                                                                                         |
| Geometric mean                  | (ref)                                                                                                    | 1.00x slower                                                                                                 |

Benchmark hidden because not significant (19): async_tree_eager_io_tg, networkx_k_core, async_tree_io_tg, async_tree_memoization, async_tree_eager_cpu_io_mixed_tg, regex_effbot, coverage, base64_small, base32_large, deepcopy_reduce, generators, unpickle, pickle_dict, base64_large, async_tree_none, pathlib, mypy2, html5lib, async_tree_none_tg

- Geometric mean (including insignificant results): 1.001x slower

# HPT report

- Reliability score: 98.80% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.01x