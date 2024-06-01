# Spack
## Installation
```bash
git clone https://github.com/spack/spack.git
cd spack
git checkout releases/latest
source ./share/spack/setup-env.sh
```
Please add the last command to `.bashrc` with absolute path to start spack by default.
## Install Packages
todo
## Compiler
- Add Compilers
  ```bash
  spack install gcc@10.2.0 ## specify version
  spack find -p gcc ## get location
  spack compiler add /jet/packages/spack/opt/spack/linux-centos8-zen/gcc-8.3.1/gcc-10.2.0-tfzxq7udz2a53dmujvasy4uz33t27iwv ## or the location of any other compilers
  ```
## Common Commands
The `-j 32` flag in `spack install` means to `make` with 32 jobs, which will reduce installation time
```bash
spack info cuda # find available version of cuda
spack install -j 32 cuda@11.8 # install specified version of cuda
spack load cuda@11.8 # load corresponding cuda
```
## Environment
- Create an Environment
  ```bash
  spack env create neko
  spack env activate neko
  ```
- Add Packages to the Environment
    Edit `spack.yaml` from `spack/var/spack/environments/neko`
    ```bash
    cd var/spack/environments/neko
    vim spack.yaml
    ```
    And modify the file to add the package you need.
    ```
    spack:
      specs:
      - zlib
      - binutils
      - cuda@11.8
      - numactl
      - xz
      - libxml2
      - libpciaccess
      - hwloc
      - libevent
      - check
      - gdrcopy
      - ucx
      - openmpi+cuda
      - openblas
      - pmix
      - fftw
      - scalapack
      - libfabric
      view: true
      concretizer:
        unify: true
    ```
    Or you can just type
    ```bash
    spack add cuda@11.8
    ```
    Concretize the packages:
    ```bash
    spack concretize
    ```
    Finally, install all packages in the environment
    ```bash
    spack install --overwrite
    ```

  More in [Reference](https://chtc.cs.wisc.edu/uw-research-computing/hpc-spack-install)


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
