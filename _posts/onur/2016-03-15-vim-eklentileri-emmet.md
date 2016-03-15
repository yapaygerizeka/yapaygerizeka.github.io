---
title: "Vim eklentileri 1: emmet"
layout: post
author: onur
---

Bu yazı dizisinde kullandığım bazı vim eklentilerinden bahsedeceğim.

Bunlardan ilki: [emmet-vim](https://github.com/mattn/emmet-vim). Emmet,
HTML ve CSS yazmayı kolaylaştırmak için yapılmış bir editör eklentisi.
Bu yazıda vim için olanından bahsedeceğiz.

Emmet `<c-y>,` komutuyla çalışıyor.

Örneğin cursor (`_` ile gösterilmiştir) altında iken `<c-y>,` e
bastığımızda, bu kod dizini bir html5 dökümanına dönüşüyor:

```
html:5_
```

`<c-y>,` den sonra:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
    
</body>
</html>
```

[Kullanılan kısaltmalar listesi](http://docs.emmet.io/abbreviations/),
emmet'in açabildiği tüm kısaltmaları içermektedir. Bu yazının devamında vim
ile bunları nasıl yapabildiğimize bakacağız.

[Tutorial](https://raw.githubusercontent.com/mattn/emmet-vim/master/TUTORIAL)
içerisinde yer alan örnekleri inceleyelim:

1. #### Kısaltmaları genişletme

   `div>p#foo$*3>a` olan bir kısaltmayı `<c-y>,` ile genişlettiğimizde şuna
   dönüşüyor:

   ```html
   <div>
       <p id="foo1"><a href=""></a></p>
       <p id="foo2"><a href=""></a></p>
       <p id="foo3"><a href=""></a></p>
   </div>
   ```

2. #### Kısaltmaları sarma

   Aşağıdaki gibi bir yazımız var diyelim:

   ```
   test1
   test2
   test3
   ```

   Bu yazıyı visual line (`shift+v`) olarak seçtikten sonra `<c-y>,`
   uygulayalım. Emmet size 'Tag: ' sorduğunda, `ul>li*` yazalım. Emmet bunu
   aşağıdaki kod bloğuna dönüştürecektir.

   ```html
   <ul>
       <li>test1</li>
       <li>test2</li>
       <li>test3</li>
   </ul>
   ```

3. #### Bir tag'ı içe doğru seçme

   Insert modundayken `<c-y>d` uyguladığınızda içerisinde bulunduğunuz tag'ı
   içeriğiyle birlikte seçebilirsiniz.

4. #### Bir tag'ı dışa doğru seçme

   Insert modundayken `<c-y>D` uyguladığınızda içerisinde bulunduğunuz tag'ın
   içerisinde bulunan tag'ı seçebilirsiniz.

5. #### Bir sonraki düzenleme noktasına gitme

   Insert modunda `<c-y>n` ile bir sonraki düzenleme noktasına (örneğin
   etiket içeriği, attribute vb.) gidebilirsiniz.

6. #### Bir önceki düzenleme noktasına gitme

   Insert modunda `<c-y>N` ile bir önceki düzenleme noktasına (örneğin
   etiket içeriği, attribute vb.) gidebilirsiniz.

7. #### img boyutunu değişme

   Cursor'u `img` tagına getirin:

   ```html
   <img src="foo.png" />
   ```

   Burada `<c-y>i` uygulayın:

   ```html
   <img src="foo.png" width="32" height="48" />
   ```

8. #### Satırları birleştirme (merge)

   `<li>` etiketleri bulunan satırları seçin:

   ```html
   <ul>
       <li>test1</li>
       <li>test2</li>
       <li>test3</li>
   </ul>
   ```

   Ardından `<c-y>m` uygulayarak satırları birleştirebilirsiniz.

   ```html
   <ul>
       <li>test1</li><li>test2</li><li>test3</li>
   </ul>
   ```

9. #### Bir etiketi silme

   Cursor'u silmek istediğiniz etiketin içinde tutun.

   ```html
   <div class="foo">
       <a>cursor'u buraya getirin</a>
   </div>
   ```

   Insert modundayken `<c-y>k` ile etiketi ve içeriğini silebilirsiniz.
   Ardıdan tekrar `<c-y>k` uygulayarak div etiketini de silebilirsiniz.

10. #### Etiketleri bölme ve birbirine katma (join)

    Cursor'u block içine alın:
 
    ```html
    <div class="foo">
        cursor'u buraya getirin
    </div>
    ```
 
    Insert modundayken `<c-y>j` uygulayın:
 
    ```html
    <div class="foo"/>
    ```
 
    Tekrar `<c-y>j` uyguladığınızda:
 
    ```html
    <div class="foo">
    </div>
    ```

11. #### Yorum haline getirme

    Cursor'u block içerisine alın
 
    ```html
    <div>
        merhaba dünya
    </div>
    ```
 
    Insert modundayken `<c-y>/` uygulayın:
 
    ```html
    <div>
        merhaba dünya
    </div>
    ```
 
    Tekrar `<c-y>/` kullandığınızda yorum kaldırılacaktır:
 
    ```html
    <div>
        merhaba dünya
    </div>
    ```

12. #### Bir URL'den a etiketi oluşturma

    Cursor'u URL'e getirin:

    ```
    http://www.google.com/
    ```

    `<c-y>a` uygulayın:

    ```html
    <a href="http://www.google.com">Google</a>
    ```

13. #### Bir URL'den altıntı yapma

    Cursor'u URL'e getirin:

    ```
    http://github.com/
    ```

    `<c-y>A` uygulayın:

    ```html
    <blockquote class="quote">
        <a href="http://github.com/">Secure source code hosting and collaborative development - GitHub</a><br />
        <p>How does it work? Get up and running in seconds by forking a project, pushing an existing repository...</p>
        <cite>http://github.com/</cite>
    </blockquote>
    ```

14. #### emmet.vim'in kullandığınız dil için kurulumu

    ```
    # cd ~/.vim
    # unzip emmet-vim.zip
    ```
    
    pathogen.vim kullanıyorsanız:
    
    ```
    # cd ~/.vim/bundle # veya dizini oluşturun
    # unzip /path/to/emmet-vim.zip
    ```
    
    Depodan kaynak kodlarını indirmek istiyorsanız:
    
    ```
    # cd ~/.vim/bundle # veya dizini oluşturun
    # git clone http://github.com/mattn/emmet-vim.git
    ```

15. #### emmet.vim'i kullandığınız dil için etkinleştirme

    Kullandığınız dillerin davranışını özelleştirebilirsiniz:

    ```viml
    let g:user_emmet_settings = {
    \  'php' : {
    \    'extends' : 'html',
    \    'filters' : 'c',
    \  },
    \  'xml' : {
    \    'extends' : 'html',
    \  },
    \  'haml' : {
    \    'extends' : 'html',
    \  },
    \}
    ```
