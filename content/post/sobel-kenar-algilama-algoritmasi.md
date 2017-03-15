title: Sobel Kenar Algılama Algoritması
link: http://orhanbalci.net/tr/?p=334
author: Orhan Balci
description: 
post_id: 334
created: 2009/09/17 23:30:51
created_gmt: 2009/09/17 20:30:51
comment_status: open
post_name: sobel-kenar-algilama-algoritmasi
status: publish
post_type: post

# Sobel Kenar Algılama Algoritması

![sobel2](/wp-content/uploads/sobel2.png) **Algoritma Adı:**Sobel Kenar Algılama Algoritması (Sobel Edge Detection) **Algoritma Türü:** Görüntü İşleme Algoritması **Açıklama:** Sobel kenar algılama algoritması görüntü işleme algoritmaları arasında en çok bilinenlerdendir. Verilen herhangi bir resimdeki kenarları elde etmeye yarar. Böylelikle resimler içindeki isteğe yönelik nesneler algılanıp gerekli işlemler yapılabilir. Sobel algoritmasında iki adet konvolusyon kerneli kullanılır. Bunlardan birisi yatay kenarları bulmaya yararken diğeri dikey kenarları bulmaya yarar. Bu kerneller görüntü içerisinde ışık yoğunluk değişiminin ani olduğu yerleri belirlememize yarar. Bir nevi türev yaklaşımıdır. Bu kerneller sırasıyla : 

1
0
-1

2
0
-2

1
0
-1

Yatay Sobel Kernel

1
2
1

0
0
0

-1
-2
-1

Dikey Sobel Kernel
şeklindedir. Gradyanlar (kernel uygulamasından sonraki yoğunluk değerleri) herhangi bir pixel için hesaplandıktan sonra büyüklükleri hesaplanarak kenarlar bulunmuş olur. Gradyan büyüklüğü iki gradyanın kareleri toplamının karekökü olarak hesaplanır. Java'da geliştirilmiş örnek bir sobel filtresini aşağıdan indirebilirsininiz. [ad#Yazi Ici Buyuk] [download id="4"]

## Comments

**[pc düşmanı](#51662 "2016-01-27 12:36:53"):** teşekkürler :)

