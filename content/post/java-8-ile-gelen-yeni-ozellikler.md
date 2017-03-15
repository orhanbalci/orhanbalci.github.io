title: Java 8 İle Gelen Yeni Özellikler
link: http://orhanbalci.net/tr/?p=1273
author: Orhan Balci
description: 
post_id: 1273
created: 2014/10/14 10:23:55
created_gmt: 2014/10/14 07:23:55
comment_status: open
post_name: java-8-ile-gelen-yeni-ozellikler
status: publish
post_type: post

# Java 8 İle Gelen Yeni Özellikler

1. Stream API [java] package net.orhanbalci.java8features; import java.util.ArrayList; import java.util.List; public class StreamExample { public static void main(String[] args) { List<Integer> numberList = new ArrayList<Integer>() {{ add(1); add(2); add(3); add(4); add(5); add(6); }}; System.out.println(sum(numberList)); } public static double sum(List<Integer> lst) { return lst.stream().filter(i -> i > 4).mapToDouble(i -> 1.0 / i).sum(); } } [/java] 
  2. Fonksiyonel Arayüzler(Functional Interfaces) [java] @FunctionalInterface interface DoerFunction{ void doSomething(); } [/java] 
  3. Method References [java]package net.orhanbalci.java8features; import java.util.ArrayList; import java.util.List; import java.util.stream.Collectors; public class FunctionReferenceExample { public static void main(String[] args) { List<String> stringList = new ArrayList<String>() {{ add("elma"); add("armut"); add("limon"); }}; stringList.forEach(i -> System.out.print(i)); stringList = stringList.stream().map(StringIncrementer::add).collect(Collectors.toList()); System.out.print("/"); stringList.forEach(i -> System.out.print(i)); } } class StringIncrementer { public static String add(String t1) { return t1.concat("-"); } } [/java] 
  4. Optional [java] package net.orhanbalci.java8features; import java.util.Optional; public class OptionalExample { public static void main(String[] args) { Optional<String> stringWithDefault = Optional.of("Default"); System.out.println(stringWithDefault.orElse("Default yoksa bu gelsin")); Optional<String> stringWithoutDefault = Optional.ofNullable(null); System.out.println(stringWithoutDefault.orElse("Default yoksa bu gelsin")); } } [/java]
  5. Tekrarlanan Annotation [java] package net.orhanbalci.java8features; import java.lang.annotation.Repeatable; @Repeatable(LogLevels.class) @interface LogLevel { String level(); } @interface LogLevels { LogLevel[] value(); } [/java] [java]package net.orhanbalci.java8features; @LogLevel(level = "INFO") @LogLevel(level = "WARNING") public class RepeatableAnnotationExample { }[/java] 
  6. Lambda İfadeleri: Java'ya eklenen en radikal yapılar lambda ifadeleri oldu. Sentaks (x) -> x * x şeklinde. Fonksiyonel programlama ile haşır neşir olanlar anlamakta zorluk çekmeyecektir. [java] public class Main { public static void main(String[] args) { List<Integer> intlist = new ArrayList<Integer> (){{add(1);add(2);add(3);add(4);add(5);}}; intlist.forEach((x)-> System.out.println(x * x)); } } [/java] 
[ad#Yazi Ici Buyuk]