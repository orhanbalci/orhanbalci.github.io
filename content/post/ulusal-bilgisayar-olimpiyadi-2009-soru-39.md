title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 39
link: http://orhanbalci.net/tr/?p=481
author: admin
description: 
post_id: 481
created: 2009/12/08 00:18:19
created_gmt: 2009/12/07 21:18:19
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-39
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 39

Soru metni için öncelikle 40. soruda verdiğimiz açıklamaları okuyun. Aşağıdakilerden hangisi (5) numaralı şekli çizer. A) 4([<i2(3(>)i)]>>) B) >4([i]>>i>>i) C) 4([ii3(>>>i)]>>)] D) 4([ii3(>>>i)]>)] E) >4([i]>>i>i) CEVAP: Şekil her ne kadar karmaşık görünsede aynı alt şeklin 4 kere tekrar edilmesinden oluşuyor. Yapı olarak 40. soruya çok benziyor. Biz 5 numaralı şeklin sol üst çeyreğindeki şeklin çizilmesine odaklanalım. ![Soru 39](/wp-content/uploads/39-244x300.png) Yukarıdaki şekle göre algoritmamızı yazmaya başlayabiliriz. Tosbağamız kuzeye baktığından dolayı öncelikle 45 derecelik sola dönüş gerekli bize. İfademiz < şeklinde başlıyor. 1'den 2'ye gitmek için ilerliyoruz. İfademiz <i oldu. 2. köşeden saat yönünde 135 derecelik dönüş lazım. İfademiz <i>>> oldu. 2'den 3'e gitmek istiyoruz. İfademiz <igt;>>i oldu. Yine 3. köşede 135 derecelik dönüş yapmamız gerekiyor. İfademiz <i>>>i>>> oldu. 3'den 4'e gitmek istiyoruz. İfademiz <i>>>i>>>i oldu. Diğer tüm alt şekiller için aynı algoritma uygulanabilir. Bunu değişik şekillerde sadeleştirebiliriz. Örneğin <2(i3(>))i veya <i2(3(>)i) şeklinde sadeleştirebiliriz. Diğer şekilleride çizebilmek için bize 90 derecelik dönüşler gerekli. Tabi bunun için öncelikle ilk konumumuzu hatırlamalı ve alt şeklin çizilmesi bittiği zaman tekrar ilk konuma dönmemiz gerekir. Yani ifade [<i2(3(>)i)] şeklini alır. Bunun sonuna 90 derecelik dönüş ekleyip işlemi 4 kere tekrarlamamız 5 numaralı şeklin çizilmesini sağlayacaktır. İfademiz 4([<i2(3(>)i)]>>) şeklini aldı. Doğru seçenek A şıkkı. Not: Çizim [Dia](http://projects.gnome.org/dia/) yazılım ile üretilmiştir.