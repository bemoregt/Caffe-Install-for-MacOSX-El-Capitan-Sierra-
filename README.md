# Caffe_Install_for_MacOSX_ElCapitan-Sierra

# Install CUDA for Mac OS X

https://developer.nvidia.com/cuda-downloads

# Install dependency

brew install boost --with-python
brew install boost-python

brew install protobuf
brew install glog
brew install gflags

brew install leveldb
brew install lmdb

brew tap homebrew/science
brew install homebrew/science/hdf5

pip install h5py

brew install numpy

# Install Caffe Github

$ git clone https://github.com/BVLC/caffe.git

# Makefile configuration

$ cp Makefile.config.example Makefile.config
$ mcedit Makefile.config

1. CPU_ONLY := 1
2. CUDA_DIR := /usr/local/cuda
3. CUDA_ARCH := -gencode arch=compute_20,code=sm_20 \
                -gencode arch=compute_20,code=sm_21 \
                -gencode arch=compute_30,code=sm_30 \
                -gencode arch=compute_35,code=sm_35 \
                -gencode arch=compute_50,code=sm_50 \
                -gencode arch=compute_50,code=compute_50
4. BLAS := atlas
5. PYTHON_INCLUDE := /usr/include/python2.7 \
                /usr/local/lib/python2.7/site-packages/numpy/core/include/
6. PYTHON_LIB := /usr/local/Cellar/python/2.7.11/Frameworks/Python.framework/Versions/2.7/lib/

# Compile

$ sudo make clean -j4

$ sudo make all -j4
$ sudo make pycaffe -j4

$ sudo make test -j4
$ sudo make runtest

$ python -c 'import caffe' 




