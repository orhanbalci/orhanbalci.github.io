title: Java 7 İle Gelen Yeni Özellikler
link: http://orhanbalci.net/tr/?p=1137
author: Orhan Balci
description: 
post_id: 1137
created: 2012/12/18 14:40:54
created_gmt: 2012/12/18 11:40:54
comment_status: open
post_name: java-7-ile-gelen-yeni-ozellikler
status: publish
post_type: post

# Java 7 İle Gelen Yeni Özellikler

Bildiğiniz üzere Java'nın major versiyon güncellemelerinde dile ait yeni özellikler eklenmekte. Java 7 versiyonu ile birlikte gelen özelliklerden önemli gördüklerimi burada örneklerle anlatmak istedim. Faydalı olması ümidiyle... 1) Java 7 versiyonuyla birlikte switch ifadelerinde string constant kullanabilme yeteneği dile kazandırıldı. Çoğu programcının ihtiyacı olabilecek bir özellik. Örnek : [java] public class StringOnSwitch { public static void main(String[] args) { String sampleString = new String("sample"); switch (sampleString) { case "Sample" : System.out.println("Case sensitivie çalışıyor mu?"); break; case "Örnek" : System.out.println("Unicode string"); break; case "sample": System.out.println("Burası ekrana yazılmalı"); break; default: System.out.println( "Burası yazılmamalı"); } } } [/java] 2)Try catch bloklarında kod tekrarını önleyen çoklu exception yakalama mekanizması geliştirilmiştir. Eğer benzer exceptionlar için benzer kod bloklarını çalıştırıyorsanız bu özellik kodun okunulurluğunu arttıracaktır. Catch anahtar kelimesinden sonra yakalayacağımız exceptionları "|" karakteri ile ayırıyoruz. Sozdizimi su sekilde --> BirinciExceptionTipi | IkinciExceptionTipi ...| NinciExceptionTipi exceptiondegiskeni. Örnek : [java] public class MultiCatch { public static void main(String[] args) { try { FileReader fis = new FileReader("test.txt"); BufferedReader br = new BufferedReader(fis); DatagramSocket ds = new DatagramSocket(6161); } catch (FileNotFoundException | SocketException e) { e.printStackTrace(); } } } [/java] 3) Yine exception handling mekanizmasına güzel bir eklenti olarak otomatik kaynak kapamaya olanak sağlayan try-with-resources blokları eklendi. Bu özellik C#'da mevcut olan kullanışlı ve faydalı özelliklerden bir tanesiydi. Kaynak kullanımını daha efektif hale getiriyor. Try anahtar kelimesinden sonraki parantezlere dikkat! Buradaki parantezlere yazacağımız kaynak nesneleri java.lang.AutoClosable arayüzünü gerçeklemek zorunda. Örnek : [java] public class AutomaticResources { public static void main(String[] args) throws IOException { try(InputStream is = new FileInputStream("girdi.txt"); OutputStream os = new FileOutputStream("çıktı.txt")) { int i = is.read(); os.write(i); } } } [/java] 4) Jenerik sınıflarda tip bilgisini belirtmek için kullanılan "<>" operatörü tip bilgisini tahmin edebilir duruma getirildi. Yine kod okunulurluğunu artıracak bir gelişme. Örnek : [java] public class DiamondOperator { public static void main(String[] args) { //java 7'den önce ArrayList<HashMap<Integer,TreeMap<Long,String>>> beforeList = new ArrayList<HashMap<Integer,TreeMap<Long,String>>>(); //java 7'den sonra ArrayList<HashMap<Integer,TreeMap<Long,String>>> afterList = new ArrayList<>(); } } [/java] [ad#Yazi Ici Buyuk]

## Comments

**[İbrahim Gündüz](#7539 "2013-01-18 01:17:07"):** Java 7 ile güzel ilerlemeler olmuşa benziyor. Galiba Switch içerisinde equals() methodunu kendi işliyor? IgnoreCase özelliği için nasıl bir şey yapmak gerek acaba merak ettim?

