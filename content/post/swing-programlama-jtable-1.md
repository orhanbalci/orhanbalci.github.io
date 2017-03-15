title: Swing Programlama: JTable Temel Kullanım
link: http://orhanbalci.net/tr/?p=14
author: Orhan Balci
description: 
post_id: 14
created: 2007/07/24 21:36:25
created_gmt: 2007/07/24 18:36:25
comment_status: open
post_name: swing-programlama-jtable-1
status: publish
post_type: post

# Swing Programlama: JTable Temel Kullanım

Bu yazımızda en basit haliyle Java UI programlamada sıkça kullandığımız JTable elemanının kullanımını ele alacağız. Herkesçe bilindiği üzere kullanıcı grafik arayüzü kütüphanelerinde veri ile ön yüzü birbirinden ayırmak için genel olarak MVC(model view controller) tasarım deseni kullanılır. Biz de işe tablomuzun model kısmını yani veri kısmını hazırlamakla başlayacağız.  **1)** Tablomuzun modelini oluşturmak için iki temel unsura ihtiyacımız var birincisi verinin kendisi yani tablonun hücrelerini dolduracak olan kısım diğeri ise sütün başlıkları. **2)** Verimizi şu şekilde tanımlayalım: [java] Object data[][] = { {"BJK", "Beşiktaş", 53}, {"GS", "Galatasaray", 50}, {"FB", "Fenerbahçe", 47}, {"KS", "Kayserispor", 44} }; [/java] **3)** Sütun başlıklarımızı da tanımlayalım: [java] String columnNames[] = {"Kısaltma", "Takım", "Puan"}; [/java] **4)** Şimdi tablo modelimizi tanımlayalım. Burada **DefaultTableModel** sınıfını kullanacağız. Fakat dikkat etmemiz gereken bir unsur var. **DefaultTableModel** sınıfı herbir sütun tipi olarak kullanıcıya tanımlı olarak Object nesnesi döner. Java dökümantasyonuna göre **DefaultTableModel** sınıfı **TableRowSorter** sınıfı ile birlikte kullanılırsa çok miktarda **toString()** metodunun çağrılmasına yol açar ve böylelikle performansta düşüş gözlenir. Bunu önlemek amacaıyla ön tanımlı olan **getColumnClass()** metodu override edilerek sütunların gerçek veri tipleri döndürülmelidir. [java] TableModel model = new DefaultTableModel(data, columnNames) { public Class getColumnClass(int column) { Class returnValue; if ((column >= 0) && (column < getColumnCount())) { returnValue = getValueAt(0, column).getClass(); } else { returnValue = Object.class; } return returnValue; } }; [/java] **5)** Artık tablomuzu oluşturabiliriz: [java] JTable table = new JTable(model); [/java] **Kaynaklar** [Java resmi sitesi JTable kullanım klavuzu.](http://java.sun.com/docs/books/tutorial/uiswing/components/table.html#eg) [JTable javadoc.](http://java.sun.com/javase/6/docs/api/)

## Comments

**[Murat](#51568 "2016-01-14 14:01:43"):** Merhaba, Ben Java 'ya yeni başladım sayılır. Basit bir evrak kayıt programı yaptım. Kaydetme tamam. Tabloya sağ tık sil-düzenle ve tekrar kaydet üzerinde çalışıyorum. Yalnız bu verileri tabloda gösterme işini yapamadım. Baya bir yerli yabancı forum gezdim. Oracle dokümanlarına da baktım ama çözemedim. Türkçe kaynak en büyük sıkıntı zaten ! Ama ilk defa performanstan bahseden bir sizi gördüm. İnce ve önemli bir ayrıntı. Bunun teşekkür ederim. Yalnız bu örneğinizi bir de MYSQL bağlantılı anlatabilir misiniz ? Ya da bu Tablo modelini performans ve güvenlik odaklı nasıl kullanabilirim ? Bir de modelinizde satır ile ilgili birşey göremedim. Açıklar mısınız ? Teşekkür ederim.

**[admin](#51612 "2016-01-20 13:44:59"):** Daha gelismis bir model sinifi olusturmak icin AbstractTableModel sinifini extend edebilirsiniz. Acikcasi Swing artik pek kullanilmiyor. Java ile desktop uygulamasi gelistirecekseniz JavaFX ogrenmenizi tavsiye ederim.

