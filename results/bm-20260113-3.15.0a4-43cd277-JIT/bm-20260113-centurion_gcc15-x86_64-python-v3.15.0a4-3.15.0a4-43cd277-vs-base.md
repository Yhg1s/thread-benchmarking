# Results vs. base

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.036x faster
- HPT reliability: 99.89%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|----------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                                                                        | 10.6 ms: 1.01x slower                                                                                              |
| docutils       | 2.01 sec                                                                                                       | 2.10 sec: 1.05x slower                                                                                             |
| fastapi_http   | 208 ms                                                                                                         | 200 ms: 1.04x faster                                                                                               |
| html5lib       | 43.4 ms                                                                                                        | 43.2 ms: 1.01x faster                                                                                              |
| tornado_http   | 97.8 ms                                                                                                        | 99.3 ms: 1.02x slower                                                                                              |
| Geometric mean | (ref)                                                                                                          | 1.01x slower                                                                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                     | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|-------------------------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| async_tree_none               | 217 ms                                                                                                         | 206 ms: 1.05x faster                                                                                               |
| async_tree_memoization        | 265 ms                                                                                                         | 254 ms: 1.04x faster                                                                                               |
| async_tree_eager_tg           | 178 ms                                                                                                         | 170 ms: 1.04x faster                                                                                               |
| async_tree_memoization_tg     | 262 ms                                                                                                         | 253 ms: 1.04x faster                                                                                               |
| async_tree_io_tg              | 485 ms                                                                                                         | 471 ms: 1.03x faster                                                                                               |
| async_tree_cpu_io_mixed       | 439 ms                                                                                                         | 427 ms: 1.03x faster                                                                                               |
| asyncio_tcp                   | 279 ms                                                                                                         | 273 ms: 1.02x faster                                                                                               |
| coroutines                    | 15.4 ms                                                                                                        | 15.2 ms: 1.01x faster                                                                                              |
| asyncio_tcp_ssl               | 1.27 sec                                                                                                       | 1.27 sec: 1.00x slower                                                                                             |
| async_tree_eager              | 77.5 ms                                                                                                        | 78.3 ms: 1.01x slower                                                                                              |
| async_tree_eager_memoization  | 166 ms                                                                                                         | 170 ms: 1.02x slower                                                                                               |
| async_tree_eager_cpu_io_mixed | 353 ms                                                                                                         | 363 ms: 1.03x slower                                                                                               |
| async_generators              | 240 ms                                                                                                         | 258 ms: 1.07x slower                                                                                               |
| Geometric mean                | (ref)                                                                                                          | 1.01x faster                                                                                                       |

Benchmark hidden because not significant (8): async_tree_io, async_tree_eager_cpu_io_mixed_tg, async_tree_eager_io, async_tree_eager_io_tg, async_tree_cpu_io_mixed_tg, asyncio_websockets, async_tree_eager_memoization_tg, async_tree_none_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|-----------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| noop      | 19.4 ns                                                                                                        | 16.7 ns: 1.16x faster                                                                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|-------------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| decimal_pi        | 207 ms                                                                                                         | 191 ms: 1.08x faster                                                                                               |
| decimal_factorial | 171 ms                                                                                                         | 171 ms: 1.01x faster                                                                                               |
| Geometric mean    | (ref)                                                                                                          | 1.04x faster                                                                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|----------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| nbody          | 65.8 ms                                                                                                        | 49.0 ms: 1.34x faster                                                                                              |
| float          | 48.0 ms                                                                                                        | 38.7 ms: 1.24x faster                                                                                              |
| quadtree_nbody | 593 ms                                                                                                         | 517 ms: 1.15x faster                                                                                               |
| pidigits       | 182 ms                                                                                                         | 181 ms: 1.00x faster                                                                                               |
| Geometric mean | (ref)                                                                                                          | 1.18x faster                                                                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|----------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| regex_compile  | 90.8 ms                                                                                                        | 81.2 ms: 1.12x faster                                                                                              |
| regex_dna      | 140 ms                                                                                                         | 139 ms: 1.00x faster                                                                                               |
| Geometric mean | (ref)                                                                                                          | 1.03x faster                                                                                                       |

Benchmark hidden because not significant (2): regex_effbot, regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|----------------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| unpickle_pure_python | 151 us                                                                                                         | 116 us: 1.30x faster                                                                                               |
| ascii85_large        | 653 ms                                                                                                         | 536 ms: 1.22x faster                                                                                               |
| urlsafe_base64_small | 372 us                                                                                                         | 306 us: 1.21x faster                                                                                               |
| ascii85_small        | 12.7 ms                                                                                                        | 10.6 ms: 1.20x faster                                                                                              |
| base64_small         | 221 us                                                                                                         | 190 us: 1.16x faster                                                                                               |
| base16_small         | 307 us                                                                                                         | 269 us: 1.14x faster                                                                                               |
| pickle_pure_python   | 233 us                                                                                                         | 208 us: 1.12x faster                                                                                               |
| base85_small         | 4.60 ms                                                                                                        | 4.12 ms: 1.12x faster                                                                                              |
| xml_etree_process    | 49.3 ms                                                                                                        | 45.1 ms: 1.09x faster                                                                                              |
| json_dumps           | 6.72 ms                                                                                                        | 6.17 ms: 1.09x faster                                                                                              |
| xml_etree_generate   | 68.8 ms                                                                                                        | 63.2 ms: 1.09x faster                                                                                              |
| base85_large         | 242 ms                                                                                                         | 225 ms: 1.08x faster                                                                                               |
| tomli_loads          | 1.53 sec                                                                                                       | 1.43 sec: 1.08x faster                                                                                             |
| base32_small         | 5.67 ms                                                                                                        | 5.53 ms: 1.03x faster                                                                                              |
| xml_etree_iterparse  | 69.5 ms                                                                                                        | 68.0 ms: 1.02x faster                                                                                              |
| pickle_list          | 3.33 us                                                                                                        | 3.26 us: 1.02x faster                                                                                              |
| pickle               | 9.36 us                                                                                                        | 9.19 us: 1.02x faster                                                                                              |
| base64_large         | 5.87 ms                                                                                                        | 5.86 ms: 1.00x faster                                                                                              |
| pickle_dict          | 21.3 us                                                                                                        | 21.4 us: 1.00x slower                                                                                              |
| base32_large         | 279 ms                                                                                                         | 281 ms: 1.01x slower                                                                                               |
| unpickle_list        | 3.51 us                                                                                                        | 3.55 us: 1.01x slower                                                                                              |
| json_loads           | 17.3 us                                                                                                        | 17.6 us: 1.01x slower                                                                                              |
| Geometric mean       | (ref)                                                                                                          | 1.07x faster                                                                                                       |

Benchmark hidden because not significant (3): unpickle, base16_large, xml_etree_parse

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|------------------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| python_startup_no_site | 6.09 ms                                                                                                        | 6.15 ms: 1.01x slower                                                                                              |
| python_startup         | 9.27 ms                                                                                                        | 9.36 ms: 1.01x slower                                                                                              |
| Geometric mean         | (ref)                                                                                                          | 1.01x slower                                                                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark      | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|----------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| mako           | 9.06 ms                                                                                                        | 6.56 ms: 1.38x faster                                                                                              |
| genshi_text    | 16.2 ms                                                                                                        | 16.9 ms: 1.05x slower                                                                                              |
| genshi_xml     | 39.5 ms                                                                                                        | 44.8 ms: 1.13x slower                                                                                              |
| Geometric mean | (ref)                                                                                                          | 1.04x faster                                                                                                       |

Benchmark hidden because not significant (1): django_template

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|-----------------------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 219 ms                                                                                                         | 190 ms: 1.16x faster                                                                                               |
| thread_mandelbrot_optimized | 219 ms                                                                                                         | 193 ms: 1.14x faster                                                                                               |
| thread_pipeline_naive       | 37.3 ms                                                                                                        | 33.1 ms: 1.13x faster                                                                                              |
| thread_pipeline_optimized   | 29.5 ms                                                                                                        | 26.2 ms: 1.12x faster                                                                                              |
| thread_accumulate_optimized | 45.4 ms                                                                                                        | 40.8 ms: 1.11x faster                                                                                              |
| thread_counter_naive        | 22.8 ms                                                                                                        | 20.6 ms: 1.11x faster                                                                                              |
| thread_memo_naive           | 9.85 ms                                                                                                        | 8.90 ms: 1.11x faster                                                                                              |
| thread_counter_optimized    | 20.9 ms                                                                                                        | 18.9 ms: 1.11x faster                                                                                              |
| thread_memo_optimized       | 19.3 ms                                                                                                        | 17.5 ms: 1.11x faster                                                                                              |
| thread_accumulate_naive     | 45.4 ms                                                                                                        | 41.1 ms: 1.10x faster                                                                                              |
| thread_montecarlo_optimized | 13.3 ms                                                                                                        | 13.3 ms: 1.00x slower                                                                                              |
| thread_montecarlo_naive     | 15.4 ms                                                                                                        | 16.4 ms: 1.06x slower                                                                                              |
| Geometric mean              | (ref)                                                                                                          | 1.09x faster                                                                                                       |

All benchmarks:
===============

| Benchmark                     | results/bm-20260113-3.15.0a4-43cd277/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json | results/bm-20260113-3.15.0a4-43cd277-JIT/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json |
|-------------------------------|:--------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| richards                      | 32.4 ms                                                                                                        | 16.0 ms: 2.03x faster                                                                                              |
| richards_super                | 37.0 ms                                                                                                        | 19.5 ms: 1.90x faster                                                                                              |
| mako                          | 9.06 ms                                                                                                        | 6.56 ms: 1.38x faster                                                                                              |
| nbody                         | 65.8 ms                                                                                                        | 49.0 ms: 1.34x faster                                                                                              |
| unpickle_pure_python          | 151 us                                                                                                         | 116 us: 1.30x faster                                                                                               |
| scimark_fft                   | 195 ms                                                                                                         | 153 ms: 1.27x faster                                                                                               |
| logging_silent                | 59.8 ns                                                                                                        | 47.9 ns: 1.25x faster                                                                                              |
| deltablue                     | 2.39 ms                                                                                                        | 1.92 ms: 1.25x faster                                                                                              |
| float                         | 48.0 ms                                                                                                        | 38.7 ms: 1.24x faster                                                                                              |
| ascii85_large                 | 653 ms                                                                                                         | 536 ms: 1.22x faster                                                                                               |
| urlsafe_base64_small          | 372 us                                                                                                         | 306 us: 1.21x faster                                                                                               |
| ascii85_small                 | 12.7 ms                                                                                                        | 10.6 ms: 1.20x faster                                                                                              |
| scimark_monte_carlo           | 37.0 ms                                                                                                        | 31.2 ms: 1.19x faster                                                                                              |
| pyflate                       | 297 ms                                                                                                         | 254 ms: 1.17x faster                                                                                               |
| base64_small                  | 221 us                                                                                                         | 190 us: 1.16x faster                                                                                               |
| noop                          | 19.4 ns                                                                                                        | 16.7 ns: 1.16x faster                                                                                              |
| thread_mandelbrot_naive       | 219 ms                                                                                                         | 190 ms: 1.16x faster                                                                                               |
| spectral_norm                 | 60.5 ms                                                                                                        | 52.4 ms: 1.16x faster                                                                                              |
| fannkuch                      | 229 ms                                                                                                         | 199 ms: 1.16x faster                                                                                               |
| quadtree_nbody                | 593 ms                                                                                                         | 517 ms: 1.15x faster                                                                                               |
| base16_small                  | 307 us                                                                                                         | 269 us: 1.14x faster                                                                                               |
| thread_mandelbrot_optimized   | 219 ms                                                                                                         | 193 ms: 1.14x faster                                                                                               |
| scimark_lu                    | 65.2 ms                                                                                                        | 57.7 ms: 1.13x faster                                                                                              |
| thread_pipeline_naive         | 37.3 ms                                                                                                        | 33.1 ms: 1.13x faster                                                                                              |
| thread_pipeline_optimized     | 29.5 ms                                                                                                        | 26.2 ms: 1.12x faster                                                                                              |
| go                            | 80.6 ms                                                                                                        | 71.7 ms: 1.12x faster                                                                                              |
| regex_compile                 | 90.8 ms                                                                                                        | 81.2 ms: 1.12x faster                                                                                              |
| pickle_pure_python            | 233 us                                                                                                         | 208 us: 1.12x faster                                                                                               |
| base85_small                  | 4.60 ms                                                                                                        | 4.12 ms: 1.12x faster                                                                                              |
| thread_accumulate_optimized   | 45.4 ms                                                                                                        | 40.8 ms: 1.11x faster                                                                                              |
| thread_counter_naive          | 22.8 ms                                                                                                        | 20.6 ms: 1.11x faster                                                                                              |
| thread_memo_naive             | 9.85 ms                                                                                                        | 8.90 ms: 1.11x faster                                                                                              |
| thread_counter_optimized      | 20.9 ms                                                                                                        | 18.9 ms: 1.11x faster                                                                                              |
| thread_memo_optimized         | 19.3 ms                                                                                                        | 17.5 ms: 1.11x faster                                                                                              |
| telco                         | 4.98 ms                                                                                                        | 4.51 ms: 1.10x faster                                                                                              |
| thread_accumulate_naive       | 45.4 ms                                                                                                        | 41.1 ms: 1.10x faster                                                                                              |
| xml_etree_process             | 49.3 ms                                                                                                        | 45.1 ms: 1.09x faster                                                                                              |
| crypto_pyaes                  | 51.0 ms                                                                                                        | 46.8 ms: 1.09x faster                                                                                              |
| json_dumps                    | 6.72 ms                                                                                                        | 6.17 ms: 1.09x faster                                                                                              |
| xml_etree_generate            | 68.8 ms                                                                                                        | 63.2 ms: 1.09x faster                                                                                              |
| decimal_pi                    | 207 ms                                                                                                         | 191 ms: 1.08x faster                                                                                               |
| base85_large                  | 242 ms                                                                                                         | 225 ms: 1.08x faster                                                                                               |
| deepcopy_memo                 | 16.7 us                                                                                                        | 15.5 us: 1.08x faster                                                                                              |
| tomli_loads                   | 1.53 sec                                                                                                       | 1.43 sec: 1.08x faster                                                                                             |
| bpe_tokeniser                 | 3.06 sec                                                                                                       | 2.88 sec: 1.06x faster                                                                                             |
| scimark_sor                   | 70.6 ms                                                                                                        | 66.8 ms: 1.06x faster                                                                                              |
| async_tree_none               | 217 ms                                                                                                         | 206 ms: 1.05x faster                                                                                               |
| async_tree_memoization        | 265 ms                                                                                                         | 254 ms: 1.04x faster                                                                                               |
| async_tree_eager_tg           | 178 ms                                                                                                         | 170 ms: 1.04x faster                                                                                               |
| json                          | 3.40 ms                                                                                                        | 3.27 ms: 1.04x faster                                                                                              |
| fastapi_http                  | 208 ms                                                                                                         | 200 ms: 1.04x faster                                                                                               |
| async_tree_memoization_tg     | 262 ms                                                                                                         | 253 ms: 1.04x faster                                                                                               |
| sqlglot_v2_parse              | 913 us                                                                                                         | 881 us: 1.04x faster                                                                                               |
| meteor_contest                | 84.1 ms                                                                                                        | 81.4 ms: 1.03x faster                                                                                              |
| async_tree_io_tg              | 485 ms                                                                                                         | 471 ms: 1.03x faster                                                                                               |
| async_tree_cpu_io_mixed       | 439 ms                                                                                                         | 427 ms: 1.03x faster                                                                                               |
| thrift                        | 1.86 ms                                                                                                        | 1.81 ms: 1.03x faster                                                                                              |
| base32_small                  | 5.67 ms                                                                                                        | 5.53 ms: 1.03x faster                                                                                              |
| networkx_connected_components | 442 ms                                                                                                         | 432 ms: 1.02x faster                                                                                               |
| asyncio_tcp                   | 279 ms                                                                                                         | 273 ms: 1.02x faster                                                                                               |
| xml_etree_iterparse           | 69.5 ms                                                                                                        | 68.0 ms: 1.02x faster                                                                                              |
| pickle_list                   | 3.33 us                                                                                                        | 3.26 us: 1.02x faster                                                                                              |
| pickle                        | 9.36 us                                                                                                        | 9.19 us: 1.02x faster                                                                                              |
| networkx_k_core               | 1.94 sec                                                                                                       | 1.91 sec: 1.02x faster                                                                                             |
| scimark_sparse_mat_mult       | 2.55 ms                                                                                                        | 2.51 ms: 1.02x faster                                                                                              |
| logging_simple                | 4.57 us                                                                                                        | 4.50 us: 1.02x faster                                                                                              |
| coroutines                    | 15.4 ms                                                                                                        | 15.2 ms: 1.01x faster                                                                                              |
| networkx_shortest_path        | 445 ms                                                                                                         | 441 ms: 1.01x faster                                                                                               |
| pathlib                       | 10.7 ms                                                                                                        | 10.6 ms: 1.01x faster                                                                                              |
| argparse_many_optionals       | 7.44 ms                                                                                                        | 7.37 ms: 1.01x faster                                                                                              |
| html5lib                      | 43.4 ms                                                                                                        | 43.2 ms: 1.01x faster                                                                                              |
| decimal_factorial             | 171 ms                                                                                                         | 171 ms: 1.01x faster                                                                                               |
| pidigits                      | 182 ms                                                                                                         | 181 ms: 1.00x faster                                                                                               |
| regex_dna                     | 140 ms                                                                                                         | 139 ms: 1.00x faster                                                                                               |
| logging_format                | 5.20 us                                                                                                        | 5.17 us: 1.00x faster                                                                                              |
| base64_large                  | 5.87 ms                                                                                                        | 5.86 ms: 1.00x faster                                                                                              |
| thread_montecarlo_optimized   | 13.3 ms                                                                                                        | 13.3 ms: 1.00x slower                                                                                              |
| pickle_dict                   | 21.3 us                                                                                                        | 21.4 us: 1.00x slower                                                                                              |
| asyncio_tcp_ssl               | 1.27 sec                                                                                                       | 1.27 sec: 1.00x slower                                                                                             |
| pycparser                     | 824 ms                                                                                                         | 828 ms: 1.00x slower                                                                                               |
| chameleon                     | 10.6 ms                                                                                                        | 10.6 ms: 1.01x slower                                                                                              |
| base32_large                  | 279 ms                                                                                                         | 281 ms: 1.01x slower                                                                                               |
| unpickle_list                 | 3.51 us                                                                                                        | 3.55 us: 1.01x slower                                                                                              |
| python_startup_no_site        | 6.09 ms                                                                                                        | 6.15 ms: 1.01x slower                                                                                              |
| argparse_subparsers           | 472 us                                                                                                         | 477 us: 1.01x slower                                                                                               |
| python_startup                | 9.27 ms                                                                                                        | 9.36 ms: 1.01x slower                                                                                              |
| async_tree_eager              | 77.5 ms                                                                                                        | 78.3 ms: 1.01x slower                                                                                              |
| chaos                         | 39.7 ms                                                                                                        | 40.3 ms: 1.01x slower                                                                                              |
| json_loads                    | 17.3 us                                                                                                        | 17.6 us: 1.01x slower                                                                                              |
| tornado_http                  | 97.8 ms                                                                                                        | 99.3 ms: 1.02x slower                                                                                              |
| async_tree_eager_memoization  | 166 ms                                                                                                         | 170 ms: 1.02x slower                                                                                               |
| typing_runtime_protocols      | 105 us                                                                                                         | 108 us: 1.03x slower                                                                                               |
| sqlglot_v2_transpile          | 1.14 ms                                                                                                        | 1.17 ms: 1.03x slower                                                                                              |
| async_tree_eager_cpu_io_mixed | 353 ms                                                                                                         | 363 ms: 1.03x slower                                                                                               |
| generators                    | 20.4 ms                                                                                                        | 21.0 ms: 1.03x slower                                                                                              |
| xdsl_constant_fold            | 34.5 ms                                                                                                        | 35.8 ms: 1.04x slower                                                                                              |
| pprint_safe_repr              | 493 ms                                                                                                         | 513 ms: 1.04x slower                                                                                               |
| pprint_pformat                | 1.03 sec                                                                                                       | 1.07 sec: 1.04x slower                                                                                             |
| sympy_expand                  | 335 ms                                                                                                         | 350 ms: 1.04x slower                                                                                               |
| genshi_text                   | 16.2 ms                                                                                                        | 16.9 ms: 1.05x slower                                                                                              |
| sqlalchemy_imperative         | 14.1 ms                                                                                                        | 14.8 ms: 1.05x slower                                                                                              |
| docutils                      | 2.01 sec                                                                                                       | 2.10 sec: 1.05x slower                                                                                             |
| deepcopy_reduce               | 2.00 us                                                                                                        | 2.11 us: 1.05x slower                                                                                              |
| comprehensions                | 10.8 us                                                                                                        | 11.4 us: 1.05x slower                                                                                              |
| thread_montecarlo_naive       | 15.4 ms                                                                                                        | 16.4 ms: 1.06x slower                                                                                              |
| nqueens                       | 55.0 ms                                                                                                        | 58.6 ms: 1.07x slower                                                                                              |
| async_generators              | 240 ms                                                                                                         | 258 ms: 1.07x slower                                                                                               |
| sympy_integrate               | 14.7 ms                                                                                                        | 16.2 ms: 1.10x slower                                                                                              |
| hexiom                        | 3.92 ms                                                                                                        | 4.34 ms: 1.11x slower                                                                                              |
| sympy_sum                     | 105 ms                                                                                                         | 117 ms: 1.11x slower                                                                                               |
| deepcopy                      | 186 us                                                                                                         | 208 us: 1.12x slower                                                                                               |
| genshi_xml                    | 39.5 ms                                                                                                        | 44.8 ms: 1.13x slower                                                                                              |
| sympy_str                     | 194 ms                                                                                                         | 222 ms: 1.15x slower                                                                                               |
| mypy2                         | 740 ms                                                                                                         | 866 ms: 1.17x slower                                                                                               |
| sqlglot_v2_normalize          | 78.7 ms                                                                                                        | 94.5 ms: 1.20x slower                                                                                              |
| mdp                           | 914 ms                                                                                                         | 1.10 sec: 1.21x slower                                                                                             |
| sqlglot_v2_optimize           | 38.8 ms                                                                                                        | 47.4 ms: 1.22x slower                                                                                              |
| pylint                        | 209 ms                                                                                                         | 261 ms: 1.25x slower                                                                                               |
| unpack_sequence               | 26.4 ns                                                                                                        | 63.5 ns: 2.41x slower                                                                                              |
| Geometric mean                | (ref)                                                                                                          | 1.04x faster                                                                                                       |

Benchmark hidden because not significant (18): async_tree_io, async_tree_eager_cpu_io_mixed_tg, coverage, async_tree_eager_io, django_template, create_gc_cycles, gc_traversal, raytrace, unpickle, regex_effbot, base16_large, xml_etree_parse, async_tree_eager_io_tg, regex_v8, async_tree_cpu_io_mixed_tg, asyncio_websockets, async_tree_eager_memoization_tg, async_tree_none_tg

- Geometric mean (including insignificant results): 1.036x faster

# HPT report

- Reliability score: 99.89% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.01x