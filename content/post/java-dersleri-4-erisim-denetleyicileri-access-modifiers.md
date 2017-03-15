title: Java Dersleri 4 - Erişim Denetleyicileri (Access Modifiers) 
link: http://orhanbalci.net/tr/?p=92
author: Orhan Balci
description: 
post_id: 92
created: 2009/04/12 18:52:05
created_gmt: 2009/04/12 16:52:05
comment_status: open
post_name: java-dersleri-4-erisim-denetleyicileri-access-modifiers
status: publish
post_type: post

# Java Dersleri 4 - Erişim Denetleyicileri (Access Modifiers) 

[caption id="attachment_794" align="aligncenter" width="600" caption="Java Dersleri 4"]![Java Dersleri 4](/wp-content/uploads/java_banner_4.png)[/caption] Bu dersimizde Java'nın metodlar ve sınıflar üzerinde erişim kurallarını düzenleyen anahtar kelimelerini ve nasıl kullanıldıklarını örnekleriyle öğreneceğiz. Java'da dört adet erişim düzeyi bulunmakla birlikte üç adet erişim denetleyici anahtar kelime vardır. Dördüncü erişim düzeyi ise bu kelimelerin bulunmadiği seviyedir. Erişim kontrolü yazılımda her birimin kendi işine odaklanmasına yardımcı olur. Temelde nesne yönelimli programanın ana unsrlarındandır. Veri kapsülleme, miras ve çok biçimlilik paradigmalarının hayata geçirilmesine olanak tanırlar. Java'da erişim denetleyici anahtar kelimeler şunlardır: **1)Public 2)Protected 3)Private ** Bu anahtar kelimelerle işaretlenmemiş her türlü Java yapısı default erişim seviyesine sahip olur ki bu da dördüncü erişim seviyesidir. Sırasıyla bu seviyeleri ve aralarındaki erişim ilişkilerini açıklamaya çalışalım. **1)Public Erişim Seviyesi** Bu anahtar kelime önüne geldiği sınıfı,değişkeni, methodu diğer bütün kod bloklarından erişilebilir olarak işaretler. Sınıf seviyesinde kullanılabildiği gibi sınıf elemanları seviyesinde de kullanılabilir. Örneğin : [java] public class FrmVet extends JPanel implements IDataChangeListener, ListSelectionListener { } [/java] FrmVet sınıfı tanımında kullanılan public anahtar kelimesi bu sınıfın proje kapsamında diğer tüm sınıflar tarafından kullanılabilieceğini belirtir. Bu örnekte ise : [java] public abstract class QueryManagerBase { public ResultSet runSelectQuery(String query) throws SQLException { Statement s = (Statement) connection.getConnection().createStatement(); return (ResultSet) s.executeQuery(query); } } [/java] public anahtar kelimesi runSelectQuery(String query) metodunu diğer sınıflar tarafından kısıtlama olmadan erişilebilir olarak işaretlemiştir. **2)Protected Erişim Seviyesi** Bu erişim seviyesi sınıflara uygulanamamakla birlikte metodlara ve sınıf değişkenlerine uygulanır. Önünen geldiği elemana "alt sınıflardan" ve "aynı pakette bulunan sınıflardan" ulaşılmasına izin verir. Örneğin : [java] public abstract class QueryManagerBase { protected IDatabaseConnection connection; protected ArrayList<idatachangelistener> dataChangeListeners; } [/java] bu sınıftaki connection ve dataChangeListeners değişkenlerine ancak QueryManagerBase sınıfının alt sınıflarından yada bu sınıfla aynı pakette yer alan sınıflardan erişilebilir. Yukarıdaki sınıfın alt sınıfı olan bu örnekte kullanımı görelim : [java] public class QueryManager extends QueryManagerBase { public boolean addClient(EntityClient client) throws SQLException { java.sql.PreparedStatement ps = connection.getConnection() .prepareStatement(_insertClientQuery); ps.setString(1, client.getAd()); ps.setString(2, client.getSoyad()); ps.setString(3, client.getAdres()); ps.setString(4, client.getTelefonEv()); ps.setString(5, client.getTelefonCep()); ps.setString(6, client.getAciklama()); int result = ps.executeUpdate(); notifyDataChangeListeners(DataChangeKey.CLIENT); return result == 1; } } [/java] Bu örnekte QueryManager sınıfı QueryManagerBase sınıfının alt sınıfıdır. QueryManagerBase sınıfında protected olarak işaretlenen connection değişkeni [java] java.sql.PreparedStatement ps = connection.getConnection() .prepareStatement(_insertClientQuery); [/java] satırında kullanılmıştır. **3)Private Erişim Seviyesi** Protected erişim seviyesine benzer olarak sadece sınıf elemanlarına yani sınıf değişkenlerine ve metodlarına uygulanabilir, sınıf seviyesinde uygulanamaz. İşaretlediği elemanı sadece sınıf içerisinden erişilebilir kılar. Yani ne aynı paketteki diğer sınıflar ne de alt sınıftan bu elemanlara erişilemez. Örnek : [java] public class MYSQLDatabaseConnection implements IDatabaseConnection { private Connection mysqlConnection; } [/java] Buradaki MYSQLDatabaseConnection sınıfına ait olan mysqlConnection değişkeni private olarak işaretlenmiş yani sadece sınıf elemanları tarafından kullanılabilir, MYSQLDatabaseConnection sınıfı haricinde kullanılamaz. **4) Default Erişim Seviyesi** Java'da sınıf seviyesinde veya sınıf üyeleri seviyesinde herhangi bir erişim belirleyici anahtar kelimenin kullanılmadığı durumdur. Bu tip sınıflara ve elemanlara kullanıldıkları sınıf içerisinden ve aynı paketteki diğer sınıflardan erişilebilir. Anlattıklarımızı aşağıdaki tabloda özetleyebiliriz: 

Erişimci
Sınıf
Paket
Alt Sınıf
Diğer

Public
Erişim Var
Erişim Var
Erişim Var
Erişim Var

Protected
Erişim Var
Erişim Var
Erişim Var
Erişim Yok

Default
Erişim Var
Erişim Var
Erişim Yok
Erişim Yok

Private
Erişim Var
Erişim Yok
Erişim Yok
Erişim Yok
Kaynaklar: 

  * [Sun Java Sitesi](http://java.sun.com/docs/books/tutorial/java/javaOO/accesscontrol.html)

## Comments

**[iicocuk](#4788 "2011-03-22 16:27:02"):** Hocam iyi güzel de bu alt sınıf üst sınıf olayına girmişsin biz sınıfı anlamadan. alt sınıf ne üst sınıf ne ayrımcılık mı var :) böyle public private in mantığı nedir yani? başka sınıflarda yazacağımız kodlarda aynı isimde sınıflar falan varsa karışmasın diye mi? işte java bu yüzden kasıyor herkesi ya çok not tutman lazım ya da çok kafa tüketmen lazım yanılıyor muyum?

**[Hooop](#5375 "2012-03-27 00:35:15"):** Hocam çok teşekkürler.Başka yerde vidyolar var.Bir konuyu 2-3 saatte anlatıyor.Burdada bayağı kısaymış :)Ortası tutturursanız daha mı iyi olur acaba? Nasıl yapsak ki onu? Yazmasam mı ki artık? Bu Leyla ile Mecnun'u izleyince insanın konuşması mı değişiyor ki? Nasıl oluyor acaba? Nasıııııl?

