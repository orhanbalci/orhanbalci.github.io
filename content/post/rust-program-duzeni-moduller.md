+++
title= "Rust Program Düzeni : Modüller"
date = "2016-01-27 15:29:31+08:00"
categories = ["Rust", "Yazilim"]
tags = ["Rust", "Modul"]
+++

Gelistiridigimiz projeler buyudukce bu karmasikligi yonetmek icin dillerin bize sagladigi soyutlama ve paketleme mekanizmalarini kullaniyoruz. Javada package, C++ da namespace kavramlari birbiriyle ilintili olan kod kumelerini gruplamaya yarayan yapilar. Rust dilinde ayni gorev icin moduller kullaniliyor. Modül tanimlamak icin `mod` anahtar kelimesi kullaniliyor. Yeri gelmisken deginmeden edemeyecegim Rust anahtar kelime konusunda diger dillere gore basitlik acisindan onde. Sık kullanılan anahtar kelımeler oldukca kısa tutulmus. Ornegin fonksiyon icin `fn`, modul icin `mod`, public icin `pub`. Ilk olarak modul tanimlamayi ogrenelim. Ornegin bir oyun yazdigimizi dusunelim. Matematik hesaplamalarda kullanacagimiz yapilari `math` modulune, ai algoritmalarimizi da `ai` modulune koyalim. Tabi bu modullere ait alt moduller de tanimlayalim :
{{<gist orhanbalci 31e6ea4482fd949d1b87>}}
Bu modulleri game_sample projemizde main.rs dosyasinda tanimliyoruz. Projemizin klasor yapisi kabaca su sekilde oluyor. 
{{<gist orhanbalci 0346d867ea24ccb818ae>}}
Aklimiza gelen ilk soru tum modulleri ayni dosya icerisine mi yazacagiz oluyor. Bu sorunu cozmek icin modul ismi ile ayni isimde bir .rs dosyasi olusturuyoruz ve modul icerigini bu dosyaya tasiyoruz. Bu ilk cozum. Math ve a.i modullerini kendi dosyalarina tasiyalim. Modul isimlendirirken snake_case isimlendirme yontemini kullaniyoruz. Tamamen kucuk harfleri kullanip kelimeler arasina _ koyuyoruz. main.rs dosyamizi duzenliyoruz. modul iceriklerini tasidigimiz icin burada sadece `mod math; mod ai;` satirlari kaliyor. Duzenlemeden sonra main.rs math.rs ai.rs dosyalarimiz :
{{<gist orhanbalci 26d320a4bf02a8e9c2ee>}}
{{<gist orhanbalci b5cf159fbcb893d5606a>}}
{{<gist orhanbalci d44117104421c67f41ae>}}
Dikkat etmemiz gereken husus hem main.rs icinde hem modul_adi.rs dosyasi icinde ayni modul tanimini tekrarlamamak. Bu adimi yaptiktan sonra klasorumuzun son hali su sekilde oluyor :
{{<gist orhanbalci 1df24b7e443d67f26e53>}}
Aslinda bir nebze de olsa karmasikliktan kurtulduk. Peki math ve ai modullerinin alt modullerini nasil dosyalamaliyiz. Onlari da ayni sekilde kendi dosyalarina alabilirmiyiz ? ai.rs dosyasinin icerigini su sekilde guncelleyelim ve bos bir agent.rs dosyasini olusturalim.  Son durumda dosyalarimiz su sekilde oluyor :
{{<gist orhanbalci 1df24b7e443d67f26e53>}}
`cargo build` komutu ile projemizi derlemeye calisinca su sekilde bir hata aliyoruz.
{{<gist orhanbalci 67da4ff939c672a6e5a6>}}
Hata mesaji aslinda ne yapmamiz gerektigini bize gosteriyor. Dallanmis modullerin bulundugu durumda hepsini ayni klasor icinde kendi dosyalarina alamiyoruz. Bu durumda Rust un ikinci modul tanimlama konfigurasyonunu kullanmamiz gerekiyor. Modul ismiyle ayni bir alt klasor olusturup icine `mod.rs` isminde kaynak dosyasi olusturuyoruz. ai klasoru olusturup icine mod.rs dosyasini olusturalim ve icerigini ai.rs dosyasindan kopyalayalim. Son durumda klasorumuzun yapisi su sekilde olusuyor. 
{{<gist orhanbalci d43ade45af3e1c50fd7d >}}
Modul yapisini klasor yapisiyla eslestirmis oluyoruz.  Rust ile gelistirilmis projeleri incelerken her alt klasorun altinda mod.rs dosyalari goreceksiniz. Bunlarin tamami modul tanim dosyalaridir. 
