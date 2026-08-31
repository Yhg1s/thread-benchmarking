# Results vs. 3.14.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.006x slower
- HPT reliability: 95.41%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                                                                 | 10.1 ms: 1.06x slower                                                                                       |
| docutils       | 1.95 sec                                                                                                | 2.05 sec: 1.05x slower                                                                                      |
| fastapi_http   | 216 ms                                                                                                  | 212 ms: 1.02x faster                                                                                        |
| html5lib       | 46.9 ms                                                                                                 | 48.5 ms: 1.03x slower                                                                                       |
| tornado_http   | 101 ms                                                                                                  | 102 ms: 1.01x slower                                                                                        |
| Geometric mean | (ref)                                                                                                   | 1.03x slower                                                                                                |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|---------------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| asyncio_tcp                     | 325 ms                                                                                                  | 292 ms: 1.11x faster                                                                                        |
| async_tree_eager_io             | 552 ms                                                                                                  | 531 ms: 1.04x faster                                                                                        |
| async_tree_eager_tg             | 182 ms                                                                                                  | 176 ms: 1.04x faster                                                                                        |
| async_tree_cpu_io_mixed_tg      | 410 ms                                                                                                  | 399 ms: 1.03x faster                                                                                        |
| async_tree_io                   | 531 ms                                                                                                  | 520 ms: 1.02x faster                                                                                        |
| async_tree_io_tg                | 539 ms                                                                                                  | 528 ms: 1.02x faster                                                                                        |
| async_tree_eager_io_tg          | 550 ms                                                                                                  | 540 ms: 1.02x faster                                                                                        |
| async_tree_memoization_tg       | 277 ms                                                                                                  | 273 ms: 1.02x faster                                                                                        |
| async_tree_cpu_io_mixed         | 407 ms                                                                                                  | 401 ms: 1.01x faster                                                                                        |
| async_tree_none                 | 228 ms                                                                                                  | 225 ms: 1.01x faster                                                                                        |
| async_tree_memoization          | 281 ms                                                                                                  | 277 ms: 1.01x faster                                                                                        |
| async_tree_eager_cpu_io_mixed   | 314 ms                                                                                                  | 311 ms: 1.01x faster                                                                                        |
| asyncio_tcp_ssl                 | 1.28 sec                                                                                                | 1.29 sec: 1.00x slower                                                                                      |
| asyncio_websockets              | 296 ms                                                                                                  | 300 ms: 1.01x slower                                                                                        |
| async_tree_eager_memoization    | 180 ms                                                                                                  | 183 ms: 1.02x slower                                                                                        |
| async_tree_eager_memoization_tg | 236 ms                                                                                                  | 241 ms: 1.02x slower                                                                                        |
| coroutines                      | 15.1 ms                                                                                                 | 15.6 ms: 1.03x slower                                                                                       |
| async_tree_eager                | 81.3 ms                                                                                                 | 86.6 ms: 1.06x slower                                                                                       |
| async_generators                | 228 ms                                                                                                  | 245 ms: 1.07x slower                                                                                        |
| Geometric mean                  | (ref)                                                                                                   | 1.01x faster                                                                                                |

Benchmark hidden because not significant (2): async_tree_eager_cpu_io_mixed_tg, async_tree_none_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| noop      | 19.4 ns                                                                                                 | 16.8 ns: 1.15x faster                                                                                       |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| decimal_pi        | 208 ms                                                                                                  | 198 ms: 1.05x faster                                                                                        |
| decimal_factorial | 173 ms                                                                                                  | 173 ms: 1.00x slower                                                                                        |
| Geometric mean    | (ref)                                                                                                   | 1.02x faster                                                                                                |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| float          | 47.3 ms                                                                                                 | 39.8 ms: 1.19x faster                                                                                       |
| quadtree_nbody | 596 ms                                                                                                  | 585 ms: 1.02x faster                                                                                        |
| nbody          | 67.9 ms                                                                                                 | 80.8 ms: 1.19x slower                                                                                       |
| Geometric mean | (ref)                                                                                                   | 1.00x faster                                                                                                |

Benchmark hidden because not significant (1): pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| regex_dna      | 150 ms                                                                                                  | 150 ms: 1.00x faster                                                                                        |
| regex_compile  | 93.9 ms                                                                                                 | 95.2 ms: 1.01x slower                                                                                       |
| regex_effbot   | 1.95 ms                                                                                                 | 1.98 ms: 1.02x slower                                                                                       |
| regex_v8       | 14.8 ms                                                                                                 | 15.6 ms: 1.05x slower                                                                                       |
| Geometric mean | (ref)                                                                                                   | 1.02x slower                                                                                                |

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| unpickle_pure_python | 152 us                                                                                                  | 130 us: 1.17x faster                                                                                        |
| ascii85_large        | 667 ms                                                                                                  | 600 ms: 1.11x faster                                                                                        |
| xml_etree_generate   | 62.6 ms                                                                                                 | 57.4 ms: 1.09x faster                                                                                       |
| ascii85_small        | 12.7 ms                                                                                                 | 11.8 ms: 1.07x faster                                                                                       |
| xml_etree_process    | 44.7 ms                                                                                                 | 41.9 ms: 1.07x faster                                                                                       |
| base85_small         | 4.69 ms                                                                                                 | 4.43 ms: 1.06x faster                                                                                       |
| tomli_loads          | 1.44 sec                                                                                                | 1.38 sec: 1.05x faster                                                                                      |
| base85_large         | 248 ms                                                                                                  | 237 ms: 1.04x faster                                                                                        |
| unpickle_list        | 3.43 us                                                                                                 | 3.35 us: 1.02x faster                                                                                       |
| base32_large         | 292 ms                                                                                                  | 288 ms: 1.02x faster                                                                                        |
| xml_etree_iterparse  | 76.2 ms                                                                                                 | 75.4 ms: 1.01x faster                                                                                       |
| xml_etree_parse      | 94.3 ms                                                                                                 | 94.0 ms: 1.00x faster                                                                                       |
| json_loads           | 17.5 us                                                                                                 | 17.4 us: 1.00x faster                                                                                       |
| pickle_dict          | 21.5 us                                                                                                 | 21.5 us: 1.00x faster                                                                                       |
| urlsafe_base64_small | 329 us                                                                                                  | 332 us: 1.01x slower                                                                                        |
| pickle_list          | 3.24 us                                                                                                 | 3.27 us: 1.01x slower                                                                                       |
| base16_small         | 305 us                                                                                                  | 312 us: 1.02x slower                                                                                        |
| pickle_pure_python   | 240 us                                                                                                  | 246 us: 1.03x slower                                                                                        |
| pickle               | 8.20 us                                                                                                 | 8.42 us: 1.03x slower                                                                                       |
| unpickle             | 10.2 us                                                                                                 | 10.5 us: 1.03x slower                                                                                       |
| Geometric mean       | (ref)                                                                                                   | 1.02x faster                                                                                                |

Benchmark hidden because not significant (5): base64_small, base32_small, base64_large, base16_large, json_dumps

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| python_startup_no_site | 6.38 ms                                                                                                 | 6.39 ms: 1.00x slower                                                                                       |
| python_startup         | 9.73 ms                                                                                                 | 9.78 ms: 1.00x slower                                                                                       |
| Geometric mean         | (ref)                                                                                                   | 1.00x slower                                                                                                |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| mako            | 7.40 ms                                                                                                 | 6.41 ms: 1.15x faster                                                                                       |
| genshi_text     | 16.8 ms                                                                                                 | 16.3 ms: 1.03x faster                                                                                       |
| genshi_xml      | 39.5 ms                                                                                                 | 40.3 ms: 1.02x slower                                                                                       |
| django_template | 27.8 ms                                                                                                 | 28.5 ms: 1.02x slower                                                                                       |
| Geometric mean  | (ref)                                                                                                   | 1.03x faster                                                                                                |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 233 ms                                                                                                  | 216 ms: 1.08x faster                                                                                        |
| thread_accumulate_optimized | 35.1 ms                                                                                                 | 32.6 ms: 1.08x faster                                                                                       |
| thread_pipeline_optimized   | 22.5 ms                                                                                                 | 21.0 ms: 1.07x faster                                                                                       |
| thread_accumulate_naive     | 35.8 ms                                                                                                 | 33.4 ms: 1.07x faster                                                                                       |
| thread_mandelbrot_optimized | 233 ms                                                                                                  | 219 ms: 1.07x faster                                                                                        |
| thread_memo_optimized       | 15.9 ms                                                                                                 | 15.0 ms: 1.06x faster                                                                                       |
| thread_memo_naive           | 11.5 ms                                                                                                 | 10.8 ms: 1.06x faster                                                                                       |
| thread_counter_optimized    | 17.1 ms                                                                                                 | 16.2 ms: 1.05x faster                                                                                       |
| thread_pipeline_naive       | 32.0 ms                                                                                                 | 30.9 ms: 1.04x faster                                                                                       |
| thread_counter_naive        | 20.2 ms                                                                                                 | 19.5 ms: 1.04x faster                                                                                       |
| thread_montecarlo_optimized | 13.9 ms                                                                                                 | 14.4 ms: 1.03x slower                                                                                       |
| thread_montecarlo_naive     | 15.8 ms                                                                                                 | 18.9 ms: 1.20x slower                                                                                       |
| Geometric mean              | (ref)                                                                                                   | 1.03x faster                                                                                                |

All benchmarks:
===============

| Benchmark                       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|---------------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| scimark_fft                     | 226 ms                                                                                                  | 185 ms: 1.22x faster                                                                                        |
| richards                        | 32.6 ms                                                                                                 | 27.1 ms: 1.20x faster                                                                                       |
| float                           | 47.3 ms                                                                                                 | 39.8 ms: 1.19x faster                                                                                       |
| unpickle_pure_python            | 152 us                                                                                                  | 130 us: 1.17x faster                                                                                        |
| richards_super                  | 37.4 ms                                                                                                 | 31.9 ms: 1.17x faster                                                                                       |
| mako                            | 7.40 ms                                                                                                 | 6.41 ms: 1.15x faster                                                                                       |
| noop                            | 19.4 ns                                                                                                 | 16.8 ns: 1.15x faster                                                                                       |
| spectral_norm                   | 65.6 ms                                                                                                 | 57.2 ms: 1.15x faster                                                                                       |
| deltablue                       | 2.34 ms                                                                                                 | 2.05 ms: 1.14x faster                                                                                       |
| asyncio_tcp                     | 325 ms                                                                                                  | 292 ms: 1.11x faster                                                                                        |
| ascii85_large                   | 667 ms                                                                                                  | 600 ms: 1.11x faster                                                                                        |
| xml_etree_generate              | 62.6 ms                                                                                                 | 57.4 ms: 1.09x faster                                                                                       |
| thread_mandelbrot_naive         | 233 ms                                                                                                  | 216 ms: 1.08x faster                                                                                        |
| scimark_sparse_mat_mult         | 3.18 ms                                                                                                 | 2.94 ms: 1.08x faster                                                                                       |
| thread_accumulate_optimized     | 35.1 ms                                                                                                 | 32.6 ms: 1.08x faster                                                                                       |
| ascii85_small                   | 12.7 ms                                                                                                 | 11.8 ms: 1.07x faster                                                                                       |
| thread_pipeline_optimized       | 22.5 ms                                                                                                 | 21.0 ms: 1.07x faster                                                                                       |
| thread_accumulate_naive         | 35.8 ms                                                                                                 | 33.4 ms: 1.07x faster                                                                                       |
| xml_etree_process               | 44.7 ms                                                                                                 | 41.9 ms: 1.07x faster                                                                                       |
| thread_mandelbrot_optimized     | 233 ms                                                                                                  | 219 ms: 1.07x faster                                                                                        |
| thread_memo_optimized           | 15.9 ms                                                                                                 | 15.0 ms: 1.06x faster                                                                                       |
| thread_memo_naive               | 11.5 ms                                                                                                 | 10.8 ms: 1.06x faster                                                                                       |
| base85_small                    | 4.69 ms                                                                                                 | 4.43 ms: 1.06x faster                                                                                       |
| thread_counter_optimized        | 17.1 ms                                                                                                 | 16.2 ms: 1.05x faster                                                                                       |
| decimal_pi                      | 208 ms                                                                                                  | 198 ms: 1.05x faster                                                                                        |
| tomli_loads                     | 1.44 sec                                                                                                | 1.38 sec: 1.05x faster                                                                                      |
| bpe_tokeniser                   | 3.00 sec                                                                                                | 2.87 sec: 1.05x faster                                                                                      |
| base85_large                    | 248 ms                                                                                                  | 237 ms: 1.04x faster                                                                                        |
| fannkuch                        | 245 ms                                                                                                  | 236 ms: 1.04x faster                                                                                        |
| async_tree_eager_io             | 552 ms                                                                                                  | 531 ms: 1.04x faster                                                                                        |
| async_tree_eager_tg             | 182 ms                                                                                                  | 176 ms: 1.04x faster                                                                                        |
| thread_pipeline_naive           | 32.0 ms                                                                                                 | 30.9 ms: 1.04x faster                                                                                       |
| thread_counter_naive            | 20.2 ms                                                                                                 | 19.5 ms: 1.04x faster                                                                                       |
| async_tree_cpu_io_mixed_tg      | 410 ms                                                                                                  | 399 ms: 1.03x faster                                                                                        |
| networkx_connected_components   | 438 ms                                                                                                  | 425 ms: 1.03x faster                                                                                        |
| genshi_text                     | 16.8 ms                                                                                                 | 16.3 ms: 1.03x faster                                                                                       |
| meteor_contest                  | 84.1 ms                                                                                                 | 82.2 ms: 1.02x faster                                                                                       |
| unpickle_list                   | 3.43 us                                                                                                 | 3.35 us: 1.02x faster                                                                                       |
| async_tree_io                   | 531 ms                                                                                                  | 520 ms: 1.02x faster                                                                                        |
| async_tree_io_tg                | 539 ms                                                                                                  | 528 ms: 1.02x faster                                                                                        |
| async_tree_eager_io_tg          | 550 ms                                                                                                  | 540 ms: 1.02x faster                                                                                        |
| quadtree_nbody                  | 596 ms                                                                                                  | 585 ms: 1.02x faster                                                                                        |
| networkx_shortest_path          | 444 ms                                                                                                  | 436 ms: 1.02x faster                                                                                        |
| networkx_k_core                 | 2.07 sec                                                                                                | 2.03 sec: 1.02x faster                                                                                      |
| fastapi_http                    | 216 ms                                                                                                  | 212 ms: 1.02x faster                                                                                        |
| async_tree_memoization_tg       | 277 ms                                                                                                  | 273 ms: 1.02x faster                                                                                        |
| base32_large                    | 292 ms                                                                                                  | 288 ms: 1.02x faster                                                                                        |
| async_tree_cpu_io_mixed         | 407 ms                                                                                                  | 401 ms: 1.01x faster                                                                                        |
| async_tree_none                 | 228 ms                                                                                                  | 225 ms: 1.01x faster                                                                                        |
| async_tree_memoization          | 281 ms                                                                                                  | 277 ms: 1.01x faster                                                                                        |
| pyflate                         | 299 ms                                                                                                  | 296 ms: 1.01x faster                                                                                        |
| xml_etree_iterparse             | 76.2 ms                                                                                                 | 75.4 ms: 1.01x faster                                                                                       |
| argparse_many_optionals         | 34.4 ms                                                                                                 | 34.1 ms: 1.01x faster                                                                                       |
| nqueens                         | 56.8 ms                                                                                                 | 56.3 ms: 1.01x faster                                                                                       |
| async_tree_eager_cpu_io_mixed   | 314 ms                                                                                                  | 311 ms: 1.01x faster                                                                                        |
| gc_traversal                    | 3.26 ms                                                                                                 | 3.24 ms: 1.01x faster                                                                                       |
| regex_dna                       | 150 ms                                                                                                  | 150 ms: 1.00x faster                                                                                        |
| xml_etree_parse                 | 94.3 ms                                                                                                 | 94.0 ms: 1.00x faster                                                                                       |
| deepcopy_memo                   | 18.0 us                                                                                                 | 17.9 us: 1.00x faster                                                                                       |
| json_loads                      | 17.5 us                                                                                                 | 17.4 us: 1.00x faster                                                                                       |
| pickle_dict                     | 21.5 us                                                                                                 | 21.5 us: 1.00x faster                                                                                       |
| decimal_factorial               | 173 ms                                                                                                  | 173 ms: 1.00x slower                                                                                        |
| python_startup_no_site          | 6.38 ms                                                                                                 | 6.39 ms: 1.00x slower                                                                                       |
| asyncio_tcp_ssl                 | 1.28 sec                                                                                                | 1.29 sec: 1.00x slower                                                                                      |
| python_startup                  | 9.73 ms                                                                                                 | 9.78 ms: 1.00x slower                                                                                       |
| deepcopy_reduce                 | 2.00 us                                                                                                 | 2.01 us: 1.01x slower                                                                                       |
| tornado_http                    | 101 ms                                                                                                  | 102 ms: 1.01x slower                                                                                        |
| urlsafe_base64_small            | 329 us                                                                                                  | 332 us: 1.01x slower                                                                                        |
| pickle_list                     | 3.24 us                                                                                                 | 3.27 us: 1.01x slower                                                                                       |
| logging_silent                  | 65.3 ns                                                                                                 | 66.0 ns: 1.01x slower                                                                                       |
| regex_compile                   | 93.9 ms                                                                                                 | 95.2 ms: 1.01x slower                                                                                       |
| asyncio_websockets              | 296 ms                                                                                                  | 300 ms: 1.01x slower                                                                                        |
| pycparser                       | 851 ms                                                                                                  | 865 ms: 1.02x slower                                                                                        |
| async_tree_eager_memoization    | 180 ms                                                                                                  | 183 ms: 1.02x slower                                                                                        |
| telco                           | 5.59 ms                                                                                                 | 5.69 ms: 1.02x slower                                                                                       |
| scimark_lu                      | 73.8 ms                                                                                                 | 75.2 ms: 1.02x slower                                                                                       |
| coverage                        | 57.4 ms                                                                                                 | 58.5 ms: 1.02x slower                                                                                       |
| regex_effbot                    | 1.95 ms                                                                                                 | 1.98 ms: 1.02x slower                                                                                       |
| sympy_integrate                 | 15.4 ms                                                                                                 | 15.7 ms: 1.02x slower                                                                                       |
| deepcopy                        | 193 us                                                                                                  | 196 us: 1.02x slower                                                                                        |
| genshi_xml                      | 39.5 ms                                                                                                 | 40.3 ms: 1.02x slower                                                                                       |
| sympy_sum                       | 106 ms                                                                                                  | 108 ms: 1.02x slower                                                                                        |
| async_tree_eager_memoization_tg | 236 ms                                                                                                  | 241 ms: 1.02x slower                                                                                        |
| base16_small                    | 305 us                                                                                                  | 312 us: 1.02x slower                                                                                        |
| pathlib                         | 13.0 ms                                                                                                 | 13.3 ms: 1.02x slower                                                                                       |
| django_template                 | 27.8 ms                                                                                                 | 28.5 ms: 1.02x slower                                                                                       |
| sympy_str                       | 194 ms                                                                                                  | 199 ms: 1.02x slower                                                                                        |
| chaos                           | 43.8 ms                                                                                                 | 44.9 ms: 1.03x slower                                                                                       |
| pickle_pure_python              | 240 us                                                                                                  | 246 us: 1.03x slower                                                                                        |
| argparse_subparsers             | 686 us                                                                                                  | 705 us: 1.03x slower                                                                                        |
| sympy_expand                    | 332 ms                                                                                                  | 341 ms: 1.03x slower                                                                                        |
| pickle                          | 8.20 us                                                                                                 | 8.42 us: 1.03x slower                                                                                       |
| scimark_monte_carlo             | 40.7 ms                                                                                                 | 41.8 ms: 1.03x slower                                                                                       |
| unpickle                        | 10.2 us                                                                                                 | 10.5 us: 1.03x slower                                                                                       |
| typing_runtime_protocols        | 112 us                                                                                                  | 115 us: 1.03x slower                                                                                        |
| coroutines                      | 15.1 ms                                                                                                 | 15.6 ms: 1.03x slower                                                                                       |
| raytrace                        | 194 ms                                                                                                  | 200 ms: 1.03x slower                                                                                        |
| crypto_pyaes                    | 54.5 ms                                                                                                 | 56.3 ms: 1.03x slower                                                                                       |
| thread_montecarlo_optimized     | 13.9 ms                                                                                                 | 14.4 ms: 1.03x slower                                                                                       |
| html5lib                        | 46.9 ms                                                                                                 | 48.5 ms: 1.03x slower                                                                                       |
| sqlglot_v2_normalize            | 78.2 ms                                                                                                 | 81.1 ms: 1.04x slower                                                                                       |
| sqlglot_v2_optimize             | 39.0 ms                                                                                                 | 40.7 ms: 1.04x slower                                                                                       |
| sqlalchemy_imperative           | 14.2 ms                                                                                                 | 14.9 ms: 1.05x slower                                                                                       |
| regex_v8                        | 14.8 ms                                                                                                 | 15.6 ms: 1.05x slower                                                                                       |
| docutils                        | 1.95 sec                                                                                                | 2.05 sec: 1.05x slower                                                                                      |
| sqlglot_v2_parse                | 911 us                                                                                                  | 959 us: 1.05x slower                                                                                        |
| xdsl_constant_fold              | 34.7 ms                                                                                                 | 36.7 ms: 1.06x slower                                                                                       |
| pylint                          | 216 ms                                                                                                  | 228 ms: 1.06x slower                                                                                        |
| chameleon                       | 9.52 ms                                                                                                 | 10.1 ms: 1.06x slower                                                                                       |
| async_tree_eager                | 81.3 ms                                                                                                 | 86.6 ms: 1.06x slower                                                                                       |
| thrift                          | 1.86 ms                                                                                                 | 1.99 ms: 1.07x slower                                                                                       |
| comprehensions                  | 10.8 us                                                                                                 | 11.5 us: 1.07x slower                                                                                       |
| sqlglot_v2_transpile            | 1.15 ms                                                                                                 | 1.23 ms: 1.07x slower                                                                                       |
| async_generators                | 228 ms                                                                                                  | 245 ms: 1.07x slower                                                                                        |
| hexiom                          | 4.11 ms                                                                                                 | 4.52 ms: 1.10x slower                                                                                       |
| go                              | 84.7 ms                                                                                                 | 98.4 ms: 1.16x slower                                                                                       |
| nbody                           | 67.9 ms                                                                                                 | 80.8 ms: 1.19x slower                                                                                       |
| thread_montecarlo_naive         | 15.8 ms                                                                                                 | 18.9 ms: 1.20x slower                                                                                       |
| pprint_pformat                  | 989 ms                                                                                                  | 1.33 sec: 1.35x slower                                                                                      |
| pprint_safe_repr                | 474 ms                                                                                                  | 667 ms: 1.41x slower                                                                                        |
| unpack_sequence                 | 25.8 ns                                                                                                 | 103 ns: 3.98x slower                                                                                        |
| Geometric mean                  | (ref)                                                                                                   | 1.01x slower                                                                                                |

Benchmark hidden because not significant (16): async_tree_eager_cpu_io_mixed_tg, base64_small, async_tree_none_tg, mdp, create_gc_cycles, logging_format, base32_small, base64_large, pidigits, logging_simple, base16_large, json_dumps, json, scimark_sor, mypy2, generators

- Geometric mean (including insignificant results): 1.006x slower

# HPT report

- Reliability score: 95.41% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.01x