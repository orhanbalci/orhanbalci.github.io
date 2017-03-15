title: Swing Programlama : JTable Hücre Editörleri
link: http://orhanbalci.net/tr/?p=16
author: Orhan Balci
description: 
post_id: 16
created: 2007/08/02 19:41:27
created_gmt: 2007/08/02 16:41:27
comment_status: open
post_name: swing-programlama-jtable-hucre-editorleri
status: publish
post_type: post

# Swing Programlama : JTable Hücre Editörleri

Bu yazıda kısaca JTable hücreleri için öntanımlı olan editörün dışında özel editörler tanımlamayı öğreneceğiz. Bir önceki yazımızda kullanmış olduğumuz tablodaki puan sütununun editörünü JSpinner olarak değiştireceğiz.  **1)** Bu işlemi gerçekleştirmek için **TableColumn** sınıfının **public void setCellEditor(TableCellEditor cellEditor)** metodunu kullanacağız. Metodun imzasında da görüldüğü üzere bize **TableCellEditor** cinsinden bir editör lazım. Bunun için **TableCellEditor** interfacini implement etmemiz lazım. Bu interface şöyle bir baktığımızda implement edilmesi gereken birçok event fire metodunun olduğunu görürüz. Bizleri düşünen Sun mühendisleri bunun için **AbstractCellEditor** sınıfında bu event fire metodlarını implement etmişler. Öyleyse biz de işimizi bu sınıftan türettiğimiz bir editörle görebiliriz. Fakat sadece **AbstractCellEditor** sınıfından türetmek yeterli değil zira bu sınıfta olmayıp da **TableCellEditor** interfacinde bulunan **public Component getTableCellEditorComponent(JTable table, Object value, boolean isSelected, int row, int column)** metodunu implement etmeliyiz. Şöyleki : [sourcecode language="java"] public class JSpinnerTableCellEditor extends AbstractCellEditor implements TableCellEditor [/sourcecode] **2)** Bizim editörümüz **JSpinner** componenti olacak. Öyleyse bir sınıfımızda bir adet JSpinner referansı bulunmalıdır. **3)** Bunu da hallettikten sonra yapmamız gereken şey public **Object getCellEditorValue()** metodunu override etmek. [sourcecode language="java"] public class JSpinnerTableCellEditor extends AbstractCellEditor implements TableCellEditor{ JSpinner spin = new JSpinner(); public JSpinnerTableCellEditor() { } public Object getCellEditorValue() { return spin.getValue(); } public Component getTableCellEditorComponent(JTable table, Object value, boolean isSelected, int row, int column) { spin.setValue(value); return spin; } } [/sourcecode] **4)** Şimdi sıra bu editörü **JTable** nesnemize eklemekte. Bunun için yazımızın başına belirttiğimiz **TableColumn** sınıfının **void setCellEditor(TableCellEditor cellEditor)** metodunu kullanacağız. JTable'imizin **TableColumn** nesnesine ise **table.getColumnModel().getColumn(2);** şeklinde ulaşabiliriz burada **getColumn()** metoduna verdiğimiz parametre sütunun tablomuzdaki yerini bildirmektedir. Bu yazımıza ait kodları [buradan ](/kod/jlistcustomcelleditor.rar)indirebilirsiniz.

## Comments

**[Ömer](#41624 "2015-02-03 23:34:21"):** Teşekkürler. Güzel siteniz var

