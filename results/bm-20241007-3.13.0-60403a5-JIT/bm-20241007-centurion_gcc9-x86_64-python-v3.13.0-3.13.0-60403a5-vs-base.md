# Results vs. base

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.005x slower
- HPT reliability: 90.37%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.07x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                                                                 | 10.2 ms: 1.03x slower                                                                                       |
| docutils       | 1.89 sec                                                                                                | 2.00 sec: 1.06x slower                                                                                      |
| fastapi_http   | 218 ms                                                                                                  | 219 ms: 1.01x slower                                                                                        |
| tornado_http   | 101 ms                                                                                                  | 104 ms: 1.03x slower                                                                                        |
| Geometric mean | (ref)                                                                                                   | 1.03x slower                                                                                                |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| asyncio_tcp                      | 318 ms                                                                                                  | 302 ms: 1.05x faster                                                                                        |
| asyncio_websockets               | 303 ms                                                                                                  | 296 ms: 1.02x faster                                                                                        |
| async_tree_cpu_io_mixed          | 474 ms                                                                                                  | 477 ms: 1.01x slower                                                                                        |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                                                                  | 287 ms: 1.01x slower                                                                                        |
| async_tree_memoization_tg        | 419 ms                                                                                                  | 423 ms: 1.01x slower                                                                                        |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                | 1.30 sec: 1.01x slower                                                                                      |
| coroutines                       | 15.4 ms                                                                                                 | 15.5 ms: 1.01x slower                                                                                       |
| async_tree_eager_memoization_tg  | 175 ms                                                                                                  | 178 ms: 1.01x slower                                                                                        |
| async_tree_eager_tg              | 58.6 ms                                                                                                 | 59.5 ms: 1.02x slower                                                                                       |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                                                                  | 328 ms: 1.02x slower                                                                                        |
| async_tree_none_tg               | 291 ms                                                                                                  | 296 ms: 1.02x slower                                                                                        |
| async_tree_eager_memoization     | 219 ms                                                                                                  | 224 ms: 1.02x slower                                                                                        |
| async_tree_eager                 | 89.6 ms                                                                                                 | 94.4 ms: 1.05x slower                                                                                       |
| async_generators                 | 240 ms                                                                                                  | 260 ms: 1.08x slower                                                                                        |
| Geometric mean                   | (ref)                                                                                                   | 1.01x slower                                                                                                |

Benchmark hidden because not significant (7): async_tree_eager_io_tg, async_tree_cpu_io_mixed_tg, async_tree_none, async_tree_eager_io, async_tree_io_tg, async_tree_io, async_tree_memoization

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| noop      | 20.5 ns                                                                                                 | 18.3 ns: 1.12x faster                                                                                       |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                                                                  | 204 ms: 1.09x faster                                                                                        |
| decimal_factorial | 177 ms                                                                                                  | 178 ms: 1.01x slower                                                                                        |
| Geometric mean    | (ref)                                                                                                   | 1.04x faster                                                                                                |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| quadtree_nbody | 626 ms                                                                                                  | 570 ms: 1.10x faster                                                                                        |
| float          | 57.0 ms                                                                                                 | 53.5 ms: 1.06x faster                                                                                       |
| nbody          | 65.9 ms                                                                                                 | 62.5 ms: 1.05x faster                                                                                       |
| pidigits       | 189 ms                                                                                                  | 188 ms: 1.00x faster                                                                                        |
| Geometric mean | (ref)                                                                                                   | 1.06x faster                                                                                                |

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| regex_v8       | 15.2 ms                                                                                                 | 14.5 ms: 1.05x faster                                                                                       |
| regex_dna      | 162 ms                                                                                                  | 159 ms: 1.02x faster                                                                                        |
| regex_compile  | 98.5 ms                                                                                                 | 98.8 ms: 1.00x slower                                                                                       |
| Geometric mean | (ref)                                                                                                   | 1.02x faster                                                                                                |

Benchmark hidden because not significant (1): regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| ascii85_large        | 717 ms                                                                                                  | 548 ms: 1.31x faster                                                                                        |
| ascii85_small        | 13.6 ms                                                                                                 | 10.9 ms: 1.25x faster                                                                                       |
| tomli_loads          | 1.62 sec                                                                                                | 1.44 sec: 1.12x faster                                                                                      |
| base85_large         | 252 ms                                                                                                  | 227 ms: 1.11x faster                                                                                        |
| base85_small         | 4.59 ms                                                                                                 | 4.19 ms: 1.10x faster                                                                                       |
| xml_etree_generate   | 64.2 ms                                                                                                 | 60.8 ms: 1.06x faster                                                                                       |
| base32_large         | 296 ms                                                                                                  | 281 ms: 1.05x faster                                                                                        |
| unpickle_pure_python | 151 us                                                                                                  | 143 us: 1.05x faster                                                                                        |
| pickle_list          | 3.14 us                                                                                                 | 3.02 us: 1.04x faster                                                                                       |
| xml_etree_iterparse  | 79.9 ms                                                                                                 | 77.8 ms: 1.03x faster                                                                                       |
| unpickle             | 10.5 us                                                                                                 | 10.3 us: 1.02x faster                                                                                       |
| base32_small         | 5.79 ms                                                                                                 | 5.68 ms: 1.02x faster                                                                                       |
| xml_etree_parse      | 104 ms                                                                                                  | 102 ms: 1.02x faster                                                                                        |
| xml_etree_process    | 46.6 ms                                                                                                 | 45.8 ms: 1.02x faster                                                                                       |
| json_loads           | 16.2 us                                                                                                 | 15.9 us: 1.02x faster                                                                                       |
| pickle_pure_python   | 223 us                                                                                                  | 219 us: 1.02x faster                                                                                        |
| json_dumps           | 6.95 ms                                                                                                 | 6.85 ms: 1.01x faster                                                                                       |
| pickle_dict          | 22.0 us                                                                                                 | 21.8 us: 1.01x faster                                                                                       |
| unpickle_list        | 3.33 us                                                                                                 | 3.31 us: 1.01x faster                                                                                       |
| pickle               | 7.44 us                                                                                                 | 7.38 us: 1.01x faster                                                                                       |
| base64_large         | 3.33 ms                                                                                                 | 3.33 ms: 1.00x faster                                                                                       |
| base16_large         | 37.0 ms                                                                                                 | 37.3 ms: 1.01x slower                                                                                       |
| urlsafe_base64_small | 325 us                                                                                                  | 329 us: 1.01x slower                                                                                        |
| base16_small         | 740 us                                                                                                  | 754 us: 1.02x slower                                                                                        |
| base64_small         | 177 us                                                                                                  | 181 us: 1.02x slower                                                                                        |
| Geometric mean       | (ref)                                                                                                   | 1.05x faster                                                                                                |

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                                                                 | 10.3 ms: 1.08x slower                                                                                       |
| python_startup_no_site | 6.46 ms                                                                                                 | 7.28 ms: 1.13x slower                                                                                       |
| Geometric mean         | (ref)                                                                                                   | 1.10x slower                                                                                                |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| mako            | 7.16 ms                                                                                                 | 5.98 ms: 1.20x faster                                                                                       |
| django_template | 27.6 ms                                                                                                 | 30.2 ms: 1.09x slower                                                                                       |
| genshi_text     | 17.8 ms                                                                                                 | 21.7 ms: 1.22x slower                                                                                       |
| genshi_xml      | 41.3 ms                                                                                                 | 51.2 ms: 1.24x slower                                                                                       |
| Geometric mean  | (ref)                                                                                                   | 1.08x slower                                                                                                |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|-----------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| thread_montecarlo_optimized | 14.5 ms                                                                                                 | 12.5 ms: 1.16x faster                                                                                       |
| thread_mandelbrot_naive     | 210 ms                                                                                                  | 184 ms: 1.14x faster                                                                                        |
| thread_mandelbrot_optimized | 208 ms                                                                                                  | 184 ms: 1.13x faster                                                                                        |
| thread_memo_optimized       | 15.3 ms                                                                                                 | 13.8 ms: 1.10x faster                                                                                       |
| thread_accumulate_optimized | 32.3 ms                                                                                                 | 29.8 ms: 1.08x faster                                                                                       |
| thread_accumulate_naive     | 33.4 ms                                                                                                 | 30.9 ms: 1.08x faster                                                                                       |
| thread_counter_optimized    | 16.5 ms                                                                                                 | 15.3 ms: 1.08x faster                                                                                       |
| thread_pipeline_optimized   | 20.9 ms                                                                                                 | 19.4 ms: 1.07x faster                                                                                       |
| thread_counter_naive        | 20.6 ms                                                                                                 | 19.8 ms: 1.04x faster                                                                                       |
| thread_memo_naive           | 36.1 ms                                                                                                 | 37.7 ms: 1.05x slower                                                                                       |
| thread_montecarlo_naive     | 19.0 ms                                                                                                 | 20.1 ms: 1.06x slower                                                                                       |
| Geometric mean              | (ref)                                                                                                   | 1.06x faster                                                                                                |

Benchmark hidden because not significant (1): thread_pipeline_naive

All benchmarks:
===============

| Benchmark                        | results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json | results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json |
|----------------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| ascii85_large                    | 717 ms                                                                                                  | 548 ms: 1.31x faster                                                                                        |
| ascii85_small                    | 13.6 ms                                                                                                 | 10.9 ms: 1.25x faster                                                                                       |
| scimark_fft                      | 226 ms                                                                                                  | 181 ms: 1.25x faster                                                                                        |
| mako                             | 7.16 ms                                                                                                 | 5.98 ms: 1.20x faster                                                                                       |
| fannkuch                         | 246 ms                                                                                                  | 207 ms: 1.19x faster                                                                                        |
| richards                         | 37.8 ms                                                                                                 | 32.4 ms: 1.17x faster                                                                                       |
| thread_montecarlo_optimized      | 14.5 ms                                                                                                 | 12.5 ms: 1.16x faster                                                                                       |
| thread_mandelbrot_naive          | 210 ms                                                                                                  | 184 ms: 1.14x faster                                                                                        |
| scimark_monte_carlo              | 46.5 ms                                                                                                 | 41.0 ms: 1.14x faster                                                                                       |
| thread_mandelbrot_optimized      | 208 ms                                                                                                  | 184 ms: 1.13x faster                                                                                        |
| tomli_loads                      | 1.62 sec                                                                                                | 1.44 sec: 1.12x faster                                                                                      |
| spectral_norm                    | 65.9 ms                                                                                                 | 58.7 ms: 1.12x faster                                                                                       |
| deepcopy_memo                    | 26.5 us                                                                                                 | 23.6 us: 1.12x faster                                                                                       |
| scimark_sparse_mat_mult          | 3.14 ms                                                                                                 | 2.81 ms: 1.12x faster                                                                                       |
| noop                             | 20.5 ns                                                                                                 | 18.3 ns: 1.12x faster                                                                                       |
| richards_super                   | 42.8 ms                                                                                                 | 38.6 ms: 1.11x faster                                                                                       |
| base85_large                     | 252 ms                                                                                                  | 227 ms: 1.11x faster                                                                                        |
| thread_memo_optimized            | 15.3 ms                                                                                                 | 13.8 ms: 1.10x faster                                                                                       |
| quadtree_nbody                   | 626 ms                                                                                                  | 570 ms: 1.10x faster                                                                                        |
| base85_small                     | 4.59 ms                                                                                                 | 4.19 ms: 1.10x faster                                                                                       |
| decimal_pi                       | 222 ms                                                                                                  | 204 ms: 1.09x faster                                                                                        |
| thread_accumulate_optimized      | 32.3 ms                                                                                                 | 29.8 ms: 1.08x faster                                                                                       |
| json                             | 3.51 ms                                                                                                 | 3.24 ms: 1.08x faster                                                                                       |
| thread_accumulate_naive          | 33.4 ms                                                                                                 | 30.9 ms: 1.08x faster                                                                                       |
| thread_counter_optimized         | 16.5 ms                                                                                                 | 15.3 ms: 1.08x faster                                                                                       |
| thread_pipeline_optimized        | 20.9 ms                                                                                                 | 19.4 ms: 1.07x faster                                                                                       |
| crypto_pyaes                     | 50.9 ms                                                                                                 | 47.7 ms: 1.07x faster                                                                                       |
| float                            | 57.0 ms                                                                                                 | 53.5 ms: 1.06x faster                                                                                       |
| pyflate                          | 342 ms                                                                                                  | 321 ms: 1.06x faster                                                                                        |
| xml_etree_generate               | 64.2 ms                                                                                                 | 60.8 ms: 1.06x faster                                                                                       |
| nbody                            | 65.9 ms                                                                                                 | 62.5 ms: 1.05x faster                                                                                       |
| telco                            | 5.83 ms                                                                                                 | 5.53 ms: 1.05x faster                                                                                       |
| base32_large                     | 296 ms                                                                                                  | 281 ms: 1.05x faster                                                                                        |
| asyncio_tcp                      | 318 ms                                                                                                  | 302 ms: 1.05x faster                                                                                        |
| unpickle_pure_python             | 151 us                                                                                                  | 143 us: 1.05x faster                                                                                        |
| regex_v8                         | 15.2 ms                                                                                                 | 14.5 ms: 1.05x faster                                                                                       |
| pickle_list                      | 3.14 us                                                                                                 | 3.02 us: 1.04x faster                                                                                       |
| thread_counter_naive             | 20.6 ms                                                                                                 | 19.8 ms: 1.04x faster                                                                                       |
| networkx_shortest_path           | 437 ms                                                                                                  | 423 ms: 1.03x faster                                                                                        |
| networkx_connected_components    | 425 ms                                                                                                  | 412 ms: 1.03x faster                                                                                        |
| xml_etree_iterparse              | 79.9 ms                                                                                                 | 77.8 ms: 1.03x faster                                                                                       |
| asyncio_websockets               | 303 ms                                                                                                  | 296 ms: 1.02x faster                                                                                        |
| deepcopy                         | 269 us                                                                                                  | 263 us: 1.02x faster                                                                                        |
| networkx_k_core                  | 2.16 sec                                                                                                | 2.11 sec: 1.02x faster                                                                                      |
| regex_dna                        | 162 ms                                                                                                  | 159 ms: 1.02x faster                                                                                        |
| unpickle                         | 10.5 us                                                                                                 | 10.3 us: 1.02x faster                                                                                       |
| base32_small                     | 5.79 ms                                                                                                 | 5.68 ms: 1.02x faster                                                                                       |
| deepcopy_reduce                  | 2.40 us                                                                                                 | 2.36 us: 1.02x faster                                                                                       |
| xml_etree_parse                  | 104 ms                                                                                                  | 102 ms: 1.02x faster                                                                                        |
| xml_etree_process                | 46.6 ms                                                                                                 | 45.8 ms: 1.02x faster                                                                                       |
| json_loads                       | 16.2 us                                                                                                 | 15.9 us: 1.02x faster                                                                                       |
| pickle_pure_python               | 223 us                                                                                                  | 219 us: 1.02x faster                                                                                        |
| json_dumps                       | 6.95 ms                                                                                                 | 6.85 ms: 1.01x faster                                                                                       |
| pickle_dict                      | 22.0 us                                                                                                 | 21.8 us: 1.01x faster                                                                                       |
| meteor_contest                   | 84.4 ms                                                                                                 | 83.7 ms: 1.01x faster                                                                                       |
| unpickle_list                    | 3.33 us                                                                                                 | 3.31 us: 1.01x faster                                                                                       |
| pickle                           | 7.44 us                                                                                                 | 7.38 us: 1.01x faster                                                                                       |
| pidigits                         | 189 ms                                                                                                  | 188 ms: 1.00x faster                                                                                        |
| base64_large                     | 3.33 ms                                                                                                 | 3.33 ms: 1.00x faster                                                                                       |
| regex_compile                    | 98.5 ms                                                                                                 | 98.8 ms: 1.00x slower                                                                                       |
| fastapi_http                     | 218 ms                                                                                                  | 219 ms: 1.01x slower                                                                                        |
| async_tree_cpu_io_mixed          | 474 ms                                                                                                  | 477 ms: 1.01x slower                                                                                        |
| gc_traversal                     | 3.07 ms                                                                                                 | 3.09 ms: 1.01x slower                                                                                       |
| sqlglot_v2_parse                 | 958 us                                                                                                  | 965 us: 1.01x slower                                                                                        |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                                                                  | 287 ms: 1.01x slower                                                                                        |
| base16_large                     | 37.0 ms                                                                                                 | 37.3 ms: 1.01x slower                                                                                       |
| decimal_factorial                | 177 ms                                                                                                  | 178 ms: 1.01x slower                                                                                        |
| async_tree_memoization_tg        | 419 ms                                                                                                  | 423 ms: 1.01x slower                                                                                        |
| asyncio_tcp_ssl                  | 1.29 sec                                                                                                | 1.30 sec: 1.01x slower                                                                                      |
| go                               | 117 ms                                                                                                  | 118 ms: 1.01x slower                                                                                        |
| coroutines                       | 15.4 ms                                                                                                 | 15.5 ms: 1.01x slower                                                                                       |
| bpe_tokeniser                    | 3.30 sec                                                                                                | 3.33 sec: 1.01x slower                                                                                      |
| urlsafe_base64_small             | 325 us                                                                                                  | 329 us: 1.01x slower                                                                                        |
| async_tree_eager_memoization_tg  | 175 ms                                                                                                  | 178 ms: 1.01x slower                                                                                        |
| async_tree_eager_tg              | 58.6 ms                                                                                                 | 59.5 ms: 1.02x slower                                                                                       |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                                                                  | 328 ms: 1.02x slower                                                                                        |
| create_gc_cycles                 | 1.75 ms                                                                                                 | 1.78 ms: 1.02x slower                                                                                       |
| base16_small                     | 740 us                                                                                                  | 754 us: 1.02x slower                                                                                        |
| async_tree_none_tg               | 291 ms                                                                                                  | 296 ms: 1.02x slower                                                                                        |
| base64_small                     | 177 us                                                                                                  | 181 us: 1.02x slower                                                                                        |
| logging_simple                   | 4.71 us                                                                                                 | 4.82 us: 1.02x slower                                                                                       |
| logging_format                   | 5.25 us                                                                                                 | 5.37 us: 1.02x slower                                                                                       |
| sqlglot_v2_transpile             | 1.20 ms                                                                                                 | 1.23 ms: 1.02x slower                                                                                       |
| async_tree_eager_memoization     | 219 ms                                                                                                  | 224 ms: 1.02x slower                                                                                        |
| argparse_many_optionals          | 12.8 ms                                                                                                 | 13.1 ms: 1.03x slower                                                                                       |
| chameleon                        | 9.95 ms                                                                                                 | 10.2 ms: 1.03x slower                                                                                       |
| logging_silent                   | 61.0 ns                                                                                                 | 62.8 ns: 1.03x slower                                                                                       |
| tornado_http                     | 101 ms                                                                                                  | 104 ms: 1.03x slower                                                                                        |
| chaos                            | 45.1 ms                                                                                                 | 46.6 ms: 1.03x slower                                                                                       |
| pycparser                        | 860 ms                                                                                                  | 888 ms: 1.03x slower                                                                                        |
| sqlalchemy_imperative            | 13.9 ms                                                                                                 | 14.4 ms: 1.03x slower                                                                                       |
| pathlib                          | 12.8 ms                                                                                                 | 13.3 ms: 1.04x slower                                                                                       |
| thread_memo_naive                | 36.1 ms                                                                                                 | 37.7 ms: 1.05x slower                                                                                       |
| generators                       | 21.2 ms                                                                                                 | 22.3 ms: 1.05x slower                                                                                       |
| async_tree_eager                 | 89.6 ms                                                                                                 | 94.4 ms: 1.05x slower                                                                                       |
| comprehensions                   | 10.9 us                                                                                                 | 11.5 us: 1.06x slower                                                                                       |
| xdsl_constant_fold               | 36.7 ms                                                                                                 | 38.8 ms: 1.06x slower                                                                                       |
| thread_montecarlo_naive          | 19.0 ms                                                                                                 | 20.1 ms: 1.06x slower                                                                                       |
| argparse_subparsers              | 452 us                                                                                                  | 478 us: 1.06x slower                                                                                        |
| docutils                         | 1.89 sec                                                                                                | 2.00 sec: 1.06x slower                                                                                      |
| raytrace                         | 195 ms                                                                                                  | 207 ms: 1.06x slower                                                                                        |
| sqlglot_v2_optimize              | 40.1 ms                                                                                                 | 42.6 ms: 1.06x slower                                                                                       |
| sympy_str                        | 197 ms                                                                                                  | 210 ms: 1.07x slower                                                                                        |
| typing_runtime_protocols         | 113 us                                                                                                  | 121 us: 1.07x slower                                                                                        |
| sympy_sum                        | 106 ms                                                                                                  | 114 ms: 1.07x slower                                                                                        |
| coverage                         | 55.8 ms                                                                                                 | 59.9 ms: 1.07x slower                                                                                       |
| sympy_expand                     | 336 ms                                                                                                  | 363 ms: 1.08x slower                                                                                        |
| python_startup                   | 9.51 ms                                                                                                 | 10.3 ms: 1.08x slower                                                                                       |
| pprint_pformat                   | 1.09 sec                                                                                                | 1.18 sec: 1.08x slower                                                                                      |
| async_generators                 | 240 ms                                                                                                  | 260 ms: 1.08x slower                                                                                        |
| pprint_safe_repr                 | 530 ms                                                                                                  | 574 ms: 1.08x slower                                                                                        |
| django_template                  | 27.6 ms                                                                                                 | 30.2 ms: 1.09x slower                                                                                       |
| hexiom                           | 4.30 ms                                                                                                 | 4.72 ms: 1.10x slower                                                                                       |
| sympy_integrate                  | 15.8 ms                                                                                                 | 17.4 ms: 1.10x slower                                                                                       |
| sqlglot_v2_normalize             | 80.5 ms                                                                                                 | 89.1 ms: 1.11x slower                                                                                       |
| mypy2                            | 724 ms                                                                                                  | 806 ms: 1.11x slower                                                                                        |
| thrift                           | 2.02 ms                                                                                                 | 2.26 ms: 1.12x slower                                                                                       |
| pylint                           | 227 ms                                                                                                  | 255 ms: 1.13x slower                                                                                        |
| python_startup_no_site           | 6.46 ms                                                                                                 | 7.28 ms: 1.13x slower                                                                                       |
| deltablue                        | 2.41 ms                                                                                                 | 2.80 ms: 1.17x slower                                                                                       |
| nqueens                          | 53.6 ms                                                                                                 | 62.6 ms: 1.17x slower                                                                                       |
| genshi_text                      | 17.8 ms                                                                                                 | 21.7 ms: 1.22x slower                                                                                       |
| genshi_xml                       | 41.3 ms                                                                                                 | 51.2 ms: 1.24x slower                                                                                       |
| scimark_sor                      | 78.9 ms                                                                                                 | 101 ms: 1.28x slower                                                                                        |
| scimark_lu                       | 74.5 ms                                                                                                 | 98.5 ms: 1.32x slower                                                                                       |
| unpack_sequence                  | 27.1 ns                                                                                                 | 80.9 ns: 2.99x slower                                                                                       |
| Geometric mean                   | (ref)                                                                                                   | 1.01x slower                                                                                                |

Benchmark hidden because not significant (11): regex_effbot, mdp, async_tree_eager_io_tg, async_tree_cpu_io_mixed_tg, async_tree_none, async_tree_eager_io, async_tree_io_tg, async_tree_io, async_tree_memoization, html5lib, thread_pipeline_naive

- Geometric mean (including insignificant results): 1.005x slower

# HPT report

- Reliability score: 90.37% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.07x