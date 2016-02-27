---
title: Debian kurarken karşılaştığım bazı sorunlar ve çözümü
layout: post
comments: false
---

Eski kurulumumun birçok gereksiz paket ve dosyayla dolmasının üzerine yedeklerimi alıp sıfırdan kurulum yapmayı planlıyordum çoktandır. Nihayet bugün Xubuntu'yu silip Debian kurmaya karar verdim. Öncelikle kampüste internet yeterince iyi olduğu için netinstall kalıbını indirip elimdeki SD karta yazdırdım. Normal cd ya da dvd kalıplarının yerine netinstall seçmemin nedeni boyutunun diğerlerine göre daha küçük olması ve aynı işlevi görmesi oldu. SD kart sorunsuzca boot ettikten sonra grafiksel kurulumu seçip ilerledim. Bu arada grafiksel kurulumun son derece stabil ve  hoş tasarlandığını söylemeden edemeyeceğim.

Yaşadığım ilk sorun Installerin "Ya aga ben cd yi bulamadım, cd nerede ?" demesi oldu :) Tabii ki böyle demesi normal çünkü bu kalıp cd ye yazdırmak için tasarlanmış ama buradan Debian geliştiricilerine sesleniyorum: Ya sene 2016 olmuş CD ne aq ? Ayrıca ikide bir taşınabilir aygıttan sürücüleri kurayım mı ? diyor, Windows kuruyoruz sanki :(
Neyse, bu sıkıntıyı şu şekilde aştım:

[![](https://3.bp.blogspot.com/-Usd0MT6gRw0/Vre3-c2sLbI/AAAAAAAAQf8/nS2ma4fPkBE/s400/IMG_20160207_231910.jpg)](https://3.bp.blogspot.com/-Usd0MT6gRw0/Vre3-c2sLbI/AAAAAAAAQf8/nS2ma4fPkBE/s1600/IMG_20160207_231910.jpg) 
[![](https://1.bp.blogspot.com/-RYI7-foJ1OQ/Vre4FaO7ZEI/AAAAAAAAQgA/D3xNgZRYIng/s400/IMG_20160207_231922.jpg)](https://1.bp.blogspot.com/-RYI7-foJ1OQ/Vre4FaO7ZEI/AAAAAAAAQgA/D3xNgZRYIng/s1600/IMG_20160207_231922.jpg)
[![](https://1.bp.blogspot.com/-weaW1t04dS0/Vre4V64gh7I/AAAAAAAAQgE/TTM80Wl6YUw/s400/IMG_20160207_231933.jpg)](https://1.bp.blogspot.com/-weaW1t04dS0/Vre4V64gh7I/AAAAAAAAQgE/TTM80Wl6YUw/s1600/IMG_20160207_231933.jpg)  
[![](https://4.bp.blogspot.com/-jsroUyHnSVo/Vre4b2DRHvI/AAAAAAAAQgI/CcN_ZsWmOeI/s400/IMG_20160207_231947.jpg)](https://4.bp.blogspot.com/-jsroUyHnSVo/Vre4b2DRHvI/AAAAAAAAQgI/CcN_ZsWmOeI/s1600/IMG_20160207_231947.jpg)

`/dev/mmcblk0`  kurulumu yaptığım SD kartın aygıt adresi. Siz bunun yerine usb bellek kullanıyorsanız onun aygıt adresini vermeniz gerekiyor.
Yaşadığım ikinci ve en çok canımı sıkan sorun ise kurulum sırasında **discover** kurulurken **Tetikçiler işleniyor libc-bin** kısmında **kurulumun donmasıydı**. Aynı sıkıntıyı bir Ubuntu türevi daha önce de yaşadığımı hatırlıyorum ve o zaman için çözüm bulamamıştım.

[![konsoldan sistemin donduğu ana ait çıktılar](https://2.bp.blogspot.com/-8aR80-_o_zI/Vre6bKM6lUI/AAAAAAAAQgc/Ul-q9SrPtaU/s400/IMG_20160207_153525.jpg)](https://2.bp.blogspot.com/-8aR80-_o_zI/Vre6bKM6lUI/AAAAAAAAQgc/Ul-q9SrPtaU/s1600/IMG_20160207_153525.jpg)

Kurulum yaptığım makina 4GB belleğe sahip olduğundan Debian kurulum esnasında otomatik olarak pae kernel atamış. Kurulumun Libc kısmında tamamen donması bana kernel ile ilgili bir uyumsuzluk olabileceğini düşündürdüğünden kurulumu bu sefer Uzman Grafiksel Kurulum modunda başlatıp pae olmayan bir kernel seçerek kuruluma devam ettim. Ve Bingo ! Böylelikle kurulum sorunsuzca bitti :)

