title: Python Deneyimleri 2
link: http://orhanbalci.net/tr/?p=620
author: Orhan Balci
description: 
post_id: 620
created: 2010/02/04 15:07:26
created_gmt: 2010/02/04 12:07:26
comment_status: open
post_name: python-deneyimleri-2
status: publish
post_type: post

# Python Deneyimleri 2

[caption id="attachment_605" align="aligncenter" width="470" caption="Python Logo"]![Python Logo](/wp-content/uploads/python_logo.png)[/caption] 

  1. Fonksiyon tanımlamak için def anahtar kelimesini kullanıyoruz. Fonksiyon çağrılmadan önce tanımlanmış olmalı
  2. from ... import ... ifadesinde birinci importtan sonra gelen yere modül adı importtan sonra gelen yere de fonksiyon adı giriliyor. Yani fonksiyonu import etme durumu var. Modül ednilen şey de bağımsız .py uzantılı dosyalar.
  3. Anladığım kadarıyla fonksiyona parametreler pass-by-value yöntemiyle gönderiliyor. [python] def fonksiyon(isim ): print "Fonksiyondan çağrıldı", isim isim = "hübele" isim = "hebele" fonksiyon(isim) print isim [/python]kod parçacığı [python] Fonksiyondan çağrıldı hebele hebele [/python] çıktısını veriyor. 
  4. Hemen bir recursive fonksiyon deneyip fibonacci yazıyorum. Sorun yok :) [python] def fibonacci(number): if number == 0: return 0 elif number == 1: return 1 else: return number + fibonacci(number-1) print fibonacci(5) [/python]
  5. Modülleri import ederken from "modül_adı import *" kullandığımızda "__" ile başlayan fonksiyonları import etmiyormuş dikkat etmek gerek
  6. Klasör oluşturma,silme,klasör içeriğini listeleme,harici çalıştırılabilir dosya çalıştırma, process açma kapama gibi işlemleri**os** modülü aracılığıyla yapıyoruz. Hayati öneme sahip.
  7. Herhangi bir modülde hangi fonksiyonların olduğunu öğrenmek için **dir(module_adı)** kullanılıyor.
  8. Text dosya okumak,yazmak çok kolay. Sadece open, write, close gibi fonksiyonlar kullanılıyor. Ama open dedikten sonra size dönen değişkenin tipini anlayamadım doğrusu. Fonksiyonlar modül dönebiliyorlar mı?
  9. [python] dosya = open("testdosyasi.txt","w") print type(dosya) [/python] çıktı olarak **type 'file'** veriyor. Bu **file** tipi nerede tanımlanmış onu bilmem lazım. 
  10. Matematikte üstlü sayıları hesaplamak için **** ** operatörü kullanılıyor
  11. zip dosyalarıyla ilgili işlemler yapmak için **zipfile** modülü mevcut. Komut satırından zip dosyası açmak kadar kolay kullanımı var
  12. Bir dosyanın zip dosyası olup olmadığını kontrol etmek için **is_zipfile()** fonksiyonu mevcut
  13. zip dosyası içinden herhangi bir dosya çıkarmak için **extract()** dosya meta verisine ulaşmak için **getinfo()** fonksiyonları mevcut.