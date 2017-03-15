title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 45
link: http://orhanbalci.net/tr/?p=440
author: Orhan Balci
description: 
post_id: 440
created: 2009/11/24 22:05:04
created_gmt: 2009/11/24 19:05:04
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-45
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 45

[cpp] char a[3][3] = {{1,2,3},{4,5,6},{7,8,9}}; void x(char i,char j) { char s; s = a[i][j]; a[i][j] = a[2-i][2-j]; a[2-i][2-j] = s; } main(void) { int i,j; for (i=0; i<4; i++) @@@@@@ ; for (i=0; i<3; i++) for (j=0; j<3; j++) printf("%d ",a[i][j]); } [/cpp] Yukarıdaki programın çalıştırılması sonucu 9 8 7 6 5 4 3 2 1 basılması için @@@@@@ ile gösterilmiş yerde ne olaması gerekir? A) x((i+1)%3-1,(i-1)%3+1) B) x((i-1)%3+1,(i+1)%3-1) C) x((i+1)%3,i/3) D) x(i/3,i%3) E) Bu seçeneklerden başka bir ifade. CEVAP : Programımızın verilen girdideki elemanlarının sırasını tersine çevirmesi beklenmektedir. Bunun için x(i,j) fonksiyonumuz tanımlanmıştır. x(i,j) iki boyutlu dizimizde (i,j) elemanı ile (2-i,2-j) elemanının yerlerini değiştiren bir swap fonksiyonudur. Örneğin i = 0, j = 0 için fonksiyonumu z a[0][0] ile a[2][2] elemanlarının yerlerini değiştirir. Dizimizin tersine çevrilmesi için şu yer değiştirme işlemleri yapılmalıdır : [0][0] <\--> [2][2] [0][1] <\--> [2][1] [0][2] <\--> [2][0] [1][0] <\--> [1][1] Yani x(i,j) fonksiyonumuzun alması gereken parametreler yukarıdaki değişimlerin sol tarafındaki değerlerdir. @@@@@@ ile gösterilen yer for (i=0; i<4; i++) döngüsünün altındadır. Buradan 1. sütundaki değerleri i/3 integer bölmesi ve i%3 mod işlemi ile elde edilebileceği görülmektedir. Doğru seçeneğimiz D olacaktır.