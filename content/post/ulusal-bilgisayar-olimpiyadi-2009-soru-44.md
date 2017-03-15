title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 44
link: http://orhanbalci.net/tr/?p=449
author: Orhan Balci
description: 
post_id: 449
created: 2009/12/02 21:49:47
created_gmt: 2009/12/02 18:49:47
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-44
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 44

Aşağıdaki programın derlenip çalıştırılması sonucu ne basılır? [cpp] int i, a[] = {1,2,3,4,5,6,7}; void f(int i, int j) { int temp; if (i==j) return; temp = a[i]; a[i] = a[j]; a[j] = temp; } main(void) { f(1,2); f(2,6); f(6,1); for (i=0; i<7; i++) printf("%d ",a[i]); } [/cpp] A) 1 2 7 4 5 6 3 B) 1 6 3 4 5 2 7 C) 1 2 3 4 5 6 7 D) 1 1 1 1 1 1 1 E) Derleme hatası oluşacağından, çalıştırılamaz. CEVAP: Nispeten kolay bir soru. Öncelikle programda herhangi bir sentaktik hata yok. Tanımlanan f fonksiyonu bir değiş tokuş fonksiyonu (swap) olup parametrelerde verilen i. ve j. elemanların yerini değiştirir. Yapmamız gereken her f fonksiyonu çağrıldığında a dizisinin içeriğini yazarak takip etmek. f(1,2) sonrası : 1 3 2 4 5 6 7 f(2,6) sonrası : 1 3 7 4 5 6 2 f(6,1) sonrası : 1 2 7 4 5 6 3 Görüldüğü gibi son durumda dizimizde sırasıyla 1 2 7 4 5 6 3 değerleri bulunur. Doğru seçenek A şıkkı.