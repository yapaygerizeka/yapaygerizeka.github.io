---
title: Python sizin tek dostunuz
layout: post
comments: false
author: Command
---

```python
def hava(sehir):
	sehir = sehir.replace("ı","i").replace("ş","s")\
	.replace("ç","c").replace("ö","o").replace("ğ","g").replace("ü","u")
	try:
		response = urllib2.urlopen('http://www.mynet.com/havadurumu/asya/turkiye/%s' % sehir,timeout = 20)
		strtext = response.read().decode("utf-8")
		response.close()
		#<span class="hvDay">Pazar</span> = gün
		#<span class="hvMood">Kar Yağışlı</span> = durum
		#<span class="hvDeg1">-10°C</span> = deger
		ey = re.compile('(<span class="hvDeg1">.+<\/span>)')
		ed = re.compile('(<span class="hvDeg2">.+<\/span>)')
		dr = re.compile('(<span class="hvMood">.+<\/span>)')
		yuk = re.findall(ey, strtext)
		dsk = re.findall(ed, strtext)
		durum = re.findall(dr, strtext)
		if durum[0]:
			print "hava durumu: ok"
			return sehir.capitalize()+": "+htmlpars_native(durum[0])+\
			" ( En Yüksek:"+htmlpars_native(yuk[0])+", En düşük:"+htmlpars_native(dsk[0])+" )"
		else:
			print colorsw()+"hava durumu null: %s" %(sehir)
			return "null"
	except urllib2.HTTPError as e:
		print "Hava Durumu: %s" %e
		return "null"
	except Exception as e:
		print "Hava Durumu: "+str(e)
		return "null"
```


