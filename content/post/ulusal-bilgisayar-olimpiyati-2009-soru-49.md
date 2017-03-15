title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 49
link: http://orhanbalci.net/tr/?p=420
author: Orhan Balci
description: 
post_id: 420
created: 2009/11/18 22:45:12
created_gmt: 2009/11/18 19:45:12
comment_status: open
post_name: ulusal-bilgisayar-olimpiyati-2009-soru-49
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 49

Aşağıdaki programın derlenip calıştırılması sonucu ne basılır? [cpp] int i=5, j=7; main(void) { ((i>j) ? i : j) = 9; printf("%d %d",i,j); } [/cpp] Cevap: Bu soru biraz detaylı bilgi gerektiren bir soru ve programlama dilinden diline değişen cevaplara sahip. Ternary operator (üçlü operator) sentaksının bilinip bilinmediğini ölçen bir soru. C dilnde üçlü ?: operatörü koşullu ifadeler yazmakta kullanılır. Örneğin : [cpp] int a; int b; b=5; a = (b > 3) ? 1 : 2; [/cpp] burada b 3'ten büyük olduğu için ilk değer yani 1 değeri a değişkenine atanacaktır. Sorumuzda önemli olan ifade [cpp] ((i>j) ? i : j) = 9; [/cpp] ifadesidir. Burada üçlü operator asignment yani atama operatörünün solunda yer almaktadır. İfadenin sentaks olarak doğru olabilmesi için üçlü operatörün çıktısının lvalue olması beklenir. C dilinin standart versiyonunda yukarıdaki üçlü operatörün çıktısı i > j yanlış olduğu için j değişkeninin değeridir yani 7 dir, değikenin kendisi değildir. 7 = 9 gibi bir ifade geçerli bir ifade olmadığından programımız derleme hatasından dolayı çalışmayacaktır. Daha önce de belirttiğim gibi bu sorunun cevabı tamamen üçlü operatörün programlama dilinde nasıl gerçeklendiğine bağlıdır. Örneğin aynı programı c++ dilinde değiştirmeden derleyip çalıştırırsanız 5 9 değerlerinin basıldığını göreceksiniz. Bu ayrımın sebebi c++'da üçlü operatörün dönüş değerinin değişkenin değeri değil kendisi olmasıdır, bu da geçerli bir lvalue olduğundan program beklenen çıktıyı verir. Yine GNU C eklentilerinde de c++'a benzer bir yaklaşım sergilenmiş olup program 5 9 çıktısını verir. Aşağıdaki linkten daha ayrıntılı bilgiye ulaşabilirsiniz : [ http://tigcc.ticalc.org/doc/gnuexts.html#SEC70 ](http://tigcc.ticalc.org/doc/gnuexts.html#SEC70)