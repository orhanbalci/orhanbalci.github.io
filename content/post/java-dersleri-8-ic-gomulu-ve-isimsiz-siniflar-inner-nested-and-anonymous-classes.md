title: Java Dersleri 8 - İç, Gömülü ve İsimsiz Sınıflar (Inner, Nested and Anonymous Classes) 
link: http://orhanbalci.net/tr/?p=176
author: Orhan Balci
description: 
post_id: 176
created: 2009/07/13 21:49:12
created_gmt: 2009/07/13 18:49:12
comment_status: open
post_name: java-dersleri-8-ic-gomulu-ve-isimsiz-siniflar-inner-nested-and-anonymous-classes
status: publish
post_type: post

# Java Dersleri 8 - İç, Gömülü ve İsimsiz Sınıflar (Inner, Nested and Anonymous Classes) 

[caption id="attachment_824" align="aligncenter" width="600" caption="Java Dersleri 8 İç, Gömülü Sınıflar"]![Java Dersleri 8 İç, Gömülü Sınıflar](/wp-content/uploads/java_banner_8.png)[/caption] Bu dersimizde Java'nın gömülü sınıf yapısını öğreneceğiz. Java programlama dili kullanıcıya bir sınıf içerisinde başka bir sınıf tanımlama olanağı sağlar. Bu tür sınıflara **Gömülü Sınıf** (Nested Class) adı verilir. Gömülü sınıflar statik ve statik olmayan gömülü sınıflar olmak üzere ikiye ayrılırlar. Statik olmayan gömülü sınıflara **İç Sınıf**(Inner Class) adı verilir. Gömülü sınıfların üç temel faydası vardır. Bunlar : 

  1. Sınıfların Mantıksal Gruplanması : Ortak iş yapan sınıfların bir arada bulunmasını sağlayarak daha sağlıklı API'ler oluşturmanızı sağlar
  2. Daha İyi Kapsülleme : Sınıf değişkenlerinin private kalmasını sağlayarak daha iyi kapsülleme sağlar
  3. Kod Okunabilirliği : Üst seviye sınıflar altında iş gören gömülü sınıflar kod okunabilirliğini arttırır.
Gömülü sınıf hiyerarşisi aynı zamanda arayüzler için de geçerlidir. Yani arayüzlerde birbirleri içerisinde tanımlanabilirler. Java JDK içerisinde gömülü sınıf kullanımına örnek olabilecek çok sayıda sınıf ve arayüz vardır. Bunlardan bir tanesini inceleyelim : [java] //üst seviye arayüz tanımı public interface Map<K ,V> { int size(); boolean isEmpty(); boolean containsKey(Object key); boolean containsValue(Object value); V get(Object key); V put(K key, V value); V remove(Object key); void putAll(Map<? extends K, ? extends V>m); void clear(); Set<K> keySet(); Collection<V> values(); //gömülü arayüze referans var Set<Map.Entry<K, V>>; entrySet(); //gömülü arayüz tanımı interface Entry<K ,V> { K getKey(); V getValue(); V setValue(V value); boolean equals(Object o); int hashCode(); } boolean equals(Object o); int hashCode(); } [/java] Örnekte görüldüğü üzere Map arayüzünün altında Entry gömülü arayüzü tanımlanmış ve [java] //gömülü arayüze referans var Set<Map.Entry<K, V>>entrySet(); [/java] metod imzasında gömülü arayüz kullanılmıştır. Bu kullanımdan yola çıkarak gömülü arayüz/sınıf tanımlarına nasıl ulaşabiliriz onu görelim. Burada yine statik gömülü sınıflar ve iç sınıflar arasında ayrım yapmalıyız. Statik gömülü sınıftan bir nesne oluşturmak istiyorsak : [java] ÜstSeviyeSınıf.StatikGömülüSınıf s = new ÜstSeviyeSınıf.StatikGömülüSınıf(); [/java] Statik gömülü sınıftan bir nesne oluşturmak için üst seviye sınıftan nesne oluşturmamıza gerek yoktur. Oysa ki iç sınıflar üst seviye sınıf olmadan oluşturulamazlar. Yani statik olmayan iç sınıfların varlığı üst seviye sınıfa bağlıdır. Herhangi bir iç sınıfdan nesne oluşturmak için ise : [java] ÜstSeviyeSınıf s = new ÜstSeviyeSınıf(); ÜstSeviyeSınıf.İçSınıf i = s.new İçSınıf(); [/java] Burada en çok dikkat etmemiz gereken kullanım **s.new** kullanımıdır. Sınıf tanımı veya herhangi bir metod tanımı içinde isim vermeden yeni bir sınıf tanımı yapılabilir. Bu şekilde tanımlanan sınıflara isimsiz (anonymous) sınıflar denir.  İsimsiz sınıflar sadece tanımlandıkları yerde kullanılırlar.  En klasik kullanım alanları ...Listener (ActionListener,MouseMotionListener vs) gerçeklemeleridir. Örneğin NetBeans tarafından düğme kontrolü için üretilen kodları inceleyelim : [java] jButton1.addActionListener(new java.awt.event.ActionListener() { public void actionPerformed(java.awt.event.ActionEvent evt) { jButton1ActionPerformed(evt); } }); [/java] Burada **addActionLisener** metodu parametre olarak **ActionListener** arayüzünü gerçekleyen bir nesne alır.  Bu nesne isimsiz olarak tanımlanıp **ActionListener'da **gerçeklenmesi gereken **actionPerformed **metodunu içerir. Görüldüğü gibi sadece sınıf tanımı yapılıp sınıfa herhangi bir isim verilmemiştir.  İsimsiz sınıf tanımlama sentaksı [java] new Sınıfİsmi/Arayüzİsmi () {} [/java] şeklindedir. Eğer **Sınıfİsmi **verilmişse isimsiz sınıf bu sınıftan türer. Eğer **Arayüzİsmi **verilmişse isimsiz sınıf bu arayüzü gerçekler. İsimsiz sınıf sentaksını kullanarak koleksiyonlarımızı kısayoldan ilk elemanlarını ekleyebiliriz. Çifte parantez (Double Bracing) yöntemine bir örnek verelim : [java] List<Integer> numberList = new ArrayList<Integer>(){{ add(1);add(2);add(3);add(4);add(5);add(6); }}; [/java] [ad#Yazi Ici Buyuk]

## Comments

**[mustafa ulu](#1591 "2009-07-14 10:51:54"):** Yazıyı örnek kodlarla desteklesen daha güzel olurdu.

**[admin](#1592 "2009-07-14 11:41:33"):** Mustafa Bey yorumunuz için teşekkür ederim. Not yazmayı unutmuşum ama şu anda zaten dersi tamamlamadım. Örneklerle birlikte devamını bu akşam yazmayı planlıyorum.

