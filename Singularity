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
export PATH=/usr/local/sbin:/usr/sbin:/sbin:/bin:/usr/bin:/usr/local/bin:/usr/local/cuda/bin:
export PYTHONPATH=/usr/share/pdb2pqr:

################################################################################
%post
################################################################################

###
### install keras + tensorflow + other useful packages
###
apt-get update
apt-get install -y wget libhdf5-dev graphviz locales python python-pip git xvfb python-vtk pdb2pqr python-pandas
locale-gen en_US.UTF-8
apt-get clean

pip install --upgrade pip
pip install tensorflow-gpu==1.4.0
pip install keras==2.0.8
pip install setuptools wheel Pillow scikit-learn matplotlib ipython==5.5.0
pip install h5py
pip install mayavi
pip install --upgrade notebook
pip install cython
pip install Biopython

wget http://freesasa.github.io/freesasa-2.0.2.tar.gz
tar -xzf freesasa-2.0.2.tar.gz
cd freesasa-2.0.2
./configure CFLAGS=-fPIC --enable-python-bindings --disable-json --disable-xml
make && make install

###
### destination for NIH HPC bind mounts
###
mkdir /gpfs /spin1 /gs2 /gs3 /gs4 /gs5 /gs6 /gs7 /gs8 /data /scratch /fdb /lscratch /pdb

