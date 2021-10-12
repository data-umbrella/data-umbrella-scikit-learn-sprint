```bash
conda create --name sklearndev
conda activate sklearndev

conda install numpy scipy matplotlib pytest sphinx cython ipykernel jupyter pytest-cov flake8 mypy
conda install -c conda-forge sphinx-gallery pre-commit
pip install black==21.6b0

# clonar repositorio de sklearn
cd scikit-learn
pip install --no-build-isolation --editable .
pre-commit install
```
