title: Fruchterman-Reingold Graf Yerleşim Algoritması
link: http://orhanbalci.net/tr/?p=584
author: Orhan Balci
description: 
post_id: 584
created: 2010/01/27 00:14:02
created_gmt: 2010/01/26 21:14:02
comment_status: open
post_name: fruchterman-reingold-graf-yerlesim-algoritmasi
status: publish
post_type: post

# Fruchterman-Reingold Graf Yerleşim Algoritması

[caption id="attachment_585" align="aligncenter" width="399" caption="Fruchterman-Reingold"]![Fruchterman-Reingold](/wp-content/uploads/FruchtermanReingold.png)[/caption] **Algoritma Adı:**Fruchterman-reingold Graf Yerleşim Algoritması** Algoritma Türü:** Graf Yerleşim Algoritması** Açıklama:** Graf yerleşim algoritmaları, graf üzerinde bulunan köşelerin verilen alan içerisine en iyi şekilde yerleştirilmesini amaçlar. En iyi yerleşimi sağlamak için şu temel prensipler göz önünde bulundurulur : 

  1. Köşeleri verilen alan içerisine homojen bir şekilde yay
  2. Kenar kesişmelerini en aza indirge
  3. Kenar uzunluklarını birbirine eşit tut
  4. Varolan simetriyi yansıt
  5. Alan büyüklüğüne adapte ol
Fructerman-Reingold algoritması bunların tamamını sağlayamasada 1,3 ve 4. prensipler bazında iyi bir performans sunar. Bu algoritma graf köşelerini birer çelik bilye kenarları ise birer yay kabul eden algoritmalar sınıfındandır. Graf yapısını fiziksel bir sisteme benzeterek enerjisini minimuma çekmeye çalışır. Gerçek fiziksel yay kuvvet hesapları kullanılmaz. Ayrıca gerçek sistemlerdeki itme ve çekme kuvvetlerini uygulamak yerine daha basit bir model takip edilir. İtme kuvvetleri tüm köşeler için hesaplanırken, sadece bağlı köşeler birbirini çeker. Algoritmanın pseudo kodu şu şekildedir : 
  1. Her köşe üzerine düşen itici kuvvetleri hesapla
  2. Her köşe üzerine düşen çekici kuvvetleri hesapla
  3. Köşeleri hareket ettir
  4. Maksimum mesafeyi azalt
  5. Yukarıdaki 4 maddeyi yeterince tekrarla
Algoritma her basamakta köşelerin maksimum hareket mesafesini biraz daha daraltarak sisteme damper etkisi vermekte. Algoritmanın nasıl çalıştığını daha iyi anlamak için ufak bir uygulama geliştirdim. Kullanmak için öncelikle graf yapınızın kayıtlı olduğu dosyayı açmanız, sonrada animasyon menüsünden başlatı seçmeniz gerekli. Algoritmanın detaylarına ve uygulamaya aşağıdaki linkten ulaşabilirsiniz. [download id="5"]