title: Kabarcık Sıralama (Bubble Sort ) Algoritma Appleti
link: http://orhanbalci.net/tr/?p=11
author: Orhan Balci
description: 
post_id: 11
created: 2007/06/20 23:57:48
created_gmt: 2007/06/20 21:57:48
comment_status: open
post_name: bubble-sort-kabarcik-siralama-algoritma-appleti
status: publish
post_type: post

# Kabarcık Sıralama (Bubble Sort ) Algoritma Appleti

**Algoritma Adı:** Kabarcık Sıralama Algoritması (Bubble Sort) **Algoritma Türü:** Sıralama Algoritması **Açıklama:** Sıralanacak eleman kümesinden ilk eleman alınır. Eğer kendinden sonrakinden büyükse yerleri değiştirilir. Sonraki elemana geçilir ve aynı işlem tekrarlanır. Dizinin sonuna varıldığında en büyük eleman sonda yer alır. Dizinin başına dönerek bu işlem sondan birinci elemana kadar tekrarlanır. Her adımda bir eleman daha azaltılarak devam eden iterasyon bütün elemanların yerini bulmasıyla sonlanır. Algoritmanın javada implement edilmiş hali : [java] for (int i = 1; i < sortArray.length; i++) { for (int j = 0; j < sortArray.length - i; j++) { if(sortArray[j] > sortArray[j+1]) { temp = sortArray[j+1]; sortArray[j+1] = sortArray[j]; sortArray[j] = temp; } } } [/java] Algoritmanin JavaScript implementasyonu : [javascript] /** * Created by Orhan Balci on 10.04.2015. */ var bubleSort = function(arrayToBeSorted){ for(var i = 1; i < arrayToBeSorted.length; i++){ for (var j = 0; j < arrayToBeSorted.length-1; j++) { if(arrayToBeSorted[j+1] < arrayToBeSorted[j]){ var tempSwap = arrayToBeSorted[j]; arrayToBeSorted[j] = arrayToBeSorted[j+1]; arrayToBeSorted[j+1] = tempSwap; } } } } var printNumbers = function(arrayTobePrinted){ var logMessage = ""; for (var i = 0; i < arrayTobePrinted.length; i++) { logMessage += arrayTobePrinted[i] + " "; } console.log(logMessage); } var testSorting = function() { var numberArray = []; numberArray.length = 100; for (var i = 0; i < numberArray.length; i++) { numberArray[i] = Math.round(Math.random() * 100); } printNumbers(numberArray); bubleSort(numberArray); printNumbers(numberArray); } testSorting(); [/javascript] 

[ad#Yazi Ici]

## Comments

**[Osman N. Yogurtcu](#29 "2007-06-29 20:26:13"):** Orhan, bu applet çalışmıyor. Sebep? :)

**[Orhan](#30 "2007-06-30 13:54:56"):** Niye çalışmasın güzel kardeşim :). Browserinda Java plugini varsa çalışır. Belki birde JRE'ni update etmen gerekebilir

**[hazan_06](#242 "2008-02-29 13:50:34"):** Sıralama uygulaman güzel olmuş. Benim de bir projem var ama nasıl yapacağımı bilmiyorum sıralama algoritmasından.Ben 10 tane resmi büyükten küçüğe doğru sıralayacağım sıralama algoritmasıyla. Bana yardımcı olursanız nasıl yapacağım konusunda teşekkür ederim. Mailinizi bekleyeceğim.

**[mdesigner](#1434 "2009-05-24 13:09:13"):** paylşım için teş.ler benim final ödevim bu dersten mesela 5,7,28,64,2,3,67 bu sayıları bu yöntemle yazmam lazımmış yardımcı olursan sevinirim

**[mavzeroglu](#1446 "2009-06-02 10:12:52"):** benim bir final ödevim var yardimci olabilirseniz sevinirim c++ da bubble sort yöntemiyle sayilarin siralanmasi icin bir program yazmamiz gerekiyo ama ben bilmiyorum bu konuda bana yardimci olabilirseniz sevinirim programda su özellikler isteniyo programın basinda kisiden kac sayi girilecegi istenecek ve teker teker sayilar istenecek ardindan büyükten küçüge mi yoksa kücükten büyügemi siralanacagi sorulacak siralama bittikten sonra ise cikmak istiyorsan h ye devam etmek istiyorsan e ye bas diye soracak ve e ye basinca program tekrar basa alip bizden aynı seyleri tekrar yapmamizi isteecek yani program tek seferlik olmayacak bo konuda yardim edebilirseniz cok sevinirim cünkü bu benim final ödevim yardiminiz icin simdiden tesekkür ederim

**[mahmut](#1443 "2009-06-01 12:40:22"):** arkadaşlar bu sitenin neresinde yazılmış halini bulabilirim ?

**[admin](#5448 "2012-05-08 13:45:19"):** Ödevlere yardımcı olmuyorum :). Sadece takıldığın yer varsa orayı cevaplayabilirim

**[isimsiz kahraman](#5449 "2012-05-08 14:53:38"):** Kırnap mısın?Aksöz mü?(Ahmet) :smile:

**[ahmet](#5444 "2012-05-06 00:36:50"):** Yüksekliği h ve 1’den 2h+1-1 , e kadar anahtarı olan mükemmel bir şekilde dengelenmiş ikili ağacı üretmek için bir fonksiyon yazınız. hocam ödev var yardımcı olur musunuz?

