<a href="https://app.naas.ai/user-redirect/naas/downloader?url=https://raw.githubusercontent.com/jupyter-naas/awesome-notebooks/master/SAP-HANA/SAP-HANA_Query_data.ipynb" target="_parent"><img src="https://naasai-public.s3.eu-west-3.amazonaws.com/open_in_naas.svg"/></a>

**Tags:** #sap-hana #sap #saphana #database #snippet #operations #dataframe

**Author:** [Jeremy Ravenel](https://www.linkedin.com/in/ACoAAAJHE7sB5OxuKHuzguZ9L6lfDHqw--cdnJg/)

## Input

### Install packages


```python
!pip install hdbcli
```

### Import library


```python
import sap_hana_connector
```

### Declare variables


```python
type: 'SapHana'
name: 'JPAK_LIVE'
user: 'USER'
password: 'PASSWORD'
port: 30015
host: 'HOST'
```

## Model

### Query to get specific table in SAP HANA


```python
query: 'SELECT * FROM JPAK_LIVE.OINV T0'
```

## Output

### Return Data Frame 


```python
df = query
```
