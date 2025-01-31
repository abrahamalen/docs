<a href="https://app.naas.ai/user-redirect/naas/downloader?url=https://raw.githubusercontent.com/jupyter-naas/awesome-notebooks/master/SharePoint/SharePoint_Get_file.ipynb" target="_parent"><img src="https://naasai-public.s3.eu-west-3.amazonaws.com/open_in_naas.svg"/></a>

**Tags:** #sharepoint #productivity #naas_drivers #operations #snippet

**Author:** [Florent Ravenel](https://www.linkedin.com/in/florent-ravenel/)

This notebook get file from your SharePoint.

## Input

### Import libraries


```python
from naas_drivers import sharepoint
import naas
```

### Setup SharePoint


```python
# SharePoint credentials
SP_ENDPOINT = naas.secret.get("SP_ENDPOINT") or "ENTER_YOUR_SP_ENDPOINT_HERE"
SP_USERNAME = naas.secret.get("SP_USERNAME") or "ENTER_YOUR_SP_USERNAME_HERE"
SP_PASSWORD = naas.secret.get("SP_PASSWORD") or "ENTER_YOUR_SP_PASSWORD_HERE"
SP_SITE = naas.secret.get("SP_SITE") or "ENTER_YOUR_SP_SITE_HERE"

# File path in SharePoint
FILE_PATH_SOURCE = "ENTER_YOUR_FILE_PATH_SOURCE_HERE"

# File path in your local
FILE_PATH_DESTINATION = "ENTER_YOUR_FILE_PATH_DESTINATION_HERE" 
```

## Model

### Get file


```python
file = sharepoint.connect(SP_ENDPOINT, SP_USERNAME, SP_PASSWORD, SP_SITE).get_file(FILE_PATH_SOURCE, FILE_PATH_DESTINATION)
```

## Output

### Display result


```python
file
```
