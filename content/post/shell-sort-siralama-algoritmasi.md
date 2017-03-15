title: Kabuk Sıralama (Shell Sort) Algoritma Appleti
link: http://orhanbalci.net/tr/?p=1083
author: Orhan Balci
description: 
post_id: 1083
created: 2011/08/04 23:26:35
created_gmt: 2011/08/04 20:26:35
comment_status: open
post_name: shell-sort-siralama-algoritmasi
status: publish
post_type: post

# Kabuk Sıralama (Shell Sort) Algoritma Appleti

[java] package net.orhanbalci.sort.shellsort; import java.util.Random; public class ShellSortExample { public static void main(String[] args) { int[] sortArray = new int[1000]; Random r = new Random(); for(int i = 0; i < 1000; i++) { sortArray[i] = r.nextInt(1000); } shellSort(sortArray); for(int i = 0; i < 1000; i++) { System.out.print(sortArray[i]+"\t"); if((i+1)%10 == 0) { System.out.println(""); } } } private static void shellSort(int[] sortArray) { int temp; for (int i = 8; i >= 1; i /= 2) { for (int j = 0; j < sortArray.length; j += i) { for (int g = j; g >= i; g -= i) { if (sortArray[g] < sortArray[g - i]) { temp = sortArray[g]; sortArray[g] = sortArray[g - i]; sortArray[g - i] = temp; } } } } } } [/java] [ad#Yazi Ici]