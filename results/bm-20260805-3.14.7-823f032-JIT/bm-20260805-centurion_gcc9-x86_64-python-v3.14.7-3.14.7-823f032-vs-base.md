# Results vs. base

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.000x faster
- HPT reliability: 85.84%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| chameleon      | 10.00 ms                                                                                                | 10.1 ms: 1.01x slower                                                                                       |
| docutils       | 1.88 sec                                                                                                | 1.94 sec: 1.03x slower                                                                                      |
| fastapi_http   | 219 ms                                                                                                  | 212 ms: 1.03x faster                                                                                        |
| tornado_http   | 102 ms                                                                                                  | 104 ms: 1.03x slower                                                                                        |
| Geometric mean | (ref)                                                                                                   | 1.00x slower                                                                                                |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                     | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-------------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| asyncio_tcp                   | 314 ms                                                                                                  | 297 ms: 1.06x faster                                                                                        |
| async_tree_memoization        | 345 ms                                                                                                  | 333 ms: 1.04x faster                                                                                        |
| async_tree_cpu_io_mixed_tg    | 468 ms                                                                                                  | 457 ms: 1.02x faster                                                                                        |
| async_tree_eager_tg           | 212 ms                                                                                                  | 207 ms: 1.02x faster                                                                                        |
| async_tree_eager_cpu_io_mixed | 314 ms                                                                                                  | 320 ms: 1.02x slower                                                                                        |
| async_tree_io                 | 668 ms                                                                                                  | 686 ms: 1.03x slower                                                                                        |
| async_tree_eager              | 83.2 ms                                                                                                 | 85.9 ms: 1.03x slower                                                                                       |
| async_tree_eager_memoization  | 189 ms                                                                                                  | 197 ms: 1.04x slower                                                                                        |
| coroutines                    | 15.6 ms                                                                                                 | 16.4 ms: 1.05x slower                                                                                       |
| async_generators              | 235 ms                                                                                                  | 257 ms: 1.09x slower                                                                                        |
| Geometric mean                | (ref)                                                                                                   | 1.00x slower                                                                                                |

Benchmark hidden because not significant (11): async_tree_eager_io_tg, async_tree_none_tg, async_tree_eager_memoization_tg, async_tree_io_tg, async_tree_cpu_io_mixed, asyncio_websockets, async_tree_none, async_tree_eager_io, asyncio_tcp_ssl, async_tree_eager_cpu_io_mixed_tg, async_tree_memoization_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| noop      | 20.4 ns                                                                                                 | 16.8 ns: 1.21x faster                                                                                       |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| decimal_pi        | 214 ms                                                                                                  | 204 ms: 1.05x faster                                                                                        |
| decimal_factorial | 174 ms                                                                                                  | 175 ms: 1.00x slower                                                                                        |
| Geometric mean    | (ref)                                                                                                   | 1.02x faster                                                                                                |

Benchmarks with tag 'math':
===========================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| float          | 50.7 ms                                                                                                 | 42.1 ms: 1.21x faster                                                                                       |
| quadtree_nbody | 612 ms                                                                                                  | 592 ms: 1.03x faster                                                                                        |
| pidigits       | 188 ms                                                                                                  | 187 ms: 1.00x faster                                                                                        |
| Geometric mean | (ref)                                                                                                   | 1.06x faster                                                                                                |

Benchmark hidden because not significant (1): nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| regex_v8       | 16.2 ms                                                                                                 | 14.9 ms: 1.08x faster                                                                                       |
| regex_compile  | 95.4 ms                                                                                                 | 95.2 ms: 1.00x faster                                                                                       |
| regex_dna      | 152 ms                                                                                                  | 153 ms: 1.00x slower                                                                                        |
| regex_effbot   | 1.99 ms                                                                                                 | 2.09 ms: 1.05x slower                                                                                       |
| Geometric mean | (ref)                                                                                                   | 1.01x faster                                                                                                |

Benchmarks with tag 'serialize':
================================

| Benchmark            | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|----------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| unpickle_pure_python | 155 us                                                                                                  | 134 us: 1.16x faster                                                                                        |
| ascii85_large        | 695 ms                                                                                                  | 613 ms: 1.13x faster                                                                                        |
| ascii85_small        | 13.3 ms                                                                                                 | 12.2 ms: 1.09x faster                                                                                       |
| xml_etree_generate   | 63.4 ms                                                                                                 | 58.5 ms: 1.08x faster                                                                                       |
| tomli_loads          | 1.53 sec                                                                                                | 1.42 sec: 1.08x faster                                                                                      |
| xml_etree_process    | 45.8 ms                                                                                                 | 42.9 ms: 1.07x faster                                                                                       |
| base85_small         | 4.83 ms                                                                                                 | 4.51 ms: 1.07x faster                                                                                       |
| base85_large         | 255 ms                                                                                                  | 242 ms: 1.05x faster                                                                                        |
| pickle_list          | 2.86 us                                                                                                 | 2.79 us: 1.03x faster                                                                                       |
| base32_large         | 306 ms                                                                                                  | 298 ms: 1.02x faster                                                                                        |
| base32_small         | 6.00 ms                                                                                                 | 5.90 ms: 1.02x faster                                                                                       |
| base16_large         | 5.34 ms                                                                                                 | 5.25 ms: 1.02x faster                                                                                       |
| unpickle_list        | 3.54 us                                                                                                 | 3.51 us: 1.01x faster                                                                                       |
| urlsafe_base64_small | 327 us                                                                                                  | 325 us: 1.01x faster                                                                                        |
| base64_large         | 3.32 ms                                                                                                 | 3.31 ms: 1.00x faster                                                                                       |
| json_loads           | 19.5 us                                                                                                 | 19.6 us: 1.01x slower                                                                                       |
| base16_small         | 307 us                                                                                                  | 310 us: 1.01x slower                                                                                        |
| pickle               | 8.29 us                                                                                                 | 8.38 us: 1.01x slower                                                                                       |
| pickle_dict          | 21.2 us                                                                                                 | 21.5 us: 1.01x slower                                                                                       |
| unpickle             | 10.5 us                                                                                                 | 10.7 us: 1.02x slower                                                                                       |
| xml_etree_parse      | 110 ms                                                                                                  | 112 ms: 1.02x slower                                                                                        |
| base64_small         | 175 us                                                                                                  | 179 us: 1.02x slower                                                                                        |
| json_dumps           | 7.11 ms                                                                                                 | 7.28 ms: 1.02x slower                                                                                       |
| pickle_pure_python   | 240 us                                                                                                  | 247 us: 1.03x slower                                                                                        |
| Geometric mean       | (ref)                                                                                                   | 1.03x faster                                                                                                |

Benchmark hidden because not significant (1): xml_etree_iterparse

Benchmarks with tag 'startup':
==============================

| Benchmark              | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| python_startup         | 9.90 ms                                                                                                 | 9.96 ms: 1.01x slower                                                                                       |
| python_startup_no_site | 6.45 ms                                                                                                 | 6.49 ms: 1.01x slower                                                                                       |
| Geometric mean         | (ref)                                                                                                   | 1.01x slower                                                                                                |

Benchmarks with tag 'template':
===============================

| Benchmark       | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| mako            | 7.57 ms                                                                                                 | 6.48 ms: 1.17x faster                                                                                       |
| django_template | 28.2 ms                                                                                                 | 28.5 ms: 1.01x slower                                                                                       |
| genshi_xml      | 40.4 ms                                                                                                 | 41.7 ms: 1.03x slower                                                                                       |
| Geometric mean  | (ref)                                                                                                   | 1.03x faster                                                                                                |

Benchmark hidden because not significant (1): genshi_text

Benchmarks with tag 'threads':
==============================

| Benchmark                   | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-----------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| thread_accumulate_optimized | 37.1 ms                                                                                                 | 32.7 ms: 1.13x faster                                                                                       |
| thread_mandelbrot_naive     | 237 ms                                                                                                  | 211 ms: 1.12x faster                                                                                        |
| thread_accumulate_naive     | 37.2 ms                                                                                                 | 33.3 ms: 1.12x faster                                                                                       |
| thread_pipeline_optimized   | 23.4 ms                                                                                                 | 21.0 ms: 1.11x faster                                                                                       |
| thread_mandelbrot_optimized | 235 ms                                                                                                  | 212 ms: 1.11x faster                                                                                        |
| thread_memo_optimized       | 16.5 ms                                                                                                 | 15.0 ms: 1.10x faster                                                                                       |
| thread_memo_naive           | 11.7 ms                                                                                                 | 10.8 ms: 1.09x faster                                                                                       |
| thread_montecarlo_optimized | 15.3 ms                                                                                                 | 14.4 ms: 1.07x faster                                                                                       |
| thread_pipeline_naive       | 32.8 ms                                                                                                 | 30.7 ms: 1.07x faster                                                                                       |
| thread_counter_optimized    | 17.8 ms                                                                                                 | 16.7 ms: 1.07x faster                                                                                       |
| thread_counter_naive        | 20.9 ms                                                                                                 | 20.3 ms: 1.03x faster                                                                                       |
| thread_montecarlo_naive     | 17.5 ms                                                                                                 | 19.7 ms: 1.13x slower                                                                                       |
| Geometric mean              | (ref)                                                                                                   | 1.07x faster                                                                                                |

All benchmarks:
===============

| Benchmark                     | results/bm-20260805-3.14.7-823f032/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json | results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json |
|-------------------------------|:-------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|
| scimark_fft                   | 237 ms                                                                                                  | 186 ms: 1.27x faster                                                                                        |
| noop                          | 20.4 ns                                                                                                 | 16.8 ns: 1.21x faster                                                                                       |
| float                         | 50.7 ms                                                                                                 | 42.1 ms: 1.21x faster                                                                                       |
| spectral_norm                 | 67.7 ms                                                                                                 | 57.4 ms: 1.18x faster                                                                                       |
| richards                      | 32.4 ms                                                                                                 | 27.6 ms: 1.17x faster                                                                                       |
| mako                          | 7.57 ms                                                                                                 | 6.48 ms: 1.17x faster                                                                                       |
| deltablue                     | 2.39 ms                                                                                                 | 2.05 ms: 1.16x faster                                                                                       |
| unpickle_pure_python          | 155 us                                                                                                  | 134 us: 1.16x faster                                                                                        |
| scimark_sparse_mat_mult       | 3.37 ms                                                                                                 | 2.93 ms: 1.15x faster                                                                                       |
| richards_super                | 37.1 ms                                                                                                 | 32.2 ms: 1.15x faster                                                                                       |
| ascii85_large                 | 695 ms                                                                                                  | 613 ms: 1.13x faster                                                                                        |
| thread_accumulate_optimized   | 37.1 ms                                                                                                 | 32.7 ms: 1.13x faster                                                                                       |
| thread_mandelbrot_naive       | 237 ms                                                                                                  | 211 ms: 1.12x faster                                                                                        |
| thread_accumulate_naive       | 37.2 ms                                                                                                 | 33.3 ms: 1.12x faster                                                                                       |
| thread_pipeline_optimized     | 23.4 ms                                                                                                 | 21.0 ms: 1.11x faster                                                                                       |
| thread_mandelbrot_optimized   | 235 ms                                                                                                  | 212 ms: 1.11x faster                                                                                        |
| thread_memo_optimized         | 16.5 ms                                                                                                 | 15.0 ms: 1.10x faster                                                                                       |
| ascii85_small                 | 13.3 ms                                                                                                 | 12.2 ms: 1.09x faster                                                                                       |
| thread_memo_naive             | 11.7 ms                                                                                                 | 10.8 ms: 1.09x faster                                                                                       |
| xml_etree_generate            | 63.4 ms                                                                                                 | 58.5 ms: 1.08x faster                                                                                       |
| regex_v8                      | 16.2 ms                                                                                                 | 14.9 ms: 1.08x faster                                                                                       |
| tomli_loads                   | 1.53 sec                                                                                                | 1.42 sec: 1.08x faster                                                                                      |
| xml_etree_process             | 45.8 ms                                                                                                 | 42.9 ms: 1.07x faster                                                                                       |
| thread_montecarlo_optimized   | 15.3 ms                                                                                                 | 14.4 ms: 1.07x faster                                                                                       |
| base85_small                  | 4.83 ms                                                                                                 | 4.51 ms: 1.07x faster                                                                                       |
| thread_pipeline_naive         | 32.8 ms                                                                                                 | 30.7 ms: 1.07x faster                                                                                       |
| thread_counter_optimized      | 17.8 ms                                                                                                 | 16.7 ms: 1.07x faster                                                                                       |
| bpe_tokeniser                 | 3.15 sec                                                                                                | 2.98 sec: 1.06x faster                                                                                      |
| asyncio_tcp                   | 314 ms                                                                                                  | 297 ms: 1.06x faster                                                                                        |
| base85_large                  | 255 ms                                                                                                  | 242 ms: 1.05x faster                                                                                        |
| networkx_connected_components | 437 ms                                                                                                  | 416 ms: 1.05x faster                                                                                        |
| decimal_pi                    | 214 ms                                                                                                  | 204 ms: 1.05x faster                                                                                        |
| logging_silent                | 69.5 ns                                                                                                 | 66.4 ns: 1.05x faster                                                                                       |
| async_tree_memoization        | 345 ms                                                                                                  | 333 ms: 1.04x faster                                                                                        |
| fannkuch                      | 250 ms                                                                                                  | 242 ms: 1.04x faster                                                                                        |
| quadtree_nbody                | 612 ms                                                                                                  | 592 ms: 1.03x faster                                                                                        |
| fastapi_http                  | 219 ms                                                                                                  | 212 ms: 1.03x faster                                                                                        |
| networkx_shortest_path        | 446 ms                                                                                                  | 432 ms: 1.03x faster                                                                                        |
| thread_counter_naive          | 20.9 ms                                                                                                 | 20.3 ms: 1.03x faster                                                                                       |
| pickle_list                   | 2.86 us                                                                                                 | 2.79 us: 1.03x faster                                                                                       |
| base32_large                  | 306 ms                                                                                                  | 298 ms: 1.02x faster                                                                                        |
| async_tree_cpu_io_mixed_tg    | 468 ms                                                                                                  | 457 ms: 1.02x faster                                                                                        |
| async_tree_eager_tg           | 212 ms                                                                                                  | 207 ms: 1.02x faster                                                                                        |
| pyflate                       | 309 ms                                                                                                  | 303 ms: 1.02x faster                                                                                        |
| base32_small                  | 6.00 ms                                                                                                 | 5.90 ms: 1.02x faster                                                                                       |
| base16_large                  | 5.34 ms                                                                                                 | 5.25 ms: 1.02x faster                                                                                       |
| unpickle_list                 | 3.54 us                                                                                                 | 3.51 us: 1.01x faster                                                                                       |
| argparse_many_optionals       | 7.69 ms                                                                                                 | 7.62 ms: 1.01x faster                                                                                       |
| mdp                           | 961 ms                                                                                                  | 954 ms: 1.01x faster                                                                                        |
| urlsafe_base64_small          | 327 us                                                                                                  | 325 us: 1.01x faster                                                                                        |
| scimark_sor                   | 75.6 ms                                                                                                 | 75.3 ms: 1.00x faster                                                                                       |
| base64_large                  | 3.32 ms                                                                                                 | 3.31 ms: 1.00x faster                                                                                       |
| regex_compile                 | 95.4 ms                                                                                                 | 95.2 ms: 1.00x faster                                                                                       |
| pidigits                      | 188 ms                                                                                                  | 187 ms: 1.00x faster                                                                                        |
| meteor_contest                | 85.3 ms                                                                                                 | 85.5 ms: 1.00x slower                                                                                       |
| regex_dna                     | 152 ms                                                                                                  | 153 ms: 1.00x slower                                                                                        |
| decimal_factorial             | 174 ms                                                                                                  | 175 ms: 1.00x slower                                                                                        |
| sympy_sum                     | 108 ms                                                                                                  | 109 ms: 1.01x slower                                                                                        |
| python_startup                | 9.90 ms                                                                                                 | 9.96 ms: 1.01x slower                                                                                       |
| json_loads                    | 19.5 us                                                                                                 | 19.6 us: 1.01x slower                                                                                       |
| python_startup_no_site        | 6.45 ms                                                                                                 | 6.49 ms: 1.01x slower                                                                                       |
| deepcopy_memo                 | 18.3 us                                                                                                 | 18.4 us: 1.01x slower                                                                                       |
| base16_small                  | 307 us                                                                                                  | 310 us: 1.01x slower                                                                                        |
| django_template               | 28.2 ms                                                                                                 | 28.5 ms: 1.01x slower                                                                                       |
| create_gc_cycles              | 1.87 ms                                                                                                 | 1.89 ms: 1.01x slower                                                                                       |
| pickle                        | 8.29 us                                                                                                 | 8.38 us: 1.01x slower                                                                                       |
| pickle_dict                   | 21.2 us                                                                                                 | 21.5 us: 1.01x slower                                                                                       |
| deepcopy_reduce               | 2.01 us                                                                                                 | 2.03 us: 1.01x slower                                                                                       |
| chameleon                     | 10.00 ms                                                                                                | 10.1 ms: 1.01x slower                                                                                       |
| chaos                         | 44.6 ms                                                                                                 | 45.2 ms: 1.02x slower                                                                                       |
| pycparser                     | 897 ms                                                                                                  | 911 ms: 1.02x slower                                                                                        |
| unpickle                      | 10.5 us                                                                                                 | 10.7 us: 1.02x slower                                                                                       |
| async_tree_eager_cpu_io_mixed | 314 ms                                                                                                  | 320 ms: 1.02x slower                                                                                        |
| sympy_integrate               | 15.7 ms                                                                                                 | 16.0 ms: 1.02x slower                                                                                       |
| deepcopy                      | 193 us                                                                                                  | 197 us: 1.02x slower                                                                                        |
| xml_etree_parse               | 110 ms                                                                                                  | 112 ms: 1.02x slower                                                                                        |
| base64_small                  | 175 us                                                                                                  | 179 us: 1.02x slower                                                                                        |
| networkx_k_core               | 2.07 sec                                                                                                | 2.12 sec: 1.02x slower                                                                                      |
| json_dumps                    | 7.11 ms                                                                                                 | 7.28 ms: 1.02x slower                                                                                       |
| sympy_str                     | 198 ms                                                                                                  | 203 ms: 1.02x slower                                                                                        |
| tornado_http                  | 102 ms                                                                                                  | 104 ms: 1.03x slower                                                                                        |
| async_tree_io                 | 668 ms                                                                                                  | 686 ms: 1.03x slower                                                                                        |
| json                          | 3.69 ms                                                                                                 | 3.80 ms: 1.03x slower                                                                                       |
| raytrace                      | 197 ms                                                                                                  | 203 ms: 1.03x slower                                                                                        |
| pickle_pure_python            | 240 us                                                                                                  | 247 us: 1.03x slower                                                                                        |
| genshi_xml                    | 40.4 ms                                                                                                 | 41.7 ms: 1.03x slower                                                                                       |
| pylint                        | 224 ms                                                                                                  | 231 ms: 1.03x slower                                                                                        |
| async_tree_eager              | 83.2 ms                                                                                                 | 85.9 ms: 1.03x slower                                                                                       |
| thrift                        | 1.92 ms                                                                                                 | 1.99 ms: 1.03x slower                                                                                       |
| generators                    | 20.5 ms                                                                                                 | 21.2 ms: 1.03x slower                                                                                       |
| logging_simple                | 4.73 us                                                                                                 | 4.89 us: 1.03x slower                                                                                       |
| argparse_subparsers           | 501 us                                                                                                  | 518 us: 1.03x slower                                                                                        |
| docutils                      | 1.88 sec                                                                                                | 1.94 sec: 1.03x slower                                                                                      |
| coverage                      | 56.1 ms                                                                                                 | 58.0 ms: 1.03x slower                                                                                       |
| nqueens                       | 56.2 ms                                                                                                 | 58.2 ms: 1.04x slower                                                                                       |
| sympy_expand                  | 338 ms                                                                                                  | 350 ms: 1.04x slower                                                                                        |
| crypto_pyaes                  | 55.5 ms                                                                                                 | 57.6 ms: 1.04x slower                                                                                       |
| async_tree_eager_memoization  | 189 ms                                                                                                  | 197 ms: 1.04x slower                                                                                        |
| sqlalchemy_imperative         | 14.3 ms                                                                                                 | 14.9 ms: 1.04x slower                                                                                       |
| sqlglot_v2_parse              | 921 us                                                                                                  | 958 us: 1.04x slower                                                                                        |
| logging_format                | 5.24 us                                                                                                 | 5.45 us: 1.04x slower                                                                                       |
| sqlglot_v2_optimize           | 39.9 ms                                                                                                 | 41.7 ms: 1.05x slower                                                                                       |
| gc_traversal                  | 3.27 ms                                                                                                 | 3.43 ms: 1.05x slower                                                                                       |
| coroutines                    | 15.6 ms                                                                                                 | 16.4 ms: 1.05x slower                                                                                       |
| regex_effbot                  | 1.99 ms                                                                                                 | 2.09 ms: 1.05x slower                                                                                       |
| typing_runtime_protocols      | 113 us                                                                                                  | 119 us: 1.05x slower                                                                                        |
| sqlglot_v2_normalize          | 80.0 ms                                                                                                 | 84.5 ms: 1.06x slower                                                                                       |
| sqlglot_v2_transpile          | 1.16 ms                                                                                                 | 1.23 ms: 1.06x slower                                                                                       |
| hexiom                        | 4.21 ms                                                                                                 | 4.53 ms: 1.08x slower                                                                                       |
| comprehensions                | 11.1 us                                                                                                 | 12.0 us: 1.08x slower                                                                                       |
| async_generators              | 235 ms                                                                                                  | 257 ms: 1.09x slower                                                                                        |
| thread_montecarlo_naive       | 17.5 ms                                                                                                 | 19.7 ms: 1.13x slower                                                                                       |
| go                            | 85.8 ms                                                                                                 | 100 ms: 1.17x slower                                                                                        |
| pprint_pformat                | 1.03 sec                                                                                                | 1.28 sec: 1.24x slower                                                                                      |
| pprint_safe_repr              | 491 ms                                                                                                  | 632 ms: 1.29x slower                                                                                        |
| mypy2                         | 730 ms                                                                                                  | 1.06 sec: 1.46x slower                                                                                      |
| unpack_sequence               | 25.4 ns                                                                                                 | 103 ns: 4.06x slower                                                                                        |
| Geometric mean                | (ref)                                                                                                   | 1.00x slower                                                                                                |

Benchmark hidden because not significant (20): xdsl_constant_fold, async_tree_eager_io_tg, async_tree_none_tg, html5lib, async_tree_eager_memoization_tg, async_tree_io_tg, nbody, telco, async_tree_cpu_io_mixed, asyncio_websockets, async_tree_none, pathlib, async_tree_eager_io, asyncio_tcp_ssl, xml_etree_iterparse, scimark_lu, genshi_text, scimark_monte_carlo, async_tree_eager_cpu_io_mixed_tg, async_tree_memoization_tg

- Geometric mean (including insignificant results): 1.000x faster

# HPT report

- Reliability score: 85.84% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.01x