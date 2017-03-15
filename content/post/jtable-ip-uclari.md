title: JTable İp Uçları
link: http://orhanbalci.net/tr/?p=23
author: Orhan Balci
description: 
post_id: 23
created: 2008/03/15 17:48:58
created_gmt: 2008/03/15 15:48:58
comment_status: open
post_name: jtable-ip-uclari
status: publish
post_type: post

# JTable İp Uçları

**1) JTable Header görünmeme problemi.** Jtable kullanırken tablonun başlığını görebilmeniz için tablonuzun mutlaka JScrollPane içerisinde gösterilmesi gerekmektedir.  Örnek Kullanım: [java] booksTable = new JTable(); JScrollPane jsp = new JScrollPane(); jsp.setViewportView(booksTable); [/java] Aksi takdirde direkt olarak başka bir JComponent içerisinde gösterilmek istenirse tablonun sadece gövde kısmı görülecektir. Eğer tablonun başlık kısmı da gösterilmek istenirse JTable getTableHeader() metodu ile tablo başlık kısmının da ayrı olarak gösterilmek istenen JComponent üzerine eklenmesi gerekir. **2) JTableHeader Yüksekliğinin Ayarlanması** Herhangi bir tablonuzun başlık yüksekliğini ayarlamak için öncelikle JTable nesnenizden JTableHedaer nesnenize getTAbleHeader() metoduyla ulaşıp bu nesne üzerinde setPreferedSize() metodunu çağırmanız gerekir. Örnek Kullanım: [java] Dimension d = booksTable.getTableHeader().getPreferredSize(); d.setSize(d.width,BOOK_TABLE_ROW_HEIGHT); booksTable.getTableHeader().setPreferredSize(d); [/java] **3) JTable Seçili Hücre Değerinin Okunması** JTable da seçili hücre değerini almak için tablonun veri kısmını tutan model nesnesine ulaşmamız gerek. Bunun için JTable'dan aldığımız seçili hücre indekslerini model indekslerine çeviren convertRowIndexToModel() ve convertColumnIndexToModel() metodlarını kullanmalıyız. Daha sonra modelden bu indekslere karşılık gelen değeri almak için TableModel sınıfının getValueAt() metodunu çağırmalıyız. Örnek Kullanım: [java] int selectedTableIndex = _tblVaccineList.getSelectedRow(); int selectedModelIndex = _tblVaccineList.convertRowIndexToModel(selectedTableIndex); int selectedId = Integer.parseInt(_tblVaccineList.getModel().getValueAt(selectedModelIndex, 0).toString()); [/java] yukarıdaki örnek seçilen satırın ilk hücresindeki integer değeri almaya yarar. Burada tblVaccineList bir JTable nesnesidir.

## Comments

**[taha](#5445 "2012-05-07 19:19:37"):** Teşekkürler bilgilendirme için

