title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 41
link: http://orhanbalci.net/tr/?p=468
author: Orhan Balci
description: 
post_id: 468
created: 2009/12/06 14:29:09
created_gmt: 2009/12/06 11:29:09
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-41
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 41

Aşağıdaki programın çalışması sonucu ekrana ne basılır? [cpp] int n=5, t, a, b, c; main(void) { for (a=1; a<=n; a+=1) for (b=1; b<=a; b+=2) for (c=1; c<=b; c+=3) t += a+b+c; printf("%d",t); } [/cpp] A) 36 B) 54 C) 67 D) 74 E) 93 CEVAP: 42. Soruyla aynı tip soru. Takip edeceğimiz yöntem 42. soru ile aynı olacaktır. Yine döngü değişkenlerinin alabilecekleri değerleri yazarak işe başlayalım. a : 1, 2, 3, 4, 5 b : 1, 3, 5 c : 1, 4 a = 1 iken b = 1 c = 1 olabilir a = 2 iken b = 1 c = 1 olabilir a = 3 iken b = 1 c = 1 olabilir b = 3 c = 1 olabilir a = 4 iken b = 1 c = 1 olabilir b = 3 c = 1 olabilir a = 5 iken b = 1 c = 1 olabilir b = 3 c = 1 olabilir b = 5 c = 1 olabilir b = 5 c = 4 olabilir Buradan t değişkeninde birikecek olan değer = [1+1+1] + [2+1+1] + [3+1+1] + [3+3+1] + [4+1+1] + [4+3+1] +[5+1+1] + [5+3+1] + [5+5+1]+ [5+5+4] = 74 Doğru seçenek D.

## Comments

**[Umur](#3352 "2010-07-29 10:22:54"):** iyi çalışmalar birşeyi belirtmek isterim. c dilinde bir integer değişkene ilk atama yapmadan direk olarak toplama işlemine tabi tutmak bazen beklenmedik sonuçlara neden olabilir.

**[Umur](#3353 "2010-07-29 10:23:30"):** yani 1. satırda "t=0" yazmak daha doğru.

**[admin](#3355 "2010-07-29 11:00:11"):** Umur bey öncelikle konuyla ilgilendiğiniz için teşekkürler. Fakat gözden kaçırdığınız bir nokta var sanırım. Bahsettiğiniz durum stack değişkenleri için geçerlidir. Yani bu değişkenler main metodunun içinde tanımlansaydı söyledikleriniz geçerliydi. main metodunun dışında tanımlandıkları için bunlar global değişkenlerdir ve C'de global değişkenlere otomatik olarak her zaman ilk değer atanır. Saygılarımla.

