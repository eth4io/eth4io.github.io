---
layout: post
title:  "Python: config files to store credential for open source project"
date:   2019-02-08 12:19:00 +1100
categories: python
author: eth4io
---

------



A config file helps an open source project ignore the credentials which you probabaly don't want to push it to a public repository.



config.json

```json
{
    "password":"my_password",
    "credentials":"my_credentials"
}
```



```python
import os
import json

DIR_PATH = os.path.dirname(os.path.realpath(__file__))

def init():
    with open(os.path.join(DIR_PATH, 'config.json') as config_json:
        config = json.load(config_json)
        password = config['password']
        credentials = config['credentials']

```



Add `.gitignore` to ignore the config file

```
config.json
```

