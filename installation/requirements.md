# Installation
TradeMaster works on Linux, Windows and MacOS for both CPU and GPU, which requires Python 3.9+, CUDA 11.3+ and PyTorch 1.12+. If you have not installed CUDA, please download it from the [official website](https://developer.nvidia.com/cuda-11.3.0-download-archive)

__Download and install Miniconda__ from the [official website](https://docs.conda.io/en/latest/miniconda.html).
## Install Miniconda on x86-64b Linux (ubuntu 20.04 /etc/lsb-release)

   ```
   mkdir -p ~/miniconda3
   wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
   bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
   rm -rf ~/miniconda3/miniconda.sh
   ```
After installing, initialize your newly-installed Miniconda. The following commands initialize for bash and zsh shells:
   ```
   ~/miniconda3/bin/conda init bash
   ~/miniconda3/bin/conda init zsh
   ```

## Ceate a conda environment and activate it

  ```
  conda update -n base -c defaults conda
  conda create --name TradeMaster python=3.9
  conda activate TradeMaster
   ```
  
## Pytorch installation
install Pytorch following [official instructions](https://pytorch.org/):

On CPU platforms
  ```
  conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cpuonly -c pytorch
  ```
On GPU platforms
  ```
  conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.3 -c pytorch
  ```
## Apex installation
Install Apex following [apex repo](https://github.com/NVIDIA/apex):
  ```
  ** pip3 install --upgrade pip

  pip install packaging mkl
  git clone https://github.com/NVIDIA/apex
  cd apex

  ** sudo apt install python3-packaging
  ** git checkout 0da3ffb -> packaging error

  ** export TORCH_CUDA_ARCH_LIST="compute capability"
  ** conda install -c nvidia cuda-nvcc -> TypeError: unsupported operand type(s) for +: 'NoneType' and 'str'

  pip install -v --no-cache-dir .
  cd ..
  ```
## TradeMaster installation  

  ```
  git clone https://github.com/TradeMaster-NTU/TradeMaster.git
  cd TradeMaster

  ** Downgrade both wheel and setuptools with pip install wheel==0.38.4 setuptools==66.0.0
  ** pip install setuptools==65.5.0 pip==21
  ** pip install wheel==0.38.0

  pip install -r requirements.txt
  ```

##  Verify installation

  ```
  python tools/algorithmic_trading/train.py
  ```

## Jupyter-notebook
[remote access](https://sishida21.github.io/2019/12/12/remote-jupyter-notebook/)
```
jupyter notebook --ip=* --no-browser

.jupyter/jupyter_notebook_config.py

c.NotebookApp.ip = '0.0.0.0'
c.NotebookApp.port = 8888
c.NotebookApp.allow_origin = '*' #allow all origins
c.NotebookApp.allow_credentials = False
c.NotebookApp.open_browser = False
c.NotebookApp.password_required = False
```
