title: Java Dersleri 6 - Arayüzler ve Gerçeklenmesi (Interface and Implementation)
link: http://orhanbalci.net/tr/?p=116
author: Orhan Balci
description: 
post_id: 116
created: 2009/05/05 20:19:09
created_gmt: 2009/05/05 18:19:09
comment_status: open
post_name: java-dersleri-6-arayuzler-ve-gerceklenmesi-interface-and-implementation
status: publish
post_type: post

# Java Dersleri 6 - Arayüzler ve Gerçeklenmesi (Interface and Implementation)

[caption id="attachment_820" align="aligncenter" width="600" caption="Java Dersleri 6 Arayüzler"]![Java Dersleri 6 Arayüzler](/wp-content/uploads/java_banner_6.png)[/caption] Nesne odaklı programlamada arayüzler sınıfların dış dünyaya açılan kapılarıdır. Bir başka deyimle arayüzler sınıflar arası iletişimde imzalanan kontratlardır. Bir arayüzü gerçekleyen sınıf o arayüze ait metodların tamamını gerçeklemek zorundadır. Java prensip olarak çoklu mirası desteklememektedir. Bunun yerine ise çoklu arayüzleri gerçekleme imkanı sağlamıştır. Arayüzleri tanımlamak için "interface" anahtar kelimesi kullanılır.  Örnek bir arayüz tanımı : [java] public interface IDatabaseConnection { public void initConnection(String databaseName, String userName, String password) throws SQLException; public void destroyConnection() throws SQLException; public Connection getConnection(); } [/java] Arayüzler "interface" anahtar kelimesiyle tanımlanırken herhangi bir sınıf belirli bir arayüzü gerçekleyeceğini "implements" anahtar kelimesiyle bildirir. Şimdi yukarıdaki arayüzü gerçekleyen sınıfa bir gözatalım : [java] public class MYSQLDatabaseConnection implements IDatabaseConnection { private Connection mysqlConnection; public MYSQLDatabaseConnection() { } public void initConnection(String databaseName, String userName, String password) throws SQLException { try { Class.forName("com.mysql.jdbc.Driver"); } catch (ClassNotFoundException ex) { ex.printStackTrace(); } mysqlConnection = (Connection) DriverManager.getConnection("jdbc:mysql://localhost/" \+ databaseName, userName, password); mysqlConnection.setEncoding("utf8"); mysqlConnection.setCharacterEncoding("utf8"); mysqlConnection.setUseUnicode(true); } public Connection getConnection() { return mysqlConnection; } public void destroyConnection() throws SQLException { if (mysqlConnection != null) mysqlConnection.close(); } } [/java] Burada dikkat etmemiz gereken hususlar şunlardır: 

  1. Arayüz tanımıdaki metodlar public veya default erişim seviyesinde olabilir. 
  2. Arayüz kendisi public veya default erişim seviyesinde olabilir. 
  3. Arayüzlerde sadece final sınıf değişkeni tanımlanabilir. 
  4. Bir sınıf sadece bir sınıftan miras alabilirken, birden fazla arayüzü gerçekleyebilir. 
  5. Arayüz ile bu arayüzü gerçekleyen sınıf arasında mirastakine benzer bir ilişki vardır(is-a relationship). [java] IDatabaseConnection dc = new MYSQLDatabaseConnection(); [/java] kullanımı doğrudur.
  6. Arayüzler birbirinden miras alabilirler.
  7. Bünyesinde herhangi bir metod bulundurmayan arayüzlere İşaretleyici Arayüz (Marker Interface) denir. Bunların en ünlüsü Serializable arayüzüdür

## Comments

**[mutkan](#5456 "2012-05-10 14:15:49"):** Merhabalar, Gercek hayattan ornek vererek, interface i ne için kullandığımızı anlatabilir misiniz? Tesekkurler.

**[omer](#5465 "2012-05-17 03:24:55"):** Bi iNsaati class olarak düşünün. Interfacede diyorsunuz ki , benim iscilerimiz( fonksiyon,değişken vs.) Var. Bu işçilerin ne iş yaptiklarini söylemiyorsunuz da sadece bu işçiler ne alır ne verir onu söylüyorsunuz .class inizin içindeki ahmet adındaki bi fonksiyon iki tane integer alır void döner gibi mesela. Buna interface deniyor.

**[admin](#5254 "2012-02-01 14:30:16"):** İsmail bey düşünceniz biraz sığ kalmış. sizin için anlam ifade etmeyen şeyler başkaları için ediyor olabilir. Sizin çerçevenizden bakarsak programlama dillerine de gerek yok assemblyle işinizi görebilirsiniz Java'ya ne gerek var. Buarada amaç işinizi görmek değil işinizi yaparken sağlıklı yapmak.

**[ismail fedakar](#5251 "2012-02-01 03:05:07"):** merhabalar; Hocam rahatsız ediyorum ama keşke Interface in ne amaçla kullanıldığını ve varlık nedeninide yazsaydınız. Bu makale benim için hiç bir anlam ifade etmiyor. Böyle boş şeyleri yazmasanız olmazmı. Burada arayüz kulanmadanda veritabanı bağlantısı yapılabilirdi.

**[misafir](#7347 "2012-12-21 17:19:37"):** Allah razı olsun. Epey faydalı oldu. Böyle şeyler yazmaya devam edin. İşine yarayan da oluyor

