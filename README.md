# GPmp: the Gaussian process micro package

## Features

GPmp intends to provide building blocks for GP-based algorithms. It
uses auto-differentiation and JIT compilation features provided by
[JAX](https://jax.readthedocs.io/). It should be fast and easily
customizable.

For the purpose of simplicity, the gpmp does not check the validity of
arguments. This is left to the responsibility of the user / calling
code.

GPmp implements :
* GP interpolation and regression with unknown mean / intrisinc kriging
* The standard Gaussian likelihood and the restricted likelihood of a model
* Leave-one-out predictions using fast cross-validation formulas
* Conditional sample paths

It is up to the user to write the mean and covariance functions for
setting a GP model. However, GPmp provides building blocks for:
* anisotropic scaling
* distance matrix
* Matérn kernels with half-integers regularties
* Parameter selection using maximum likelihood / restricted maximum
  likelihood / or user-defined criteria


## Installation

Clone the git repository:
```
git clone https://github.com/emvazquez/gpmp.git
```
(or download a zip version)

Install in dev mode:
```
pip install -e .
```

Remarks:

1. GPmp is based on JAX, which requires jaxlib, and which is
   supported on Linux and macOS platforms, and on Windows via the
   Windows Subsystem for Linux. There is some initial native Windows
   support, but it is still somewhat immature (see below).

2. To install JAX with both CPU and NVidia GPU support, CUDA and CuDNN
   must be installed first. See
   https://github.com/google/jax#installation and
   https://jax.readthedocs.io/en/latest/changelog.html for details.

   For instance, to install jaxlib  with Cuda 11 and cudnn 8.2 or newer:
```bash   
pip install jax[cuda11_cudnn82] -f https://storage.googleapis.com/jax-releases/jax_releases.html
```
   
3. To install jaxlib on Windows, one can follow instructions at
   https://github.com/cloudhan/jax-windows-builder.  Select and
   download a version of jaxlib from
   https://whls.blob.core.windows.net/unstable/index.html according to
   your Python version. Then install jax manually.

```powershell
pip install <jaxlib_whl>
pip install jax
```

## Usage

Please refer to the examples that illustrate the different features of GPmp.

## To do

* provide a documentation
* unit tests
* improve package setup

## Authors

 See AUTHORS.md

## Copyright

 Copyright (C) 2022 CentraleSupelec

## License

 GPmp is free software: you can redistribute it and/or modify it
 under the terms of the GNU General Public License as published by
 the Free Software Foundation, either version 3 of the License, or
 (at your option) any later version.

 GPmp is distributed in the hope that it will be useful, but WITHOUT
 ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
 or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public
 License for more details.

 You should have received a copy of the GNU General Public License
 along with gpmp. If not, see http://www.gnu.org/licenses/.
