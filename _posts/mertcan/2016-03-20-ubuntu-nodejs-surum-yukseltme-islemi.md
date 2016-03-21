---
layout: post
title: Ubuntu NodeJs Sürüm Yükseltme İşlemi
date: 2016-03-20
type: post
author: Mertcan
categories: Linux
description: Dün standart bir şekilde nodejs kurulumumu yaptıktan sonra uygulamayı kurayımda
---

Dün standart bir şekilde nodejs kurulumumu yaptıktan sonra uygulamayı kurayımda işime gücüme döneyim dedim sonra uygulamanın birden hata verdiğini fark ettim hata ise şu şekildeydi

```
Error: Missing child_process.execSync. Please use node 0.12 or iojs
```

Bu hata benden ya sürüm yükseltmemi yada iojs kurulumu yapmamı ve işlemleri ona göre düzenlememi istiyordu çünkü child process bulamıyordu her ne hikmetse detaylıca hata kodun neresinde diye bakmadım açıkçası ama sorunu çözmek amacıyla sürümü yükselteyim dedim.

yükseltmeyi iki aşamada gerçekleştirdim ilk olarak npm sürüm güncelleştirmesi yaptım

```
sudo npm cache clean -f
sudo npm install -g n
sudo n 0.12.9
```

Ardından nodejs güncellemesi için aşağıdaki komutları uyguladım.Komutumuz da `sudo n stable` diyerek de en son kararlı sürümü kurabilirsiniz.

```
curl -sL https://deb.nodesource.com/setup_0.12 | sudo bash -
```

daha sonrasında ise sistemimizde var olsa bile tekrar kurulum komutumuzu veriyoruz ve paket listemize gerekenler ekleniyor.(Ubuntu 15.10 sürümünde sorunsuz olarak çalışmaktadır.Aynı şekilde Debian tabanlı sistemlerde sorunsuz çalışmaktadır.)

```
sudo apt-get install nodejs
```
olup olmadığını kontrol etmek için ise `node -v` dememiz yeterli ve aşağıdaki gibi çıktımızı aldık başarıyla güncelleştirmemizi yapmış ve sürümümüzü 0.12.9 yapmış olduk

```
root@0x2e88ce4:/home/mertcan# node -v
v0.12.9
```
