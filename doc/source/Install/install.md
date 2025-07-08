# Installation 
Kssdutils requires the Python 3 environment and the dependent packages pandas, and requests. If kssdutils is installed using the pip command, these dependencies will be installed automatically. For MacOS, it requires Python 3.8 or higher version. For Windows, it requires Python 3.6 version and the installation of the gzip tool (https://gnuwin32.sourceforge.net/packages/gzip.htm) for sequence decompression.
## 1. Linux

```
pip install kssdutils
```
## 2. MacOS

```
# (Optional) Install gcc (/opt/homebrew/bin/gcc-12) 
brew install gcc@12

# Create a virtual environment
conda create --name=kssdutils python=3.10

# Activate the virtual environment
conda activate kssdutils

# Install kssdutils
pip install kssdutils
```
## 3. Windows

```
# Create a virtual environment
conda create --name=kssdutils python=3.6.13

# Activate the virtual environment
conda activate kssdutils

# (Optional) Install libpython and m2w64-toolchain
conda install libpython m2w64-toolchain -c msys2

# Install kssdutils
pip install kssdutils
```