title: Swing Programlama : JFileChooser
link: http://orhanbalci.net/tr/?p=727
author: Orhan Balci
description: 
post_id: 727
created: 2010/04/03 22:22:59
created_gmt: 2010/04/03 19:22:59
comment_status: open
post_name: swing-programlama-jfilechooser
status: publish
post_type: post

# Swing Programlama : JFileChooser

Bu derste Java swing arayüzlerimizden sistemimizdeki dosya sistemine erişimi sağlayan JFileChooser sınıfının detaylarını anlatmaya çalışacağım. İlk olarak en temel haliyle bir JFileChooser diyalog penceresi nasıl açılır onu görelim : [java] JFileChooser jfc = new JFileChooser(); jfc.showOpenDialog(null); [/java] Bu kod parçacığı kullanıcının ön tanımlı dizinini gösteren bir dosya diyaloğu açar. Ön tanımlı dizininizi linux ortamında komut satırına "env" komutunu vererek ulaşabilirsiniz. Bu komutu çalıştırdığınızda karşınıza gelen listedeki HOME ortam değişkeni kullanıcının ön tanımlı dizinidir. Örnek görüntümüz şu şekilde olacaktır : [caption id="attachment_730" align="aligncenter" width="300" caption="JFileChooser Öntanımlı Klasör"]![JFileChooser Öntanımlı Klasör](/wp-content/uploads/JFileChooser1-300x204.png)[/caption] Peki biz dosya diyalogumuzu öntanımlı klasörde değil de başka klasörde açmak istersek ne yapmalıyız? Bunun için JFileChooser sınıfının parametre olarak dosya yolu yada dosya alan diğer yapılandırıcı metodunu kullanmalıyız. Örneğin ben dosya seçme diyaloğumu **"/home/orhan/Downloads"** klasöründe açmak istersem şu kod parçasını kullanmam gerekir : [java] JFileChooser jfc = new JFileChooser("/home/orhan/Downloads"); jfc.showOpenDialog(null); [/java] Bundan sonra ihtiyacımız olan kullanıcının hangi seçeneği seçtiğini öğrenmek. Kullanıcı herhangi bir dosyayı seçebilir veya işlemi iptal edebilir. Diyalogdan kullanıcı çıktısını şu şekilde alıyoruz : [java] JFileChooser jfc = new JFileChooser("/home/orhan/Downloads"); int kullaniciSecimi = jfc.showOpenDialog(null); [/java] Kullanıcı seiçimi değişkeninin alabileceği değerler de JFileChooser sınıfında tanımlanmıştır. Bu değerler : [java] JFileChooser.APPROVE_OPTION //seçim onaylandı JFileChooser.CANCEL_OPTION //seçim iptal edildi JFileChooser.ERROR_OPTION //işlem sırasında hata oluştu [/java] Şimdi kullanıcının seçmiş olduğu dosya ismini JFileChooser sınıfından almayı öğrenelim. [java] if (kullaniciSecimi == JFileChooser.APPROVE_OPTION) { System.out.println(jfc.getSelectedFile()); } [/java] Kullanıcı tarafından seçilen dosya referansına ulaşmak için **getSelectedFile()** metodunu kullanıyoruz. Eğer kullanıcıya birden fazla dosya seçme imkanı tanımak istiyorsak sırasıyla şu işlemleri yapmalıyız. [java] jfc.setMultiSelectionEnabled(true); int kullaniciSecimi = jfc.showOpenDialog(null); if (kullaniciSecimi == JFileChooser.APPROVE_OPTION) { for(File f : jfc.getSelectedFiles()) { System.out.println(f); } } [/java] Son olarak seçimimiza filtre eklemeyi öğrenelim. Örneğin sadec zip uzantılı dosyaların seçilebilmesini istiyorsak : [java] jfc.setFileFilter(new FileFilter() { @Override public boolean accept(File f) { if(f.isDirectory()) return true; String fileName = f.getName(); int nokta = fileName.lastIndexOf('.'); String ext = ""; if(nokta > 0) ext = fileName.substring(nokta+1); return ext.equalsIgnoreCase("zip"); } @Override public String getDescription() { return "ZIP Dosyaları"; } }); [/java] Yeni bir filtre eklemek için setFileFilter metodundan faydalandık. Bu filtremizde kullanıcının klasörleri ve zip uzantılı dosyaları seçebilmesine izin verdik. Dosya uzantısını saptayabilmek için String sınıfının lastIndexOf ve substring metodlarından yararlandık.

## Comments

**[çağdaş](#2685 "2010-04-28 14:28:56"):** tebrikler..

**[byrm](#4160 "2010-09-30 11:19:57"):** bu uygulama web browserda çalışmıyor. yani filechode penceresi çıkmıyor butona tıklayınca. ama derleme sırasında çalışıyor. signed applet yaptım gene olmadı...

