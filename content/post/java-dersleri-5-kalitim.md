title: Java Dersleri 5 - Kalıtım (Inheritance)
link: http://orhanbalci.net/tr/?p=103
author: Orhan Balci
description: 
post_id: 103
created: 2009/04/26 13:56:54
created_gmt: 2009/04/26 11:56:54
comment_status: open
post_name: java-dersleri-5-kalitim
status: publish
post_type: post

# Java Dersleri 5 - Kalıtım (Inheritance)

[caption id="attachment_818" align="aligncenter" width="600" caption="Java Dersleri 5 Kalıtım"]![Java Dersleri 5 Kalıtım](/wp-content/uploads/java_banner_5.png)[/caption] Bu derste Java'nın nesne yönelimli programlamanın temeli olan kalıtım(Inheritance) kavramını nasıl gerçeklediğini öğreneceğiz. Yazılım terminolojisinde kalıtım bir sınıfın diğer bir sınıfın özelliklerini belirli kısıtlar çerçevesinde kazanmasıdır. Aynı kod parçalarının tekrar tekrar yazılmasını engellemenin yanı sıra nesneler arasında gerçek hayata benzer mantiki bağlar kurulmasını kolaylaştırır. Kalıtımın gerçeklenmesini sağlayan anahtar kelime "extends" dir. Örneğin :  [java] public class PointPlotter extends JXGraph [/java] sınıf tanımında PointPlotter sınıfının JXGraph sınıfından miras aldığını belirtmiş oluyoruz. Buradaki JXGraph sınıfına PointPlotter sınıfının üst sınıfı denir. Kalıtım sınıflar arasında tek yönlü bir ilişki tanımlar. PointPlotter sınıfının her nesnesi aynı zamanda bir JXGraph nesnesinin özelliklerini taşımakta iken tersi yani JXGraph nesnelerinin PointPlotter nesnesi özellikleri taşıması söz konusu değildir. Buradaki sınıf değişkenleri ve metodlarının miras alınmasında erişim denetleyicilerin kısıtlamaları söz konusudur. Erişim denetleyicilerin anlatımı için [buraya](http://orhanbalci.net/tr/?p=92) bakabilirsiniz. Bir örnekle kalıtım mekanizmasının nasıl işlediğini daha iyi anlayalım: [java] package net.orhanbalci.data; /** * * @author Orhan BALCI */ public class Point2D<t> { protected T x_; protected T y_; public Point2D(T x_, T y_) { this.x_ = x_; this.y_ = y_; } public Point2D(Point2D</t><t> p) { this.x_ = p.getX(); this.y_ = p.getY(); } public Point2D() { } public T getX() { return x_; } public void setX(T x) { this.x_ = x; } public T getY() { return y_; } public void setY(T y) { this.y_ = y; } @Override public String toString() { return "Point2D ["+x_+"," +y_+"]"; } } [/java] [java] package net.orhanbalci.data; /** * * @author orhan */ public class Point3D</t><t> extends Point2D</t><t> { private T z_; public Point3D(T z) { this.z_ = z; } public Point3D(Point2D</t><t> p, T z) { super(p); this.z_ = z; } public Point3D(T x, T y, T z) { super(x, y); this.z_ = z; } public Point3D(Point3D</t><t> p) { this.z_ = p.z_; this.y_ = p.y_; this.x_ = p.x_; } public T getZ() { return z_; } public void setZ(T z) { this.z_ = z; } @Override public String toString() { return "Point3D ["+x_+","+y_+","+z_+"]"; } } [/java] Yukarıdaki örnekte yazılımımızda kullanmak üzere iki ve üç boyutlu noktaları temsil eden iki tane sınıf tanımlıyoruz. Point2D sınıfımızın x_ ve y_ olmak üzere iki adet sınıf değişkeni var. Point3D sınıfımızın kendisinde ise sadece z_ sınıf değişkeni varken Point2D sınıfından miras alarak x_ ve y_ değişkenlerine de sahip olmuştur. Dikat edilecek olursa x_ve y_ değişkenlerinin erişim denetleyicisi protected olarak ayarlanmıştır. Böylelikle alt sınıflardan erişilebilirler. Burada dikkat etmemiz gereken bir diğer husus ise üst sınıf metodlarının alt sınıftan nasıl çağrıldığıdır. "super" anahtar kelimesi alt sınıftan üst sınıf metodlarına ve değişkenlerine erişimi sağlayan kapıdır. [java] public Point3D(T x, T y, T z) { super(x, y); this.z_ = z; } [/java] yapıcı metodunda super(x, y); satırları üst sınıfın [java] public Point2D(T x_, T y_) { this.x_ = x_; this.y_ = y_; } [/java] yapıcı metodunun çağrılmasını sağlar. Yapıcı metodlar dışındaki metdolara "super." şaklinde ulaşabiliriz.

## Comments

**[Burak Altunyuva](#1527 "2009-06-30 22:32:25"):** guzel anlatim tesekkurler

**[iicocuk](#4789 "2011-03-22 16:31:56"):** güzel anlatım da biz birşey anlamadık. örnekler daha açıklayıcı olabilirdi ama site güncellenmiyor sanırım. :sad:

**[umut](#10166 "2014-01-02 20:22:53"):** hiç güzel anlatamadınız. Bu nasıl anlatım şekli yanlarına neyin ne işe yaradığını yazmanız gerekirdi. Bütün ingilizce kaynakları böyle yapıyor.Sizde böyle yaparsanız daha yararlı olur. :!:

