title: Google Java Kütüphanesi : Guava Cache
link: http://orhanbalci.net/tr/?p=1235
author: Orhan Balci
description: 
post_id: 1235
created: 2013/03/22 15:12:11
created_gmt: 2013/03/22 12:12:11
comment_status: open
post_name: google-java-kutuphanesi-guava-cache
status: publish
post_type: post

# Google Java Kütüphanesi : Guava Cache

[java] package net.orhanbalci.guavasamples; import com.google.common.base.Joiner; import com.google.common.base.Stopwatch; import com.google.common.cache.Cache; import com.google.common.cache.CacheBuilder; import java.math.BigInteger; import java.util.concurrent.Callable; import java.util.concurrent.ExecutionException; import java.util.concurrent.TimeUnit; /** * User: ob005273 * Date: 22.03.2013 * Time: 13:24 * Kullanıldığında http://orhanbalci.net adresi referans verilmelidir */ public class GuavaCache { private Cache<Integer,BigInteger> factorialCache; //private final Integer[] sampleArray = new Integer[] {1,2,3,4,5,6,7,8,9,10,11,12,13,14,15}; public GuavaCache() { factorialCache = CacheBuilder.newBuilder().maximumSize(1000).expireAfterWrite(3, TimeUnit.MINUTES).build(); } public static void main(String[] args) { GuavaCache gc = new GuavaCache(); try { gc.measureIt(); } catch (ExecutionException e) { e.printStackTrace(); } } public void measureIt() throws ExecutionException { BigInteger[] resultArray = new BigInteger[100]; Stopwatch s = new Stopwatch(); s.start(); for(int i = 0; i < 1000; i++) { resultArray[i] = factorial(i % 15); } s.stop(); System.out.println(Joiner.on(",").join(resultArray)); System.out.println("Cache olmadan : " \+ s.elapsed(TimeUnit.MILLISECONDS)); s.reset(); s.start(); for(int i = 0; i < 1000; i++) { resultArray[i] = factorialWithGuavaCache( i % 15); } s.stop(); System.out.println(Joiner.on(",").join(resultArray)); System.out.println("Guava cache : " \+ s.elapsed(TimeUnit.MILLISECONDS)); } public BigInteger factorialWithGuavaCache(final Integer a) throws ExecutionException { if(a == 1) { return BigInteger.valueOf(1); } return factorialCache.get(a, new Callable<BigInteger>() { @Override public BigInteger call() throws Exception { return BigInteger.valueOf(a).multiply(factorialWithGuavaCache( a - 1)); } }); } public BigInteger factorial(final Integer a) { if(a == 1) { return BigInteger.valueOf(1); } else { return BigInteger.valueOf(a).multiply(factorial(a - 1)); } } } [/java]