# OpenNFT
OpenNFT is an integrated software package designed for neurofeedback training. It constitutes the core technical framework for developments in this exciting new field of neuroimaging. OpenNFT is based on best practices of Python and Matlab software and incorporates, but is not limited to, the functionality of the SPM and Psychtoolbox software suits. An integrated Python/Matlab framework is specifically selected to address the needs of neurofeedback developers and users with different background, which allows for flexibility in developments and implementations without compromising for speed and functionality. More specifically, the OpenNFT’s GUI, synchronization module, and multi-processing core are implemented in Python, whilst computational modules for neurofeedback are implemented in Matlab.

Refer to www.OpenNFT.org and to our Neuroimage manuscript ["OpenNFT: An open-source Python/Matlab framework for real-time fMRI neurofeedback training based on activity, connectivity and multivariate pattern analysis"](http://www.sciencedirect.com/science/article/pii/S1053811917305050) for further description.
Direct link to [OpenNFT manual](https://github.com/OpenNFT/opennft.github.io/blob/master/OpenNFT_Manual_v1.0.pdf), to be updated.
Note, we are still tuning our pre-release version. Please check the updates regularly.

## Installation (based on the to be updated [OpenNFT manual](https://github.com/OpenNFT/opennft.github.io/blob/master/OpenNFT_Manual_v1.0.pdf))

### Prerequisites
- MATLAB (x64) `>= R2017b`
    - Image Processing Toolbox
    - Statistics and Machine Learning Toolbox
- Python (x64) `>= 3.6, < 3.9`, for example [Miniconda3](https://docs.conda.io/en/latest/miniconda.html)
- [Git](https://git-scm.com/downloads): for installing SPM, Psychtoolbox, OpenNFT

### Install MATLAB Toolboxes
- [SPM12](https://github.com/spm/spm12.git)
- [Psychtoolbox 3](https://github.com/Psychtoolbox-3/Psychtoolbox-3.git)
- [JSONlab](https://uk.mathworks.com/matlabcentral/mlc-downloads/downloads/submissions/33381/versions/22/download/zip)

### Install optional/supplementary MATLAB Toolboxes
- [prepNFB](https://github.com/lucp88/prepNFB). Matlab toolbox to prepare neurofeedback session(s) by Lucas Peek.

### Install OpenNFT in virtual environment 
Recommended installation is illustrated in the rtFIN 2019 presentation number 4 on [Project Set Up](https://github.com/OpenNFT/Courses/releases/tag/1.0).
Please also check all the other useful presentations there.
Alternative instalaltions and useful tips are also listed below.

Install with conda and e.g. Python 3.6:
- `$ conda create -n OpenNFT_venv python=3.6 pip setuptools`
- `$ conda activate OpenNFT_venv`
- `(OpenNFT_venv)$ python -m pip install -U pip setuptools wheel`
- (optional for numpy+MKL) `(OpenNFT_venv)$ conda install mkl numpy`
- `(OpenNFT_venv)$ pip install git+https://github.com/OpenNFT/OpenNFT.git --install-option "--matlab-root=<MATLABROOT>"`

Install without conda using your existing Python (>=3.6, <3.9):
- `$ python -m venv OpenNFT_venv`
- (Linux/macos) `$ source OpenNFT_venv/bin/acivate`
- (Windows) `$ OpenNFT_venv\Scripts\acivate.bat`
- `(OpenNFT_venv)$ python -m pip install -U pip setuptools wheel`
- `(OpenNFT_venv)$ pip install git+https://github.com/OpenNFT/OpenNFT.git --install-option "--matlab-root=<MATLABROOT>"`

Also if you do not set install option `--matlab-root` we try to find Matlab automatically.
You can check installation result using `-v` (verbose) option:

```
(OpenNFT_venv)$ pip install git+https://github.com/OpenNFT/OpenNFT.git -v
```

**NOTE**: 
If you do not have write access in MATLABROOT the installer will try to install "Matlab Engine for Python" 
with Administrator/root privileges (It elevates privileges via UAC/sudo).

Also you can install OpenNFT from your working directory (OpenNFT project root directory):

```
(OpenNFT_venv)$ pip install /path/to/OpenNFT/root/dir/
```

or:

```
(OpenNFT_venv)$ cd /path/to/OpenNFT/root/dir/
(OpenNFT_venv)$ pip install .
```

Also you can use option `-e/--editable` for installing in [editable mode](https://pip.pypa.io/en/stable/reference/pip_install/#editable-installs) (mode for development):

```
(OpenNFT_venv)$ pip install -e .
(OpenNFT_venv)$ pip list
Package               Version    Location
--------------------- ---------- -----------------------------
...
matlabengineforpython R2016b
...
numpy                 1.16.2+mkl
OpenNFT               1.0.0rc0   c:\workspace\projects\opennft
...
```

## Updating OpenNFT dependencies

Update pip:

`python -m pip install -U pip setuptools wheel`

Update dependencies:

`pip install -U -r requirements.txt`

## Running OpenNFT application

Just run the following command:

`(OpenNFT_venv)$ opennft`

or with console window:

`(OpenNFT_venv)$ opennft_console`

## Running and debuging OpenNFT from pyCharm

If you want to run the program from PyCharm run/debug configuration, you should use something like this:  

![ ](https://user-images.githubusercontent.com/1299189/59237394-d1408300-8c02-11e9-89be-6fc74125d078.png)  

If you don't see "Module name:" caption in the config dialog, you need to update your pyCharm.

## Running and debuging OpenNFT from VSCode

If you want to run the program from VSCode run/debug configuration, you should add the followings to launch.json configuration: 

```json
{
    "name": "Python: Module",
    "type": "python",
    "request": "launch",
    "module": "opennft"
}
```

## Demo dataset
https://github.com/OpenNFT/OpenNFT_Demo/releases 
 
#### N.B.:
Use the updated Setup and Protocol files provided with OpenNFT - https://github.com/OpenNFT/OpenNFT/tree/master/opennft/configs
