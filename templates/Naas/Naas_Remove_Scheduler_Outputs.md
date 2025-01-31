<a href="https://app.naas.ai/user-redirect/naas/downloader?url=https://raw.githubusercontent.com/jupyter-naas/awesome-notebooks/master/Naas/Naas_Remove_Scheduler_Outputs.ipynb" target="_parent"><img src="https://naasai-public.s3.eu-west-3.amazonaws.com/open_in_naas.svg"/></a>

**Tags:** #naas #scheduler #automation #operations

**Author:** [Maxime Jublou](https://www.linkedin.com/in/maximejublou)

The goal of this notebook is to remove your production scheduler outputs automatically.

## Input

### Import library


```python
import glob
import os
import naas
```

### Schedule your notebook


```python
# Schedule your notebook everyday at 9 AM
naas.scheduler.add(cron="0 9 * * *")

#-> Uncomment the line below to remove your scheduler
# naas.scheduler.delete()
```

## Model

### Remove scheduler outputs.


```python
def remove_scheduler_outputs():
    for scheduler_output in glob.glob('/home/ftp/.naas/home/ftp/**/*__output_*.ipynb', recursive=True):
        os.remove(scheduler_output)
        print(f'✅ DELETED: {scheduler_output}')
```

## Output


```python
remove_scheduler_outputs()
```
