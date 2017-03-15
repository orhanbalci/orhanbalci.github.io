title: Java Dersleri 15 – Koleksiyon API (Collection API) Map
link: http://orhanbalci.net/tr/?p=696
author: Orhan Balci
description: 
post_id: 696
created: 2010/03/17 18:31:35
created_gmt: 2010/03/17 15:31:35
comment_status: open
post_name: java-dersleri-15-%e2%80%93-koleksiyon-api-collection-api-map
status: publish
post_type: post

# Java Dersleri 15 – Koleksiyon API (Collection API) Map

[caption id="attachment_840" align="aligncenter" width="600" caption="Java Dersleri 15 Map"]![Java Dersleri 15 Map](/wp-content/uploads/java_banner_15.png)[/caption] Map arayüzü anahtar-değer ikililerini bir arada tutmak için tasarlanmıştır. Matemetikteki fonksiyonların yazılım tarafında karşılığı olan map veri yapıları yazılım mimarisinde sıkça kullanılır. Örneğin yazılımımızda bulunan nesnelere birer kimlik numarası vererek bu numara ile nesne arasında anahtar-değer ilişkisi kurabiliriz. Böylelikle istediğimiz nesneye kimlik numarası aracılığıyla rahatlıkla erişebiliriz. Java Map arayüzü herhangi bir sıralama kısıtı getirmez. Map'e eklenen anahtar-değer ikililerinin eklendiği sırada kalacağı garanti değildir. Map arayüzünü gerçekleyen sınıflar arasında en bilineni HashMap sınıfıdır. HashMap verilen anahtardan hash fonksiyonu yardımıyla bir array indeksi oluşturur. Verilen değer de bu array indeksindeki belleğe yerleştirilir. Hash fonksiyonları çok temel matematiksel işlemler kullandıklarından hızlıdırlar. Dolayısıyla HashMap'de verilere erişim sabit zamanda olur. HashMap performansı için önemli olan iki parametre ilk kapasite ve yük faktörüdür. Varsayılan olarak ilk kapasite 11'dir. Yük faktörü HashMap koleksiyonumuzun herhangi bir anda maksimum doluluk oranını ölçer. Bu değer varsayılan olarak %75 dir. HashMap'de doluluk oranı bu değerin üzerine çıktığında kapasite arttırımına gidilerek değerler tekrar hash'lenir. Şimdi bir örnekle Map veri yapısına eleman eklemeyi ve geri almayı görelim : [java] package net.orhanbalci.collections; import java.util.HashMap; import java.util.Iterator; import java.util.Map; import java.util.Set; public class HashMapExample { public static void main(String[] args) { Map<Integer,String> m = new HashMap<Integer,String>(); for (int i = 0; i < 10; i++) { m.put(i, String.valueOf(i) + " değer"); } Set<Integer> ks = m.keySet(); Iterator<Integer> i = ks.iterator(); while (i.hasNext()) { Integer key = i.next(); System.out.print(key + " "); System.out.println(m.get(key)); } } } [/java] Örneğimizde 11. satırda yeni bir HashMap nesnesi tanımlıyoruz. Java'nın generics özelliğini (şablon sınıflar) kullanılarak anahtarların veri tipini Integer değerlerin veri tipini ise String olarak belirttik. 14. satırda Map arayüzünün put() metodunu kullanarak HashMap koleksiyonumuza yeni eleman ekliyoruz. 24. satırda ise get() metodu yardımıyla HashMap koleksiyonumuzdan anahtar yardımıyla değerimize ulaşıyoruz. Yukarıda bahsettiğimiz ilk kapasitenin performansa olan etkisini başka bir örnekte görelim : [java] Map<Integer,String> m2 = new HashMap<Integer,String>(10); Map<Integer,String> m3 = new HashMap<Integer,String>(100); long time1 = System.currentTimeMillis(); for (int k = 0; k < 10000; k++) { m2.put(k, String.valueOf(k) + " değer"); } long time2 = System.currentTimeMillis(); System.out.println(String.valueOf(time2-time1) + " milisaniye"); time1 = System.currentTimeMillis(); for (int k = 0; k < 10000; k++) { m3.put(k, String.valueOf(k) + " değer"); } time2 = System.currentTimeMillis(); System.out.println(String.valueOf(time2-time1) + " milisaniye"); [/java] Bu örneğimizde ise iki adet HashMap nesnesi oluşturuken ilk kapasiteyi yapılandırıcı metoda parametre olarak veriyoruz. m2 koleksiyonumuzun ilk kapasitesi 10 iken diğerinin ilk kapasitesi 100 dür. Her iki koleksiyona arka arkaya 10000 anahtar-değer ikilisi ekleyip performansı ölçtüğümüzde ilk kapasitesi 10 olan koleksiyona ekleme işlemi 46-47 milisaniye sürerken ilk kapasitesi 100 olan koleksiyona ekleme işlemi 19-20 milisaniye sürmekte. Görüldüğü üzere kapasite artırımına gitmek zaman kaybına neden olmaktadır. Map arayüzünün birden fazla implementasyonu mevcuttur. Bunlardan en sık kullanılanları HashMap ve TreeMap'tir. İkisi arasında en göze çarpan fark TreeMap'in sıralı HashMap'in ise sırasız olmasıdır. Örneğin bir TreeMap kullanıldığında : [java] public static void main(String[] args) { Map<Integer,String> map = new TreeMap<Integer,String>(); map.put(4,"four"); map.put(1,"one"); map.put(2,"two"); map.put(3,"three"); Set<Integer> keys = map.keySet(); //Kural treeset elemanları natural ordering ile sıralar Iterator<Integer> it = keys.iterator(); while(it.hasNext()) { System.out.println(map.get(it.next())); } } [/java] bu kod bloğu her zaman sıralanmış çıktı verecektir. [ad#Yazi Ici Buyuk]

## Comments

**[Java Yazılım](#2663 "2010-04-17 09:57:26"):** Merhaba, java yazılım ile ilgili googleda araştırma yaparken tesadüfen websitenize ulaştım. Web tasarım açısından ve arama motoru optimizasyonu açısından çok başarılı bulduğumu söyleyebilirim.Biraz daha teknik destek ile bu websitesi daha iyi noktalara ulaşacaktır diye düşünüyorum. :lol:

**[web sitesi](#7602 "2013-01-25 21:02:12"):** arkadaşa katılıyorum. başarılar dilerim

**[mustafa](#15932 "2014-04-30 17:35:59"):** merhaba, google da arama yaparken karşılaştığım sitenizi makalelerinizi çok beğendim. paylaşımlarınızın devamını dilerim

**[Ahmet](#43288 "2015-03-16 22:05:21"):** Çok faydalı bir yazı. Map kullanımını araştırıyodum denk geldim elinize sağlık

**[admin](#43455 "2015-03-19 19:13:00"):** Map çok temel bir veri yapısıdır. Değişik varyasyonları da mevcuttur. Örneğin aynı anahtara birden fazla değer atayabildiğimiz multimap ve çift yönlü veri erişimine olanak sağlayan bimap bunlara örnektir. bahsettiğim map türleri standart java kütüphanesinde mevcut değil bunlar için Guava kütüphanesini kullanabilirsiniz.

**[sefa](#50620 "2015-10-31 02:28:33"):** örnekler için teşekkürler. elimizdeki bir hashmapi dosyaya nasıl yazdırabiliriz? Şimdiden teşekkürler, iyi günler.

**[admin](#50732 "2015-11-06 23:11:57"):** Hashmapi binary dosyaya yazmak istiyorsaniz serialization kullanabilirsiniz. Text dosyaya yazmak icin http://orhanbalci.net/tr/?p=1205 buradaki derste anlatilan guava kutuphanesi isinizi kolaylastiracaktir

