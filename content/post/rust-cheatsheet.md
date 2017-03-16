---
title: "Rust Cheatsheet"
link: http://orhanbalci.net/tr/?p=1501
author: Orhan Balci
description: 
post_id: 1501
date: "2015-12-18 15:29:31+08:00"
status: publish
post_type: post
---

# Rust Cheatsheet

Rust ile ilgili hatirlamak amacli notlardir : 

# Cargo Komutlari

  * Yeni proje olusturmak icin `cargo new proje_adi --bin` komutunu kullaniyoruz
  * carate aramak icin `cargo search crate_adi`
  * test build run icin `cargo test` `cargo build`` cargo run`
  * cargo alt komutlarini listelemek icin `cargo --list`

# String

  * &str; -> String donusumu String::from(&str;) seklinde yapiliyor
  * substring almak icin String yapisinin [begin_index..end_index] operatoru kullanilabilir
  * Herhangi bir tipi String e cevirmek icin o tipin to_string() fonksiyonunu kullanabilirsiniz `num.to_string()`
  * Herhangi bir Stringi diger tiplere cevirmek icin` parse::().unwrap()` fonksiyonunu kullaniyoruz
  * Stringi u8 vectore cevirmek icin `into_bytes` fonksiyonunu kullaniyoruz
  * byte arraydan Stringe donusum `String::from_utf8_lossy` fonksiyonu ile gerceklesiyor. Stringinizde unicode karakterler varsa istenmeyen sonuclar alabilirsiniz

# Collections

  * HashMap kullanimi icin use std::collections::HashMap
  * HashMap eklemek icin insert(key,value) apisi kullaniliyor
  * HashMap de varmi kontrolu contains_key(key) apisi ile oluyor
  * HashMap de value get(key) ile alinabiliyor Option donuyor unwrap yapmak gerekiyor
  * Vec son elemani `last()` ile aliyoruz. eger son eleman uzerinde degisiklik yapmak istersek `last_mut()` kullanmaliyiz
  * Vec iterasyonlarinda `i in vec.iter()` yerine okunaklilik acisindan `i in &vec;` kullaniyoruz
  * Elimizde Vec varsa bunu tek bir stringde birlestirmek icin concat() ve join() fonksiyonlarini kullaniyoruz
  * Vec nesnesinden 2 serli 3 erli gruplar elde etmek icin `chunks` fonksiyonunu kullaniyoruz. String icin bu yok maalesef.
  * slice parametreleri ffi interfaceden gecmek icin as_ptr kullaniyoruz

# Iterator

  * Azalan bir iterator elde etmek icin `(a..b).rev()` kullaniyoruz
  * Iterasyonda ilk n elemani atlamak icin `iter().skip(n) `kullaniyoruz

# Test

  * Floating point sayilar icin esitlik makrosu bulunmuyor. approx cratesi kulanilabilir
  * #[macro use] extern crate approx; partial_eq!()
