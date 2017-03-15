title: Çarpışma Algılama Yöntemleri ve Algoritmaları #1: Matematik Temelleri
link: http://orhanbalci.net/tr/?p=874
author: Orhan Balci
description: 
post_id: 874
created: 2010/10/29 12:36:24
created_gmt: 2010/10/29 09:36:24
comment_status: open
post_name: carpisma-algilama-yontemleri-ve-algoritmalari-1-matematik-temelleri
status: publish
post_type: post

# Çarpışma Algılama Yöntemleri ve Algoritmaları #1: Matematik Temelleri

[caption id="attachment_878" align="aligncenter" width="600" caption="Çarpışma Algılama Algoritmaları"]![](/wp-content/uploads/collision_detection_banner.png)[/caption] Yeni bir makale dizisiyle tecrübelerimi sizinle paylaşmak istiyorum. Yine uzun soluklu bir yazı dizisi olacağını tahmin ediyorum. Çarpışma algılama yöntemleri fiziksel olayların taklit edildiği veya birebir simüle edildiği yazılımlarda nesneler arasındaki etkileşimi gerçekçi kılmak için kullanılırlar. Oyunlar ve simülasyonlar temel kullanım alanları olmakla beraber haptik uygulamaları, sanal gerçeklik uygulamaları da akademik alanda çarpışma kontrol algoritmalarının ilgi alanındadır. İçerisinde çok fazla geometrik problem barındıran bu alanda geliştirilen algoritmalar tatminkar sonuçlar üretebilmektedir. Özellikle oyun sektörünün çok fazla gelişmesiyle bu konu üzerinde ilerleme de gayet hızlı olmuştur. Bu kadar girizgahtan sonra çarpışma algılama algoritmaları geliştirirken göz önünde bulundurulan kriterlere değinelim : 

  * Ölçeklenebilirlik : Üzerlerinde çarpışma kontrolü yapılacak olan nesne sayısının azaltılıp arttıralabilmesi durumudur. Az sayıda nesne üzerinde iyi sonuçlar verebilen bir algoritmanın çok fazla sayıda nesne üzerinde işe yarayacağının garantisi yoktur. Örneğin elinizle sanal ortamdaki kısıtlı sayıda nesnelerle etkileşime girmenizi sağlayan bir sanal gerçeklik uygulaması için gerekli olan algoritma ile yüzlerce aracın içerisinde bulunduğu trafiği simüle etmek için gerekli olan algoritma ölçeklenebilirlik açısından farklı olabilir.
  * Performans : Bir önceki kriterle doğrudan ilintili olan bir problemdir. Geliştirdiğiniz çözüm yöntemi belki binlerce nesne üzerinde çalışabilir fakat bunu saniyeler mertebesinde yapıyorsa çoğu zaman kullanışsızdır. Çarpışma algılama algoritmalarının kullanıldığı uygulamaların büyük çoğunluğu gerçek zamanlıdır. Yani hesaplamalrı en kötü ihtimalle 60 hetz'de yapılabiliyor olması gereklidir. Bu da sistemdeki tüm işlemler için elinizde yaklaşık olarak 1000ms/60 = 16.67 mili saniye var demektir. Bir işlemci için bu zaman uzun olmakla beraber çözdüğünüz problem yüzlerce hatta binlerce nesneyi içeriyorsa ciddi bir problemle karşı karşıyasınız demektir.
  * Güvenilirlik : Bu tür algoritmalar doğası gereği çok fazla sayıda ondalık sayı işlemi gerektirir. Bu da her zaman için hataya açık bir konu olmuştur. Geometrik nesnelerin tanımlanmasından kaynaklanan hatalarda sistemi kararsız hala getirebilir. Bu tür sorunlar gözönünde bulundurulduğunda çok çeşitli çarpışma sorgu girdisine karşı algoritmanın her zaman aynı güvenilirlikte sonuç vermesi azami önem taşımaktadır.
  * Hassasiyet : Yine yukarıdaki kriteri tamamlar niteliktedir. Uygulamanın türüne göre hassasiyet belirlemek mümkündür. Örneğin cerrahi bir simülatör için mm hassasiyet bile yeterli olmayabilecekken basit bir oyunda 10-15 cm hassasiyet sorun olmayacaktır.
En temelde geometrik sorulara cevap aradığımız için temel lineer cebir bilgisi şarttır. Çok sayıda matris ve vektör işlemi yapacağımızdan bu işlemleri destekleyen kütüphanelerden yararlanmak işinizi büyük oranda kolaylaştıracaktır. Java tarafında bunun için Cern araştırmaları kapsamında geliştirilen [Colt](http://acs.lbl.gov/software/colt/) kütüphanesini önerebilirim (yazacağım örneklerde bu kütüphaneyi kullanacağım). Bu kütüphaneyi kullanarak matris işlemleri yapmayı bir örnekle görelim. [java] void doSampleOperations() { DoubleFactory2D f1 = DoubleFactory2D.dense; DoubleMatrix2D m2d = f1.random(3, 3); System.out.println("Rastgele matrix:"); System.out.println(m2d.toString()); Algebra a = new Algebra(); DoubleMatrix2D m2d2 = a.transpose(m2d); System.out.println("Transpose alınmış hali:"); System.out.println(m2d2); DoubleMatrix2D m2dInverse = a.inverse(m2d); System.out.println("Tersi:"); System.out.println(m2dInverse); System.out.println(a.det(m2d)); System.out.println(a.det(m2d2)); } [/java] [ad#Yazi Ici]

## Comments

**[vantutiri](#4349 "2010-11-18 04:44:49"):** Harika bi yazı.Bu yazının devamını bekleyemiyorum

**[KayL](#4209 "2010-10-30 01:37:41"):** Yazı için teşekkürler.Sabırsızlıkla bekliyoruz

