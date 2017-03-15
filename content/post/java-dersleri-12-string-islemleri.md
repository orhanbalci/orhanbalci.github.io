title: Java Dersleri 12 - String İşlemleri
link: http://orhanbalci.net/tr/?p=367
author: Orhan Balci
description: 
post_id: 367
created: 2009/10/05 22:41:23
created_gmt: 2009/10/05 19:41:23
comment_status: open
post_name: java-dersleri-12-string-islemleri
status: publish
post_type: post

# Java Dersleri 12 - String İşlemleri

[caption id="attachment_832" align="aligncenter" width="600" caption="Java Dersleri 12 String İşlemleri"]![Java Dersleri 12 String İşlemleri](/wp-content/uploads/java_banner_12.png)[/caption] Bu dersimizde Java'nın ve diğer dillerin en temel elemanlarından olan String sınıfını inceleyeceğiz. Java'da String nesneleri immutable yani değiştirilemeyen nesnelerdir. Herhangi bir string nesnesi üzerinde değişiklik yapıldığında tamamen yeni bir nesne oluşturularak değişiklikler üzerine yansıtılır. Örneğin toUpperCase metodunu ele alalım : [java] String s = new String("orhan"); s.toUpperCase(); System.out.println(s) [/java] şeklinde yazacağımız kod parçası istenilenin aksine "ORHAN" değil "orhan" yazacaktır çünki toUpperCase metodu üzerinde çalıştığı nesneye herhangi bir değişiklik yapamaz, yeni bir String nesnesi döner. İkinci satırımızı [java] s = s.toUpperCase(); [/java] olarak değiştirisek istenilen çıktıyı alabiliriz. Stringlerle ilgili ikinci hatırlamamız gereken konu ise karşılaştırma meselesidir. Stringler karşılaştırılırken mümkün olduğunca == ifadelerinden sakınılmalıdır. == ifadeleri referans karşılaştırması yaptığından istenmeyen sonuçlara yol açabilirler. Örneğin : [java] String s = new String("orhan"); String s2 = new String("orhan"); if(s == s2) System.out.println("true"); else System.out.println("false"); [/java] Yukarıdaki kod parçası beklenilenin aksine false yazacaktır. Karşılaştırdığımız iki nesne bellekte farklı yerlerde bulunduğundan dolayı == karşılaştırması yanlış dönecektir. Üçüncü satırımızı : [java] if(s.equals(s2)) [/java] olarak değiştirirsek doğru sonucu elde ederiz. equals() metodu alfabeye göre karşılaştırma yaparak sonuca ulaşır. Diğer veri türlerinden String tipine dönüşüm yapmak için String sınıfının statik overload metodları olan valueOf() metodları kullanılır. Örneğin : [java] int s = 50; String k = String.valueOf(s); System.out.println(k); [/java] kod parçasında s integer değişkeninden k stringi elde edilmiştir. Herhangi bir string nesnesinin belirli bir parçasını almak için substring() metodunu kullanabiliriz : [java] String s = new String("deneme"); String l = s.substring(1); [/java] bu örnekte l string nesnemizin değeri "eneme" olacaktır. Burada substring() metodumuza ikinci parametre olarak bitiş indeksini de verebiliriz. Son olarak split() ve replace metodlarından bahsetmek istiyorum. Herhangi bir string nesnesini belirli ayraçlarla bölmek için split() metodunu kullanabiliriz. Örneğin dosyadan virgülle ayrılmış değerleri bir string nesnesine okuduğumuzu düşünelim : [java] String s = new String("Afyon,Bayat,İstanbul"); String[] result = s.split(","); [/java] burada result string arrayimizde "Afyon","Bayat" ve "İstanbul" elemanları bulunacaktır. replace() metodu ise herhangi bir string nesnesi içinde geçen alt stringi istediğimiz başka bir stringle değiştirmeye yarar. Bu metoda özellikle HTML rapor hazırlarken şablonda gerekli yerleri doldurmada baş vurabilirsiniz. Örneğin : [java] String s = new String("Hava Durumu : @@@"); s = s.replace("@@@", "Bulutlu"); [/java] Son durumda s string nesnemizde "Hava Durumu : Bulutlu" değeri bulunacaktır. Bir diğer sıkça kullanılan metod contains metodudur. Contains metodu string içinde string aramaya yarar. Örneğin: [java] String s = new String("alt string"); s.contains("string"); [/java] buradaki ikinci ifade true değeri dönecektir. String sınıfının birkaç tane yardımcı sınıfı vardır ki bunlar string'ler üzerinde işlem yapan sınıflardır. Bunlardan birincisi StringBuilder sınıfıdır. StringBuilder sınıfı string birleştirme işlemini daha verimli hale getirmek için kullanılır. Performansı, "+" operatörüyle stringleri birleştirme işlemine göre daha iyidir. StringBuilder sınıfının en önemli metodları insert() ve append() metodlarıdır. Bu metodların değişik tiplerde parametre alan overloadları vardır. Bu metodlar kullanıldıkları StringBuilder nesnesinin referansını döndükleri için arka arkaya kullanılabilirler (metod chaining). Örneğin : [java] StringBuilder sb = new StringBuilder(); sb.append("Manavdan "); for(Meyve m : Meyveler) { sb.append(m.toString()); } sb.append("aldım"); System.out.print(sb.toString()); [/java] StringBuilder sınıfı ile aynı işlemleri yapan ve thread safe olan StringBuffer sınıfını da çoklu thread uygulamalarınızda kullanabilirsiniz. Diğer bir yardımcı sınıf ise stringleri ayrıştırma, parçalama işlemlerini yapan StringTokenizer sınıfıdır. Bu işlem için basit olarak String sınıfının split() metodunu kullanabilirsiniz fakat daha gelişmiş fonksiyonalite için StringTokenizer'dan yararlanabilirsiniz. String işilemleri için güçlü bir kütüphane için [Guava ](http://orhanbalci.net/tr/?p=1205)makalemi inceleyebilirsiniz. [ad#Yazi Ici Buyuk]

## Comments

**[adem](#4405 "2010-12-07 22:52:19"):** merhaba… sizden bi ricam var girilen e-mail adresinin dogru yazılıp yazılmadıgını nasıl anlayabilirim.. hatta girilen metin içinde arama yapma kodu nedir mesela @ varsa email adresi doğru yazılmıştır.. gibi bir program yazmam lazımda yardımcı olursanız sevinirimm…

**[admin](#4423 "2010-12-07 23:46:30"):** Adem bey bunun için kullanılan Regular Expression yapıları mevcuttur. Google da java e-mail regex diye aratırsanız epey bir kaynak bulabilirsiniz

**[handan](#4202 "2010-10-24 23:15:17"):** örnek uygulamalar paylaşsa idin daha iyi idi.aslında imkan olsa ben yollamak isterdim

**[güney eser](#5306 "2012-02-16 14:48:26"):** stringlerin uzunluğunu nasıl karşılaştıra biliriz

**[admin](#5308 "2012-02-17 13:07:30"):** String sınıfının length() methodu o stringin uzunluğunu verir.

**[admin](#8047 "2013-04-08 16:11:02"):** şule hanım string sınıfının replace metodunu kullanabilirsiniz /** * Kullanıldığında http://orhanbalci.net adresi referans verilmelidir */ public class StringReplace { public static void main(String[] args) { String s = new String("abc\"def\""); s = s.replace("\"", "\\\\\""); System.out.println(s); } }

**[şule](#8046 "2013-04-08 15:55:33"):** Merhaba, String bir değişkenden aldığım veriyi " öncesine \ ekleyerek nasıl değiştirebilirim: giriş: abc "def" sonuç: abc \"def\" olmalı.

**[kemal](#8920 "2013-05-25 14:22:23"):** s.a ben javada örneğin string parcalamada öğrencinin sadece adlarını almak istiyorum.nasıl yapabilirim

**[admin](#36781 "2014-11-14 12:06:06"):** Ferhat bey normalde bu işi yapmak için parser yazmanız gerekir. Fakat çok bunu yazmak maaliyetli olacağından hazır kütüphane kullanmanızı öneiririm. Java 1.6 ile birlikte gelen javascript motorunu bu iş için kullanabilirsiniz. http://stackoverflow.com/questions/3422673/evaluating-a-math-expression-given-in-string-form bu adreste detaylı bilgi var.

**[ferhat](#36734 "2014-11-13 16:55:39"):** String verilen bir aritmetik işlemi nasıl yaptıra bilirim ?örnek "String s = new String("514+78/85"); "ifadesinin nasıl sonucunu bulurum ?

