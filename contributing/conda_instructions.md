# Set up virtual environment

```bash
# clonar repositorio de sklearn
cd scikit-learn

conda create --name sklearndev
conda activate sklearndev

conda install numpy scipy matplotlib pytest sphinx cython ipykernel jupyter pytest-cov flake8 mypy
conda install -c conda-forge sphinx-gallery pre-commit
pip install black==21.6b0

# this installs scikit-learn dev mode
pip install --no-build-isolation --editable .

# allows us to run code style checks before each commit
pre-commit install
```


# For documentation
```bash
pip install numpydoc Pillow pandas scikit-image packaging seaborn sphinx-prompt sphinxext-opengraph
```

# Questions
- ask about building documentation
- ask about adding pair partner to get credit for commit

1. have to have folder open already and then send request for person to join live share
2. 
