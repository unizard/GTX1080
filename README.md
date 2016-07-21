
# ubuntu 14.04 + GTX1080 + CUDA8.0 + CUDNNv5 + Torch7



## Ubuntu 14.04
 - ubuntu 14.04 do it yourself!

## GTX1080 Driver installation 
 - sudo apt-get update 
 - sudo apt-get upgrade 
 - sudo add-apt-repository ppa:graphics-drivers/ppa 
 - sudo apt-get update 
 - sudo apt-get install nvidia-367 
 - sudo apt-get install mesa-common-dev 
 - sudo apt-get install freeglut3-dev 
 - sudo reboot 


## CUDA 8.0 intallation ( after download ) 

 - cd Downloads/ 
 - chmod +x cuda_8.0.27_linux.run 
 - ./cuda_8.0.27_linux.run 
 - nvidia-smi 
 - gedit ~/.bashrc 

     // insert following two path 
     
     export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}} 
     
     export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}} 

 - sudo apt-get install nvidia-modprobe ( for cuda  )
 - sudo reboot 
 - th	


## CUDNN v5 installation 

 - cd Downloads/cuda/lib64/ 
 - sudo cp libcudnn.so /usr/local/cuda-8.0/lib64/ 
 - sudo cp libcudnn.so.5 /usr/local/cuda-8.0/lib64/ 
 - sudo cp libcudnn.so.5.0.5 /usr/local/cuda-8.0/lib64/ 
 - sudo cp libcudnn_static.a /usr/local/cuda-8.0/lib64/ 
 - sudo cp ./include/cudnn.h /usr/local/cuda-8.0/include/ 
 - sudo reboot

## Torch7 installation 

 - sudo curl -sk https://raw.githubusercontent.com/torch/ezinstall/master/install-deps | bash 
 - git clone https://github.com/torch/distro.git ~/torch --recursive 
 - cd ~/torch/ 
 - ./install.sh 
 - sudo reboot 

## preparation for iTorch installation 

 - sudo apt-get install -y python-pip python-dev 
 - sudo pip install --upgrade pip 
 - sudo pip install --upgrade virtualenv 
 - sudo pip install --upgrade "ipython[all]" 
 

## iTorch installation 
 - git clone https://github.com/facebook/iTorch.git 
 - cd iTorch/ 
 - sudo apt-get install -y luarocks 
 - luarocks install image 
 - luarocks make 
 - itorch notebook 


## FBLuaLib installization ( after downloading ) 
  FBlualib has dependency on Python-dev. 
  
 - cd fblualib/ 
 - ./install_all.sh 
 - th

