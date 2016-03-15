---
title: Aşama Aşama Vim Öğrenin
date: Tue, 15 Mar 2016 18:26:36 +0200
layout: post
author: onur
comments: true
---

*En hızlı şekilde Vim (insanoğlu tarafından bilinen en iyi editör) öğrenmek
istiyorsanız benim yöntemim bu: Dayanacacak kadar asgâri düzeyde
başlayın ve diğer püf noktaları zamanla öğrenin.*

### Altı Milyar Dolarlık editör: *Vim*

> *Daha iyi, Güçlü, Hızlı.*

Vim'i bir kere öğrenin ve vim kullandığınız tek editör olacaktır. Bildiğim
daha iyi bir editör yok. Öğrenmesi zor fakat kullanılabilirliği olağanüstü
düzeyde.

Size Vim'i öğrenebileceğiniz dört adım öneriyorum:

1. Dayanın
2. Daha rahat işlem yapın
3. Daha iyi, güçlü ve hızlı olun
4. Vim'in süpergüçlerini kullanın

Bu yolculuğun sonunda bir Vim süperstarı olacaksınız.

Fakat başlamadan önce bir uyarı yapayım. Vim'i öğrenmek ilk başlarda biraz
sancılı olabilir ve zaman alabilir. Bu, bir müzik enstrümanı çalmaya çok
benziyor. 3 gün içerisinde Vim'de diğer editörlerden daha verimli olmayı
beklemeyin. İşin aslı 3 gün değil, 2 hafta da sürebilir.


### Seviye 1: Dayanın

1. Vim'i kurun
2. Vim'i çalıştırın
3. BAŞKA HİÇ BİR ŞEY YAPMAYIN! Sadece okuyun.

Standart bir editörde klavyeden bir şey yazmak, ekranda yazdığınızı
görmeniz için yeterli. Vim *Normal* moddayken, bu geçerli değil. *Insert*
moduna geçelim.  `i` harfine basın.

Biraz daha iyi hissediyor olmalısınız. Harfleri standart bir editör
kullanıyormuş gibi yazabilirsiniz. *Normal* moda geçmek için `ESC` tuşuna
basın.

Artık *Insert* ve *Normal* modları arasında nasıl geçiş yapabildiğinizi
biliyorsunuz. Şimdi *Normal* modda hayatta kalmanız için gerekli komutlara
bakalım:

> * `i` → *Insert* moduna geçer. *Normal* moda geçmek için `ESC` tuşuna basın.
> * `x` → İşaretci altında yer alan karakteri siler.
> * `:wq` → Kaydet ve Çık (`:w` kaydet, `:q` çık).
> * `dd` → Satırı siler (ve kopyalar).
> * `p` → Yapıştır (paste).
>
> Öneriler:
>
> * `hjkl` (gerekli değil fakat büyük ölçüde önerilir) → İşaretci
>   hareketlerini sağlar (←↓↑→). *İpucu:* `j` aşağı oka benziyor.
> * `:help <komut>` → `<komut>` hakkında yardım gösterir. Genel bir
>   yardım almak için `:help`'i `<komut>` olmadan  kullanabilirsiniz.

Başlarken ihtiyacınız olan her şey sadece bu 5 komut. Bu komutları
kullanmanız artık doğal bir hal aldığında (belki birkaç gün sonra), ikinci
seviyeye geçebilirsiniz.

Fakat öncelikle, *Normal* mod hakkında bir açıklama yapayım. Standart
editörlerde kopyalama yapmak için `Ctrl` tuşu kullanılır (genelde
`Ctrl-c`). Aslında siz `Ctrl`'ye bastığınızda, diğer tuşların davranışı
değişir. Vim'in normal modu, editörün sizin yerinize sürekli
`Ctrl`'ye basması gibi yorumlanabilir.

Yazı içerisinde yer alan gösterimler hakkında son bir söz:

* `Ctrl-λ` yazmak yerine, `<C-λ>` yazacağım.
* `:` ile başlayan komutlar `<enter>` ile biter. Örneğin `:q` yazdığımda,
  `:q<enter>`'i kastediyorum.


### Seviye 2: Daha rahat işlem yapın

Hayatta kalmak için gereken komutları artık biliyorsunuz. Bir kaç yeni
komut öğrenmenin zamanı geldi. Benim önerilerim şunlar:

1. Çeşitli Insert modu geçişleri:

   > * `a` → İşaretciden sonrasına ekle.
   > * `o` → Şimdiki satırdan sonrasına ekle.
   > * `O` → Şimdiki satırdan öncesine ekle.
   > * `cw` → İşaretci üzerindeki kelimeyi sil ve ekle.

2. Temel hareketler:

   > * `0` → İlk sütuna git.
   > * `^` → Satırdaki ilk boş olmayan karaktere git.
   > * `$` → Satırın sonuna git.
   > * `g_` → Satırdaki son boş olmayan karaktere git.
   > * `/şablon` → `şablon`'u ara

3. Kopyala/Yapıştır

   > * `P` → Öncesine yapıştır, hatırlayın `p` şimdiki pozisyonun sonrasına
   >   yapıştırıyor.
   > * `yy` → Satırı kopyala, `ddP`'nin aynısı ve daha kolayıdır.

4. Geri/İleri al

   > * `u` → Geri al
   > * `<C-r>` → İleri al

5. Aç/Kaydet/Çık/Dosya değiştir (buffer).

   > * `:e <yol/dosya>` → Dosya aç
   > * `:w` → Kaydet
   > * `:saveas <yol/dosya>` → `<yol/dosya>`'ya kaydet
   > * `:x`, `ZZ` veya `:wq` → Kaydet ve çık (`:x` sadece gerekliyse
   >   kaydeder).
   > * `:q!` → Kaydetmeden çık, ayrıca `:qa!` başka değiştirilmiş bufferlar
   >   varsa bile çıkar.
   > * `:bn` (önceki: `:bp`) → Sonraki (veya önceki) dosyayı göster
   >   (buffer)

Bu komutları zaman içerisinde öğrenin ve öğrendikten sonra diğer
editörlerde yapabildiğiniz herşeyi Vim içerisinde de yapacak hale
gelirsiniz. Biraz garip hissediyor olabilirsiniz fakat yazıyı okumaya devam
ederseniz bir sonraki seviyede vim'i öğrenmeye neden değeceğini göreceksiniz.


### Seviye 3:  Daha iyi, Güçlü, Hızlı

Buraya kadar gelebildiğiniz için tebrikler! Artık daha ilgi çekici şeyleri
yapmaya başlayabiliriz. Bu seviyede sadece eski vi editörüyle uyumlu
komutlar hakkında konuşacağız.

#### 3.1 Daha iyi

Tekrar eden şeyler Vim'de nasıl yapılıyor bir bakalım:

1. `.` →  (nokta) son komutu tekrar eder
2. `N<komut>` → komutu N kere tekrar eder

Bazı örnekler, bir dosya açın ve şunları yazın:

> * `2dd` → 2 satırı siler.
> * `3p` → 3 kere yapıştırır.
> * `100idesu [ESC]` → "desu desu desu desu desu desu desu desu desu desu
>    desu desu desu desu desu desu desu desu desu desu desu desu desu desu
>    desu desu desu desu desu desu desu desu desu desu desu desu desu desu
>    desu desu desu desu desu desu desu desu desu desu desu desu desu desu
>    desu desu desu desu desu desu desu desu desu desu desu desu desu desu
>    desu desu desu desu desu desu desu desu desu desu desu desu desu desu
>    desu desu desu desu desu desu desu desu desu desu desu desu desu desu
>    desu desu desu desu desu desu" yazar.
> * `.` → 100 kere desu yazan komutu tekrar çalıştırır.
> * `3.` → 3 kere desu yazar (300 değil, gayet zekice).


#### 3.2 Güçlü

Vim'de nasıl daha verimli gidebileceğinizi bilmek *çok* önemlidir. Bu
bölümü kesinlikle atlamayın.

1. `NG` → N'inci satıra gider (N bir sayı).
2. `gg` → Dosyanın başlangıcına gider - `1G`'nin kısayoludur.
3. `G` → Son satıra gider.
4. Kelime hareketleri:

   > 1. `w` → Kelimenin başlangıcına gider.
   > 2. `e` → Kelimenin sonuna gider.
   >
   > Varsayılan olarak kelimeler; harf, sayılar ve alt tireden oluşur.
   > *KELIME*'ye boşluk ile ayrılan karakterler diyelim. Eğer siz bu
   > tanımdaki *KELIME*'ler ile çalışıyorsanız, bu komutların büyük harfle
   > olanını kullanın.
   >
   > 1. `W` → *KELIME*'nin başına gider.
   > 2. `E` → *KELIME*'nin sonuna gider.
   >
   > ![kelimeler](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/word_moves.jpg)


Şimdi *çok* verimli hareketlere bakalım:

> * `%` → `(`, `{`, `[`'e gider
> * `*` (önceki: `#`) → İşaretci altında bulunan kelimenin bir sonrakine
>   (veya öncekine) gider.

İnanın son üç komut altın değerinde.


#### 3.3 Hızlı

Vi hareketlerinin ne kadar önemli olduğunu hatırladınız mı? Nedenini
söyleyeyim. Birçok komut şu biçimde kullanılır:

```
<başlangıç pozisyonu><komut><bitiş pozisyonu>
```

Örneğin; `0y$` şunları yapar:

* `0` → Satırın başlangıcına git.
* `y` → Buradan kopyalamaya başla ...
* `$` → ... satırın sonuna kadar

`ye` gibi, imleçten kelimenin sonuna kadar kopyala. Ayrıca, `y2/foo` ikinci
"foo" geçen yere kadar kopyala.

`y` (yank) için geçerli olan her şey; `d` (delete) için de, `v` (visual
select [görsel seçim]) için de, `gU` (büyük harf) için de, `gu` (küçük
harf) vb. için de geçerlidir.



### Seviye 4: Vim Süpergüçleri

Buraya kadar öğrendiğiniz komutlarla Vim'i gayet rahat kullanabilirsiniz.
Fakat bundan sonra Vim'i diğer editörlerden ayıran "ölümcül" özelliklerine
bakacağız. Bunların bazıları Vim'i kullanmaya başlamamın nedenidir.


#### 4.1 Satır içi hareketler: `0 ^ $ g_ f F t T , ;`

> * `0` → 0'ıncı sütuna git.
> * `^` → Satırdaki ilk karaktere git.
> * `$` → Satırdaki son sütuna git.
> * `g_` → Satırdaki son karaktere git.
> * `fa` → `a` harfinin geçtiği bir sonraki yere git. `,` (önceki: `;`) bir
>   sonrakine (veya öncekine) gider.
> * `t,` → `,` karakterinin bir öncesine gider.
> * `3fa` → Satırdaki 3'üncü `a`'ya gider.
> * `F` ve `T` → `f` ve `t` gibidir fakat tersine gider.
>
> ![geçisler](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/line_moves.jpg)

Kullanışlı bir tüyo: `dt"` → `"`'e kadar olan herşeyi siler


#### 4.2 Alan seçimleri `<eylem>a<nesne>` veya `<eylem>i<nesne>`

Bu komutlar sadece *visual* modda bir operatörün ardından kullanılır. Çok
güçlülerdir ve şöyle yazılır:

`<eylem>a<nesne>` ve `<eylem>i<nesne>`

Eylem; `d` (delete [sil]), `y` (yank [kopyala]), `v` (görsel mod seçimi)
gibi herhangi bir eylem olabilir. Nesne; kelime: `w`, *KELIME* (extended
word): `W`, cümle: `s`, paragraf: `p` olabilir. Ayrıca; `"`, `'`, `)`, `}`,
`]` gibi bir karakter de olabilir.

Diyelim imleç `(map (+) ("foo"))` içerisinde yer alan ilk `o` üzerinde:

> * `vi"` → `foo` seçer.
> * `va"` → `"foo"` seçer.
> * `vi)` → `"foo"` seçer.
> * `va)` → `("foo")` seçer.
> * `v2i)` → `map (+) ("foo")` seçer.
> * `v2a)` → `(map (+) ("foo"))` seçer.
>
> ![textobjects](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/textobjects.png)


#### 4.3 Dörtgen blokların seçimi: `<C-v>`

Dörtgen bloklar birçok satırı yorum haline getirirken çok kullanışlıdır.
Örneğin: `0<C-v><C-d>I-- [ESC]`

* `^` → Satırda ki ilk boş olmayan karaktere git.
* `<C-v> → Blok seçimine başla.
* `<C-d> → Aşagı in (`jjj` veya `%` vb. de olabilir).
* `I-- [ESC]` → Her bir satıra `--` ekle.

![rectangular-blocks](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/rectangular-blocks.gif)

Not: Windows kullanıyorsanız ve clipboard boş değilse `<C-v>` yerine
`<C-q>` kullanmanız gerekebilir.


#### 4.4 Tamamlama: `<C-n>` ve `<C-p>`

Insert modundayken bir kelime yazmaya başlayın ve ardından `<C-p>` büyüsünü
yapın...

![magic](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/completion.gif)


#### 4.5 Makrolar `:qa` bir şey yapın `q`, `@a`, `@@`

`qa` yaptıklarınızı `a` işaretçisine kaydeder. Ardıdan `@a`, `a`
işaretçisine kaydedilmiş makroları oynatır. `@@` son çalıştırılmış makronun
bir kısayoludur.

> Örnek:
>
> Sadece içerisinde 1 sayısı bulunan bir satırda şunları yazın:
>
> * `qaYp<C-a>q` →
>   * `qa` kayda başlar
>   * `Yp` satırın bir kopyasını oluşturur
>   * `<C-a>` sayıyı arttırır
>   * `q` kaydı sonlandırır
> * `@a` → 1 altına 2 yazar
> * `@@` → 2 altına 3 yazar
> * `100@@` yaptığınızda 103 olana kadar yeni sayılar oluşturur.
>
> ![macros](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/macros.gif)


#### 4.6 Görsel Seçim: `v`, `V`, `<C-v>`

`<C-v>` kullandığımız bir örnek görmüştük. Ayrıca `v` ve `V` var. Seçim
yapıldıktan sonra yapabileceğiniz şeyler:

* `J` → satırları birleştir
* `<` (veya `>`) → satırları sola (veya sağa) kaydır
* `=` → satırları otomatik kaydır

![autoindent](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/autoindent.gif)

Görsel seçilmiş satırların sonuna bir şey ekleme:

* `<C-v>`
* İstediğiniz satıra gidin (`jjj` veya `<C-d>` veya `/şablon` veya `%` vb.)
* `$` ile satır sonuna gidin
* `A`, ekleyeceğinizi yazın, `ESC`.

![append_many_lines](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/append-to-many-lines.gif)


#### 4.7 Bölümler: `:split` ve `:vsplit`

Bunlar en önemli komutlardır fakat bunları öğrenmek için `:help split`'e
bakın.

* `:split` → bir bölüm oluştur (`:vsplit` dikey bir bölüm oluştur).
* `<C-w><yön>` → bölümü değistir, Yön herhangi bir `hjkl` veya ←↓↑→ olabilir.
* `<C-w>_` (dikey `<C-w>|`) → Bölüm boyutunu ekran kadar yapar.
* `<C-w>+` (tersi `<C-w>-`) → Bölüm boyutunu arttırır veya azaltır.

![split](http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/split.gif)


### Sonuç

Bunlar her gün kullandığım komutların %90'ıydı. Size her gün bir ya da iki
yeni komut öğrenmenizi tavsiye ediyorum. İki-üç hafta sonra vim'in gücünü
ellerinizde hissedeceksiniz.

Vim öğrenmek, hatırlamaktan çok kendinizi geliştirmeniz ile alakalı. Neyse
ki Vim çok iyi araçlar ve mükemmel bir dökümantasyon ile gelmekte. Temel
komutlara hakim olduktan sonra vimtutor'u çalıştırın. Ayrıca şu sayfayı
dikkatlice okumalısınız: `:help usr_02.txt`.

Ardıdan; `!`, katlamalar, işaretciler, eklentiler ve daha birçok özelliği
ögreneceksiniz. Vim'i piyano çalmayı öğrenir gibi öğrenirseniz hiç bir
sorun olmaz.


*Bu yazı, [Learn Vim
Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)
yazısının bir çevirisidir.*
