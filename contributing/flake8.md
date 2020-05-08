# `flake8`

#### `flake8` Formatting Tests
Can install using `pip` or `conda`:  

>my example
```python
conda install flake8 
```

### Running `flake8`
`flake8` <filename.py>

>my example
```bash
flake8 /Users/reshamashaikh/scikit-learn/sklearn/metrics/scorer.py
```

When there are formatting issues, here's an example of what it will return:  

>my example
```bash
(sklearndev) % flake8 scorer.py
scorer.py:186:39: E225 missing whitespace around operator
scorer.py:189:80: E501 line too long (85 > 79 characters)
scorer.py:190:80: E501 line too long (87 > 79 characters)
```



