pydeeplearn
===========

Library for deep belief nets and rbms. Provides code for dropout, rmsprop rectified linear units, sparsity constraints, weight decay, etc.

# TO INSTALL


1. Create a python virtualenv

2. Clone numpy

 `git clone https://github.com/numpy/numpy`

3. Optional: setup numpy to work with OpenBlas
  `git clone git://github.com/xianyi/OpenBLAS`
  `cd OpenBLAS && make FC=gfortran`
  `sudo make PREFIX=prefixpath install`
  `ldconfig (requires sudo if prefixpath is a global path)`

  in the directory numpy was downloaded:
  `vim site.cfg`
  set the contents to:

  `[atlas]`
  `atlas_libs = openblas`
  `library_dirs = prefixpath/lib`

  or for numpy 19.dev

 ` [openblas]`
  `libraries = openblas`
  `library_dirs = prefixpath/lib`
  `include_dirs = prefixpath/include`

4. `python setup.py config` to ensure everything is OK
5. `python setup.py build && python setup.py install`
6. `pip install --upgrade scikit-learn`
7. `pip install --upgrade cython`
8. `pip install --upgrade scikit-image`
9. `pip install theano`
10. install opencv for python
11. install matplotlib
   `easy_install -m matplotlib`

Note that for theano to work on the GPU you need cuda installed and setting up some environment variables.

`PATH` needs to containt the path to nvcc (usually `/usr/local/cuda/bin`)

`CUDA_PATH` needs to contain the path to cuda (usually `/usr/local/cuda/`)

`LD_LIBRARY_PATH` needs to contain the linker libraries for cuda (`/usr/local/cuda/lib64`)

`LD_LIBRARY_PATH` needs to contain the path to openblas (for numpy to find it: this is the prefix path you chose at step 3)

`LIBRARY_PATH` needs to contain the path to the nvidia driver (something like `/usr/lib/nvidia-331`)

