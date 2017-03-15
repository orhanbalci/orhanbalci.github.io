title: NetBeans Javadoc Entegrasyonu
link: http://orhanbalci.net/tr/?p=15
author: Orhan Balci
description: 
post_id: 15
created: 2007/07/26 21:59:30
created_gmt: 2007/07/26 19:59:30
comment_status: open
post_name: netbeans-javadoc-entegrasyonu
status: publish
post_type: post

# NetBeans Javadoc Entegrasyonu

**NetBeans 5.5 versiyonu için geçerlidir.** Java ile uygulma geliştirenler için başucu kaynağı niteliğindeki JDK Javadoc dökümantasyonuna erişim bu işin olmazsa olmazları arasındadır. Erişimle beraber dökümantasyonda aradığını anında bulabilme ve alabildiğine geniş onlarca dökümanı düzgün bir şekilde kontrol etmekte projelerin sağlıklı yürütülmesi açısından önemlidir. Bu yazıda kullandığımız herhangi bir java API'sinin dökümantasyonuna NetBeans'den nasıl erişeceğimizi öğreneneceğiz.  **1)** Öncelikle temel olan Java Platform Javadoc'unu NetBeans'e eklemeliyiz. Bunun için **Tools->Java Platform Manager** menüsünü seçin. **2)** Karşınıza çıkan pencereden önce sol taraftan Javadoc eklemek istediğiniz platformu seçin ve Javadoc sekmesini tıklayıp Add ZIP/Folder tuşuna basarak JDK'nıza ait Javadoc klasörünün veya zip dosyasının yerini bildirin. ![NetBeans Java Platform Manager](/wp-includes/images/netbeans/netbeans_platform_manager.png) **3)** Eğer JDK için değil de herhangi bir dış kaynaklı kütüphane kullanmak istiyorsanız ikinci adımı **Tools->Library Manager** seçerek tekrarlayın. **4)** Javadoc'larımızı NetBeans'e tanıttıktan sonra kod yazarken hızlı bir şekilde ulaşmak için aramak istediğimiz sınıfın veya methodun ismini editörde işaretledikten sonra **Shift+F1** tuş kombinasyonunu kullanabiliriz. Bir diğer yöntem ise **Tools->Javadoc** Index Search menüsünü kullanmaktır. ![NetBeans Javadoc Index Search](http://orhanbalci.net/tr/wp-includes/images/netbeans/netbeans_javadoc_index_search.png)

## Comments

**[erhan](#1319 "2008-11-17 01:52:29"):** selam ben üniversite son sınıf öğrencisiyim ve mobil öğrenme ortamları ile ilgili bir tezim var. tezde öğrencilerin cep tellerine derslerin konu anlatımlarını göndermem ve onları sınav yapmam gerekiyor. Netbeans' de yapmaya çalışıyorum fakat çözmek uzun zaman alıyor bu konu da özellikle kodları ile ilgili bir kaynak varmı? Yardımcı olursanız sevinirim.

