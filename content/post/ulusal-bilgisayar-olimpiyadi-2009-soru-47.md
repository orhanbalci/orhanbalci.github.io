title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 47
link: http://orhanbalci.net/tr/?p=435
author: Orhan Balci
description: 
post_id: 435
created: 2009/11/20 01:15:03
created_gmt: 2009/11/19 22:15:03
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-47
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 47

Aşağıdaki programın derlenip çalıştırılmasında ne olur? [cpp] char i, *p="ABCDEFG", q[8]="GFEDCBA"; main() { for(i=1; i<7; i++) q[i-1] -= p[i] % p[i-1]; printf("%s",q); } [/cpp] A) i değişkenine sayısal değer atandığından derleme hatası oluşur. B) p değişkenine atanan ilk değerin türünden ötürü derleme hatası oluşur. C) FEDCBAA D) AAAAAAA E) FFFFFFF CEVAP : i değişkeni her ne kadar char olarak tanımlansada sayısal değer atanabilir çünkü C'de char değişkenler sayısal değer olarak hafızada tutulurlar. p değişkeni de karakter işaretçi (pointer) olarak tanımlanmış olup atanan ilk değerde sorun yoktur. Döngümüzü inceleyecek olursak i değişkeni 1'den 6'ya kadar değerler alır yani döngümüz 6 kere döner. q[i-1] -= p[i] % p[i-1]; ifadesinin sağ tarafına bakacak olursak p[i] mod p[i-1] hesaplanmıştır yani p dizisinde bir sonraki elemanın bir önceki elemana göre modu alınmıştır. Örneğin döngünün ilk turunda bu ifade 'B' % 'A' şeklinde olacaktır. p dizisini incelediğimizde birer karakter artarak giden bir seri olduğunu görürüz. Yani bu işlemin sonucu her daim 1 olacaktır. İfademiz q[i-1] -= 1 şekline gelir. Bu da q dizisindeki elemanları birer azaltmak manasına gelir. Doğru şıkkımız C olacaktır.