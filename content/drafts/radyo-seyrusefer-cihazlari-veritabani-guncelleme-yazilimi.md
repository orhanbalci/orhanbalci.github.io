title: Radyo Seyrüsefer Cihazları Veritabanı Güncelleme Yazılımı
link: http://orhanbalci.net/tr/?p=206
author: admin
description: 
post_id: 206
created: 2009/07/22 21:04:25
created_gmt: 2009/07/22 18:04:25
comment_status: open
post_name: radyo-seyrusefer-cihazlari-veritabani-guncelleme-yazilimi
status: draft
post_type: post

# Radyo Seyrüsefer Cihazları Veritabanı Güncelleme Yazılımı

Proje Tanımı :
HELSİM projesi kapsamında hava taşıtlarının gereksinim duyduğu seyrüsefer cihazlarınıın bilgilerinin güncellenmesi.

Proje Türü:
Ticari

Teknolojiler :
C++, Qt, PostgreSQL, PostGis, OGR, ARINC 424

Rol :

  * Harita altlık yapısının PostGis ve Qt yardımı ile gerçeklenmesi
  * ARINC 424 verisinin ayrıştırılması ve veritabanına aktarılması
  * VOR, TACAN, DME, Airport, Runway, FIR/UIR, Restricted Airspace, Controlled Airspace verilerinin vektörel olarak haritaya çizilmesi
  * Yukarıda sayılan verilerin ICAO kodu vs. anahtarlara göre sorgulanması
  * Verilerin belirli aralıklarla yedeğinin alınması