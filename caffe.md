 
### requirement: ubuntu 14.04 + GTX1080 + CUDA8.0 + CUDNNv5 


## preparing 

$ sudo apt-get install build-essential <br />
$ uname -r <br />
$ sudo apt-get install linux-headers-'uname-r' <br />
$ sudo apt-get install linux-headers-4.2.0-27-generic <br />
$ sudo apt-get install -y libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libboost-all-dev libhdf5-serial-dev protobuf-compiler gfortran libjpeg62 libfreeimage-dev libatlas-base-dev git python-dev python-pip libgoogle-glog-dev libbz2-dev libxml2-dev libxslt1-dev libffi-dev libssl-dev libgflags-dev liblmdb-dev <br />


## caffe install 

$ git clone https://github.com/BVLC/caffe.git  <br />
$ cd caffe/  <br />
$ cat python/requirements.txt | xargs -L 1 sudo pip install  <br />
$ sudo ln -s /usr/include/python2.7/ /usr/local/include/python2.7  <br />
$ sudo ln -s /usr/local/lib/python2.7/dist-packages/numpy/core/include/numpy /usr/local/include/python2.7/numpy  <br />
$ cp Makefile.config.example Makefile.config  <br />
$ gedit  Makefile.config  <br />

```
# modified regard to softlink 
PYTHON_INCLUDE := /usr/local/include/python2.7 \ 
                  /usr/local/include/python2.7/numpy 
```

$ cd caffe/  <br />
$ make pycaffe  <br />
$ make -j8 all  <br />
$ make -j8 test  <br />




## testing 
$ python scripts/download_model_binary.py models/bvlc_reference_caffenet  <br />
$ sh data/ilsvrc12/get_ilsvrc_aux.sh  <br />
$ itorch notebook <br />
  
  
