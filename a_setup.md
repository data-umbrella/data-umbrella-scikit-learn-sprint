# Setting up Environment and Repo

## PART A:  Set-up work environment

#### Install conda

For instance using the Miniforge3 installer:

https://github.com/conda-forge/miniforge

#### Set up virtual environment
```bash
conda create -n sklearndev -c conda-forge numpy scipy matplotlib pytest sphinx cython ipykernel
```

#### Helpful virtual environment commands to know 
- To view a **list** of your virtual environments:  `conda env list`
- To **activate** a virtual environment: `conda activate sklearndev`
- To **deactivate** a virtual environment:  `conda deactivate`
- To **remove** a virtual environment:  `conda env remove --name myenv`

#### Activate virtual environment:  
```bash
conda activate sklearndev
```
#### Additional installs
```bash
conda install -c conda-forge sphinx-gallery
```
#### Install a C/C++ compiler

##### On Linux or macOS

```bash
conda install -c conda-forge compilers
```

##### On Windows

Install **Tools for Visual Studio** from the menu at the bottom of this page:

https://visualstudio.microsoft.com/downloads/

**You do not need to install the full Visual Studio IDE**, just the "Tools".

---

## PART B:  Set-up repository

### Fork repo:  https://github.com/scikit-learn/scikit-learn

### Set up local repo  
#### `git clone` your forked repo url.  (Use `HTTPS` url over `SSH` if you do not have `ssh` keys set up.)

```bash
git clone https://github.com/reshamas/scikit-learn.git
```

#### `cd scikit-learn` into your folder

```bash
cd scikit-learn
```

#### Build from source
```bash
pip install -e .
```
Note:  this will overwrite existing installations
Reference:  ["Editable" Installs](https://pip.pypa.io/en/stable/reference/pip_install/#examples)


#### Add `upstream` remote
```
git remote add upstream https://github.com/scikit-learn/scikit-learn.git
```

#### Check remotes are there using `git remote -v`

>my example
```bash
origin	https://github.com/reshamas/scikit-learn.git (fetch)
origin	https://github.com/reshamas/scikit-learn.git (push)
upstream	https://github.com/scikit-learn/scikit-learn.git (fetch)
upstream	https://github.com/scikit-learn/scikit-learn.git (push)
```

### Update local repo
```bash
git pull upstream main
```

 
