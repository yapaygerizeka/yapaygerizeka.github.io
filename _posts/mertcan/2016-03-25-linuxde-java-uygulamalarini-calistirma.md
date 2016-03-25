---
layout: post
title: Linux'de Java Uygulamalarını Çalıştırma
date: 2016-03-25
type: post
author: Mertcan
categories: Linux
description: Kullanmamız gereken java uygulamaları oluyor çoğu zaman
---

Kullanmamız gereken java uygulamaları oluyor çoğu zaman bunlarıda `java -jar` komutu veripde konsolda çalıştırmaktan gına geldi ayrıca çift tıklama ile çalıştırmayıda istiyordum herkes gibi bende düşündüm ya bunu nasıl yaparız hemen bi google araştırması hemen bi RTFM ve karşıma aşağıdaki gibi bir yapı oluşturma yolu gözüktü çünkü çift tıklama işini `/usr/share/applications/*` yolu içerisindeki dosyalar sayesinde yapıyorduk

Java için çift tıklama şeklinde çalıştırma işlemimizi gerçekleştirecek olan bu kodu yukarıdaki yazan yola giderek bir adet `java.desktop` oluşturarak rahatlıkla yapabilirsiniz.

```
[Desktop Entry]
Name=Java Application
Comment=Java Application
GenericName=Java Application
Keywords=java
Exec=java -jar %f
Terminal=false
X-MultipleArgs=false
Type=Application
MimeType=application/x-java-archive
StartupNotify=true
```

Bu kodları eklediğiniz andan itibaren ön tanımlı olarak ayarlarsanız `.jar` uzantılı tüm dosyaları bu yöntem ile kolaylıkla açabileceksiniz.
