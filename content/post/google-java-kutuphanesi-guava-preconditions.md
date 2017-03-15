title: Google Java Kütüphanesi : Guava Preconditions
link: http://orhanbalci.net/tr/?p=1230
author: Orhan Balci
description: 
post_id: 1230
created: 2013/03/19 14:38:37
created_gmt: 2013/03/19 11:38:37
comment_status: open
post_name: google-java-kutuphanesi-guava-preconditions
status: publish
post_type: post

# Google Java Kütüphanesi : Guava Preconditions

İyi kod yazmanın önemli bir unsuruda defansif kod yazmaktır. Yani olabilecek hataları önceden sezip önlem almaktır. Defansif programlamanın önemli unsurlarından biriside kullanıcı tarafından verilen girdilerin, method parametrelerinin istenilen şartları sağlayıp sağlamadığının kontrolüdür. Bu ihtiyaca yönelik olarak çeşitli validasyon kütüphaneleri geliştirilmiş olmakla birlikte burada Guava'nın çözümünü anlatacağım. Guava'da parametre, değişken vs. validasyonu için Preconditions sınıfı geliştirilmiştir. Validasyonlar statik methodlar aracılığıyla yapılır. Bu methodların statik import edilmesiyle kod kalabalığından ciddi oranda kurtulabilirsiniz. Örneğin aşağıda Guava varken ve yokken parametre validasyonu yapan kodları inceleyelim : [java] package net.orhanbalci.guavasamples; import static com.google.common.base.Preconditions.*; public class GuavaPreconditions { public static void main(String[] args) { parameterCheckingWithoutGuava(null); parameterCheckingWithGuava(null); parameterCheckingWithoutGuava(5); parameterCheckingWithGuava(4); } public static void parameterCheckingWithGuava(Integer a) { checkNotNull(a,"a null olamaz"); checkArgument(a > 5, "a 5 ten küçük olamaz"); } public static void parameterCheckingWithoutGuava(Integer a) { if (a == null) { throw new NullPointerException("a null olamaz"); } if ( a < 5) { throw new IllegalArgumentException("a 5 ten küçük olamaz"); } } } [/java] Örnekte **parameterCheckingWithGuava()** methodu **Preconditions **sınıfından static olarak import edilen **checkNotNull **ve **checkArgument **methodlarını kullanıyor. Guava kullanımı yazılımdaki kod kalabalığını önlemiş oluyor. Örnekde bahsedilenlerin dışında array indeks kontrolüne yönelik de hazır methodlar bulunmakta. Aslında Java çekirdek kütüphanesinde bu işe yarayan **assert() **methodları bulunmakta. Fakat bu methodun işlevi compiler parametreleriyle düzenlenmiş durumda. Guava'yı yazılımın dış dünyayla haberleştiği arayüzlerde kullanıcı tarafından girilen verilerin doğrulamasında kullanıp, yazılımın kendi iç dünyasında assert() methodlarını tercih edebiliriz.