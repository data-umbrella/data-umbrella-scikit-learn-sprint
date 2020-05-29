# Workflow: Setup Environment

PR = Pull Request  
**Important Note:**  Please include **(#DataUmbrella)** in your PR commit message so we can track them. 

---

## PART A:  Set-up work environment

#### Set up virtual environment
```bash
conda create -n sklearndev numpy scipy matplotlib pytest sphinx cython ipykernel
```

#### Helpful virtual environment commands to know 
- To view a **list** of your virtual environments:  `conda env list`
- To **activate** a virtual environment: `conda activate sklearndev`
- To **deactivate** a virtual environment:  `conda deactivate`
- To **remove** a virtual environment:  `conda env remove --name myenv`

#### Activate virtual environment:  
```bash
source activate sklearndev
```
#### Additional installs
```bash
conda install -c conda-forge sphinx-gallery
```

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
git pull upstream master
```

 
