# Spack
## Installation
```bash
git clone https://github.com/spack/spack.git
cd spack
git checkout releases/latest
source share/spack/setup-env.sh
```
## Install Packages
todo
## Compiler
- Add Compilers
  ```bash
  spack install gcc@10.2.0 ## specify version
  spack find -p gcc ## get location
  spack compiler add /jet/packages/spack/opt/spack/linux-centos8-zen/gcc-8.3.1/gcc-10.2.0-tfzxq7udz2a53dmujvasy4uz33t27iwv ## or the location of any other compilers
  ```

# Conda
## Installation
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
```
Terminal needs to be restarted.

## Create Environment
```bash
conda create -n my_env ## or any other names
conda activate my_env
conda install python=3.11 
```
