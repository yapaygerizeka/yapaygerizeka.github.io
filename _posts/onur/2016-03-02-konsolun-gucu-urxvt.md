---
title: "Konsolun Gücü 1: urxvt"
layout: post
author: onur
---

Bu yazı dizisinde en çok kullandığım konsol uygulamalarını göstereceğim.

Bunlardan ilki elbette bir terminal emülatörü olan: `rxvt` veya unicode
sürümü `urxvt`. Debian tabanlı dağıtımlarda `rxvt-unicode` paketi ile
kurabileceğiniz terminal emulatörü, `xterm`in yerini almak için
geliştirilmiş olsa da, modern oluşu ve barındırdığı bir çok özellik ile
ön plana çıkıyor.

`rxvt` kullanmamın en önemli nedeni çok hızlı oluşu ve çok düşük bir bellek
kullanımına sahip olması. Ayrıca hayli özelleştirilebilir olması da rxvt'i
öne çıkarıyor. Kısaca rxvt bir terminal emulatöründen beklediğiniz tüm
özellikleri iyi bir şekilde, hızlı ve en az sistem kaynağı kullanarak
yapabiliyor.

`rxvt` X kaynaklarını kullanarak özelleştiriliyor. Özelleştirilebilen tüm
değerlerin bir listesine `man rxvt` diyerek ulaşabilirsiniz. Benim
kullandığım bir kaç değer şöyle:

```conf
! Terminal için kullandığım font
URxvt*font: xft:Roboto:size=10:hinting=false

! Scrollbarlar gizli
URxvt*scrollBar: false

! Clipboard ve matcher eklentisi, kopyalama-yapıştırma ve
! URLleri tıklanabilir hale getirmeye yarıyor
URxvt*perl-ext-common:  default,matcher,clipboard

! Tıklanan URL x-www-browser ile açılıyor
URxvt*urlLauncher:      /usr/bin/x-www-browser
URxvt*matcher.button:   1

! X fontlarının çift buffera alınması
! Bu (intel grafik aygıtı olan) bir makinemde performans sorunu yarattığı
! için devre dışı bıraktım, aynı zamanda transparanlık desteğine de
! ihtiyacım olmadığından devre dışı
URxvt*buffered: false
URxvt*transparent: false

! Eğer transparanlığı aktifleştirirseniz, shading ile terminalinizin
! ne kadar transparan olacağını belirleyebilirsiniz.
URxvt*shading: 20

! Renkler
URxvt*background: #151515
URxvt*foreground: #DEDEDE

URxvt*colorUL: #86a2b0

! siyah
URxvt*color0  : #2E3436
URxvt*color8  : #555753
! kirmizi
URxvt*color1  : #CC0000
URxvt*color9  : #EF2929
! yesil
URxvt*color2  : #4E9A06
URxvt*color10 : #8AE234
! sari
URxvt*color3  : #C4A000
URxvt*color11 : #FCE94F
! mavi
URxvt*color4  : #3465A4
URxvt*color12 : #729FCF
! magenta
URxvt*color5  : #75507B
URxvt*color13 : #AD7FA8
! cyan
URxvt*color6  : #06989A
URxvt*color14 : #34E2E2
! beyaz
URxvt*color7  : #D3D7CF
URxvt*color15 : #EEEEEC
```

Bu ayarların ardından `irssi` çalışan `rxvt`den bir ekran görüntüsü:

<a
href="https://1.bp.blogspot.com/-5k7XWcKddpc/VtbAnEnBLLI/AAAAAAAABoA/MyXmTf8GMaM/s1600/urxvt.png"
imageanchor="1" ><img border="0"
src="https://1.bp.blogspot.com/-5k7XWcKddpc/VtbAnEnBLLI/AAAAAAAABoA/MyXmTf8GMaM/s200/urxvt.png"
/></a>
