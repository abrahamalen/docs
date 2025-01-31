<a href="https://app.naas.ai/user-redirect/naas/downloader?url=https://raw.githubusercontent.com/jupyter-naas/awesome-notebooks/master/LinkedIn/LinkedIn_Send_message_to_profile_from_post_likes.ipynb" target="_parent"><img src="https://naasai-public.s3.eu-west-3.amazonaws.com/open_in_naas.svg"/></a>

**Tags:** #linkedin #post #likes #naas_drivers #message #content #snippet

**Author:** [Florent Ravenel](https://www.linkedin.com/in/florent-ravenel/)

## Input

### Import libraries


```python
from naas_drivers import linkedin
import pandas as pd
import naas
import time
```

### Setup LinkedIn
👉 <a href='https://www.notion.so/LinkedIn-driver-Get-your-cookies-d20a8e7e508e42af8a5b52e33f3dba75'>How to get your cookies ?</a>


```python
# Credentials
LI_AT = 'YOUR_COOKIE_LI_AT'  # EXAMPLE AQFAzQN_PLPR4wAAAXc-FCKmgiMit5FLdY1af3-2
JSESSIONID = 'YOUR_COOKIE_JSESSIONID'  # EXAMPLE ajax:8379907400220387585

# Post url
POST_URL = "POST_URL"

# Message
MESSAGE = "Hi there, thanks for liking my post !"
```

### Setup Outputs


```python
# Post likes
csv_post_likes = f"LINKEDIN_POST_LIKES_{POST_URL.split('activity-')[1].split('-')[0]}.csv"
```

## Model

### Get likes from post


```python
df_post_likes = linkedin.connect(LI_AT, JSESSIONID).post.get_likes(POST_URL)
print("👍 Post likes :", len(df_post_likes))
df_post_likes.tail(1)
```

### Get connections from post likes


```python
def get_connections(df):
    for index, row in df.iterrows():
        df_network = pd.DataFrame()
        profile = row["PUBLIC_ID"]
        print(f"➡️ Checking :", profile)
        
        # Get distance with profile
        if profile != 0:
            df_network = linkedin.connect(LI_AT, JSESSIONID).profile.get_network(profile)
            
        # Check if profile is already in your network
        if len(df_network) > 0:
            distance = df_network.loc[0, "DISTANCE"]
            df.loc[index, "DISTANCE"] = distance
            df.to_csv(csv_post_likes, index=False)
    return df

df_profile = get_connections(df_post_likes)
df_profile
```

## Output

### Send message to connections


```python
def send_message(df):
    df = df[df.DISTANCE == "DISTANCE_1"].reset_index(drop=True)
    for index, row in df.iterrows():
        fullname = row["FULLNAME"]
        firstname = row["FIRSTNAME"]
        profile_id = row["PROFILE_ID"]
        message_custom = MESSAGE.replace("Hi there,", f"Hi {firstname},")
        print(f"➡️ Sending to :", fullname)
        
        # Get distance with profile
        try:
            linkedin.message.send(content=message_custom, recipients_url=profile_id)
        except Exception as e:
            print("❌ Message not sent", e)
        time.sleep(3)
    return df

df_message = send_message(df_profile)
df_message
```
