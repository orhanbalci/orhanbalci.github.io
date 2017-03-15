title: Rust Trait
link: http://orhanbalci.net/tr/?p=1459
author: Orhan Balci
description: 
post_id: 1459
created: 2015/10/13 22:29:00
created_gmt: 2015/10/13 19:29:00
comment_status: open
post_name: rust-trait
status: publish
post_type: post

# Rust Trait

Rust dili bildiğimiz manada kalitimi desteklemiyor. Yani herhangi bir sinifi diğerinden türetip var olan methodlardan faydalanamiyorsunuz. Bu duruma degisik cozumler uretebiliyoruz. Ornegin kalitim yerine composition deseni kullanilabilir. Kalitim desteklenmese de Trait denen yapilar sayesinde interfaceler destekleniyor. Trait lerin diger ismi de type classes. C++ stl kutuphanesinde, Scala gibi dillerde de trait kullanimini gorebiliriz. Trait lerin interfacelerden farki default bir gerceklemelerinin olabilmesi ki bu ozellik son versiyonunda Java'ya da eklendi, ve varolan siniflar icin de gerceklenebilir olmasi, Ornegin siz yeni bir trait tanimladiginizda bunu sizin tanimlamadiginiz veri tipleri icin de gercekleyebilirsiniz. Trait anahtar kelimesi kullanilarak tanimlaniyorlar. Implementasyonlari ise impl ve for anahtar kelimeleri ile oluyor. Ornegimizi karsilastirilabilir yapilari temsil etmek uzere bir Comparable trait tanimi ve bunun farkli iki struct icin gerceklemesini gosterek gelistirelim :  1\. satirda comparable trait taniminin gorebilirsiniz. Bu trait tek bir method imzasi tanimindan ibaret. Self tipinin kullanimi onemli. 11. ve 27. satirlarda ise comparable taritinin StockField ve ScoreSheet isimli iki struct icin gerceklemesini goruyoruz. Tanimladigimiz structlardan ikiser tane olusturup bunlari karsilastirarak kullnimi da gormus olalim :