# Configure a system for DLI

1. Log in to the host as root. 
   
2. Install NCCL1 from the PowerAI repository.  
```
   yum install libnccl*
``` 
   
3. Create an Anaconda environment named dli for the installation of DLI. 
```
  conda create --name dli --yes pip python=2.7
```

4. Activate dli and install dependencies.
```
   source activate dli
   conda install --yes --no-update-dependencies cython==0.25.2 h5py==2.7.0 ipython==5.3.0 python-lmdb==0.92 matplotlib==2.0.2 networkx==1.11 nose==1.3.7 pandas==0.20.3 pillow==4.1.1 python-dateutil==2.6.1 pyyaml==3.12 requests==2.13.0 scipy==1.1.0 six==1.11.0 scikit-image==0.13.0 redis-py==2.10.5 chardet==3.0.4
   pip install Keras==2.0.5 easydict==1.6 python-gflags==2.0 
   source deactivate
```

5. For large model support, install additional packages.
```
   source activate dli
   pip install hanziconv gensim
   source deactivate
```

 6. Install PowerAI deep learning dependencies.  
   - Install TensorFlow dependencies.
```   
      /opt/DL/tensorflow/bin/install_dependencies -n dli
```
   - Install TensorBoard dependencies.
```   
       /opt/DL/tensorboard/bin/install_dependencies -n dli
```
   - Install PyTorch to its own Anaconda environment.
   
```  
     conda create --name dli-pytorch --yes pip python=2.7
     source activate dli-pytorch
     /opt/DL/pytorch/bin/install_dependencies --yes
     source deactivate
```
7. Install OpenCV and create symbolic links. 
```
     yum install opencv-devel python-devel opencv-python boost-python snappy-devel
     ln -s /usr/lib64/python2.7/site-packages/cv.py /opt/anaconda2/envs/dli/lib/python2.7/site-packages/cv.py
     ln -s /usr/lib64/python2.7/site-packages/cv.pyc /opt/anaconda2/envs/dli/lib/python2.7/site-packages/cv.pyc
     ln -s /usr/lib64/python2.7/site-packages/cv.pyo /opt/anaconda2/envs/dli/lib/python2.7/site-packages/cv.pyo
     ln -s /usr/lib64/python2.7/site-packages/cv2.so /opt/anaconda2/envs/dli/lib/python2.7/site-packages/cv2.so
```

8. Install elastic distributed training dependencies.
```
    yum install openblas-devel glog-devel gflags-devel hdf5-devel leveldb-devel libsodium-devel lmdb-devel
```
9. Install additional dependency packages.
```
    yum install gcc-c++ gcc-gfortran freetype-devel libpng-devel libffi-devel openssl-devel
```

10. Create an Anaconda environment named dlinsights for DLI training insights. 
```
    conda create --name dlinsights --yes pip python=2.7 
```   
11. Activate dlinsights and install dependencies.
```
    source activate dlinsights
    pip install numpy==1.12.1 
    pip install requests==2.14.2 elasticsearch==5.2.0 Flask==0.12.2 Flask-Cors==3.0.3 Flask-Script==2.0.5 Flask-HTTPAuth==3.2.2 mongoengine==0.11.0 pathlib==1.0.1 pyOpenSSL==17.1.0 python-heatclient==1.2.0 SQLAlchemy==1.1.13 scipy==1.0.1 alembic==0.8.2 python-keystoneclient==3.8.0  
    source deactivate 
```   
