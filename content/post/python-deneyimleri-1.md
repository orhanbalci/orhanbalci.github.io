title: Python Deneyimleri 1
link: http://orhanbalci.net/tr/?p=593
author: Orhan Balci
description: 
post_id: 593
created: 2010/02/02 14:25:54
created_gmt: 2010/02/02 11:25:54
comment_status: open
post_name: python-deneyimleri-1
status: publish
post_type: post

# Python Deneyimleri 1

[caption id="attachment_605" align="aligncenter" width="470" caption="Python Logo"]![Python Logo](/wp-content/uploads/python_logo.png)[/caption] 

  1. <http://www.istihza.com> buradaki python2.x derslerini takip ediyorum
  2. from ... import ... ifadeleri sayfanın başına yazılmalıymış
  3. from'dan sonra gelen şeyin paket importtan sonra gelen şeyin sınıf tarzı bir şey olduğunu zannediyorum
  4. Türkçe karakterleri kullanabilmek için #_*_ coding: utf-8 _*_ yazıyoruz. Yine sayfamızın en başına ekliyoruz bunu
  5. print fonksiyonuna birden fazla argüman verirken , kullanıyoruz
  6. Kullanıcıdan girdi input() ve raw_input() fonksiyonları ile alınıyor. input() nümerik değer dönerken, raw_input() string değer dönüyor
  7. pre/post increment/decrement (++/--) operatörleri mevcut değil. [python] a = 1 while a < 10: print "Daha Bitmedi" ++a; [/python] ifadesi sonsuz döngüye sebep oluyor. Syntax hatası vermedi ilginç!
  8. döngülerde range() fonksiyonu kullanılıyor. Bu fonksiyon Matlab'dan tanıdık geldi bana.
  9. Java ve C++ dan bildiğim liste veri yapısı Python'da built in type olarak karşıma çıktı. Kullanımı çok kolay. append(), insert() gibi fonksiyonlarla düzenleme yapmak pratik.
  10. Liste içinde farklı veri tipleri barınabiliyor.
  11. Listeler + operatörü ile birleştirlebiliyor fakat - operatörü tanımlı değil
  12. pop() listenin son elemanını atıyor
  13. Listeler tersten indekslenebiliyor liste[-1] son elemanı gösteriyor. Büyük kolaylık
  14. Matlab'da bulunan aralık indeksleme yöntemi mevcut. Liste[1:3] 1. eleman dahil 3. eleman dahil olmamak kaydıyla aralıktaki elemanları belirtiyor
  15. Değiştirilemeten bir liste yapısı (tuple) var. Bunun tam olarak ne işe yaradığından emin değilim.
  16. HashTable benzeri sözlük veri yapısı da built in type olarak mevcut. Farklı bir özellik olarak tüm anahtarlar aynı tipte olmak zorunda değil. Scripting diye buna diyorlar herhalde

## Comments

**[istihza](#2183 "2010-02-04 18:33:40"):** Evet, C ve C++'dan gelenler Python'da "pre/post increment/decrement operator" gibi bir kavram olmamasına şaşırıyor. Python'da bu işlece en yakın şey "+=" veya "-=" gibi birleşik işleçler olur. Gerçi bunun C/C++ programcılarını pek tatmin edeceğini sanmıyorum... :) Bu arada, istihza.com'un işinize yaramasına sevindim. Size iyi çalışmalar dilerim.

**[istihza](#2181 "2010-02-04 16:34:15"):** Aslında o while döngüsünün sözdizimi hatası vermemesi normal. Çünkü Python ++a ifadesini ++1 olarak algılıyor. Yani pozitif bir sayı olarak... O yüzden herhangi bir hata mesajı göstermiyor. Eğer print -a yazarsanız -1 çıktısı alırsınız. Eğer print --1 yazarsanız, iki negatif sayı bir pozitif sayı ürettiği için +1 olur. Siz o while döngüsünde ++a (yani ++1) sayısını print yardımıyla ekrana basmadığınız için çıktıda görünmüyor. Eğer bu ifadeyi print ile yazarsanız "Daha bitmedi" ve 1 çıktılarını birlikte alırsınız.

**[admin](#2182 "2010-02-04 17:24:20"):** Değerli ve öğretici yorumunuz için teşekkür ederim. Python'la ilgilenmeye yeni başladım. Aslında odaklandığım nokta syntax hatası değildi de klasik manada pre/post increment/decrement operatörlerinin olmamasıydı. C++ ve Java tecrübem olduğu için onlarla çok sık yaptığım şeyleri burada denemek istedim. Bu örnek de C++'dan Python'a geçiş yapmak isteyen birisinin hataya düşmesi muhtemel bir örnek. Tıpkı benim düştüğüm gibi :). Bu arada sitenizdeki anlatım çok düzenli ve öğretici. Böyle bir kaynağı Türkçe olarak nette yayınladığınız için teşekkür ederim.

