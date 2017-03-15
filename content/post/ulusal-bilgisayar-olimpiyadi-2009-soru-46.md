title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 46
link: http://orhanbalci.net/tr/?p=438
author: Orhan Balci
description: 
post_id: 438
created: 2009/11/20 14:22:49
created_gmt: 2009/11/20 11:22:49
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-46
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 46

Aşağıdaki programın derlenip çalıştırılması sonucu ne basılır? [cpp] int a,b,c; int main(void) { a = 9; { int b = 8; c = b; { int c=7; a = b;}} printf("%d %d %d",a,b,c);} [/cpp] A) 8 7 8 B) 8 0 8 C) 9 8 7 D) 7 0 8 E) Derleme hatası vereceğinden çalıştırılamaz. CEVAP: Yine klasik sayılabilecek bir değişken kapsamı (scope) ve gölgeleme (shadowing) sorusu. C'de değişkenlerin kapsamları ve ömürleri kapsama alanı içinde bulundukları süslü parantezlerle {} belirlenir. Örneğin programın başında tanımlanan int a,b,c, değişkenleri herhangi bir parantez içinde olmadıklarından evrensel(global) değişkenlerdir ve kod içinde her yerden ulaşılabilirler. Ömürleri programın başlamasıyla başlar bitişiyle sona erer. main fonksiyonu gövdesi içinde içiçe iki kod bloğu var. Bunlardan birincisinde tanımlanan int b = 8 ifadesi global b değişkenini gölgeler. Yani bu ifadededen sonra gelen ve blok içinde kalan tüm b'ler bu tanımdaki b'ye işaret eder. yine aynı şekilde ikinci iç blokta tanımlanan int c = 7 ifadesi evrensel c değişkenini gölgeler. Bu kurallar gözönünde bulundurarak değişkenlerimize atanan değerleri iç bloktan dış bloğa doğru takip edersek kolayca çözüme ulaşırız. En iç bloktaki a = b ifadesi ile evrensel a değişkenine 8 değeri atanır. İlk bloktaki c = b ifadesi ile de aynı şekil de evrensel c değişkenine 8 değeri atanır. kod bloklarına dikkatlice bakılacak olursa evrensel b değişkenine herhangi bir değer atanmamıştır dolayısıyla varsayılan değer olarak 0 değerindedir. Doğru cevabımız B seçeneği olacaktır.