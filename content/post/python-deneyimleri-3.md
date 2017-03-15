title: Python Deneyimleri 3
link: http://orhanbalci.net/tr/?p=639
author: admin
description: 
post_id: 639
created: 2010/02/17 12:05:45
created_gmt: 2010/02/17 09:05:45
comment_status: open
post_name: python-deneyimleri-3
status: publish
post_type: post

# Python Deneyimleri 3

[caption id="attachment_605" align="aligncenter" width="470" caption="Python Logo"]![Python Logo](/wp-content/uploads/python_logo.png)[/caption] 

  1. Python'da resim işlemek için standart bir kütüphane yok. Harici kütüphane olarak [PIL](http://effbot.org/zone/pil-index.htm) kullanılabilir
  2. Herhangi bir resim dosyasını açmak için **Image.open()** kullanılıyor. Teker teker piksellere **getpixel()** fonksiyonuyla ulaşılabiliyor
  3. Herhangi bir ASCII kodu karaktere çevirmek için **chr()** fonksiyonu kullanılıyor
  4. Herhangi bir listedeki değerleri tek string nesnesinde birleştirmek için sıkça **join()** fonksiyonu kullanılıyor. Örneğin [python] mesaj=[78, 110, 66, 101, 143, 114, 105, 116, 71] print '(',''.join([chr(k) for k in mesaj]),')' [/python]
  5. Resim dosyası üzerine çizmek için ImageDraw modülü kullanılıyor. Örnek : [python] im = Image.new('1', (500,500), 1) draw = ImageDraw.Draw(im) draw.line(listOfXYTuples) [/python]
  6. Dosya silmek için os modülünün **remove()** fonksiyonu kullanılıyor. Örneğin : [python] os.remove('sample.png') [/python]
  7. QString'den python stringine dönüşümü str fonksiyonu ile yapiyoruz
  8. PyQt denemeleri yapmak için QtDesigner entegrasyonu olan ERIC IDE'sini denedim ama NetBeans çok daha rahat bu konuda.