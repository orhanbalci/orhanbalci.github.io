title: Rust Temel Veri Yapıları Struct ve Enum
link: http://orhanbalci.net/tr/?p=1427
author: Orhan Balci
description: 
post_id: 1427
created: 2015/09/04 00:45:23
created_gmt: 2015/09/03 21:45:23
comment_status: open
post_name: rust-temel-veri-yapilari
status: publish
post_type: post

# Rust Temel Veri Yapıları Struct ve Enum

Rust ile nesne yonelimli ve fonksiyonel programlama yapabilmek mumkun. Bu yazida biraz nesne yonelimli programlamaya yonelik temel veri yaplarindan ornekler verecegim. En temel veri yapilari enum ve struct. Enum ve struct yapilarini c/c++ daki gibi kullanmak da mumkunken rustta ek birkac ozellik de bulunuyor. Temel bir simulasyon catisi olusturarak bu yapilari ogrenelim. Enumlarla baslayalim. Simulasyon catisinda kullanacagimiz eksen ve carpisma kontrolunda kullanilacak geometri cesitlerini enum olarak tanimlayalim :  Ornekte tamamen c/c++ tarzinda bir enum tanimi goruyorsunuz. Aslinda rustta enumlar union tipine daha yakindir. Dokumanda enumlar birkac farkli variant tipinde olabilien verileri tanimlayan tipler olarak anlatiliyor. Ve bu variantlar farkli veri tipinde deger tutabiliyorlar. Java'da da enum tipleri ekstra veri tasiyabilirler fakat enuma ait tum elemanlar ayni tipte veri tutarlar, homojen bir yapisi vardir. Bahsettigimiz enum kullanimina bir ornek verelim :  Rustta enum ve structlarin yaptiklari isler birbirine cok benzemektedir. Dolayisiyla ikisinin ayni anda varolmasiyla ilgili ciddi tartismalar var. Structlar syntactic sugar olarak nitelendirilmektdir. Structlarin varolus sebebi birbiriyle ilintili verilerin isimlendirilerek bir arada tutulmasi olarak gorunuyor. Basit simulasyon catimizda kullanacagimiz structlari asagidaki gibi tanimlayalim :  Verilerimizi saklayacak yapilari yazdigimiza gore verileri isleyecek aksiyonlari tanimlamaya sira geldi. Rust da fonksiyonlar standalone (fonksiyon) olarak tanimlanip kullanilabildikleri gibi herhangi bir struct uzerinde islem yapmak uzere de tanimlanabilir (method). Bu hususta ilk dikkati ceken veri blogu ile method bloklarinin birbirinden ayrilmis olmasi. Bunun icin `impl` anahtar kelimesini kullanarak method blogu tanimliyoruz. `this` pointeri yerine de `self` anahtar kelimesi kullaniliyor. Tanimlamis oldugumuz structlara ait methodlari gorelim. Ornegin Orientation structi icin rotate methodumuzu ve digerlerini inceleyelim :  Yukaridaki kod blogunda struclarin nasil ilklendirilmesi gerektigine dair ornekler de bulunmakta. Herhangi bir structi ilklendirmek icin `alan adi : deger` ikililerini kullanmamiz gerekiyor. Ornek olarak 25. satirda Vector structimizi ilklendirirken `position : Vector{x:0,y:0,z:0},` kod satirini kullandik. Main fonksiyonumuzu da tanimlayarak ornegimizi tamamlayalim.  [ad#Yazi Ici Buyuk]