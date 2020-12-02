# Sparse Convolutions on Continuous Domains

This repository provides instructions on running experiments for the paper _Sparse Convolutions on Continuous Domains forPoint Cloud and Event Stream Networks_ (ACCV 2020).

- [ACCV 2020 Paper](paper)
- [Spotlight Video](https://youtu.be/OihcDbfT1ks) (1min)
- [Oral Presentation](https://youtu.be/26GDhWfU280) (9min)

```tex
@InProceedings{Jack_2020_ACCV,
    author    = {Jack, Dominic and Maire, Frederic and Denman, Simon and Eriksson, Anders},
    title     = {Sparse Convolutions on Continuous Domains for Point Cloud and Event Stream Networks},
    booktitle = {Proceedings of the Asian Conference on Computer Vision (ACCV)},
    month     = {November},
    year      = {2020}
}
```

The paper investigates two applications based on the same theoretical convolution operator. These are implemented in separate repositories. See the respective `README`s for instructions on installation / experimentation details.

- Point Cloud Networks: [pcn](pcn)
- Event Cloud Networks: [ecn](ecn)

[requirements.txt](requirements.txt) contains exact versions of packages to aid installation. For development, you may wish to clone the repositories and as below.

```bash
# shared pip dependencies
pip install tensorflow  # or tf-nightly
pip install absl-py gin-config setproctitle scipy uuid psutil pyyaml numba

# shared dependencies
git clone https://github.com/jackd/kblocks.git
git clone https://github.com/jackd/meta-model.git
git clone https://github.com/jackd/tfrng.git
git clone https://github.com/jackd/wtftf.git
pip install --no-deps -e kblocks
pip install -e meta-model
pip install -e tfrng
pip install -e wtftf

# for point cloud models
git clone https://github.com/jackd/pcn.git
git clone https://github.com/jackd/shape-tfds.git
git clone https://github.com/jackd/numba-neighbors.git
pip install --no-deps -e pcn
pip install -e shape-tfds
pip install -e numba-neighbors

# for event streams
git clone https://github.com/jackd/ecn.git
git clone https://github.com/jackd/events-tfds.git
git clone https://github.com/jackd/numba-stream.git
pip install --no-deps -e ecn
pip install -e events-tfds
pip install -e numba-stream
```

## Project Dependencies

To assist code reuse, this project has been broken into many sub-repositories.

- shared dependencies:
  - [kblocks](https://github.com/jackd/kblocks): dependency-injectable keras blocks
  - [meta-model](https://github.com/jackd/meta-model): framework for building multiple networks simultaneously for models with architecture-dependent data pipelining
  - [tfrng](https://github.com/jackd/tfrng): a uniform interface for tensorflow random number generation implementations and custom dataset map implementation
  - [wtftf](https://github.com/jackd/wtftf): keras layer wrappers that will be removed once a stable tensorflow 2.4 is released
- Point convolution specific:
  - [pcn](pcn): point cloud convolution implementations and training configs
  - [numba-neighbors](https://github.com/jackd/numba-neighbors): optimized nearest-neighbors implementations with [numba](https://numba.pydata.org/)
  - [shape-tfds](https://github.com/jackd/shape-tfds): [tensorflow-datasets](https://github.com/tensorflow/datasets) implementations of various shape datasets
- Event convolution specific:
  - [ecn](ecn): event convolution implementations and training configs
  - [numba-stream](https://github.com/jackd/numba-stream): optimized implementations of event stream preprocessing operations with [numba](https://numba.pydata.org/)
  - [events-tfds](https://github.com/jackd/events-tfds): [tensorflow-datasets](https://github.com/tensorflow/datasets) implementations of various shape datasets

[paper]: https://openaccess.thecvf.com/content/ACCV2020/html/Jack_Sparse_Convolutions_on_Continuous_Domains_for_Point_Cloud_and_Event_ACCV_2020_paper.html
[pcn]: https://github.com/jackd/pcn
[ecn]: https://github.com/jackd/ecn
