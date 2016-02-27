# Örnek

Bu bir örnek yazıdır.

Jekyll'da yeni bir post `_posts` klasoru altına oluşturulur. Bizim sitemiz
birden fazla yazar tarafından oluşturulduğundan, `_posts/yazar` dizini
tercih edilmelidir. Post dosya adında tarih kullanılabilir ya da tarih daha
sonra sayfa içerisine eklenebilir. Örnegin onur yazarı `linux` başlıklı
yeni bir yazı yazmak istediğinde `_post/onur/2016-02-07-linux.md` dosyasına
yazmalıdır.

Jekyll da her sayfanın bir ön eki bulunmalıdır. Bu ön ek sayfanın başlığını
ve kullanacağı temayı belirler. Ön ek `---` ile başlayıp yine ayni karakter
dizisiyle biter. Örnek bir ön ek:

```
---
layout: post
title: Example content
author: onur
---
```

Markdown çok basit bir biçimlendirme yapısına sahiptir. Bir kaç örnek:

Başlıklar # ile başlar.

# 1. Seviye başlık
## 2. Seviye başlık
### 3. Seviye başlık
#### 4. Seviye başlık
##### 5. Seviye başlık
###### 6. Seviye başlık

Listeler basinda * olarak yazilabilir. * yerine - de kullanılabilir:

* Bu bir liste itemi.
* Baska bir liste itemi.
* İtalic yazılar *böyle* olmalıdır.
* Bold kullanma isterseniz **bu şekilde** yazabilirsiniz.
* Satır içinde kod bloğu `arasında` yer alır.

İsterseniz listeniz sayısal da olabilir:

1. Bu bir liste
2. Evet harika değil mi


Link vermek için: [google](https://google.com) kullanılır.

Eğer uzun bir kod bloğu paylaşmak isterseniz:

```c
int main() {
    return 0;
}
```

Bu kod C dili olarak tanımlandığından, sistem otomatikmen renklendirir.

Resimler:

![yazi](http://placehold.it/800x400 "Bu bir resimdir")
