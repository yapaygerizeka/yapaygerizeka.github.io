---
layout: post
title: Manjaro Siyah Ekran Sorunu Ve Çözümü
date: 2016-04-13
type: post
author: Mertcan
categories: Linux
description: Deneme amaçlı 2 adet laptobuma Manjaro kordum hali hazırda birinde sıkıntı yaşatmazken diğerinde
---

Deneme amaçlı 2 adet laptobuma Manjaro kordum hali hazırda birinde sıkıntı yaşatmazken diğerinde haliyle **NVIDIA** driver kuruluydu 4.günün sonunda haliyle bi siyah ekran aldık bildiğiniz üzere non-free sürücüler içerisinde en leş olanı NVIDIA bunu çözmek için ise aşağıdaki yöntemi uyguladım.

Bilgisayarı yeniden başlattım ve ön yükleme aşamasında `CTRL + ALT + F2` yaparak `TTY` ekranımıza geçişi yaptım.Deneme yanılma ile çözeceğimi hiç düşünmemiştim ama biraz öyle oldu ilk olarak interneti getirmem gerekiyordu çünkü bağlanmamıştı ve hemen aşağıdaki komutu verdim

```
sudo systemctl start NetworkManager
```

daha sonra tekrar mesa-libgl kurayım dedim.Siyah ekran sıkıntısını bunun çıkarttığını stackoverda okumuştum çünkü

```
sudo pacman -S mesa-libgl
```

kurulum esnasında ekran kartınız ile ilgili bir seçenek çıkıcak karşınıza siz sıkıntı çektiğinizi seçeceksiniz **NVIDIA** yani

eğer bir sıkıntı olursa yada el ile ayarlayacam ben ya aderseniz aşağıdaki komutu kullanabilirsiniz.

**NVIDIA Kartlar**

```
sudo mhwd-gpu --setgl nvidia --setxorg /etc/X11/mhwd.d/nvidia.conf
```


**INTEL Kartlar**

```
sudo mhwd-gpu --setgl intel --setxorg /etx/X11/mhwd.d/intel.conf
```

**ATI Kartlar**


```
sudo mhwd-gpu --setgl mesa --setxorg /etc/X11/mhwd.d/ati.conf
```
veya

```
sudo mhwd-gpu --setgl catalyst --setxorg /etc/X11/mhwd.d/catalyst.conf
```

**ATI Ekran** kartlarında karşılaşmazsınız ancak ne olur ne olmaz size aşağıdaki seçenekleri sunmak istiyorum.Bu sorunu kolaylıkla çözebilirsiniz.Tüm bu işlemler bittikten sonra sistemi yeniden başlatmanız gerekiyor ki normal olarak çalıştırın.

```
sudo reboot
```

Ben dün yaşamış olduğum Black Screen sorununu bu şekilde çözdüm XORG kardeş genelde drive den dolayı patlıyor.Normalde yükleniyor herşey geliyor ama siz görmüyorsunuz haliylede başınıza iş açıyor.Yukarıdaki yöntem işinize bir nebze yarayacak eğer hala çözülmez ise free sürücüyü kurarak işinize devam edebilirsiniz.

**_dipnot: Yukarıda yazılanlar Kernel 4.4.6 da denenmiştir._**

Öptüm bye <3
