title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 50
link: http://orhanbalci.net/tr/?p=416
author: Orhan Balci
description: 
post_id: 416
created: 2009/11/18 21:58:50
created_gmt: 2009/11/18 18:58:50
comment_status: open
post_name: ulusal-bilgisayar-olimpiyati-2009-soru-50
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 50

Aşağıdaki programın derlenip çalıştırılması sonucu ne basılır? [cpp] #include <stdio.h> int x,y,z; main(void) { for (x=1,y=2,z=3; x<10,y<5,z<10; x++,y--,z=x++); printf("*"); } [/cpp] Cevap : Klasik bir dikkat sorusu. Hemen döngünün kaç kere dönmesi gerektiğini hesaplamak yerine sentaktik olarak programı incelememiz gerekir. For döngüsünün hemen sonundaki ; döngü gövdesi yerine geçmiştir. Yani aşağıdaki printf("*") satırı döngü dışındadır böylelikle sadece bir kere çalışmış olur. Cevabımız 1 adet * basılır olacaktır. Bu soruda döngü sonundaki ; kaldırılacak olursa cevabımız 5 adet * basılır olacaktır. Döngü sayısını kısıtlayan değişken z değişkenidir. z değişkeni sırasıyla 3,2,4,6,8 değerlerini alarak döngü koşulunu 5 kere sağlamış olacaktır.