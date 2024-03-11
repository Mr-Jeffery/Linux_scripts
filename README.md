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
      - zlib@1.2.11
      - binutils@2.35
      - cuda@11.1.1
      - numactl@2.0.13
      - xz@5.2.5
      - libxml2@2.9.10
      - libpciaccess@0.16
      - hwloc@2.2.0
      - libevent@2.1.12
      - check@0.15.2
      - gdrcopy@2.1%cuda@11.1.1
      - ucx@1.9.0%cuda@11.1.1
      - openmpi@4.05%cuda@11.1.1
      - openblas@0.3.12
      - pmix@3.15
      - fftw@3.3.8
      - scalapack@2.1.0
      - libfabric@1.11.0
      - openmpi@4.05%cuda@11.1.1
      - cuda@11.1.1
      view: true
      concretizer:
        unify: when_possible
      ```
    Or you can just type
    ```bash
    spack add cuda@11.1.1
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
