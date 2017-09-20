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
export PATH=/bin:/usr/bin:/usr/local/bin:/usr/local/cuda/bin:

################################################################################
%post
################################################################################

###
### install keras + tensorflow + other useful packages
###
apt-get update
apt-get install -y libhdf5-dev graphviz locales python python-pip git
locale-gen en_US.UTF-8
apt-get clean

pip install --upgrade pip
pip install tensorflow-gpu==1.3.0
pip install keras==2.0.8
pip install Pillow scikit-learn pandas matplotlib notebook ipython==5.5.0
pip install git+https://github.com/edraizen/3DUnetCNN.git

###
### destination for NIH HPC bind mounts
###
mkdir /gpfs /spin1 /gs2 /gs3 /gs4 /gs5 /gs6 /gs7 /gs8 /data /scratch /fdb /lscratch

