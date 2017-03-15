title: HSQLDB İpuçları
link: http://orhanbalci.net/tr/?p=560
author: Orhan Balci
description: 
post_id: 560
created: 2010/01/18 01:16:36
created_gmt: 2010/01/17 22:16:36
comment_status: open
post_name: hsqldb-ipuclari
status: publish
post_type: post

# HSQLDB İpuçları

1. HSQLDB'yi sunucu kipinde çalıştırmak için : `java -cp ./hsqldb.jar org.hsqldb.Server -database.0 file:veritabanı dosya adı -dbname.0 veritabanı alias adı` komutu girilmlidi. Bu komut hsqldb.jar dosyasının olduğu klasör içinde verilmiştir. 
  2. HSQLDB'ye dosya kipinde bağlanırken veritabanı dosya yolunu jar dosyanıza göreceli verebilirsiniz. Jar dosyanız ile veritabaı dosyanız aynı klasörde bulunuyorlarsa veritabanı bağlantı Stringiniz : `"jdbc:hsqldb:file:./veritabanı dosya adı"` şeklinde olmalıdır.