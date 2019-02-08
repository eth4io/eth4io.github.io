---
layout: post
title:  "Python: config files to store credential for open source project"
date:   2019-02-08 12:19:00 +1100
categories: python
author: eth4io
---

------



a config file helps an open source project ignore the credentials which you probabaly don't want to push it to a public repository.



`config.json`

```json
{
    "password":"my_password",
}
```



```python
import os

def init():
    dir_path = os.path.dirname(os.path.realpath(__file__))
    PASSWORD = 'PASSWORD'

    with open(dir_path + '/config.json') as config_json:
        config = json.load(config_json)
        password = config[PASSWORD]

```



.gitignore

```
config.json
```

