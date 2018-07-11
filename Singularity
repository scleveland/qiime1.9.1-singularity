Bootstrap: shub
From: scleveland/centos7-base-singularity

%environment
PATH=/opt/conda/envs/qiime1.9.1/bin:/opt/conda/bin:$PATH
export PATH

%post
yum update -y
yum  install -y @"Development Tools"
yum install -y git curl which python3 python3-devel vim htop wget tar bzip2 gzip lz4 lzma mesa-libGL mesa-libGLU
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh -b -p /opt/conda
export PATH=/opt/conda/bin:$PATH
conda install -y conda
conda update -y conda
mkdir /lus
mkdir /lus/scratch
conda create -n qiime1.9.1 python=2.7 qiime matplotlib=1.4.3 mock nose numpy -c bioconda -y
source activate qiime1.9.1
pip install cogent

%runscript
exec qiime "$@"
