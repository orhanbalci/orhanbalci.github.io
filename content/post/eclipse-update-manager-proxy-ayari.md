title: Eclipse Update Manager Proxy Ayarı
link: http://orhanbalci.net/tr/?p=12
author: Orhan Balci
description: 
post_id: 12
created: 2007/06/21 22:20:03
created_gmt: 2007/06/21 19:20:03
comment_status: open
post_name: eclipse-update-manager-proxy-ayari
status: publish
post_type: post

# Eclipse Update Manager Proxy Ayarı

Gün itibari ile Eclipse ile Subversion entegrasyonunu sağlayan Subclipse eklentisini geliştirme ortamıma dahil ederken bir problemle karşılaştım. Bildiğiniz üzre Eclipse'in gayet başarılı bir eklenti yönetim mekanizması var. Sistemimize eklemek istediğimiz eklentinin güncelleme repositorisini **Help->SoftwareUpdates->Find and Install** menü yollarını takip ederek Eclipse tanıttıktan sonra Eclipse bize o repositorideki eklentilerin bir listesini sunar, arkasından birkaç kez **next** tuşundan ve en son olarak **finish **düğmesine bastıktan sonra eklentimiz kullanıma hazır hale gelirdi.  Lakin bugün Eclipse inat etti progress barda %6 dan ilerisini göstermedi bana :). Belliki güncelleme sitesine bağlanamamaktaydı. Birden aklıma şirketteki internet akışının proxy server üzerinden denetlendiği aklıma geldi. Firefox'ta proxy ayarının nereden yapıldığını bilmekle beraber böyle bir durum Eclipse için ilk defa başıma geldiğinden proxy sunucuyu Eclipse nasıl tanıtacağımı birazcık araştırmam gerekti ve işte sonuç. **Window->Preferences **penceresinden** Install/Update **seçeneğini seçerek amacıma ulaştım. Tabi önemli olan problemin proxy sunucudan kaynaklandığını farketmekti. Biraz acı çektim ama sonunda Subclipse'e kavuştum. Yardımcı olması dileğiyle... ![Eclipse Update Manager Proxy Ayarı](/wp-includes/images/eclipse/eclipse_update_ayari.JPG)