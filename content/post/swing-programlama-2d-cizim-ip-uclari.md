title: Swing Programlama : 2D Çizim İp Uçları
link: http://orhanbalci.net/tr/?p=1092
author: admin
description: 
post_id: 1092
created: 2011/08/06 11:23:49
created_gmt: 2011/08/06 08:23:49
comment_status: open
post_name: swing-programlama-2d-cizim-ip-uclari
status: publish
post_type: post

# Swing Programlama : 2D Çizim İp Uçları

Bu yazım tam bir ders niteliğinde olmayıp bazı ip uçlarını barındırmaktadır. Eğer Java'da 2D çizim işlemleri hakkında bilginiz yoksa yararlı olmayabilir. 

  1. Dolgulu çizim yapmak için setPaint() ve fill...() metod çiftlerini kullanıyoruz. Örnek : [java] g2.setPaint(p); g2.fillRect(0, 0, 50, 70); [/java] 
  2. Çizimlerimizde text antialising modunu ayarlamak için : [java] //text antializing on g2.setRenderingHint(RenderingHints.KEY_TEXT_ANTIALIASING, RenderingHints.VALUE_TEXT_ANTIALIAS_ON); [/java] 
  3. Çizeceğimiz yazının boyutlarını almak için FontMetrics sınıfını kullanıyoruz. Örnek : [java] //çizeceğimiz stringin boyutlarını alıyoruz FontMetrics fm = g2.getFontMetrics(); Rectangle2D r2d = fm.getStringBounds(String.valueOf(number_), g2); [/java]