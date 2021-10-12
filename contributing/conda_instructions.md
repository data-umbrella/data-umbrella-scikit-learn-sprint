```bash
conda create -n sklearn-dev numpy scipy matplotlib pytest sphinx cython ipykernel jupyter pytest-cov flake8 mypy
conda activate sklearn-dev
conda install -c conda-forge sphinx-gallery pre-commit
pip install black==21.6b0
# clonar repositorio de sklearn
cd scikit-learn
pip install --no-build-isolation --editable .
pre-commit install
```
