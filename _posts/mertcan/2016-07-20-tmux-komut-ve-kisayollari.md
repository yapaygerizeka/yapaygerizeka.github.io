---
layout: post
title:  TMUX Komut ve Kısayolları
date: 2016-07-20
type: post
author: Mertcan
categories: Linux
description:   tmux özellikle bir çok sanal terminal açmamıza imkan sağladığı için kullanıyoruz.Ya birader bunu ben tab ile yaparım
---

Herhangi bir linux distro kullanıyorsanız en az 2-3 kez ilgilenmiş olmanız gerekiyor diye düşünüyorum **tmux** özellikle bir çok sanal terminal açmamıza imkan sağladığı için kullanıyoruz.Ya birader bunu ben tab ile yaparım en olmadı sağ tıklayıp yeni sekme açarım niye bunu kurayım boşa paket kurdurma bize ya diyen bir kaç kişiyi görür gibiyim belki onlardan biride siz olabilirsiniz.

Ancak unutmayın tam o işlemi yaptığınız esnada elektrik gitti yada internetiniz koptu hadi bunlar olmadı kullandığınız bilgisayar kendini bi şekilde kapattı yada terminal işleminizi engelleyecek bir durum oldu ne yapacaksınız ?

İşte bu noktada **tmux** bizi kurtarıyor. Açtığınız sekmeler devam edbilebilir sekmelerdir. istediğiniz zaman kapatıp gidebilirsiniz. **screen** uygulaması ile aynı görevi görür daha yeni ve daha esnek bir yapısı vardır.

Kurulumu oldukça basit her dağıtımda bulunuyor.

```console
sudo apt-get install tmux
```

Kurulum tamamlandıktan sonra ufak bir ayarlama yapmamız gerekiyor normalde ön tanımlı olarak gelen kısayol `CTRL + b` tuşudur ancak b biraz uzağımızda kaldığı için ben bunu her zaman `CTRL + a` ya getiriyorum böylelikle biraz daha hızlı işimi görüyorum.

```console
nano ~/.tmux.conf
```

içerisinde bir takım değerler olacak biz bunu şu şekilde değiştiriyoruz.

```console
unbind C-b
set -g prefix C-a
```

kayıt edip çıktıktan sonra başlattığımızda zaten aktif hale geldiğini göreceksiniz. Gelmez ise aşağıda ipucunu verdim ben oradan yola çıkarsınız artık. Şimdi geldik aydınlanmaya;

**Tmux** oturumu açılmadan önce yapabilecekleriniz;

| Komut    |    Açıklama   |
|----------|-------------|
| `tmux list-sessions` | Oturumları listeler |
| `tmux list-keys` | Kısayolları gösterir |
| `tmux list-commands` | Tüm komutları listeler |
| `tmux source-file ~/.tmux.conf`| TMUX ayarlarını yeniler |
| `tmux a -t oturum_adi` | oturumu sabitler |

**Tmux** oturumu oluşturulduğunda geçerli olan kısayollar (prefix olarak tmux'un varsayılanı `Ctrl+b` kullanılmıştır);

| Komut    |    Açıklama   |
|----------|-------------|
| `C-b new -s oturum_adi` | Yeni adlandırılmış oturum açar |
| `C-b c` | Yeni pencere açar |
| `C-b [0-9]` | 0-9 arası istenilen pencereyi seçer |
| `C-b ,` | Ekranı adlandırmak |
| `C-b w` | Ekranları listeleme |
| `C-b l` | Önceki seçilen ekrana geçer |
| `C-b n` | Sonraki ekrana geçer |
| `C-b p` | Önceki ekrana geçer |
| `C-b d` | Oturumdan ayrılma |
| `C-b D` | Oturumları listeleyip istenileni ayırma |
| `C-b s` | Oturumları listeler(varsayılan), eşleşmiyor ise |
| `C-b ?` | Tüm kısayolları listeler |
| `C-b %` | Ekranı dikey böler |
| `C-b "` | Ekranı yatay böler |
| `C-b n` ve `C-b p` | Ekranlar arasında geçiş |
| `C-b {Yukarı, Aşağı, Sol, Sağ}` | Bölünmüş ekranlar arası geçiş |
| `C-b space` | Her ekranı aynı boyutlandır |
| `C-b s` | Oturumları eşitleme |
| `C-b [` | Kopyalama modu |
| `C-b ]` | Kopyalama modundan kopyalanı yapıştırma |

Bu aşamadan sonra benim kullandığım ve oldukça sevdiğim bir yöntem var ben bunu oturumları takip etmek için kullanıyorum. Belirli süre işlem yapmadığımda renk değişiyor ve ben son olarak işlem ney yapmışım onu görebiliyorum.

```console
setw -g monitor-silence 60
```

Böylelikle ben 1 dakika boyunca işlem yapmaz ise oturum farklı bir renk ile gözükecek bana bende anlayacağım ki orada işlem yapıyormuşum ama yapmayı durdurmuşum.

Bir diğer kullandığım olay ise aktif olan oturumun renginin değiştirilmesi onuda şu şekilde sağlıyoruz.

```console
set-window-option -g window-status-current-bg red
```

Son olarak fare ile kopyalamayı açalım ben bunu genellikle kullandığım için diğer türlü zorlandığımdan açtım isterseniz açmayabilirsiniz.

```console
setw -g mode-mouse on
```

Bu ayarları yukarıda bahsettiğim kişisel ayar dosyanıza uygulamayı unutmayın yani `~/.tmux.conf`
