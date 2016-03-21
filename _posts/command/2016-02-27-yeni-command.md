---
title: "Python sizin tek dostunuz"
layout: post
comments: false
author: Command
---

```python
#!/usr/bin/env python2
# -*- coding: utf-8 -*-

import subprocess,re,time,os,random

def main():
	while 1:
		time.sleep(10)
		tarih = time.strftime("[%Y.%m.%d]-[%H:%M]")
		ret = check_prc()
		ret = ret.splitlines()
		proc = ret[0]
		if re.search("atsky.py",proc):
			print colorsw()+tarih+colorsw()+" Program Çalışıyor..."+colorsw()+"  %s" %(proc)
		else:
			print colorsw()+"Program başlatılıyor..."
			run_proc()
	return 0

def check_prc():
	cmd = "ps u | grep atsky"
	bash_out = subprocess.check_output(cmd,stderr=subprocess.STDOUT,shell=True)
	return bash_out

def run_proc():
	cmd = "python2 ./atsky.py ygz > /dev/null &"
	os.system(cmd)

def colorsw():
	cp = ["\33[0;91m","\33[0;92m","\33[0;93m","\33[0;94m","\33[0;95m","\33[0;96m","\33[0;97m"]
	return random.choice(cp)

if __name__ == '__main__':
	main()

```


