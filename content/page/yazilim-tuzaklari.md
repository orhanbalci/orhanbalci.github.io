title: Yazılım Pratikleri
link: http://orhanbalci.net/tr/?page_id=139
author: Orhan Balci
description: 
post_id: 139
created: 2009/06/23 10:56:37
created_gmt: 2009/06/23 07:56:37
comment_status: open
post_name: yazilim-tuzaklari
status: publish
post_type: page

# Yazılım Pratikleri

1. XML dosyası işlerken yorum bloklarının da birer düğüm olduğunu unutma.
  2. Yazılımın durum geçişlerinde listelerini gözden geçirmeyi, gerekiyorsa temizlemeyi unutma.
  3. Kullanıcının yazılımı beklenilen düzende,sırada kullanacağını düşünme. Arayüzde kullanıcıyı doğru sıralamaya zorla. Basmaması gereken tuşları pasifleştir. Durum geçişlerini iyi kavra.
  4. Kaynak kontrolü (CVS,SVN) altında bulunan klasörleri taşırken dikkatli ol. Mümkünse kopyala-taşı yerine ithal-taşı (Export) yöntemini uygula.
  5. Cebirsel ifadelerle uğraşırken birimlere dikkat et. Özellikle trigonometrik hesaplarda derece, radyan ayrımına özen göster.
  6. C++ fonksiyonu override ederken fonksiyonun const olup olmadığına dikkat et.
  7. Kullandığın IDE'yi iyi tanı. Etkili klavye kullanımını öğren. Kısayolları öğren. Visual Studio 2005 kısayolları : 
    * Derle : Ctrl + F7
    * Debug : F5
    * Debug Tek Adım : F10
    * Tüm Satırı Sil : Ctrl + Shift + L
    * Proje Ayarlarını Aç : Alt + F7
    * İmleci Geri Al: Ctrl + -
    * Fonksiyonu Takip Et : F12
    * Tam Ekran : Alt + Shift + Enter
    * Seçili Metni Yorum Bloğuna Al : Ctrl + K, Ctrl + C
    * Seçili Metni Yorum Bloğundan Çıkar : Ctrl + K, Ctrl + U
    * İmleç Altındaki Kelimeyi Seç: Ctrl + W
  8. Kaynak kontrolü (CVS,SVN) altında bulunan projeni **hergün en üst klasörden** güncelle. Yapılan değişikliklerden haberdar ol.
  9. 0'a bölme hatasına dikkat et!
  10. Veri yapılarının avantajlarını iyi öğren. Her zaman liste kullanmaktan vazgeç. HashTable, Ağaç vb. veriyapılarını uygun yerlerde kullanmaya gayret et.
  11. Kütüphane : [JUNG ](http://jung.sourceforge.net/)Java'da graf yapılarını görselleştiren, graf algoritmalarını gerçekleyen geniş bir kütüphane.
  12. Kütüphane : [Colt](http://acs.lbl.gov/~hoschek/colt/) Java'da yüksek performanslı hesaplama kütüphanesi.
  13. Yazılımın stabilitesini korumak için aynı anda bir tek değişiklik yap.
  14. Veritabanı : [HSQLDB](http://www.hsqldb.org/doc/guide/index.html). Java Sanal Makinası üzerinde hem sunucu hem tekbaşına taşınabilir bir şekilde çalışabilen veritabanı yönetim sistemi.
  15. İf kontrol ifadelerinde == yerine = kullanımından doğan hatalara dikkat et.
  16. Kullandığın OOP dilin tür dönüşümü(casting) ve metod yükleme (method overloading) kurallarını çok iyi bil
  17. Tortoise, Team Foundation Server gibi versiyonlama sistemlerinin karşılaştırma (diff) ve birleştirme (merge) araçlarını kullanmak yerine [Beyond Compare](http://www.scootersoftware.com/) veya [Araxis Merge](http://www.araxis.com/) tarzı daha profesyonel araçları kullan
  18. Hibernate kullanarak proje yapıyorsanız bilgisayarınızın dil ayarlarını İngilizce olarak ayarlamayı unutmayın
  19. Yazılım dünyasında "amele işi" olarak tanımlanan ve sıkça tekrarlanan işleri her seferinde manuel olarak yapmak yerine bu işleri otomatik olarak yapan araçları programlayıp geliştirin.
  20. Yazılım dünyası sadece desktop ve web programcılığından ibaret değildir. Kendinizi geliştirmek için varolan araçlara ihtiyacınızı karşılayacak pluginler programlayın.
  21. Programlama dili fanatiği olmayın. İhtiyacınızı en kısa zamanda en hızlı şekilde giderebilmenin yollarını arayın. Herhangi bir script dili ile 5 dk'da yapılabilecek iş için saatlerce C kodu yazmayın.

##### Vim Komutlari

  1. :colo TAB -> Renk temasini degistir
  2. BufferNumber Ctrl+6 -> Su an guncelledigimiz bufferi degistir
  3. gg -> ilk satira git
  4. :ls -> acik bufferlari listele
  5. G$ -> son satirin son karakterine git
  6. 0 -> satir basina git
  7. ^ -> satirin ilk karakterine git
  8. :%s/eski/yeni/g -> find replace all

#####  Calisma Ortamim 

##### 

  1. <https://github.com/bhilburn/powerlevel9k>
  2. <https://github.com/powerline/fonts>
  3. <https://github.com/vim-airline/vim-airline>
  4. <https://github.com/Anthony25/gnome-terminal-colors-solarized>
  5. <https://github.com/bling/vim-bufferline>
  6. <https://github.com/ivanceras/rust-vim-setup>
  7. <https://github.com/airblade/vim-gitgutter>

## Comments

**[elif](#4348 "2010-11-17 22:32:10"):** hocam,veri yapıları hakkında araştırma yaparken sitenize rastladım,ne kadar yardımcı oldu anlatamam..herşey için çok teşekkürler,artık müdavimiyim buranın :)

**[admin](#7245 "2012-12-07 10:13:07"):** google adsense den kaynaklanan bir sorun :) yine de teşekkürler

**[mustafa](#7228 "2012-12-03 21:07:23"):** hocam sana da faydalı olsun diye reklama tıklayayım dedim ama reklam yok :)

**[Orhan Balci](#8353 "2013-05-07 19:50:59"):** Guzel yapmissin bu siteyi Hollanda'dan selamlar Orhan Balci'dan.www.linkedin.com/orhanbalci :???:

