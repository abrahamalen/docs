<a href="https://app.naas.ai/user-redirect/naas/downloader?url=https://raw.githubusercontent.com/jupyter-naas/awesome-notebooks/master/Jupyter/Jupyter_Restart_server.ipynb" target="_parent"><img src="https://naasai-public.s3.eu-west-3.amazonaws.com/open_in_naas.svg"/></a>

**Tags:** #jupyter #server #restart #snippet #operations #naas

**Author:** [Florent Ravenel](https://www.linkedin.com/in/ACoAABCNSioBW3YZHc2lBHVG0E_TXYWitQkmwog/)

## Input

### Import libraries


```python
from naas_drivers import jupyter
from os import environ
```

### Setup your Jupyter


```python
# Jupyter token stored in your env
JUPYTER_TOKEN = environ.get('JUPYTERHUB_API_TOKEN')

# Username => email address linked to your jupyter account
username = "wsr@naas.ai"
```

## Model

### Restart server


```python
jupyter.connect(JUPYTER_TOKEN).restart_user(username)
```

## Output

### Display result


```python

```
