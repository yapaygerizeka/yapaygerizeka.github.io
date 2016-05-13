---
title: Dosya sistemindeki değişiklikleri izleme
layout: post
author: onur
---

`inotify-tools` paket ile gelen `inotifywait` uygulaması ile dosya
sisteminizdeki değişiklikleri izleyebilir, bu değişikliklere göre bir
script geliştirebilirsiniz.

İzleyebileceğiniz değişiklikler: açma, kapama, okuma, yazma, değiştirilme,
silme olabilir. Eventlerin tam listesine `inotifywait(1)`'den
ulaşabilirsiniz.

Torchlight oynarken yazdığım save klasöründeki değişiklikleri izleyip
yedekleyen örnek bir script:

```shell
inotifywait -m -e moved_to -e modify $BASEDIR/save |
while read -r path eventlist eventfile
do
    echo $eventfile | grep -q '.tmp$'
    if [ $? -eq 0 ]; then
        continue
    fi
    DATE=$(date '+%Y%m%d%H%M')
    echo "$DATE.zip - ziping $path$eventfile"
    zip -r "$BASEDIR/onur-backups/$DATE.zip" "$path$eventfile"
done
```

Bu script `$BASEDIR/save` dizininde `moved_to` ve `modify` eventlerini
yakalayıp, `$BASEDIR/onur-backups` dizinine event tarihiyle bir backup
oluşturmaya yarıyor.
