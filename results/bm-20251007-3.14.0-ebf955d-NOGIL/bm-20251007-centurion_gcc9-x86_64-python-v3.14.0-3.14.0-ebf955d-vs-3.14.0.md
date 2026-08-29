# Results vs. 3.14.0

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.008x faster
- HPT reliability: 99.88%
- HPT 99th percentile: 1.01x slower
- Memory change: 1.46x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                                                                 | 10.9 ms: 1.14x slower                                                                                         |
| docutils       | 1.95 sec                                                                                                | 2.06 sec: 1.06x slower                                                                                        |
| fastapi_http   | 216 ms                                                                                                  | 191 ms: 1.13x faster                                                                                          |
| html5lib       | 46.9 ms                                                                                                 | 49.3 ms: 1.05x slower                                                                                         |
| tornado_http   | 101 ms                                                                                                  | 94.8 ms: 1.07x faster                                                                                         |
| Geometric mean | (ref)                                                                                                   | 1.01x slower                                                                                                  |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 550 ms                                                                                                  | 404 ms: 1.36x faster                                                                                          |
| async_tree_io_tg                 | 539 ms                                                                                                  | 413 ms: 1.31x faster                                                                                          |
| async_tree_eager_io              | 552 ms                                                                                                  | 434 ms: 1.27x faster                                                                                          |
| async_tree_none_tg               | 223 ms                                                                                                  | 181 ms: 1.23x faster                                                                                          |
| async_tree_io                    | 531 ms                                                                                                  | 446 ms: 1.19x faster                                                                                          |
| async_tree_memoization_tg        | 277 ms                                                                                                  | 237 ms: 1.17x faster                                                                                          |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                                                                  | 359 ms: 1.14x faster                                                                                          |
| async_tree_eager_tg              | 182 ms                                                                                                  | 160 ms: 1.14x faster                                                                                          |
| async_tree_eager_memoization_tg  | 236 ms                                                                                                  | 214 ms: 1.10x faster                                                                                          |
| async_tree_none                  | 228 ms                                                                                                  | 213 ms: 1.07x faster                                                                                          |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                                                                  | 340 ms: 1.07x faster                                                                                          |
| async_tree_memoization           | 281 ms                                                                                                  | 265 ms: 1.06x faster                                                                                          |
| async_tree_cpu_io_mixed          | 407 ms                                                                                                  | 392 ms: 1.04x faster                                                                                          |
| asyncio_tcp                      | 325 ms                                                                                                  | 314 ms: 1.03x faster                                                                                          |
| asyncio_websockets               | 296 ms                                                                                                  | 289 ms: 1.03x faster                                                                                          |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                                                                  | 316 ms: 1.01x slower                                                                                          |
| coroutines                       | 15.1 ms                                                                                                 | 15.6 ms: 1.03x slower                                                                                         |
| asyncio_tcp_ssl                  | 1.28 sec                                                                                                | 1.39 sec: 1.08x slower                                                                                        |
| async_generators                 | 228 ms                                                                                                  | 266 ms: 1.17x slower                                                                                          |
| async_tree_eager                 | 81.3 ms                                                                                                 | 98.7 ms: 1.21x slower                                                                                         |
| Geometric mean                   | (ref)                                                                                                   | 1.08x faster                                                                                                  |

Benchmark hidden because not significant (1): async_tree_eager_memoization

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| noop      | 19.4 ns                                                                                                 | 21.9 ns: 1.13x slower                                                                                         |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                                                                  | 189 ms: 1.09x slower                                                                                          |
| decimal_pi        | 208 ms                                                                                                  | 246 ms: 1.18x slower                                                                                          |
| Geometric mean    | (ref)                                                                                                   | 1.14x slower                                                                                                  |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| pidigits       | 189 ms                                                                                                  | 185 ms: 1.02x faster                                                                                          |
| float          | 47.3 ms                                                                                                 | 51.5 ms: 1.09x slower                                                                                         |
| quadtree_nbody | 596 ms                                                                                                  | 662 ms: 1.11x slower                                                                                          |
| nbody          | 67.9 ms                                                                                                 | 83.2 ms: 1.23x slower                                                                                         |
| Geometric mean | (ref)                                                                                                   | 1.10x slower                                                                                                  |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| regex_v8       | 14.8 ms                                                                                                 | 14.2 ms: 1.05x faster                                                                                         |
| regex_effbot   | 1.95 ms                                                                                                 | 1.98 ms: 1.02x slower                                                                                         |
| regex_dna      | 150 ms                                                                                                  | 154 ms: 1.02x slower                                                                                          |
| regex_compile  | 93.9 ms                                                                                                 | 105 ms: 1.12x slower                                                                                          |
| Geometric mean | (ref)                                                                                                   | 1.03x slower                                                                                                  |

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| xml_etree_iterparse  | 76.2 ms                                                                                                 | 65.0 ms: 1.17x faster                                                                                         |
| base64_large         | 3.63 ms                                                                                                 | 3.34 ms: 1.08x faster                                                                                         |
| base16_large         | 5.33 ms                                                                                                 | 4.94 ms: 1.08x faster                                                                                         |
| base64_small         | 186 us                                                                                                  | 176 us: 1.06x faster                                                                                          |
| base16_small         | 305 us                                                                                                  | 291 us: 1.05x faster                                                                                          |
| xml_etree_parse      | 94.3 ms                                                                                                 | 92.5 ms: 1.02x faster                                                                                         |
| pickle_list          | 3.24 us                                                                                                 | 3.21 us: 1.01x faster                                                                                         |
| pickle_dict          | 21.5 us                                                                                                 | 22.0 us: 1.02x slower                                                                                         |
| pickle               | 8.20 us                                                                                                 | 8.41 us: 1.03x slower                                                                                         |
| unpickle_pure_python | 152 us                                                                                                  | 158 us: 1.04x slower                                                                                          |
| base85_small         | 4.69 ms                                                                                                 | 4.90 ms: 1.04x slower                                                                                         |
| xml_etree_generate   | 62.6 ms                                                                                                 | 66.5 ms: 1.06x slower                                                                                         |
| pickle_pure_python   | 240 us                                                                                                  | 256 us: 1.07x slower                                                                                          |
| base85_large         | 248 ms                                                                                                  | 267 ms: 1.08x slower                                                                                          |
| base32_large         | 292 ms                                                                                                  | 323 ms: 1.11x slower                                                                                          |
| xml_etree_process    | 44.7 ms                                                                                                 | 49.5 ms: 1.11x slower                                                                                         |
| ascii85_large        | 667 ms                                                                                                  | 741 ms: 1.11x slower                                                                                          |
| base32_small         | 5.71 ms                                                                                                 | 6.37 ms: 1.12x slower                                                                                         |
| tomli_loads          | 1.44 sec                                                                                                | 1.62 sec: 1.12x slower                                                                                        |
| ascii85_small        | 12.7 ms                                                                                                 | 14.2 ms: 1.12x slower                                                                                         |
| unpickle             | 10.2 us                                                                                                 | 11.6 us: 1.14x slower                                                                                         |
| unpickle_list        | 3.43 us                                                                                                 | 3.94 us: 1.15x slower                                                                                         |
| json_dumps           | 6.95 ms                                                                                                 | 7.98 ms: 1.15x slower                                                                                         |
| json_loads           | 17.5 us                                                                                                 | 20.2 us: 1.16x slower                                                                                         |
| Geometric mean       | (ref)                                                                                                   | 1.04x slower                                                                                                  |

Benchmark hidden because not significant (1): urlsafe_base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|------------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                                                                 | 11.8 ms: 1.21x slower                                                                                         |
| python_startup_no_site | 6.38 ms                                                                                                 | 8.33 ms: 1.31x slower                                                                                         |
| Geometric mean         | (ref)                                                                                                   | 1.26x slower                                                                                                  |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| genshi_xml      | 39.5 ms                                                                                                 | 43.2 ms: 1.09x slower                                                                                         |
| django_template | 27.8 ms                                                                                                 | 30.9 ms: 1.11x slower                                                                                         |
| genshi_text     | 16.8 ms                                                                                                 | 19.8 ms: 1.18x slower                                                                                         |
| mako            | 7.40 ms                                                                                                 | 11.5 ms: 1.56x slower                                                                                         |
| Geometric mean  | (ref)                                                                                                   | 1.22x slower                                                                                                  |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 233 ms                                                                                                  | 63.1 ms: 3.70x faster                                                                                         |
| thread_mandelbrot_optimized | 233 ms                                                                                                  | 63.7 ms: 3.66x faster                                                                                         |
| thread_accumulate_optimized | 35.1 ms                                                                                                 | 9.78 ms: 3.59x faster                                                                                         |
| thread_pipeline_optimized   | 22.5 ms                                                                                                 | 6.27 ms: 3.58x faster                                                                                         |
| thread_counter_optimized    | 17.1 ms                                                                                                 | 4.96 ms: 3.45x faster                                                                                         |
| thread_memo_optimized       | 15.9 ms                                                                                                 | 5.48 ms: 2.91x faster                                                                                         |
| thread_montecarlo_optimized | 13.9 ms                                                                                                 | 4.87 ms: 2.85x faster                                                                                         |
| thread_accumulate_naive     | 35.8 ms                                                                                                 | 12.6 ms: 2.84x faster                                                                                         |
| thread_pipeline_naive       | 32.0 ms                                                                                                 | 27.3 ms: 1.17x faster                                                                                         |
| thread_counter_naive        | 20.2 ms                                                                                                 | 21.2 ms: 1.05x slower                                                                                         |
| thread_montecarlo_naive     | 15.8 ms                                                                                                 | 26.9 ms: 1.70x slower                                                                                         |
| thread_memo_naive           | 11.5 ms                                                                                                 | 24.2 ms: 2.10x slower                                                                                         |
| Geometric mean              | (ref)                                                                                                   | 2.01x faster                                                                                                  |

All benchmarks:
===============

| Benchmark                        | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------------------|:-------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------:|
| thread_mandelbrot_naive          | 233 ms                                                                                                  | 63.1 ms: 3.70x faster                                                                                         |
| thread_mandelbrot_optimized      | 233 ms                                                                                                  | 63.7 ms: 3.66x faster                                                                                         |
| thread_accumulate_optimized      | 35.1 ms                                                                                                 | 9.78 ms: 3.59x faster                                                                                         |
| thread_pipeline_optimized        | 22.5 ms                                                                                                 | 6.27 ms: 3.58x faster                                                                                         |
| thread_counter_optimized         | 17.1 ms                                                                                                 | 4.96 ms: 3.45x faster                                                                                         |
| thread_memo_optimized            | 15.9 ms                                                                                                 | 5.48 ms: 2.91x faster                                                                                         |
| thread_montecarlo_optimized      | 13.9 ms                                                                                                 | 4.87 ms: 2.85x faster                                                                                         |
| thread_accumulate_naive          | 35.8 ms                                                                                                 | 12.6 ms: 2.84x faster                                                                                         |
| gc_traversal                     | 3.26 ms                                                                                                 | 1.69 ms: 1.93x faster                                                                                         |
| create_gc_cycles                 | 1.96 ms                                                                                                 | 1.34 ms: 1.47x faster                                                                                         |
| async_tree_eager_io_tg           | 550 ms                                                                                                  | 404 ms: 1.36x faster                                                                                          |
| async_tree_io_tg                 | 539 ms                                                                                                  | 413 ms: 1.31x faster                                                                                          |
| async_tree_eager_io              | 552 ms                                                                                                  | 434 ms: 1.27x faster                                                                                          |
| async_tree_none_tg               | 223 ms                                                                                                  | 181 ms: 1.23x faster                                                                                          |
| async_tree_io                    | 531 ms                                                                                                  | 446 ms: 1.19x faster                                                                                          |
| xml_etree_iterparse              | 76.2 ms                                                                                                 | 65.0 ms: 1.17x faster                                                                                         |
| thread_pipeline_naive            | 32.0 ms                                                                                                 | 27.3 ms: 1.17x faster                                                                                         |
| async_tree_memoization_tg        | 277 ms                                                                                                  | 237 ms: 1.17x faster                                                                                          |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                                                                  | 359 ms: 1.14x faster                                                                                          |
| async_tree_eager_tg              | 182 ms                                                                                                  | 160 ms: 1.14x faster                                                                                          |
| fastapi_http                     | 216 ms                                                                                                  | 191 ms: 1.13x faster                                                                                          |
| async_tree_eager_memoization_tg  | 236 ms                                                                                                  | 214 ms: 1.10x faster                                                                                          |
| base64_large                     | 3.63 ms                                                                                                 | 3.34 ms: 1.08x faster                                                                                         |
| base16_large                     | 5.33 ms                                                                                                 | 4.94 ms: 1.08x faster                                                                                         |
| tornado_http                     | 101 ms                                                                                                  | 94.8 ms: 1.07x faster                                                                                         |
| async_tree_none                  | 228 ms                                                                                                  | 213 ms: 1.07x faster                                                                                          |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                                                                  | 340 ms: 1.07x faster                                                                                          |
| async_tree_memoization           | 281 ms                                                                                                  | 265 ms: 1.06x faster                                                                                          |
| base64_small                     | 186 us                                                                                                  | 176 us: 1.06x faster                                                                                          |
| base16_small                     | 305 us                                                                                                  | 291 us: 1.05x faster                                                                                          |
| regex_v8                         | 14.8 ms                                                                                                 | 14.2 ms: 1.05x faster                                                                                         |
| async_tree_cpu_io_mixed          | 407 ms                                                                                                  | 392 ms: 1.04x faster                                                                                          |
| asyncio_tcp                      | 325 ms                                                                                                  | 314 ms: 1.03x faster                                                                                          |
| asyncio_websockets               | 296 ms                                                                                                  | 289 ms: 1.03x faster                                                                                          |
| pidigits                         | 189 ms                                                                                                  | 185 ms: 1.02x faster                                                                                          |
| pycparser                        | 851 ms                                                                                                  | 832 ms: 1.02x faster                                                                                          |
| xml_etree_parse                  | 94.3 ms                                                                                                 | 92.5 ms: 1.02x faster                                                                                         |
| pickle_list                      | 3.24 us                                                                                                 | 3.21 us: 1.01x faster                                                                                         |
| pathlib                          | 13.0 ms                                                                                                 | 13.0 ms: 1.00x slower                                                                                         |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                                                                  | 316 ms: 1.01x slower                                                                                          |
| regex_effbot                     | 1.95 ms                                                                                                 | 1.98 ms: 1.02x slower                                                                                         |
| pickle_dict                      | 21.5 us                                                                                                 | 22.0 us: 1.02x slower                                                                                         |
| regex_dna                        | 150 ms                                                                                                  | 154 ms: 1.02x slower                                                                                          |
| pickle                           | 8.20 us                                                                                                 | 8.41 us: 1.03x slower                                                                                         |
| generators                       | 20.3 ms                                                                                                 | 20.9 ms: 1.03x slower                                                                                         |
| coroutines                       | 15.1 ms                                                                                                 | 15.6 ms: 1.03x slower                                                                                         |
| networkx_k_core                  | 2.07 sec                                                                                                | 2.15 sec: 1.04x slower                                                                                        |
| unpickle_pure_python             | 152 us                                                                                                  | 158 us: 1.04x slower                                                                                          |
| mypy2                            | 753 ms                                                                                                  | 783 ms: 1.04x slower                                                                                          |
| base85_small                     | 4.69 ms                                                                                                 | 4.90 ms: 1.04x slower                                                                                         |
| bpe_tokeniser                    | 3.00 sec                                                                                                | 3.14 sec: 1.04x slower                                                                                        |
| thread_counter_naive             | 20.2 ms                                                                                                 | 21.2 ms: 1.05x slower                                                                                         |
| html5lib                         | 46.9 ms                                                                                                 | 49.3 ms: 1.05x slower                                                                                         |
| pylint                           | 216 ms                                                                                                  | 229 ms: 1.06x slower                                                                                          |
| docutils                         | 1.95 sec                                                                                                | 2.06 sec: 1.06x slower                                                                                        |
| xml_etree_generate               | 62.6 ms                                                                                                 | 66.5 ms: 1.06x slower                                                                                         |
| pickle_pure_python               | 240 us                                                                                                  | 256 us: 1.07x slower                                                                                          |
| argparse_many_optionals          | 34.4 ms                                                                                                 | 37.0 ms: 1.07x slower                                                                                         |
| base85_large                     | 248 ms                                                                                                  | 267 ms: 1.08x slower                                                                                          |
| thrift                           | 1.86 ms                                                                                                 | 2.01 ms: 1.08x slower                                                                                         |
| xdsl_constant_fold               | 34.7 ms                                                                                                 | 37.4 ms: 1.08x slower                                                                                         |
| argparse_subparsers              | 686 us                                                                                                  | 740 us: 1.08x slower                                                                                          |
| mdp                              | 946 ms                                                                                                  | 1.02 sec: 1.08x slower                                                                                        |
| asyncio_tcp_ssl                  | 1.28 sec                                                                                                | 1.39 sec: 1.08x slower                                                                                        |
| sympy_sum                        | 106 ms                                                                                                  | 115 ms: 1.08x slower                                                                                          |
| sqlglot_v2_optimize              | 39.0 ms                                                                                                 | 42.5 ms: 1.09x slower                                                                                         |
| float                            | 47.3 ms                                                                                                 | 51.5 ms: 1.09x slower                                                                                         |
| json                             | 3.42 ms                                                                                                 | 3.74 ms: 1.09x slower                                                                                         |
| decimal_factorial                | 173 ms                                                                                                  | 189 ms: 1.09x slower                                                                                          |
| logging_silent                   | 65.3 ns                                                                                                 | 71.3 ns: 1.09x slower                                                                                         |
| genshi_xml                       | 39.5 ms                                                                                                 | 43.2 ms: 1.09x slower                                                                                         |
| sympy_str                        | 194 ms                                                                                                  | 213 ms: 1.10x slower                                                                                          |
| chaos                            | 43.8 ms                                                                                                 | 48.2 ms: 1.10x slower                                                                                         |
| sqlglot_v2_normalize             | 78.2 ms                                                                                                 | 86.1 ms: 1.10x slower                                                                                         |
| sympy_integrate                  | 15.4 ms                                                                                                 | 17.0 ms: 1.10x slower                                                                                         |
| logging_format                   | 5.35 us                                                                                                 | 5.91 us: 1.10x slower                                                                                         |
| base32_large                     | 292 ms                                                                                                  | 323 ms: 1.11x slower                                                                                          |
| sympy_expand                     | 332 ms                                                                                                  | 367 ms: 1.11x slower                                                                                          |
| xml_etree_process                | 44.7 ms                                                                                                 | 49.5 ms: 1.11x slower                                                                                         |
| scimark_fft                      | 226 ms                                                                                                  | 251 ms: 1.11x slower                                                                                          |
| quadtree_nbody                   | 596 ms                                                                                                  | 662 ms: 1.11x slower                                                                                          |
| deltablue                        | 2.34 ms                                                                                                 | 2.59 ms: 1.11x slower                                                                                         |
| ascii85_large                    | 667 ms                                                                                                  | 741 ms: 1.11x slower                                                                                          |
| django_template                  | 27.8 ms                                                                                                 | 30.9 ms: 1.11x slower                                                                                         |
| base32_small                     | 5.71 ms                                                                                                 | 6.37 ms: 1.12x slower                                                                                         |
| tomli_loads                      | 1.44 sec                                                                                                | 1.62 sec: 1.12x slower                                                                                        |
| ascii85_small                    | 12.7 ms                                                                                                 | 14.2 ms: 1.12x slower                                                                                         |
| deepcopy                         | 193 us                                                                                                  | 216 us: 1.12x slower                                                                                          |
| regex_compile                    | 93.9 ms                                                                                                 | 105 ms: 1.12x slower                                                                                          |
| logging_simple                   | 4.79 us                                                                                                 | 5.38 us: 1.12x slower                                                                                         |
| nqueens                          | 56.8 ms                                                                                                 | 63.9 ms: 1.13x slower                                                                                         |
| telco                            | 5.59 ms                                                                                                 | 6.30 ms: 1.13x slower                                                                                         |
| networkx_connected_components    | 438 ms                                                                                                  | 495 ms: 1.13x slower                                                                                          |
| noop                             | 19.4 ns                                                                                                 | 21.9 ns: 1.13x slower                                                                                         |
| go                               | 84.7 ms                                                                                                 | 96.1 ms: 1.13x slower                                                                                         |
| unpickle                         | 10.2 us                                                                                                 | 11.6 us: 1.14x slower                                                                                         |
| pyflate                          | 299 ms                                                                                                  | 341 ms: 1.14x slower                                                                                          |
| richards                         | 32.6 ms                                                                                                 | 37.2 ms: 1.14x slower                                                                                         |
| scimark_sor                      | 75.7 ms                                                                                                 | 86.4 ms: 1.14x slower                                                                                         |
| sqlglot_v2_transpile             | 1.15 ms                                                                                                 | 1.31 ms: 1.14x slower                                                                                         |
| chameleon                        | 9.52 ms                                                                                                 | 10.9 ms: 1.14x slower                                                                                         |
| deepcopy_reduce                  | 2.00 us                                                                                                 | 2.29 us: 1.15x slower                                                                                         |
| unpickle_list                    | 3.43 us                                                                                                 | 3.94 us: 1.15x slower                                                                                         |
| networkx_shortest_path           | 444 ms                                                                                                  | 510 ms: 1.15x slower                                                                                          |
| spectral_norm                    | 65.6 ms                                                                                                 | 75.3 ms: 1.15x slower                                                                                         |
| json_dumps                       | 6.95 ms                                                                                                 | 7.98 ms: 1.15x slower                                                                                         |
| richards_super                   | 37.4 ms                                                                                                 | 43.2 ms: 1.16x slower                                                                                         |
| json_loads                       | 17.5 us                                                                                                 | 20.2 us: 1.16x slower                                                                                         |
| hexiom                           | 4.11 ms                                                                                                 | 4.77 ms: 1.16x slower                                                                                         |
| meteor_contest                   | 84.1 ms                                                                                                 | 97.6 ms: 1.16x slower                                                                                         |
| pprint_pformat                   | 989 ms                                                                                                  | 1.15 sec: 1.16x slower                                                                                        |
| pprint_safe_repr                 | 474 ms                                                                                                  | 553 ms: 1.17x slower                                                                                          |
| async_generators                 | 228 ms                                                                                                  | 266 ms: 1.17x slower                                                                                          |
| comprehensions                   | 10.8 us                                                                                                 | 12.6 us: 1.17x slower                                                                                         |
| sqlglot_v2_parse                 | 911 us                                                                                                  | 1.07 ms: 1.17x slower                                                                                         |
| scimark_sparse_mat_mult          | 3.18 ms                                                                                                 | 3.73 ms: 1.17x slower                                                                                         |
| genshi_text                      | 16.8 ms                                                                                                 | 19.8 ms: 1.18x slower                                                                                         |
| decimal_pi                       | 208 ms                                                                                                  | 246 ms: 1.18x slower                                                                                          |
| raytrace                         | 194 ms                                                                                                  | 231 ms: 1.19x slower                                                                                          |
| scimark_lu                       | 73.8 ms                                                                                                 | 88.2 ms: 1.19x slower                                                                                         |
| crypto_pyaes                     | 54.5 ms                                                                                                 | 65.3 ms: 1.20x slower                                                                                         |
| async_tree_eager                 | 81.3 ms                                                                                                 | 98.7 ms: 1.21x slower                                                                                         |
| python_startup                   | 9.73 ms                                                                                                 | 11.8 ms: 1.21x slower                                                                                         |
| deepcopy_memo                    | 18.0 us                                                                                                 | 21.9 us: 1.22x slower                                                                                         |
| typing_runtime_protocols         | 112 us                                                                                                  | 137 us: 1.22x slower                                                                                          |
| nbody                            | 67.9 ms                                                                                                 | 83.2 ms: 1.23x slower                                                                                         |
| fannkuch                         | 245 ms                                                                                                  | 310 ms: 1.26x slower                                                                                          |
| scimark_monte_carlo              | 40.7 ms                                                                                                 | 52.6 ms: 1.29x slower                                                                                         |
| python_startup_no_site           | 6.38 ms                                                                                                 | 8.33 ms: 1.31x slower                                                                                         |
| unpack_sequence                  | 25.8 ns                                                                                                 | 35.5 ns: 1.38x slower                                                                                         |
| coverage                         | 57.4 ms                                                                                                 | 80.7 ms: 1.41x slower                                                                                         |
| mako                             | 7.40 ms                                                                                                 | 11.5 ms: 1.56x slower                                                                                         |
| thread_montecarlo_naive          | 15.8 ms                                                                                                 | 26.9 ms: 1.70x slower                                                                                         |
| thread_memo_naive                | 11.5 ms                                                                                                 | 24.2 ms: 2.10x slower                                                                                         |
| Geometric mean                   | (ref)                                                                                                   | 1.01x faster                                                                                                  |

Benchmark hidden because not significant (2): async_tree_eager_memoization, urlsafe_base64_small
Ignored benchmarks (1) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.008x faster

# HPT report

- Reliability score: 99.88% likely to be slow
- 90% likely to have a slowdown of 1.03x
- 95% likely to have a slowdown of 1.03x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 1.46x