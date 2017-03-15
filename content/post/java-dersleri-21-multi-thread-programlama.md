title: Java Dersleri 21 - Multi Thread Programlama
link: http://orhanbalci.net/tr/?p=1099
author: Orhan Balci
description: 
post_id: 1099
created: 2011/08/11 23:31:52
created_gmt: 2011/08/11 20:31:52
comment_status: open
post_name: java-dersleri-21-multi-thread-programlama
status: publish
post_type: post

# Java Dersleri 21 - Multi Thread Programlama

İşlemciye aynı zaman diliminde birden fazla iş yaptırmanın iki yolu vardır. Bunlar farklı processler oluşturmak ve aynı process içinde farklı threadler oluşturmaktır. İşletim sistemimizde kendi başına çalışan tüm servisler, programlar birer process'tir. Process'lerin kendine ait bir çalışma ortamı bulunur. Burada çalışma ortamından kasıt ram'de kedine has bir çalışma yığınının (execution stack) olmasdır. Çoğu zaman elimizde hazır bulunan bir konsol uygulamasını kendi uygulamamız içinden çağırmak istediğimizde yeni bir process oluşturmamız gerekecektir. Java kendi uygulamamız içerisinden yeni processler oluşturmamızı ve bu processlerden çıktı almamızı sağlayan sınırlı bir API sunmaktadır. Küçük bir örnekle Java'da nasıl process oluşturulduğuna göz atalım. Bu örneğimizde linux sistem çağrıları yaparak yeni bir klasör oluşturup, var olan bir dosyayı sileceğim :  [java] import java.io.IOException; import org.openide.util.Exceptions; /** * * @author orhan */ public class CreateProcessExample { public static void main(String[] args) { try { ProcessBuilder pb = new ProcessBuilder("mkdir","afyon"); pb.start(); deleteFile("/media/Multimedia/projeler/netbeans/AlgorithmsPack/ShellSortApplet.java"); } catch (IOException ex) { Exceptions.printStackTrace(ex); } } public static void deleteFile(String fullFileName) throws IOException { ProcessBuilder pb = new ProcessBuilder("rm",fullFileName); pb.start(); } } [/java] Process'lerden kısaca bahsettikten sonra threadlerin nasıl oluşturulacağını öğrenelim. Bunun için iki yöntemimiz var : 

  1. **Thread sınıfını miras almak**
  2. **Runnable arayüzünü gerçeklemek**
Brinci yöntemimizde Thread sınıfından miras alınıp run() metodu override edilmelidir. Thread oluşturmanın en kolay yöntemi bu olmakla birlikte basit işlemler dışında tavsiye edilmemektedir. Sebebi ise Java'nın çoklu mirası desteklemediğinden dolayı Thread sınıfından miras alan bir sınıf başka bir sınıftan miras alamayacaktır. Bunun yerine ikinci yöntem olan Runnable arayüzünü gerçeklemek yazılımcıya daha rahat hareket etme olanağı sağlayacaktır. Bu şekilde oluşturulmuş bir thread örneğini inceleyelim : [java] /* * Bu kod parçası 14-08-2011 tarihinde * Orhan BALCI tarafından geliştirilmiştir. Herhangi bir lisansa * tabi olmayıp. Kulanıldığında http\\\orhanbalci.net adresi * referans olarak gösterilmelidir. */ package net.orhanbalci.threading; import java.io.BufferedReader; import java.io.BufferedWriter; import java.io.FileNotFoundException; import java.io.FileReader; import java.io.FileWriter; import java.io.IOException; import org.openide.util.Exceptions; /** * * @author orhan */ public class FileProcessingThread implements Runnable { private String fileName; private static final String[] reservedWords = {"select", "declare", "where", "from", "inner", "join"}; public FileProcessingThread(String fileName) { this.fileName = fileName; } public void run() { FileReader fr = null; FileWriter fw = null; try { fr = new FileReader(fileName); fw = new FileWriter(getTempFileName(fileName)); BufferedReader br = new BufferedReader(fr); BufferedWriter bw = new BufferedWriter(fw); String line = br.readLine(); while (line != null) { String[] lineSplit = line.split(" "); for (String element : lineSplit) { if (isReservedWord(element)) { element = element.toUpperCase(); } bw.write(element); bw.write(" "); } line = br.readLine(); bw.write("\n"); } bw.flush(); br.close(); fw.close(); } catch (FileNotFoundException ex) { StringBuilder sb = new StringBuilder(); sb.append("Dosya : ").append(fileName).append(" ").append("bulunamadı"); System.out.println(sb.toString()); } catch (IOException ex) { Exceptions.printStackTrace(ex); } finally { try { fr.close(); } catch (IOException ex) { Exceptions.printStackTrace(ex); } } } public synchronized String getTempFileName(String fileName) { int lastIndexOfDot = fileName.lastIndexOf('.'); String firstPart = fileName.substring(0, lastIndexOfDot); //System.out.println(firstPart); String secondPart = fileName.substring(lastIndexOfDot); //System.out.println(secondPart); StringBuilder sb = new StringBuilder(firstPart); sb.append("_temp").append(secondPart); return sb.toString(); } public synchronized boolean isReservedWord(String testString) { for (String keyword : reservedWords) { if (testString.equals(keyword)) { return true; } } return false; } } [/java] Örnekte methodların başında bulunan **synchronized** anahtar kelimesi önemlidir. Bu anahtar kelime tüm methodu thread safe yapmaya yarar. Yani iki ayrı thread bu methoda erişmeye çalıştıklarında erişim sequential hale gelecektir. Javada bu uygulamaya **intrinsic lock** mekanizması denir. Bu şekilde yazılmış bir kod thread safe olmakla beraber performans problemi yaşatacaktır. Multi-thread programlar geliştirirken aşağıdaki 3 problemin farkında olmak gerekir : 

  1. **Güvenilirlik Problemi :** Bu problem aslında multi-thread programlara özel değildir. Yazdığınız kod parçasının her koşulda doğru sonuç üretmesi prensibidir. Multi-thread programalama yaparken bu koşulu tehlikeye atan durumlar single-thread uygulamalara göre daha çoktur. Örneğin basit bir singleton pattern kodlamasını inceleyelim : [java] public Instance getInstance() { if(singleInstance == null) singleInstance = new Instance(); return singleInstance; } [/java] Bu kod parçası single-thread ortamda sorun yaratmayacağı halde multi-thread erişim olduğu durumda hatalı çalışma olasılığı vardır. 
[ad#Yazi Ici Buyuk]

## Comments

**[güney eser](#5382 "2012-03-29 15:33:08"):** çok faydalı oldu çok sağol :lol:

**[Mehmet Can MURAT](#45287 "2015-04-20 21:33:23"):** " Multi-thread programlar geliştirirken aşağıdaki 3 problemin farkında olmak gerekir. " demişsin ama sadece 1 tane var ..

**[admin](#45292 "2015-04-20 22:49:47"):** Bazi yazilarin icerigi uzun oldugu icin yarida birakiyorum. Bunu da tamamlayamamistim. Konuyu ogrenmek isterseniz Java Concurrency In Practice kitabi faydali olacaktir.

**[İlhan Kevser](#46903 "2015-05-10 06:36:06"):** Yarım anlatacaksanız hiç anlatmayın daha iyi. Hayır bırakın tamamlamayı yarım olduğunu bile biri sorana kadar belirtmemişsiniz.

