# Sparse Convolutions on Continuous Domains

This repository provides instructions on running experiments for the paper _Sparse Convolutions on Continuous Domains forPoint Cloud and Event Stream Networks_ (ACCV 2020).

The paper investigates two applications based on the same theoretical convolution operator. These are implemented in separate repositories. See the respective `README`s for instructions on installation / experimentation details.

- Point Cloud Networks: [pcn](https://github.com/jackd/pcn.git)
- Event Cloud Networks: [ecn](https://github.com/jackd/ecn.git)

## Project Dependencies

To assist code reuse, this project has been broken into many sub-repositories.

- shared dependencies:
  - [kblocks](https://github.com/jackd/kblocks): dependency-injectable keras blocks
  - [meta-model](https://github.com/jackd/meta-model): framework for building multiple networks simultaneously for models with architecture-dependent data pipelining
  - [tfrng](https://github.com/jackd/tfrng): a uniform interface for tensorflow random number generation implementations and custom dataset map implementation
  - [wtftf](https://github.com/jackd/wtftf): keras layer wrappers that will be removed once a stable tensorflow 2.4 is released
- Point convolution specific:
  - [pcn](https://github.com/jackd/pcn): point cloud convolution implementations and training configs
  - [numba-neighbors](https://github.com/jackd/numba-neighbors): optimized nearest-neighbors implementations with [numba](https://numba.pydata.org/)
  - [shape-tfds](https://github.com/jackd/shape-tfds): [tensorflow-datasets](https://github.com/tensorflow/datasets) implementations of various shape datasets
- Event convolution specific:
  - [ecn](https://github.com/jackd/ecn): event convolution implementations and training configs
  - [numba-stream](https://github.com/jackd/numba-stream): optimized implementations of event stream preprocessing operations with [numba](https://numba.pydata.org/)
  - [events-tfds](https://github.com/jackd/events-tfds): [tensorflow-datasets](https://github.com/tensorflow/datasets) implementations of various shape datasets
