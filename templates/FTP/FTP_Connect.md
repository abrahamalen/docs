<a href="https://app.naas.ai/user-redirect/naas/downloader?url=https://raw.githubusercontent.com/jupyter-naas/awesome-notebooks/master/FTP/FTP_Connect.ipynb" target="_parent"><img src="https://naasai-public.s3.eu-west-3.amazonaws.com/open_in_naas.svg"/></a>

**Tags:** #ftp #file #naas_drivers #operations #snippet

**Author:** [Jeremy Ravenel](https://www.linkedin.com/in/ACoAAAJHE7sB5OxuKHuzguZ9L6lfDHqw--cdnJg/)

## Input

### Import library


```python
from naas_drivers import ftp
```

### Variables


```python
user = "my user"
passwd = "my passwd"
```

## Model

### Connect to FTP


```python
ftp_get = ftp.connect(user, passwd, port=990, secure=True)
```

## Output


```python
ftp_get
```
