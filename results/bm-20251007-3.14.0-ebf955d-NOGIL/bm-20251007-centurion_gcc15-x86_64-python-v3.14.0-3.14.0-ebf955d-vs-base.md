# Results vs. base

- fork: python
- ref: v3.14.0
- machine: linux-x86_64
- commit hash: ebf955d
- commit date: 2025-10-07
- overall geometric mean: 1.013x faster
- HPT reliability: 99.90%
- HPT 99th percentile: 1.01x slower
- Memory change: 1.48x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                                                                  | 11.9 ms: 1.12x slower                                                                                          |
| docutils       | 2.02 sec                                                                                                 | 2.12 sec: 1.05x slower                                                                                         |
| fastapi_http   | 215 ms                                                                                                   | 185 ms: 1.16x faster                                                                                           |
| tornado_http   | 101 ms                                                                                                   | 93.5 ms: 1.08x faster                                                                                          |
| Geometric mean | (ref)                                                                                                    | 1.01x faster                                                                                                   |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 549 ms                                                                                                   | 409 ms: 1.34x faster                                                                                           |
| async_tree_io_tg                 | 529 ms                                                                                                   | 412 ms: 1.28x faster                                                                                           |
| async_tree_eager_io              | 548 ms                                                                                                   | 431 ms: 1.27x faster                                                                                           |
| async_tree_none_tg               | 221 ms                                                                                                   | 178 ms: 1.24x faster                                                                                           |
| async_tree_io                    | 527 ms                                                                                                   | 440 ms: 1.20x faster                                                                                           |
| async_tree_memoization_tg        | 275 ms                                                                                                   | 235 ms: 1.17x faster                                                                                           |
| async_tree_eager_tg              | 179 ms                                                                                                   | 160 ms: 1.12x faster                                                                                           |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                                                                   | 392 ms: 1.11x faster                                                                                           |
| async_tree_eager_memoization_tg  | 235 ms                                                                                                   | 213 ms: 1.10x faster                                                                                           |
| async_tree_none                  | 223 ms                                                                                                   | 208 ms: 1.08x faster                                                                                           |
| async_tree_memoization           | 274 ms                                                                                                   | 258 ms: 1.06x faster                                                                                           |
| asyncio_websockets               | 305 ms                                                                                                   | 290 ms: 1.05x faster                                                                                           |
| async_tree_cpu_io_mixed          | 430 ms                                                                                                   | 418 ms: 1.03x faster                                                                                           |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                                                                   | 376 ms: 1.03x faster                                                                                           |
| coroutines                       | 15.4 ms                                                                                                  | 15.2 ms: 1.01x faster                                                                                          |
| async_tree_eager_memoization     | 175 ms                                                                                                   | 173 ms: 1.01x faster                                                                                           |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                                                                   | 345 ms: 1.04x slower                                                                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                 | 1.38 sec: 1.07x slower                                                                                         |
| asyncio_tcp                      | 332 ms                                                                                                   | 360 ms: 1.08x slower                                                                                           |
| async_generators                 | 243 ms                                                                                                   | 270 ms: 1.11x slower                                                                                           |
| async_tree_eager                 | 78.8 ms                                                                                                  | 96.0 ms: 1.22x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                    | 1.07x faster                                                                                                   |

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| noop      | 18.7 ns                                                                                                  | 21.3 ns: 1.14x slower                                                                                          |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                                                                   | 188 ms: 1.11x slower                                                                                           |
| decimal_pi        | 201 ms                                                                                                   | 241 ms: 1.20x slower                                                                                           |
| Geometric mean    | (ref)                                                                                                    | 1.15x slower                                                                                                   |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| pidigits       | 181 ms                                                                                                   | 178 ms: 1.02x faster                                                                                           |
| quadtree_nbody | 602 ms                                                                                                   | 626 ms: 1.04x slower                                                                                           |
| float          | 48.1 ms                                                                                                  | 51.8 ms: 1.08x slower                                                                                          |
| nbody          | 67.2 ms                                                                                                  | 83.7 ms: 1.25x slower                                                                                          |
| Geometric mean | (ref)                                                                                                    | 1.08x slower                                                                                                   |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| regex_effbot   | 1.80 ms                                                                                                  | 1.76 ms: 1.02x faster                                                                                          |
| regex_v8       | 15.0 ms                                                                                                  | 15.3 ms: 1.02x slower                                                                                          |
| regex_compile  | 91.6 ms                                                                                                  | 103 ms: 1.12x slower                                                                                           |
| Geometric mean | (ref)                                                                                                    | 1.03x slower                                                                                                   |

Benchmark hidden because not significant (1): regex_dna

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| xml_etree_iterparse  | 76.5 ms                                                                                                  | 63.4 ms: 1.21x faster                                                                                          |
| xml_etree_parse      | 102 ms                                                                                                   | 98.7 ms: 1.04x faster                                                                                          |
| pickle_list          | 3.26 us                                                                                                  | 3.20 us: 1.02x faster                                                                                          |
| base16_large         | 5.41 ms                                                                                                  | 5.35 ms: 1.01x faster                                                                                          |
| pickle               | 9.23 us                                                                                                  | 9.14 us: 1.01x faster                                                                                          |
| base64_large         | 6.31 ms                                                                                                  | 6.33 ms: 1.00x slower                                                                                          |
| base16_small         | 298 us                                                                                                   | 300 us: 1.01x slower                                                                                           |
| urlsafe_base64_small | 383 us                                                                                                   | 386 us: 1.01x slower                                                                                           |
| base64_small         | 230 us                                                                                                   | 233 us: 1.01x slower                                                                                           |
| xml_etree_generate   | 71.1 ms                                                                                                  | 72.0 ms: 1.01x slower                                                                                          |
| unpickle_pure_python | 153 us                                                                                                   | 157 us: 1.02x slower                                                                                           |
| xml_etree_process    | 50.0 ms                                                                                                  | 53.3 ms: 1.07x slower                                                                                          |
| base85_small         | 4.44 ms                                                                                                  | 4.77 ms: 1.07x slower                                                                                          |
| tomli_loads          | 1.41 sec                                                                                                 | 1.53 sec: 1.09x slower                                                                                         |
| unpickle             | 10.3 us                                                                                                  | 11.3 us: 1.09x slower                                                                                          |
| base85_large         | 233 ms                                                                                                   | 255 ms: 1.10x slower                                                                                           |
| json_dumps           | 7.37 ms                                                                                                  | 8.11 ms: 1.10x slower                                                                                          |
| base32_large         | 276 ms                                                                                                   | 310 ms: 1.12x slower                                                                                           |
| ascii85_large        | 651 ms                                                                                                   | 735 ms: 1.13x slower                                                                                           |
| base32_small         | 5.43 ms                                                                                                  | 6.14 ms: 1.13x slower                                                                                          |
| ascii85_small        | 12.5 ms                                                                                                  | 14.3 ms: 1.15x slower                                                                                          |
| json_loads           | 17.3 us                                                                                                  | 20.3 us: 1.17x slower                                                                                          |
| unpickle_list        | 3.64 us                                                                                                  | 4.53 us: 1.24x slower                                                                                          |
| Geometric mean       | (ref)                                                                                                    | 1.05x slower                                                                                                   |

Benchmark hidden because not significant (2): pickle_pure_python, pickle_dict

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                                                                  | 11.6 ms: 1.21x slower                                                                                          |
| python_startup_no_site | 6.29 ms                                                                                                  | 8.10 ms: 1.29x slower                                                                                          |
| Geometric mean         | (ref)                                                                                                    | 1.25x slower                                                                                                   |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| genshi_xml      | 38.4 ms                                                                                                  | 41.7 ms: 1.08x slower                                                                                          |
| django_template | 28.4 ms                                                                                                  | 31.2 ms: 1.10x slower                                                                                          |
| genshi_text     | 16.4 ms                                                                                                  | 19.5 ms: 1.19x slower                                                                                          |
| mako            | 7.66 ms                                                                                                  | 11.9 ms: 1.56x slower                                                                                          |
| Geometric mean  | (ref)                                                                                                    | 1.22x slower                                                                                                   |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|-----------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_pipeline_optimized   | 26.3 ms                                                                                                  | 7.15 ms: 3.68x faster                                                                                          |
| thread_accumulate_optimized | 40.8 ms                                                                                                  | 11.3 ms: 3.62x faster                                                                                          |
| thread_counter_optimized    | 18.7 ms                                                                                                  | 5.28 ms: 3.54x faster                                                                                          |
| thread_mandelbrot_optimized | 215 ms                                                                                                   | 62.0 ms: 3.47x faster                                                                                          |
| thread_mandelbrot_naive     | 217 ms                                                                                                   | 62.7 ms: 3.46x faster                                                                                          |
| thread_memo_optimized       | 17.9 ms                                                                                                  | 5.92 ms: 3.03x faster                                                                                          |
| thread_accumulate_naive     | 41.6 ms                                                                                                  | 13.9 ms: 2.99x faster                                                                                          |
| thread_montecarlo_optimized | 12.6 ms                                                                                                  | 4.75 ms: 2.65x faster                                                                                          |
| thread_pipeline_naive       | 35.4 ms                                                                                                  | 27.2 ms: 1.30x faster                                                                                          |
| thread_counter_naive        | 21.4 ms                                                                                                  | 21.0 ms: 1.02x faster                                                                                          |
| thread_montecarlo_naive     | 14.6 ms                                                                                                  | 26.3 ms: 1.80x slower                                                                                          |
| thread_memo_naive           | 11.8 ms                                                                                                  | 24.0 ms: 2.03x slower                                                                                          |
| Geometric mean              | (ref)                                                                                                    | 2.03x faster                                                                                                   |

All benchmarks:
===============

| Benchmark                        | results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json | results/bm-20251007-3.14.0-ebf955d-NOGIL/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json |
|----------------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_pipeline_optimized        | 26.3 ms                                                                                                  | 7.15 ms: 3.68x faster                                                                                          |
| thread_accumulate_optimized      | 40.8 ms                                                                                                  | 11.3 ms: 3.62x faster                                                                                          |
| thread_counter_optimized         | 18.7 ms                                                                                                  | 5.28 ms: 3.54x faster                                                                                          |
| thread_mandelbrot_optimized      | 215 ms                                                                                                   | 62.0 ms: 3.47x faster                                                                                          |
| thread_mandelbrot_naive          | 217 ms                                                                                                   | 62.7 ms: 3.46x faster                                                                                          |
| thread_memo_optimized            | 17.9 ms                                                                                                  | 5.92 ms: 3.03x faster                                                                                          |
| thread_accumulate_naive          | 41.6 ms                                                                                                  | 13.9 ms: 2.99x faster                                                                                          |
| thread_montecarlo_optimized      | 12.6 ms                                                                                                  | 4.75 ms: 2.65x faster                                                                                          |
| gc_traversal                     | 3.33 ms                                                                                                  | 1.56 ms: 2.14x faster                                                                                          |
| create_gc_cycles                 | 1.93 ms                                                                                                  | 1.29 ms: 1.49x faster                                                                                          |
| async_tree_eager_io_tg           | 549 ms                                                                                                   | 409 ms: 1.34x faster                                                                                           |
| thread_pipeline_naive            | 35.4 ms                                                                                                  | 27.2 ms: 1.30x faster                                                                                          |
| async_tree_io_tg                 | 529 ms                                                                                                   | 412 ms: 1.28x faster                                                                                           |
| async_tree_eager_io              | 548 ms                                                                                                   | 431 ms: 1.27x faster                                                                                           |
| async_tree_none_tg               | 221 ms                                                                                                   | 178 ms: 1.24x faster                                                                                           |
| xml_etree_iterparse              | 76.5 ms                                                                                                  | 63.4 ms: 1.21x faster                                                                                          |
| async_tree_io                    | 527 ms                                                                                                   | 440 ms: 1.20x faster                                                                                           |
| async_tree_memoization_tg        | 275 ms                                                                                                   | 235 ms: 1.17x faster                                                                                           |
| fastapi_http                     | 215 ms                                                                                                   | 185 ms: 1.16x faster                                                                                           |
| async_tree_eager_tg              | 179 ms                                                                                                   | 160 ms: 1.12x faster                                                                                           |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                                                                   | 392 ms: 1.11x faster                                                                                           |
| async_tree_eager_memoization_tg  | 235 ms                                                                                                   | 213 ms: 1.10x faster                                                                                           |
| tornado_http                     | 101 ms                                                                                                   | 93.5 ms: 1.08x faster                                                                                          |
| async_tree_none                  | 223 ms                                                                                                   | 208 ms: 1.08x faster                                                                                           |
| async_tree_memoization           | 274 ms                                                                                                   | 258 ms: 1.06x faster                                                                                           |
| asyncio_websockets               | 305 ms                                                                                                   | 290 ms: 1.05x faster                                                                                           |
| pycparser                        | 837 ms                                                                                                   | 808 ms: 1.04x faster                                                                                           |
| xml_etree_parse                  | 102 ms                                                                                                   | 98.7 ms: 1.04x faster                                                                                          |
| async_tree_cpu_io_mixed          | 430 ms                                                                                                   | 418 ms: 1.03x faster                                                                                           |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                                                                   | 376 ms: 1.03x faster                                                                                           |
| regex_effbot                     | 1.80 ms                                                                                                  | 1.76 ms: 1.02x faster                                                                                          |
| thread_counter_naive             | 21.4 ms                                                                                                  | 21.0 ms: 1.02x faster                                                                                          |
| pickle_list                      | 3.26 us                                                                                                  | 3.20 us: 1.02x faster                                                                                          |
| pidigits                         | 181 ms                                                                                                   | 178 ms: 1.02x faster                                                                                           |
| coroutines                       | 15.4 ms                                                                                                  | 15.2 ms: 1.01x faster                                                                                          |
| base16_large                     | 5.41 ms                                                                                                  | 5.35 ms: 1.01x faster                                                                                          |
| pickle                           | 9.23 us                                                                                                  | 9.14 us: 1.01x faster                                                                                          |
| async_tree_eager_memoization     | 175 ms                                                                                                   | 173 ms: 1.01x faster                                                                                           |
| base64_large                     | 6.31 ms                                                                                                  | 6.33 ms: 1.00x slower                                                                                          |
| base16_small                     | 298 us                                                                                                   | 300 us: 1.01x slower                                                                                           |
| urlsafe_base64_small             | 383 us                                                                                                   | 386 us: 1.01x slower                                                                                           |
| pathlib                          | 12.5 ms                                                                                                  | 12.6 ms: 1.01x slower                                                                                          |
| base64_small                     | 230 us                                                                                                   | 233 us: 1.01x slower                                                                                           |
| xml_etree_generate               | 71.1 ms                                                                                                  | 72.0 ms: 1.01x slower                                                                                          |
| regex_v8                         | 15.0 ms                                                                                                  | 15.3 ms: 1.02x slower                                                                                          |
| generators                       | 20.7 ms                                                                                                  | 21.2 ms: 1.02x slower                                                                                          |
| unpickle_pure_python             | 153 us                                                                                                   | 157 us: 1.02x slower                                                                                           |
| bpe_tokeniser                    | 3.10 sec                                                                                                 | 3.18 sec: 1.03x slower                                                                                         |
| networkx_k_core                  | 2.07 sec                                                                                                 | 2.13 sec: 1.03x slower                                                                                         |
| mypy2                            | 756 ms                                                                                                   | 783 ms: 1.04x slower                                                                                           |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                                                                   | 345 ms: 1.04x slower                                                                                           |
| pylint                           | 215 ms                                                                                                   | 223 ms: 1.04x slower                                                                                           |
| quadtree_nbody                   | 602 ms                                                                                                   | 626 ms: 1.04x slower                                                                                           |
| thrift                           | 1.84 ms                                                                                                  | 1.92 ms: 1.05x slower                                                                                          |
| docutils                         | 2.02 sec                                                                                                 | 2.12 sec: 1.05x slower                                                                                         |
| sqlglot_v2_optimize              | 38.7 ms                                                                                                  | 40.9 ms: 1.06x slower                                                                                          |
| xdsl_constant_fold               | 35.1 ms                                                                                                  | 37.2 ms: 1.06x slower                                                                                          |
| mdp                              | 935 ms                                                                                                   | 990 ms: 1.06x slower                                                                                           |
| sympy_sum                        | 104 ms                                                                                                   | 110 ms: 1.06x slower                                                                                           |
| xml_etree_process                | 50.0 ms                                                                                                  | 53.3 ms: 1.07x slower                                                                                          |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                 | 1.38 sec: 1.07x slower                                                                                         |
| base85_small                     | 4.44 ms                                                                                                  | 4.77 ms: 1.07x slower                                                                                          |
| sqlglot_v2_normalize             | 77.8 ms                                                                                                  | 83.6 ms: 1.07x slower                                                                                          |
| sqlalchemy_imperative            | 14.3 ms                                                                                                  | 15.3 ms: 1.08x slower                                                                                          |
| float                            | 48.1 ms                                                                                                  | 51.8 ms: 1.08x slower                                                                                          |
| argparse_subparsers              | 665 us                                                                                                   | 717 us: 1.08x slower                                                                                           |
| logging_silent                   | 59.7 ns                                                                                                  | 64.4 ns: 1.08x slower                                                                                          |
| pyflate                          | 300 ms                                                                                                   | 324 ms: 1.08x slower                                                                                           |
| sympy_str                        | 192 ms                                                                                                   | 208 ms: 1.08x slower                                                                                           |
| genshi_xml                       | 38.4 ms                                                                                                  | 41.7 ms: 1.08x slower                                                                                          |
| asyncio_tcp                      | 332 ms                                                                                                   | 360 ms: 1.08x slower                                                                                           |
| tomli_loads                      | 1.41 sec                                                                                                 | 1.53 sec: 1.09x slower                                                                                         |
| logging_simple                   | 4.72 us                                                                                                  | 5.14 us: 1.09x slower                                                                                          |
| argparse_many_optionals          | 33.3 ms                                                                                                  | 36.2 ms: 1.09x slower                                                                                          |
| logging_format                   | 5.24 us                                                                                                  | 5.71 us: 1.09x slower                                                                                          |
| sympy_integrate                  | 14.7 ms                                                                                                  | 16.0 ms: 1.09x slower                                                                                          |
| chaos                            | 41.9 ms                                                                                                  | 45.6 ms: 1.09x slower                                                                                          |
| unpickle                         | 10.3 us                                                                                                  | 11.3 us: 1.09x slower                                                                                          |
| nqueens                          | 56.3 ms                                                                                                  | 61.4 ms: 1.09x slower                                                                                          |
| sympy_expand                     | 330 ms                                                                                                   | 360 ms: 1.09x slower                                                                                           |
| pprint_safe_repr                 | 484 ms                                                                                                   | 529 ms: 1.09x slower                                                                                           |
| json                             | 3.42 ms                                                                                                  | 3.75 ms: 1.09x slower                                                                                          |
| base85_large                     | 233 ms                                                                                                   | 255 ms: 1.10x slower                                                                                           |
| deltablue                        | 2.24 ms                                                                                                  | 2.46 ms: 1.10x slower                                                                                          |
| django_template                  | 28.4 ms                                                                                                  | 31.2 ms: 1.10x slower                                                                                          |
| json_dumps                       | 7.37 ms                                                                                                  | 8.11 ms: 1.10x slower                                                                                          |
| decimal_factorial                | 170 ms                                                                                                   | 188 ms: 1.11x slower                                                                                           |
| async_generators                 | 243 ms                                                                                                   | 270 ms: 1.11x slower                                                                                           |
| sqlglot_v2_transpile             | 1.15 ms                                                                                                  | 1.28 ms: 1.11x slower                                                                                          |
| hexiom                           | 4.00 ms                                                                                                  | 4.46 ms: 1.11x slower                                                                                          |
| scimark_sor                      | 72.8 ms                                                                                                  | 81.1 ms: 1.11x slower                                                                                          |
| go                               | 82.6 ms                                                                                                  | 92.3 ms: 1.12x slower                                                                                          |
| chameleon                        | 10.6 ms                                                                                                  | 11.9 ms: 1.12x slower                                                                                          |
| deepcopy                         | 195 us                                                                                                   | 218 us: 1.12x slower                                                                                           |
| regex_compile                    | 91.6 ms                                                                                                  | 103 ms: 1.12x slower                                                                                           |
| pprint_pformat                   | 982 ms                                                                                                   | 1.10 sec: 1.12x slower                                                                                         |
| base32_large                     | 276 ms                                                                                                   | 310 ms: 1.12x slower                                                                                           |
| networkx_connected_components    | 435 ms                                                                                                   | 491 ms: 1.13x slower                                                                                           |
| ascii85_large                    | 651 ms                                                                                                   | 735 ms: 1.13x slower                                                                                           |
| base32_small                     | 5.43 ms                                                                                                  | 6.14 ms: 1.13x slower                                                                                          |
| noop                             | 18.7 ns                                                                                                  | 21.3 ns: 1.14x slower                                                                                          |
| deepcopy_reduce                  | 2.05 us                                                                                                  | 2.33 us: 1.14x slower                                                                                          |
| comprehensions                   | 11.2 us                                                                                                  | 12.7 us: 1.14x slower                                                                                          |
| richards                         | 32.5 ms                                                                                                  | 37.1 ms: 1.14x slower                                                                                          |
| networkx_shortest_path           | 445 ms                                                                                                   | 509 ms: 1.14x slower                                                                                           |
| sqlglot_v2_parse                 | 909 us                                                                                                   | 1.04 ms: 1.15x slower                                                                                          |
| ascii85_small                    | 12.5 ms                                                                                                  | 14.3 ms: 1.15x slower                                                                                          |
| raytrace                         | 194 ms                                                                                                   | 225 ms: 1.16x slower                                                                                           |
| telco                            | 5.26 ms                                                                                                  | 6.10 ms: 1.16x slower                                                                                          |
| meteor_contest                   | 83.9 ms                                                                                                  | 97.4 ms: 1.16x slower                                                                                          |
| scimark_lu                       | 66.7 ms                                                                                                  | 78.1 ms: 1.17x slower                                                                                          |
| richards_super                   | 37.2 ms                                                                                                  | 43.6 ms: 1.17x slower                                                                                          |
| json_loads                       | 17.3 us                                                                                                  | 20.3 us: 1.17x slower                                                                                          |
| spectral_norm                    | 59.6 ms                                                                                                  | 70.0 ms: 1.17x slower                                                                                          |
| scimark_fft                      | 197 ms                                                                                                   | 233 ms: 1.18x slower                                                                                           |
| genshi_text                      | 16.4 ms                                                                                                  | 19.5 ms: 1.19x slower                                                                                          |
| decimal_pi                       | 201 ms                                                                                                   | 241 ms: 1.20x slower                                                                                           |
| crypto_pyaes                     | 51.5 ms                                                                                                  | 61.7 ms: 1.20x slower                                                                                          |
| python_startup                   | 9.62 ms                                                                                                  | 11.6 ms: 1.21x slower                                                                                          |
| deepcopy_memo                    | 18.2 us                                                                                                  | 22.1 us: 1.21x slower                                                                                          |
| async_tree_eager                 | 78.8 ms                                                                                                  | 96.0 ms: 1.22x slower                                                                                          |
| typing_runtime_protocols         | 106 us                                                                                                   | 130 us: 1.23x slower                                                                                           |
| scimark_monte_carlo              | 37.5 ms                                                                                                  | 46.1 ms: 1.23x slower                                                                                          |
| fannkuch                         | 234 ms                                                                                                   | 291 ms: 1.24x slower                                                                                           |
| unpickle_list                    | 3.64 us                                                                                                  | 4.53 us: 1.24x slower                                                                                          |
| nbody                            | 67.2 ms                                                                                                  | 83.7 ms: 1.25x slower                                                                                          |
| scimark_sparse_mat_mult          | 2.58 ms                                                                                                  | 3.27 ms: 1.27x slower                                                                                          |
| python_startup_no_site           | 6.29 ms                                                                                                  | 8.10 ms: 1.29x slower                                                                                          |
| coverage                         | 55.4 ms                                                                                                  | 76.0 ms: 1.37x slower                                                                                          |
| unpack_sequence                  | 24.1 ns                                                                                                  | 33.8 ns: 1.40x slower                                                                                          |
| mako                             | 7.66 ms                                                                                                  | 11.9 ms: 1.56x slower                                                                                          |
| thread_montecarlo_naive          | 14.6 ms                                                                                                  | 26.3 ms: 1.80x slower                                                                                          |
| thread_memo_naive                | 11.8 ms                                                                                                  | 24.0 ms: 2.03x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                    | 1.01x faster                                                                                                   |

Benchmark hidden because not significant (4): regex_dna, pickle_pure_python, pickle_dict, html5lib

- Geometric mean (including insignificant results): 1.013x faster

# HPT report

- Reliability score: 99.90% likely to be slow
- 90% likely to have a slowdown of 1.02x
- 95% likely to have a slowdown of 1.02x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 1.48x