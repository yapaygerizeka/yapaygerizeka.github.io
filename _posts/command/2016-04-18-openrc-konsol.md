---
title: "OpenRC: Türkçe UTF terminal"
layout: post
comments: false
author: Command
---

Evet sevgili takipcilerim 

Gün geçmiyorki GNU/Linux aleminde bir sorunla karşılaşmayalım bu günki sorunumuz
OpernRC ile terminali nasıl türkçeleştiririm eğer benim gibi "illaki türkçe karakterleri görmeliyim" takıntılıysanız
conf dosyasını ayarlamayı ihmal etmeyesiniz

buyrun efenim dosyamız "/etc/conf.d/consolefont" içeriğide şu şekilde olacak

```
consolefont="ter-v16n"
consoletranslation="8859-9_to_uni"
```

dosyayı kaydettikten sonra 
```
cd /etc/init.d/
./consolefont restart
```

işte bu kadar sisteminizde artık türkçe karakterler sorunsuz 
tadını çıkarın <3
