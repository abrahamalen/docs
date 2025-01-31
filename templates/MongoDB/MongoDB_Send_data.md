<a href="https://app.naas.ai/user-redirect/naas/downloader?url=https://raw.githubusercontent.com/jupyter-naas/awesome-notebooks/master/MongoDB/MongoDB_Send_data.ipynb" target="_parent"><img src="https://naasai-public.s3.eu-west-3.amazonaws.com/open_in_naas.svg"/></a>

**Tags:** #mongodb #database #naas_drivers #snippet #operations #naas

**Author:** [Florent Ravenel](https://www.linkedin.com/in/ACoAABCNSioBW3YZHc2lBHVG0E_TXYWitQkmwog/)

## Input

### Import library


```python
from naas_drivers import mongo
import pandas as pd
```

### Variables


```python
# Credentials
user = "my user"
passwd = "my passwd"
host = "url"
port = 9090

# DB parameters
collection_name = "col"
db_name = "db_name"
```

## Model

### Read dataframe


```python
data = {"LABEL": "Label 1", "VALUE": 0}
df = pd.DataFrame([data])
df
```

## Output

### Send data


```python
mongo.connect(host, port, user, passwd).send(df, collection_name, db_name, replace=False)
```
