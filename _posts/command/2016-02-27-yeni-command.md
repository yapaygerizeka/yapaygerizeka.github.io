---
title: Python sizin tek dostunuz
layout: post
comments: false
author: Command
---

```python
def mpdcontrol():
    #lamerlik dizboyu
    home = os.getenv("HOME")
    if os.path.exists(home+"/.mpd/mpd.pid"):
        return True
    else:
        return False
```


