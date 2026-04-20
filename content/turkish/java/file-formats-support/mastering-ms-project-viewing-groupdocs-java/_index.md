---
date: '2026-02-26'
description: GroupDocs.Viewer for Java kullanarak proje raporu oluşturmayı ve MS Project
  dosyası ayrıntılarını görüntülemeyi öğrenin. Geliştiriciler, proje yöneticileri
  ve analistler için idealdir.
keywords:
- MS Project viewing
- Java GroupDocs.Viewer
- extracting project information
title: GroupDocs.Viewer ile Java'da MS Project Dosyalarından Proje Raporu Nasıl Oluşturulur
type: docs
url: /tr/java/file-formats-support/mastering-ms-project-viewing-groupdocs-java/
weight: 1
---

 produce the translated content.

Be careful with bullet lists, tables.

Translate headings.

Translate bullet points.

Translate table content.

Translate "Last Updated", "Tested With", "Author".

Make sure to keep URLs unchanged.

Also keep the "## Quick Answers" etc.

Let's start.

We'll produce final answer.

# MS Project Dosyalarından Java ile GroupDocs.Viewer Kullanarak Proje Raporu Oluşturma

## Giriş

MS Project dosyasından bir proje raporu oluşturmak, proje yöneticileri ve geliştiriciler için yaygın bir ihtiyaçtır. Bu öğreticide **GroupDocs.Viewer for Java**’nın **proje raporu oluşturma** verilerini nasıl hızlı ve güvenli bir şekilde **MS Project dosyası** ayrıntılarını görüntülemenizi sağladığını göreceksiniz. Kurulum, kod parçacıkları ve gerçek dünya kullanım senaryoları üzerinden geçerek bugün içgörülü panolar oluşturmaya başlayabilirsiniz.

![Java için GroupDocs.Viewer ile MS Project Görüntüleme](/viewer/file‑formats-support/ms-project-viewing.png)

Bu rehberin sonunda şunları yapabilecek olacaksınız:

- Maven projesinde GroupDocs.Viewer for Java’yu kurmak.  
- Bir proje raporunun temelini oluşturan görüntüleme bilgilerini almak.  
- Şifre korumalı dosyalar için yükleme seçeneklerini yapılandırmak.  

Haydi başlayalım ve MS Project verilerini işleme şeklinizi dönüştürelim!

## Hızlı Yanıtlar
- **“Proje raporu oluşturma” burada ne anlama geliyor?** Raporlama araçlarına beslemek için ana proje meta verilerini (tarihler, görev sayıları vb.) çıkarmak.  
- **Hangi kütüphane gerekiyor?** GroupDocs.Viewer for Java (v25.2 veya sonrası).  
- **Bir MS Project dosyasını lisans olmadan görüntüleyebilir miyim?** Değerlendirme için ücretsiz deneme çalışır, ancak üretim için lisans gerekir.  
- **Şifre korumalı dosyalarla nasıl başa çıkılır?** `Viewer` oluştururken şifreyi sağlamak için `LoadOptions` kullanın.  
- **Hangi Java sürümü destekleniyor?** JDK 8 ve üzeri.

## GroupDocs.Viewer ile “proje raporu oluşturma” nedir?
Proje raporu oluşturmak, bir MS Project belgesinden başlangıç/bitiş tarihleri, görev sayıları ve kaynak tahsisleri gibi yapılandırılmış bilgileri çıkarmak demektir. GroupDocs.Viewer, bu ayrıntıların tümünü içeren bir `ProjectManagementViewInfo` nesnesi sağlar; böylece bu verileri raporlama panolarına beslemek veya diğer formatlara aktarmak kolaylaşır.

## MS Project dosyası ayrıntılarını GroupDocs.Viewer ile neden görüntüleyelim?
- **Hız:** Microsoft Project yüklü olmadan veri işleyip çıkarır.  
- **Güvenlik:** Yükleme seçenekleri sayesinde şifre korumalı dosyalar güvenli bir şekilde açılır.  
- **Çapraz platform:** Masaüstünden buluta, Java uyumlu herhangi bir ortamda çalışır.  

## Ön Koşullar

Başlamadan önce şunların olduğundan emin olun:

1. **Kütüphaneler ve Bağımlılıklar**  
   - GroupDocs.Viewer Java kütüphanesi (versiyon 25.2 ve sonrası).  
   - Bağımlılık yönetimi için Maven kurulu.  

2. **Ortam Kurulumu**  
   - IntelliJ IDEA veya Eclipse gibi bir IDE.  
   - JDK 8 ve üzeri.  

3. **Bilgi Ön Koşulları**  
   - Temel Java ve Maven becerileri.  
   - MS Project dosya formatları hakkında bilgi (yararlı ama zorunlu değil).  

## GroupDocs.Viewer for Java Kurulumu

### Maven ile Kurulum

`pom.xml` dosyanıza depo ve bağımlılığı ekleyin:

```xml
<repositories>
    <repository>
        <id>repository.groupdocs.com</id>
        <name>GroupDocs Repository</name>
        <url>https://releases.groupdocs.com/viewer/java/</url>
    </repository>
</repositories>
<dependencies>
    <dependency>
        <groupId>com.groupdocs</groupId>
        <artifactId>groupdocs-viewer</artifactId>
        <version>25.2</version>
    </dependency>
</dependencies>
```

### Lisans Edinme

Tam işlevselliği açmak için aşağıdaki lisans seçeneklerinden birini değerlendirin:

- **Ücretsiz deneme** – Kredi kartı gerektirmeden tüm özellikleri test edin.  
- **Geçici lisans** – Değerlendirme dönemleri için uzatılmış erişim.  
- **Tam lisans** – Sınırsız destekle üretim ortamı kullanımı.  

Adım adım lisans talimatları için [GroupDocs satın alma sayfasını](https://purchase.groupdocs.com/buy) ziyaret edin.

### Temel Başlatma

Bağımlılık eklendikten sonra, MS Project dosyanızın yolunu geçirerek bir `Viewer` örneği oluşturabilirsiniz.

## Uygulama Kılavuzu

### MS Project Belgesi İçin Görünüm Bilgilerini Almak

Bu özellik, **proje raporu oluşturma** içeriği için gereken temel verileri çıkarır.

#### Adım 1: Belge Yolunu Tanımlayın

MS Project dosyanızın bulunduğu yeri belirtin:

```java
String documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP";
```

#### Adım 2: ViewInfoOptions’ı Başlatın

HTML‑stilinde görünüm bilgisi talep etmek için seçenekleri yapılandırın:

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
```

#### Adım 3: Proje Ayrıntılarını Alın ve Çıktılayın

Bir `Viewer` oluşturun, `ProjectManagementViewInfo` nesnesini alın ve tipik bir proje raporunu oluşturan ana alanları yazdırın:

```java
try (Viewer viewer = new Viewer(documentPath)) {
    ProjectManagementViewInfo info = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);

    System.out.println("Document type: " + info.getFileType());
    System.out.println("Pages count: " + info.getPages().size());
    System.out.println("Project start date: " + info.getStartDate());
    System.out.println("Project end date: " + info.getEndDate());
}
```

**Açıklama**  
- `getViewInfo(viewInfoOptions)` sağlanan seçeneklere göre meta verileri çeker.  
- Dönen `info` nesnesi dosya türü, sayfa sayısı ve kritik tarihleri içerir—tam da **proje raporu oluşturma** verilerine ihtiyacınız olan parçalar.

### GroupDocs.Viewer Yapılandırması İçin Ayarlar

MS Project dosyalarınız şifre korumalıysa, şifreyi yükleme seçenekleri aracılığıyla sağlamanız gerekir.

#### Adım 1: Yükleme Seçeneklerini Yapılandırın

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setPassword("your_password_if_needed");
```

#### Adım 2: Yükleme Seçenekleriyle Viewer’ı Başlatın

`Viewer` oluştururken `loadOptions` parametresini geçirin:

```java
try (Viewer viewer = new Viewer(documentPath, loadOptions)) {
    // Viewer is now ready for use with the specified document and options.
}
```

**Açıklama**  
`LoadOptions`, şifre gibi ek parametreleri tanımlamanıza olanak tanır ve korumalı dosyalara güvenli erişim sağlar.

## Pratik Uygulamalar

1. **Proje Yönetimi Panoları** – Çıkarılan tarih ve görev sayılarını paydaşlar için gerçek‑zamanlı panolara besleyin.  
2. **Otomatik Raporlama** – Birden fazla `.mpp` dosyasını döngüye alıp özet raporlar oluşturun ve otomatik olarak e‑posta gönderin.  
3. **CRM Entegrasyonu** – Proje zaman çizelgelerini müşteri verileriyle birleştirerek teslim tahminlerini iyileştirin.

## Performans Düşünceleri

- **Bellek Yönetimi** – `Viewer`’ın hızlı bir şekilde kapanmasını sağlamak için `try‑with‑resources` (gösterildiği gibi) kullanın.  
- **Önbellekleme** – Tekrarlanan dosya okumalarını önlemek için sık erişilen görünüm bilgilerini bir önbellekte saklayın.  
- **İzleme** – Büyük projeleri işlerken JVM bellek kullanımını izleyin ve yığın boyutunu buna göre ayarlayın.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|----------|
| `File not found` hatası | Yanlış `documentPath` | Mutlak ya da göreli yolu doğrulayın ve dosyanın var olduğundan emin olun. |
| Tarihler için veri gelmiyor | Desteklenmeyen MS Project sürümü | En yeni GroupDocs.Viewer sürümüne yükseltin veya dosyayı desteklenen bir formata dönüştürün. |
| Büyük dosyalarda OutOfMemoryError | Yetersiz JVM yığını | `-Xmx` bayrağını artırın veya sayfalama seçenekleriyle dosyayı parçalara bölerek işleyin. |

## Sık Sorulan Sorular

**S: GroupDocs.Viewer Java nedir?**  
C: MS Project belgeleri dahil olmak üzere 100’den fazla dosya formatını render eden ve bilgi çıkaran bir Java kütüphanesidir.

**S: Şifre korumalı MS Project dosyaları nasıl işlenir?**  
C: `Viewer` örneğini oluşturmadan önce şifreyi ayarlamak için `LoadOptions` sınıfını kullanın.

**S: GroupDocs.Viewer ticari projelerde kullanılabilir mi?**  
C: Evet, GroupDocs’tan uygun bir lisans alındıktan sonra kullanılabilir.

**S: Görünüm bilgisi alırken yaygın tuzaklar nelerdir?**  
C: Yanlış dosya yolları, eski kütüphane sürümü kullanmak veya desteklenmeyen MS Project özelliklerini okumaya çalışmak.

**S: Büyük MS Project dosyalarında performans nasıl artırılır?**  
C: Önbellekleme uygulayın, güvenli olduğunda `Viewer` örneklerini yeniden kullanın ve JVM bellek ayarlarını optimize edin.

## Kaynaklar
- [GroupDocs Viewer Dokümantasyonu](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer for Java İndir](https://releases.groupdocs.com/viewer/java/)
- [Lisans Satın Al](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme Sürümü](https://releases.groupdocs.com/viewer/java/)
- [Geçici Lisans Başvurusu](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Destek Forumları](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-02-26  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs