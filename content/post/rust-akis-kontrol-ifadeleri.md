title: Rust Akış Kontrol İfadeleri
link: http://orhanbalci.net/tr/?p=1452
author: Orhan Balci
description: 
post_id: 1452
created: 2015/09/14 23:04:37
created_gmt: 2015/09/14 20:04:37
comment_status: open
post_name: rust-akis-kontrol-ifadeleri
status: publish
post_type: post

# Rust Akış Kontrol İfadeleri

Rust dilinde klasik kod akis kontrol ifadeleri bulunmakla beraber çok temel sentaks ve semantik farklar da var. Ilk olarak if/else yapisini inceleyerek farkları gormeye calisalim.  Yukarıda klasik bir if else yapisi ornegi verdim. Sentaks olarak dikkat etmemiz gereken ilk husus 4. satırda conditional ifade yazilirken `()` parantezlerin opsiyonel olmasi. Varsayilan olarak kullnilmiyor bu parantezler. kullanildiginda derleyici uyari veriyor. Ikinci sentaks kurali ise if-else bloklarini bildiren `{}` parantezlerinin zorunlu olmasi. Icinde tek ifade de yer alsa bunlar zorunlu. Ikinci ornekle asil can alici farki gorelim. If-else bloklari birer expression'dir. Yani atama ifadelerinde sag deger olarak kullanilabilirler.  Yukarıdaki örnekte 5. satırda if-else blokunun ciktisini `age_class` degiskenine atayabiliyoruz. Burada dikkat edilmesi gereken en önemli şey tum kontrol bloklarinin ayni tip veriyi donmesi gerektigidir. While dongusu c/c++ ile ayni. Do-while dongusu yok. Continue ve break ifadeleri aynen korunmus. Diger dillerden farkli olarak sonsuz dongu blogu icin `loop` bloklari mevcut. Bu bloklardan `break` ifadesi ile cikabilirsiniz.  For dongusu ise c/c++ dan farkli olarak Iterator'lar uzerinden calisiyor. Genel sentaks `for degisken in expression{}` seklinde. Burada `expression` bir iterator uretmek zorunda. En basit haliyle for dongulerini Range iteratorleri ile kullaniyoruz.  2\. satirdaki `1..15` ifadesi 1 dahil 15 haric olmak uzere bir Range iterator tanimi yapar. Birer birer degil de farkli bir artisla bir Range tanimlamak istersek :  Herhangi bir collection gezilmek istendiginde eger Iterator traitine sahipse for dongusu kullanilabilir. Ornnegin bir vektorun for loop ile guncellenmesi ornegine bakalim :  [ad#Yazi Ici Buyuk]