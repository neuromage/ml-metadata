
# ML Metadata

[![Python](https://img.shields.io/pypi/pyversions/ml-metadata.svg?style=plastic)](https://github.com/google/ml-metadata)
[![PyPI](https://badge.fury.io/py/ml-metadata.svg)](https://badge.fury.io/py/ml-metadata)

*ML Metadata (MLMD)* is a library for recording and retrieving metadata
associated with ML developer and data scientist workflows.

Caution: ML Metadata may be backwards incompatible before version 1.0.

## Getting Started

For more background on MLMD and instructions on using it, see the
[getting started guide](https://github.com/google/ml-metadata/blob/master/g3doc/get_started.md)

## Installing from PyPI

The recommended way to install ML Metadata is to use the
[PyPI package](https://pypi.org/project/ml-metadata/):

```bash
pip install ml-metadata
```

## Installing from source


### 1. Prerequisites

To compile and use ML Metadata, you need to set up some prerequisites.


#### Install Bazel

If Bazel is not installed on your system, install it now by following [these
directions](https://bazel.build/versions/master/docs/install.html).

#### Install cmake
If cmake is not installed on your system, install it now by following [these
directions](https://cmake.org/install/).

### 2. Clone ML Metadata repository

```shell
git clone https://github.com/tensorflow/ml-metadata
cd ml-metadata
```

Note that these instructions will install the latest master branch of ML
Metadata. If you want to install a specific branch (such as a release branch),
pass `-b <branchname>` to the `git clone` command.

### 3. Build the pip package

ML Metadata uses Bazel to build the pip package from source:

```shell
bazel run -c opt --define grpc_no_ares=true ml_metadata:build_pip_package
```

You can find the generated `.whl` file in the `dist` subdirectory.

### 4. Install the pip package

```shell
pip install dist/*.whl
```

### 5.(Optional) Build the grpc server

ML Metadata uses Bazel to build the c++ binary from source:

```shell
bazel build -c opt --define grpc_no_ares=true  //ml_metadata/metadata_store:metadata_store_server
```

## Supported platforms

MLMD is built and tested on the following 64-bit operating systems:

  * macOS 10.12.6 (Sierra) or later.
  * Ubuntu 14.04 or later.
