title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 48
link: http://orhanbalci.net/tr/?p=428
author: Orhan Balci
description: 
post_id: 428
created: 2009/11/20 00:11:58
created_gmt: 2009/11/19 21:11:58
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-48
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 48

Aşağıdaki programın derlenip calıştırılması sonucu ne basılır? [cpp] int i; main(void) { printf("%d",(++i)++); } [/cpp] Cevap: 49. soruya benzer bir soru. Pre increment ve post increment operatörlerinin kullanımı soruluyor. Bu operatörlerin aldığı parametreler lvalue cinsinden olmalıdır yani pointer veya variable cinsinden olmalıdır. Yani 9++ gibi bir ifade geçersizdir. Dolayısıyla (++i)++ ifadesinde (++i) değeri lvalue olamayacağı için ifade geçersizdir. Programımız derleme hatası verecektir.