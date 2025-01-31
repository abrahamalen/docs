<a href="https://app.naas.ai/user-redirect/naas/downloader?url=https://raw.githubusercontent.com/jupyter-naas/awesome-notebooks/master/Python/Python_Create_dataframe_from_lists.ipynb" target="_parent"><img src="https://naasai-public.s3.eu-west-3.amazonaws.com/open_in_naas.svg"/></a>

**Tags:** #python #list #dataframe #snippet #pandas #operations

**Author:** [Florent Ravenel](https://www.linkedin.com/in/ACoAABCNSioBW3YZHc2lBHVG0E_TXYWitQkmwog/)

Here below you will find how to create a pandas DataFrame from two lists in Python.

## Input

### Import libraries


```python
import pandas as pd
```

### Variables


```python
# Setup your columns name
col_key = "KEYS"
col_value = "VALUE"
```

### Lists


```python
keys = [1995, 1996, 1997, 1998, 1999, 2000, 2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012]
value = [219, 146, 112, 127, 124, 180, 236, 207, 236, 263, 350, 430, 474, 526, 488, 537, 500, 439]
```

## Model

### Create zip iterator


```python
# Call zip(iter1, iter2) with one list as iter1 and another list as iter2 to create a zip iterator containing pairs of elements from the two lists.
zip_iterators = zip(keys, value)
```

## Output

### Create dataframe


```python
df = pd.DataFrame(zip_iterators, columns=[col_key, col_value])
df
```


```python

```
