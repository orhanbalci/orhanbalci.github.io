title: Eklemeli Sıralama (Insertion Sort) Algoritma Appleti
link: http://orhanbalci.net/tr/?p=22
author: Orhan Balci
description: 
post_id: 22
created: 2008/03/15 17:27:54
created_gmt: 2008/03/15 15:27:54
comment_status: open
post_name: insertion-sort-algoritmasi-appleti
status: publish
post_type: post

# Eklemeli Sıralama (Insertion Sort) Algoritma Appleti

**Algoritma Adı:** Eklemeli Sıralama Algoritması(Insertion Sort) **Algoritma Türü:** Sıralama Algoritması **Açıklama:** Bu sıralama algoritması düzensiz dizi elemanlarını tek tek ele alarak her birini dizinin sıralanmış kısmındaki uygun yerine yerleştirme esasına dayanır. Genellikle günlük hayatımızda farketmeden sıkça kullandığımız bir çözüm yöntemidir. 2. elemandan başlayarak elemanın kendinden önceki elemanlarla karşılaştırılması suretiyle büyük elemanlar dizide sağa doğru kaydırılır. Böylelikle açılan uygun pozisyona o anda sıralanmakta olan eleman yerleştirilir.  Örnek İterasyonlar: İlk hal : 9 5 4 8 1 1\. İterasyon : Dizinin birinci elemanı 9 dizide kendinden bir sonraki elemandan büyük olduğu için 9 elemanı bir sağa kaydırılır 9'dan boşalan yere 5 elemanı yerleştirilir. 1\. İterasyon : 5 9 4 8 1 2\. İterasyon : Dizinin 2. elemanı 9 dizide kendinden bir sonraki elemandan büyük olduğu için 9 elemanı bir sağa kaydırılır. 2\. İterasyon : 5 4 9 8 1 3\. İterasyon : Dizinin 1. elemanı 5 sıralanmak istenen 4'ten büyük olduğu için 5 elemanı bir sağa kaydırılır. 5'ten boşalan yere sıralanmak istenen 4 yerleştirilir. 3\. İterasyon : 4 5 9 8 1 4\. İterasyon : 4 5 8 9 1 5\. İterasyon : 4 5 8 9 1 6\. İterasyon : 4 5 8 1 9 7\. İterasyon : 4 5 1 8 9 8\. İterasyon : 4 1 5 8 9 9\. İterasyon : 1 4 5 8 9 10.İterasyon : 1 4 5 8 9 

Algoritmanin javascript implementasyonu : [javascript] function insertionSort(sortArray) { for (var i = 1; i < sortArray.length; i++) { var k = i; while (k>0 && sortArray[k] < sortArray[k - 1]) { var swapTemp = sortArray[k]; sortArray[k] = sortArray[k-1]; sortArray[k-1] = swapTemp; k--; } } console.log(sortArray); } [/javascript]

## Comments

**[admin](#5469 "2012-05-17 17:20:13"):** Sayıların yerini hangi kurala göre değiştiriyorsunuz. Bunu söylerseniz algoritmayı söyleyebilirim.

**[esma](#5468 "2012-05-17 16:05:02"):** Merhaba, sıralamayı; 9 5 4 8 1 5 9 4 8 1 5 4 9 8 1 5 4 8 9 1 5 4 8 1 9 4 5 8 1 9 4 5 1 8 9 4 1 5 8 9 1 4 5 8 9.. şeklinde yapılamaz mı_? bu sıralama yönteminin kodlarını bilmiyorum. yazdıgınız sıralama üzerinden yorum yapıyorum..yda yaptıgım srıalama belki başka bir sıralama yöntemidir. bilgilendirirseniz sevinirim.

**[Eren](#5582 "2012-06-10 16:59:49"):** @Esma bubble sort yapmış

**[Can](#8948 "2013-06-02 12:41:45"):** 2.elemandan başlayarak sol taraf ile karşılaştırılmalı yazmışsınız fakat hep sağ tarfı ile karşılaştırıyorsunuz. üstelik 1. elemandn başlamışsınz. bu algoritma uygulaması hatalı bence

