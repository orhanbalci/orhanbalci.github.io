title: Rust Closure
link: http://orhanbalci.net/tr/?p=1472
author: Orhan Balci
description: 
post_id: 1472
created: 2015/10/16 08:28:05
created_gmt: 2015/10/16 05:28:05
comment_status: open
post_name: rust-closure
status: publish
post_type: post

# Rust Closure

Fonksiyonel programlamanin bas aktorleri birinci sinif fonksiyonlar Rust dilinde de es gecilmemis. Isimli fonksiyonlarin nasil tanimlandigini daha onceki yazilarda gormustuk. Bu makalede isimsiz fonksiyonlardan yani closure lardan bahsedecegim. Closure yapilari fonksiyonel programlamanin bel kemigidir. Fonksiyonlarin diger fonksiyonlara parametre olarak gecilip, donus degeri olarak fonksiyonlari kullanabilmemizi saglarlar. Closurlerin en goze batan ozelligi tanimlandigi ortamdaki degiskenlere erisebilmeleridir ki isimleri de buradan gelir. Rust da closure sentaksi fonksiyonla birebir ayni olup `()` yerine `||` kullanilir. Ornek bir closure tanimini gorelim :  Yukarida verdigimiz closure ornegi parametresinden baska herhangi bir degiskene erismiyor, bir nevi statik fonksiyon. Yeni bir ornekte closurelarin tanimlandiklari ortamdaki degiskenleri nasil kapsama alanina aldigini (capture) gorelim.  3\. satirda tanimladigimiz `bigger_than_threshold` closure 2. satirda tanimladigimiz `threshold` degiskenine erisebiliyor. 5. satirda ise tanimladigimiz closureu `filter` methoduna parametre olarak geciyoruz. Yani bir fonksiyonu digerine parametre olarak gonderiyoruz. Peki her fonksiyonu her fonksiyona parametre olarak gecebilir miyiz? Tabi ki de hayir. Buradaki `filter` fonksiyonunun imzasina baktigimizda parametre olarak aldigi fonksiyonun imzasinin da belitildigini goruyoruz. Bu imzada anlamadiginiz yerler olabilir. Generic ler ve genericlerin traitler ile sinirlandirilmasi sozkonusu.  2\. satirda predicate parametresinin tipinin hangi tariti implement etmesi gerektigi gosteriliyor. Bu ornekten yola cikarak kendi metodlarimiza closure parametre almayi ve closurelari metodlarimizdan geri donmeyi ogrenelim. Bu sayede fonksiyon ureten fonksiyonlar yazabilir.Genel olarak gelistirdigimiz algoritmalarin ozel kisimlarini disaridan fonksiyon parametresi olarak alabiliriz. Bir ornekle fonksiyonlara parametre olarak fonksiyon gecmeyi ogrenelim. Yazacagimiz fonksiyon iki fonk. parametre alip bunlari 3. parametreye zincirleme olarak uygulayalim.  8\. satirda tanimladigimiz `closure_pipe` fonksiyonumuz parametre olarak iki tane fonk. aliyor. 9. ve 10. satirlarda bu fonk. parametrelerinin tipini belirtiyoruz. [ad#Yazi Ici Buyuk]