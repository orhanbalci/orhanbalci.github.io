title: Ulusal Bilgisayar Olimpiyadı 2009 - Soru 42
link: http://orhanbalci.net/tr/?p=462
author: Orhan Balci
description: 
post_id: 462
created: 2009/12/03 21:41:16
created_gmt: 2009/12/03 18:41:16
comment_status: open
post_name: ulusal-bilgisayar-olimpiyadi-2009-soru-42
status: publish
post_type: post

# Ulusal Bilgisayar Olimpiyadı 2009 - Soru 42

Aşağıdaki programın çalışması sonucu ne basılır? [cpp] int n=5, t, a, b, c; main(void) { for (a=1; a<=n; a+=1) for (b=1; b<=a; b+=3) for (c=1; c<=b; c+=2) t += a+b+c; printf("%d",t); } [/cpp] A) 36 B) 54 C) 67 D) 74 E) 93 CEVAP : İçiçe geçmiş döngü soruları çetrefilli olabilir. Genelde bu tür sorular için herkesin ayrı bir stratejisi vardır. Benim stretejim döngü değişkenlerinin alabileceği değerleri listeleyip kontrol ifadelerini doğrulamaktır. Yukarıdaki soru için sırasıyla a, b, c değişkeninin alabileceği değerleri yazalım : a : 1, 2, 3, 4, 5 b : 1, 4 c : 1, 3 a = 1 iken b = 1 ve c = 1 olabilir. a = 2 iken b = 1 ve c = 1 olabilir. a = 3 iken b = 1 ve c = 1 olabilir. a = 4 iken b = 1 ve c = 1 olabilir. b = 4 ve c = 1 olabilir. b = 4 ve c = 3 olabilir. a = 5 iken b = 1 ve c = 1 olabilir. b = 4 ve c = 1 olabilir. b = 4 ve c = 3 olabilir. Buradan t değişkeninde birikecek olan değer = [1+1+1] + [2+1+1] + [3+1+1] +[4+1+1] +[4+4+1] +[4+4+3] + [5+1+1] \+ [5+4+1] + [5+4+3] = 67. Doğrue seçenek C.