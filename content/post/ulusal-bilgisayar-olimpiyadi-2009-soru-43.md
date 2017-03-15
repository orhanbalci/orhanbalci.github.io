title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 43
link: http://orhanbalci.net/tr/?p=453
author: Orhan Balci
description: 
post_id: 453
created: 2009/12/02 22:20:58
created_gmt: 2009/12/02 19:20:58
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-43
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 43

Aşağıdaki programın derlenip çalıştırılmasında ne olur? [cpp] int i,j; main(void) { for (;i<j<10; i++,j++) printf("*"); } [/cpp] A)Sonsuz döngüye girip sürekli '*' basar B) 9 tane ‘*’ basar. C) 45 tane ‘*’ basar. D) Derleme hatası oluşacağından çalıştırılamaz E) Çalışır ama hiç birşey basmaz. CEVAP: Güzel bir operatör associativity sorusu. Associativity baskınlığı aynı olan operatörlerin sağdan sola mı soldan sağa mı hesaplanacağını belirtir. Burada döngü kontrol ifadesi olan [cpp]i<j<10[/cpp] buna bir örnektir. < operatörünün hesaplanma yönü soldan sağadır. Yani yukarıdaki [cpp]i<j<10[/cpp] ifadesinde öncelikle [cpp]i<j [/cpp] hesaplanır. < operatörü mantıksal (logical) bir operatör olduğu için yanlış olduğu durumda 0 doğru olduğu durumda 1 döner. Soruda i ve j'ye değer atanmadığından dolayı ilk olarak 0 değerini alırlar. Bundan dolayı [cpp]i < j [/cpp] ifadesi yanlış olur böylelikle 0 değeri döner. [cpp]i<j<10 [/cpp] ifadesi [cpp]0 < 10 [/cpp] olur ve döngüyü doğrular. i ve j değişkenleri döngünün her turunda eşit olacaklarından [cpp]i<j [/cpp] ifadesi her zaman 0 döncektir. Böylelikle döngü sürekli dönecektir. Doğru şıkkımız A.