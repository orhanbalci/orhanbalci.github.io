title: Seçim Sıralama(Selection Sort) Algoritma Appleti
link: http://orhanbalci.net/tr/?p=21
author: Orhan Balci
description: 
post_id: 21
created: 2008/03/08 20:15:11
created_gmt: 2008/03/08 18:15:11
comment_status: open
post_name: secim-siralamaselection-sort-algoritma-appleti
status: publish
post_type: post

# Seçim Sıralama(Selection Sort) Algoritma Appleti

**Algoritma Adı:** Seçim Sıralama Algoritması(Selection Sort) **Algoritma Türü:** Sıralama Algoritması **Açıklama:** Bu sıralama algoritması her iterasyonda düzensiz dizi içinden en küçük elemanın "seçilmesi" esasına dayandığı için seçim algoritması ismini almıştır. Algoritma 1. dizi elemanının, dizinin 2. elemanından sonuncu elemanına kadar olan küme içerisindeki en küçük eleman ile yer değiştirmesiyle başlar. Bir sonraki adımda 2. eleman, 3. elemandan son elemana kadar olan küme içerisinden en küçük elemanla yer değiştirir. Bu işlemler son elemanında yerini bulmasıyla sona erer.  Örnek İterasyonlar: İlk hal : 9 5 4 8 1 1\. İterasyon : Dizinin ilk elemanı 9 dizinin geri kalanının en küçük elemanı 1 ile yer değiştirir 1\. İterasyon : 1 5 4 8 9 2\. İterasyon : Dizinin ikinci elemanı 5 dizinin geri kalanının en küçük elemanı 4 ile yer değiştirir 2\. İterasyon : 1 4 5 8 9 3\. İterasyon : Dizinin üçüncü elemanı 5 dizinin geri kalanından küçük olduğu için değişime gerek yok. 3\. İterasyon : 1 4 5 8 9 3\. İterasyon : Dizinin dördüncü elemanı 8 dizinin geri kalanından küçük olduğu için değişime gerek yok. 3\. İterasyon : 1 4 5 8 9 [javascript]/** * Created by Orhan Balci on 10.04.2015. */ var selectionSort = function(arrayToBeSorted){ for(var i = 0; i < arrayToBeSorted.length -1; i++){ var smallest = Number.MAX_VALUE; var smallestIndex = Number.MAX_VALUE; for (var j = i+1; j < arrayToBeSorted.length; j++) { if(arrayToBeSorted[j] < smallest){ smallest = arrayToBeSorted[j]; smallestIndex = j; } } var tempSwap = arrayToBeSorted[i]; arrayToBeSorted[i] = smallest; arrayToBeSorted[smallestIndex] = tempSwap; } } var printNumbers = function(arrayTobePrinted){ var logMessage = ""; for (var i = 0; i < arrayTobePrinted.length; i++) { logMessage += arrayTobePrinted[i] + " "; } console.log(logMessage); } var testSorting = function() { var numberArray = []; numberArray.length = 100; for (var i = 0; i < numberArray.length; i++) { numberArray[i] = Math.round(Math.random() * 100); } printNumbers(numberArray); selectionSort(numberArray); printNumbers(numberArray); } testSorting();/** * Created by admin on 10.04.2015. */ [/javascript]