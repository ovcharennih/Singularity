BootStrap: docker
From: nvidia/cuda:8.0-cudnn6-runtime-ubuntu16.04

################################################################################
%labels
################################################################################
MAINTAINER Wolfgang Resch
VERSION v3

################################################################################
%environment
################################################################################
export PATH=~/base/bin:/bin:/usr/bin:/usr/local/bin:/usr/local/cuda/bin:

################################################################################
%post
################################################################################

###
### install keras + tensorflow + other useful packages
###
apt-get update
apt-get install -y libhdf5-dev graphviz locales python python-pip git xvfb
locale-gen en_US.UTF-8
apt-get clean

curl -O https://raw.githubusercontent.com/cctbx/cctbx_project/master/libtbx/auto_build/bootstrap.py
python boostrap.py --nproc=8

base/bin/pip install --upgrade pip
base/bin/pip install tensorflow-gpu==1.3.0
base/bin/pip install keras==2.0.8
base/bin/pip install setuptools wheel Pillow scikit-learn pandas matplotlib ipython==5.5.0
base/bin/pip install h5py
base/bin/pip install pyside
base/bin/pip install mayavi
base/bin/pip install --upgrade notebook

###
### destination for NIH HPC bind mounts
###
mkdir /gpfs /spin1 /gs2 /gs3 /gs4 /gs5 /gs6 /gs7 /gs8 /data /scratch /fdb /lscratch

