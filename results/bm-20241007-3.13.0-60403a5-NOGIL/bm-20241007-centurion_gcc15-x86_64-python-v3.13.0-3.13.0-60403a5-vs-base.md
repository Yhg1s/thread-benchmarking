# Results vs. base

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.179x slower
- HPT reliability: 100.00%
- HPT 99th percentile: 1.15x slower
- Memory change: 1.45x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                                                                  | 17.1 ms: 1.56x slower                                                                                          |
| docutils       | 1.98 sec                                                                                                 | 2.41 sec: 1.22x slower                                                                                         |
| fastapi_http   | 215 ms                                                                                                   | 290 ms: 1.35x slower                                                                                           |
| html5lib       | 49.1 ms                                                                                                  | 67.6 ms: 1.38x slower                                                                                          |
| tornado_http   | 99.2 ms                                                                                                  | 111 ms: 1.12x slower                                                                                           |
| Geometric mean | (ref)                                                                                                    | 1.32x slower                                                                                                   |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 724 ms                                                                                                   | 644 ms: 1.12x faster                                                                                           |
| async_tree_io_tg                 | 777 ms                                                                                                   | 695 ms: 1.12x faster                                                                                           |
| async_tree_eager_io              | 749 ms                                                                                                   | 697 ms: 1.07x faster                                                                                           |
| async_tree_memoization_tg        | 417 ms                                                                                                   | 395 ms: 1.06x faster                                                                                           |
| asyncio_websockets               | 304 ms                                                                                                   | 296 ms: 1.02x faster                                                                                           |
| async_tree_none_tg               | 289 ms                                                                                                   | 309 ms: 1.07x slower                                                                                           |
| async_tree_memoization           | 389 ms                                                                                                   | 419 ms: 1.08x slower                                                                                           |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                                                                   | 347 ms: 1.08x slower                                                                                           |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                                                                   | 392 ms: 1.09x slower                                                                                           |
| async_tree_cpu_io_mixed          | 514 ms                                                                                                   | 561 ms: 1.09x slower                                                                                           |
| coroutines                       | 17.6 ms                                                                                                  | 19.4 ms: 1.10x slower                                                                                          |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                 | 1.44 sec: 1.12x slower                                                                                         |
| async_tree_none                  | 310 ms                                                                                                   | 349 ms: 1.13x slower                                                                                           |
| async_tree_eager_memoization_tg  | 173 ms                                                                                                   | 197 ms: 1.14x slower                                                                                           |
| asyncio_tcp                      | 326 ms                                                                                                   | 378 ms: 1.16x slower                                                                                           |
| async_tree_eager_memoization     | 215 ms                                                                                                   | 251 ms: 1.17x slower                                                                                           |
| async_generators                 | 262 ms                                                                                                   | 364 ms: 1.39x slower                                                                                           |
| async_tree_eager                 | 90.0 ms                                                                                                  | 133 ms: 1.48x slower                                                                                           |
| async_tree_eager_tg              | 58.6 ms                                                                                                  | 92.3 ms: 1.57x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                    | 1.10x slower                                                                                                   |

Benchmark hidden because not significant (2): async_tree_io, async_tree_cpu_io_mixed_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| noop      | 20.4 ns                                                                                                  | 24.9 ns: 1.22x slower                                                                                          |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                                                                   | 185 ms: 1.07x slower                                                                                           |
| decimal_pi        | 210 ms                                                                                                   | 232 ms: 1.10x slower                                                                                           |
| Geometric mean    | (ref)                                                                                                    | 1.09x slower                                                                                                   |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| pidigits       | 181 ms                                                                                                   | 180 ms: 1.01x faster                                                                                           |
| float          | 56.6 ms                                                                                                  | 95.0 ms: 1.68x slower                                                                                          |
| nbody          | 66.8 ms                                                                                                  | 131 ms: 1.97x slower                                                                                           |
| quadtree_nbody | 620 ms                                                                                                   | 1.36 sec: 2.19x slower                                                                                         |
| Geometric mean | (ref)                                                                                                    | 1.64x slower                                                                                                   |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| regex_dna      | 144 ms                                                                                                   | 147 ms: 1.03x slower                                                                                           |
| regex_v8       | 14.7 ms                                                                                                  | 15.4 ms: 1.05x slower                                                                                          |
| regex_compile  | 97.7 ms                                                                                                  | 146 ms: 1.49x slower                                                                                           |
| Geometric mean | (ref)                                                                                                    | 1.13x slower                                                                                                   |

Benchmark hidden because not significant (1): regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| xml_etree_parse      | 107 ms                                                                                                   | 99.7 ms: 1.08x faster                                                                                          |
| base16_large         | 31.6 ms                                                                                                  | 30.7 ms: 1.03x faster                                                                                          |
| pickle_dict          | 21.9 us                                                                                                  | 21.6 us: 1.01x faster                                                                                          |
| base64_large         | 6.32 ms                                                                                                  | 6.33 ms: 1.00x slower                                                                                          |
| pickle               | 8.22 us                                                                                                  | 8.26 us: 1.00x slower                                                                                          |
| pickle_list          | 3.03 us                                                                                                  | 3.13 us: 1.03x slower                                                                                          |
| unpickle             | 10.3 us                                                                                                  | 10.9 us: 1.06x slower                                                                                          |
| json_loads           | 16.7 us                                                                                                  | 18.9 us: 1.13x slower                                                                                          |
| base32_large         | 286 ms                                                                                                   | 325 ms: 1.14x slower                                                                                           |
| xml_etree_generate   | 66.3 ms                                                                                                  | 76.6 ms: 1.16x slower                                                                                          |
| base32_small         | 5.69 ms                                                                                                  | 6.64 ms: 1.17x slower                                                                                          |
| ascii85_large        | 814 ms                                                                                                   | 966 ms: 1.19x slower                                                                                           |
| json_dumps           | 7.49 ms                                                                                                  | 8.96 ms: 1.20x slower                                                                                          |
| ascii85_small        | 15.5 ms                                                                                                  | 18.7 ms: 1.21x slower                                                                                          |
| base16_small         | 656 us                                                                                                   | 830 us: 1.27x slower                                                                                           |
| unpickle_list        | 3.45 us                                                                                                  | 4.38 us: 1.27x slower                                                                                          |
| base85_large         | 243 ms                                                                                                   | 315 ms: 1.30x slower                                                                                           |
| xml_etree_process    | 48.1 ms                                                                                                  | 63.1 ms: 1.31x slower                                                                                          |
| tomli_loads          | 1.63 sec                                                                                                 | 2.19 sec: 1.34x slower                                                                                         |
| base85_small         | 4.41 ms                                                                                                  | 6.04 ms: 1.37x slower                                                                                          |
| base64_small         | 228 us                                                                                                   | 320 us: 1.40x slower                                                                                           |
| urlsafe_base64_small | 379 us                                                                                                   | 541 us: 1.43x slower                                                                                           |
| unpickle_pure_python | 149 us                                                                                                   | 250 us: 1.68x slower                                                                                           |
| pickle_pure_python   | 223 us                                                                                                   | 394 us: 1.77x slower                                                                                           |
| Geometric mean       | (ref)                                                                                                    | 1.20x slower                                                                                                   |

Benchmark hidden because not significant (1): xml_etree_iterparse

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.38 ms                                                                                                  | 11.3 ms: 1.21x slower                                                                                          |
| python_startup_no_site | 6.36 ms                                                                                                  | 7.84 ms: 1.23x slower                                                                                          |
| Geometric mean         | (ref)                                                                                                    | 1.22x slower                                                                                                   |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| genshi_xml      | 39.7 ms                                                                                                  | 54.6 ms: 1.37x slower                                                                                          |
| genshi_text     | 17.6 ms                                                                                                  | 27.9 ms: 1.59x slower                                                                                          |
| django_template | 27.3 ms                                                                                                  | 44.8 ms: 1.64x slower                                                                                          |
| mako            | 7.43 ms                                                                                                  | 14.3 ms: 1.92x slower                                                                                          |
| Geometric mean  | (ref)                                                                                                    | 1.62x slower                                                                                                   |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_accumulate_optimized | 39.8 ms                                                                                                  | 11.8 ms: 3.36x faster                                                                                          |
| thread_mandelbrot_optimized | 218 ms                                                                                                   | 65.1 ms: 3.34x faster                                                                                          |
| thread_pipeline_optimized   | 25.6 ms                                                                                                  | 7.67 ms: 3.34x faster                                                                                          |
| thread_mandelbrot_naive     | 220 ms                                                                                                   | 66.1 ms: 3.33x faster                                                                                          |
| thread_accumulate_naive     | 40.9 ms                                                                                                  | 13.0 ms: 3.14x faster                                                                                          |
| thread_counter_optimized    | 18.7 ms                                                                                                  | 6.68 ms: 2.80x faster                                                                                          |
| thread_memo_optimized       | 18.2 ms                                                                                                  | 6.85 ms: 2.66x faster                                                                                          |
| thread_montecarlo_optimized | 13.3 ms                                                                                                  | 5.39 ms: 2.47x faster                                                                                          |
| thread_pipeline_naive       | 52.1 ms                                                                                                  | 50.9 ms: 1.02x faster                                                                                          |
| thread_counter_naive        | 22.6 ms                                                                                                  | 27.7 ms: 1.22x slower                                                                                          |
| thread_memo_naive           | 39.0 ms                                                                                                  | 49.8 ms: 1.28x slower                                                                                          |
| thread_montecarlo_naive     | 17.8 ms                                                                                                  | 60.8 ms: 3.40x slower                                                                                          |
| Geometric mean              | (ref)                                                                                                    | 1.83x faster                                                                                                   |

All benchmarks:
===============

| Benchmark                        | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-NOGIL/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------------------|:--------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------:|
| thread_accumulate_optimized      | 39.8 ms                                                                                                  | 11.8 ms: 3.36x faster                                                                                          |
| thread_mandelbrot_optimized      | 218 ms                                                                                                   | 65.1 ms: 3.34x faster                                                                                          |
| thread_pipeline_optimized        | 25.6 ms                                                                                                  | 7.67 ms: 3.34x faster                                                                                          |
| thread_mandelbrot_naive          | 220 ms                                                                                                   | 66.1 ms: 3.33x faster                                                                                          |
| thread_accumulate_naive          | 40.9 ms                                                                                                  | 13.0 ms: 3.14x faster                                                                                          |
| thread_counter_optimized         | 18.7 ms                                                                                                  | 6.68 ms: 2.80x faster                                                                                          |
| thread_memo_optimized            | 18.2 ms                                                                                                  | 6.85 ms: 2.66x faster                                                                                          |
| thread_montecarlo_optimized      | 13.3 ms                                                                                                  | 5.39 ms: 2.47x faster                                                                                          |
| gc_traversal                     | 3.16 ms                                                                                                  | 2.45 ms: 1.29x faster                                                                                          |
| async_tree_eager_io_tg           | 724 ms                                                                                                   | 644 ms: 1.12x faster                                                                                           |
| async_tree_io_tg                 | 777 ms                                                                                                   | 695 ms: 1.12x faster                                                                                           |
| xml_etree_parse                  | 107 ms                                                                                                   | 99.7 ms: 1.08x faster                                                                                          |
| async_tree_eager_io              | 749 ms                                                                                                   | 697 ms: 1.07x faster                                                                                           |
| async_tree_memoization_tg        | 417 ms                                                                                                   | 395 ms: 1.06x faster                                                                                           |
| base16_large                     | 31.6 ms                                                                                                  | 30.7 ms: 1.03x faster                                                                                          |
| asyncio_websockets               | 304 ms                                                                                                   | 296 ms: 1.02x faster                                                                                           |
| thread_pipeline_naive            | 52.1 ms                                                                                                  | 50.9 ms: 1.02x faster                                                                                          |
| create_gc_cycles                 | 1.70 ms                                                                                                  | 1.68 ms: 1.01x faster                                                                                          |
| pickle_dict                      | 21.9 us                                                                                                  | 21.6 us: 1.01x faster                                                                                          |
| pidigits                         | 181 ms                                                                                                   | 180 ms: 1.01x faster                                                                                           |
| base64_large                     | 6.32 ms                                                                                                  | 6.33 ms: 1.00x slower                                                                                          |
| pickle                           | 8.22 us                                                                                                  | 8.26 us: 1.00x slower                                                                                          |
| regex_dna                        | 144 ms                                                                                                   | 147 ms: 1.03x slower                                                                                           |
| pickle_list                      | 3.03 us                                                                                                  | 3.13 us: 1.03x slower                                                                                          |
| regex_v8                         | 14.7 ms                                                                                                  | 15.4 ms: 1.05x slower                                                                                          |
| unpickle                         | 10.3 us                                                                                                  | 10.9 us: 1.06x slower                                                                                          |
| json                             | 3.49 ms                                                                                                  | 3.73 ms: 1.07x slower                                                                                          |
| async_tree_none_tg               | 289 ms                                                                                                   | 309 ms: 1.07x slower                                                                                           |
| decimal_factorial                | 173 ms                                                                                                   | 185 ms: 1.07x slower                                                                                           |
| async_tree_memoization           | 389 ms                                                                                                   | 419 ms: 1.08x slower                                                                                           |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                                                                   | 347 ms: 1.08x slower                                                                                           |
| networkx_connected_components    | 460 ms                                                                                                   | 501 ms: 1.09x slower                                                                                           |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                                                                   | 392 ms: 1.09x slower                                                                                           |
| async_tree_cpu_io_mixed          | 514 ms                                                                                                   | 561 ms: 1.09x slower                                                                                           |
| decimal_pi                       | 210 ms                                                                                                   | 232 ms: 1.10x slower                                                                                           |
| coroutines                       | 17.6 ms                                                                                                  | 19.4 ms: 1.10x slower                                                                                          |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                 | 1.44 sec: 1.12x slower                                                                                         |
| networkx_k_core                  | 2.15 sec                                                                                                 | 2.41 sec: 1.12x slower                                                                                         |
| tornado_http                     | 99.2 ms                                                                                                  | 111 ms: 1.12x slower                                                                                           |
| async_tree_none                  | 310 ms                                                                                                   | 349 ms: 1.13x slower                                                                                           |
| json_loads                       | 16.7 us                                                                                                  | 18.9 us: 1.13x slower                                                                                          |
| networkx_shortest_path           | 464 ms                                                                                                   | 527 ms: 1.14x slower                                                                                           |
| base32_large                     | 286 ms                                                                                                   | 325 ms: 1.14x slower                                                                                           |
| async_tree_eager_memoization_tg  | 173 ms                                                                                                   | 197 ms: 1.14x slower                                                                                           |
| mdp                              | 2.11 sec                                                                                                 | 2.41 sec: 1.14x slower                                                                                         |
| xml_etree_generate               | 66.3 ms                                                                                                  | 76.6 ms: 1.16x slower                                                                                          |
| asyncio_tcp                      | 326 ms                                                                                                   | 378 ms: 1.16x slower                                                                                           |
| base32_small                     | 5.69 ms                                                                                                  | 6.64 ms: 1.17x slower                                                                                          |
| async_tree_eager_memoization     | 215 ms                                                                                                   | 251 ms: 1.17x slower                                                                                           |
| ascii85_large                    | 814 ms                                                                                                   | 966 ms: 1.19x slower                                                                                           |
| json_dumps                       | 7.49 ms                                                                                                  | 8.96 ms: 1.20x slower                                                                                          |
| pylint                           | 226 ms                                                                                                   | 272 ms: 1.20x slower                                                                                           |
| meteor_contest                   | 89.9 ms                                                                                                  | 108 ms: 1.20x slower                                                                                           |
| python_startup                   | 9.38 ms                                                                                                  | 11.3 ms: 1.21x slower                                                                                          |
| ascii85_small                    | 15.5 ms                                                                                                  | 18.7 ms: 1.21x slower                                                                                          |
| pathlib                          | 12.4 ms                                                                                                  | 15.0 ms: 1.21x slower                                                                                          |
| docutils                         | 1.98 sec                                                                                                 | 2.41 sec: 1.22x slower                                                                                         |
| thread_counter_naive             | 22.6 ms                                                                                                  | 27.7 ms: 1.22x slower                                                                                          |
| noop                             | 20.4 ns                                                                                                  | 24.9 ns: 1.22x slower                                                                                          |
| scimark_fft                      | 211 ms                                                                                                   | 258 ms: 1.23x slower                                                                                           |
| argparse_subparsers              | 446 us                                                                                                   | 548 us: 1.23x slower                                                                                           |
| python_startup_no_site           | 6.36 ms                                                                                                  | 7.84 ms: 1.23x slower                                                                                          |
| coverage                         | 52.2 ms                                                                                                  | 64.8 ms: 1.24x slower                                                                                          |
| bpe_tokeniser                    | 3.40 sec                                                                                                 | 4.25 sec: 1.25x slower                                                                                         |
| pycparser                        | 884 ms                                                                                                   | 1.10 sec: 1.25x slower                                                                                         |
| fannkuch                         | 265 ms                                                                                                   | 332 ms: 1.25x slower                                                                                           |
| sqlalchemy_imperative            | 13.8 ms                                                                                                  | 17.4 ms: 1.26x slower                                                                                          |
| base16_small                     | 656 us                                                                                                   | 830 us: 1.27x slower                                                                                           |
| xdsl_constant_fold               | 36.7 ms                                                                                                  | 46.4 ms: 1.27x slower                                                                                          |
| unpickle_list                    | 3.45 us                                                                                                  | 4.38 us: 1.27x slower                                                                                          |
| telco                            | 5.50 ms                                                                                                  | 6.99 ms: 1.27x slower                                                                                          |
| thread_memo_naive                | 39.0 ms                                                                                                  | 49.8 ms: 1.28x slower                                                                                          |
| generators                       | 22.0 ms                                                                                                  | 28.3 ms: 1.29x slower                                                                                          |
| base85_large                     | 243 ms                                                                                                   | 315 ms: 1.30x slower                                                                                           |
| nqueens                          | 57.3 ms                                                                                                  | 74.7 ms: 1.30x slower                                                                                          |
| sympy_integrate                  | 15.4 ms                                                                                                  | 20.1 ms: 1.30x slower                                                                                          |
| xml_etree_process                | 48.1 ms                                                                                                  | 63.1 ms: 1.31x slower                                                                                          |
| scimark_sparse_mat_mult          | 2.66 ms                                                                                                  | 3.55 ms: 1.34x slower                                                                                          |
| tomli_loads                      | 1.63 sec                                                                                                 | 2.19 sec: 1.34x slower                                                                                         |
| fastapi_http                     | 215 ms                                                                                                   | 290 ms: 1.35x slower                                                                                           |
| pyflate                          | 358 ms                                                                                                   | 489 ms: 1.36x slower                                                                                           |
| base85_small                     | 4.41 ms                                                                                                  | 6.04 ms: 1.37x slower                                                                                          |
| genshi_xml                       | 39.7 ms                                                                                                  | 54.6 ms: 1.37x slower                                                                                          |
| html5lib                         | 49.1 ms                                                                                                  | 67.6 ms: 1.38x slower                                                                                          |
| async_generators                 | 262 ms                                                                                                   | 364 ms: 1.39x slower                                                                                           |
| mypy2                            | 726 ms                                                                                                   | 1.01 sec: 1.40x slower                                                                                         |
| base64_small                     | 228 us                                                                                                   | 320 us: 1.40x slower                                                                                           |
| crypto_pyaes                     | 50.0 ms                                                                                                  | 71.0 ms: 1.42x slower                                                                                          |
| urlsafe_base64_small             | 379 us                                                                                                   | 541 us: 1.43x slower                                                                                           |
| sqlglot_v2_optimize              | 40.0 ms                                                                                                  | 58.5 ms: 1.46x slower                                                                                          |
| deepcopy_memo                    | 26.6 us                                                                                                  | 38.9 us: 1.46x slower                                                                                          |
| deepcopy                         | 267 us                                                                                                   | 394 us: 1.47x slower                                                                                           |
| async_tree_eager                 | 90.0 ms                                                                                                  | 133 ms: 1.48x slower                                                                                           |
| argparse_many_optionals          | 12.6 ms                                                                                                  | 18.7 ms: 1.49x slower                                                                                          |
| regex_compile                    | 97.7 ms                                                                                                  | 146 ms: 1.49x slower                                                                                           |
| sympy_str                        | 193 ms                                                                                                   | 291 ms: 1.50x slower                                                                                           |
| sqlglot_v2_normalize             | 79.1 ms                                                                                                  | 119 ms: 1.51x slower                                                                                           |
| typing_runtime_protocols         | 106 us                                                                                                   | 161 us: 1.52x slower                                                                                           |
| deepcopy_reduce                  | 2.37 us                                                                                                  | 3.61 us: 1.52x slower                                                                                          |
| comprehensions                   | 11.6 us                                                                                                  | 18.1 us: 1.56x slower                                                                                          |
| chameleon                        | 10.9 ms                                                                                                  | 17.1 ms: 1.56x slower                                                                                          |
| richards                         | 36.8 ms                                                                                                  | 57.7 ms: 1.57x slower                                                                                          |
| pprint_safe_repr                 | 541 ms                                                                                                   | 849 ms: 1.57x slower                                                                                           |
| async_tree_eager_tg              | 58.6 ms                                                                                                  | 92.3 ms: 1.57x slower                                                                                          |
| genshi_text                      | 17.6 ms                                                                                                  | 27.9 ms: 1.59x slower                                                                                          |
| pprint_pformat                   | 1.11 sec                                                                                                 | 1.76 sec: 1.59x slower                                                                                         |
| spectral_norm                    | 64.1 ms                                                                                                  | 102 ms: 1.59x slower                                                                                           |
| thrift                           | 2.07 ms                                                                                                  | 3.35 ms: 1.62x slower                                                                                          |
| hexiom                           | 4.42 ms                                                                                                  | 7.20 ms: 1.63x slower                                                                                          |
| django_template                  | 27.3 ms                                                                                                  | 44.8 ms: 1.64x slower                                                                                          |
| scimark_sor                      | 97.0 ms                                                                                                  | 159 ms: 1.64x slower                                                                                           |
| logging_format                   | 5.23 us                                                                                                  | 8.60 us: 1.64x slower                                                                                          |
| sympy_expand                     | 330 ms                                                                                                   | 544 ms: 1.65x slower                                                                                           |
| sympy_sum                        | 104 ms                                                                                                   | 174 ms: 1.67x slower                                                                                           |
| float                            | 56.6 ms                                                                                                  | 95.0 ms: 1.68x slower                                                                                          |
| scimark_monte_carlo              | 44.3 ms                                                                                                  | 74.3 ms: 1.68x slower                                                                                          |
| unpickle_pure_python             | 149 us                                                                                                   | 250 us: 1.68x slower                                                                                           |
| logging_simple                   | 4.60 us                                                                                                  | 7.74 us: 1.68x slower                                                                                          |
| richards_super                   | 41.3 ms                                                                                                  | 69.9 ms: 1.69x slower                                                                                          |
| chaos                            | 45.0 ms                                                                                                  | 79.1 ms: 1.76x slower                                                                                          |
| pickle_pure_python               | 223 us                                                                                                   | 394 us: 1.77x slower                                                                                           |
| sqlglot_v2_transpile             | 1.20 ms                                                                                                  | 2.11 ms: 1.77x slower                                                                                          |
| go                               | 121 ms                                                                                                   | 218 ms: 1.79x slower                                                                                           |
| logging_silent                   | 60.6 ns                                                                                                  | 116 ns: 1.91x slower                                                                                           |
| sqlglot_v2_parse                 | 953 us                                                                                                   | 1.82 ms: 1.91x slower                                                                                          |
| mako                             | 7.43 ms                                                                                                  | 14.3 ms: 1.92x slower                                                                                          |
| nbody                            | 66.8 ms                                                                                                  | 131 ms: 1.97x slower                                                                                           |
| raytrace                         | 199 ms                                                                                                   | 401 ms: 2.02x slower                                                                                           |
| quadtree_nbody                   | 620 ms                                                                                                   | 1.36 sec: 2.19x slower                                                                                         |
| deltablue                        | 2.52 ms                                                                                                  | 5.75 ms: 2.29x slower                                                                                          |
| scimark_lu                       | 70.2 ms                                                                                                  | 170 ms: 2.42x slower                                                                                           |
| unpack_sequence                  | 26.2 ns                                                                                                  | 79.8 ns: 3.04x slower                                                                                          |
| thread_montecarlo_naive          | 17.8 ms                                                                                                  | 60.8 ms: 3.40x slower                                                                                          |
| Geometric mean                   | (ref)                                                                                                    | 1.22x slower                                                                                                   |

Benchmark hidden because not significant (4): async_tree_io, xml_etree_iterparse, regex_effbot, async_tree_cpu_io_mixed_tg

- Geometric mean (including insignificant results): 1.179x slower

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.18x
- 95% likely to have a slowdown of 1.17x
- 99% likely to have a slowdown of 1.15x

# Memory
- memory change: 1.45x