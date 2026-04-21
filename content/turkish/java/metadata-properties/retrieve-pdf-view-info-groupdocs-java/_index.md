---
date: '2026-04-13'
description: GroupDocs.Viewer for Java kullanarak PDF sayfa sayısını ve belge türü
  ile izinler gibi diğer PDF meta verilerini nasıl çıkaracağınızı öğrenin. Uygulamanızın
  belge işleme yeteneklerini geliştirmek için bu adım adım kılavuzu izleyin.
keywords:
- extract pdf page count
- read pdf document type
- retrieve pdf metadata java
title: PDF sayfa sayısını ve meta verilerini GroupDocs.Viewer Java ile çıkar
type: docs
url: /tr/java/metadata-properties/retrieve-pdf-view-info-groupdocs-java/
weight: 1
---

# GroupDocs.Viewer Java ile PDF sayfa sayısını ve meta verileri çıkarma

Java'da GroupDocs.Viewer kütüphanesini kullanarak bir PDF belgesinden **extract pdf page count** ve diğer görüntüleme bilgilerini çıkarmak için bu kapsamlı rehbere hoş geldiniz. PDF'nin belge türünü programlı olarak okumak, izinlerini almak veya sadece sayfalarını saymak istiyorsanız, doğru yerdesiniz.

![GroupDocs.Viewer for Java ile PDF Meta Verilerini ve Özelliklerini Al](/viewer/metadata-properties/retrievepdf-metadata-and-properties-java.png)

## Hızlı Yanıtlar
- **Ne alabilirim?** PDF sayfa sayısı, belge türü ve yazdırma izinleri.  
- **Hangi kütüphane?** GroupDocs.Viewer for Java (versiyon 25.2).  
- **Bir lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü çalışır; üretim için ticari bir lisans gereklidir.  
- **Desteklenen Java sürümü?** Java 8 veya üzeri.  
- **Kaç satır kod?** Tam görüntüleme bilgisi almak için 20 satırdan az.

## Neler Öğreneceksiniz
- GroupDocs.Viewer for Java'ın belge görüntüleme işlevselliğini nasıl sağladığını anlayın.  
- Java ile GroupDocs.Viewer'ı kullanmak için ortamınızı kurun.  
- PDF dosyasından görüntüleme bilgilerini alın ve yazdırın, **extract pdf page count** dahil.  
- Pratik uygulamaları ve performans hususlarını keşfedin.

## Neden pdf sayfa sayısını ve diğer meta verileri çıkaralım?
Sayfa sayısını, belge türünü ve izinleri bilmek size yardımcı olur:
1. **Kısa özetler göster** içerik yönetim sistemlerinde.  
2. **Güvenliği uygula** render etmeden önce yazdırma izninin olup olmadığını kontrol ederek.  
3. **Kaynak kullanımını optimize et** sadece gerekli sayfaları yükleyerek.

## Ön Koşullar
- **Kütüphaneler ve Bağımlılıklar**: GroupDocs.Viewer for Java (Maven üzerinden eklenir).  
- **Ortam**: Geliştirme makinenizde Java 8 veya daha yeni bir sürüm yüklü.  
- **Bilgi Tabanı**: Temel Java programlama ve Maven bilgisi.

## GroupDocs.Viewer for Java'ı Kurma

### Maven Yapılandırması
`pom.xml` dosyanıza depoyu ve bağımlılığı ekleyin:

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

### Lisans Alımı
Tam özelliklerini keşfetmek için ücretsiz deneme ile başlayabilir veya geçici bir lisans edinebilirsiniz. Uzun vadeli kullanım için bir lisans satın almanız önerilir.

## Java'da GroupDocs.Viewer ile pdf sayfa sayısını nasıl çıkarabilirsiniz

### Adım 1: `ViewInfoOptions`'ı yapılandırın
```java
// Create ViewInfoOptions for HTML view, which is necessary for retrieving view info
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
```
*Neden*: `ViewInfoOptions`, Viewer'a hangi temsili istediğinizi söyler. `forHtmlView()` kullanmak, motoru HTML render'ı için faydalı meta verileri, sayfa sayısını da içerecek şekilde hazırlamayı sağlar.

### Adım 2: `Viewer`'ı başlatın
```java
try (Viewer viewer = new Viewer(pdfFilePath)) {
    // Retrieval and processing steps will be done here
}
```
*Neden*: `Viewer` nesnesi PDF dosya yolunuza bağlanır. Bir try‑with‑resources bloğuna sarılması, yerel kaynakların otomatik olarak serbest bırakılmasını garanti eder.

### Adım 3: Görüntüleme bilgilerini (meta verileri) al
```java
// Retrieve view information from the document using the specified options
PdfViewInfo viewInfo = (PdfViewInfo) viewer.getViewInfo(viewInfoOptions);

// Output the retrieved view information
System.out.println("Document type is: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
System.out.println("Printing allowed: " + viewInfo.isPrintingAllowed());
```
*Neden*: Bu kod parçacığı, **read pdf document type**, **extract pdf page count**, ve **get pdf permissions java**'yı tek bir çağrıda çıkarır. `PdfViewInfo` nesnesi, sonraki işleme için ihtiyacınız olan tüm verileri tutar.

### Yaygın Tuzaklar ve İpuçları
- **Yanlış dosya yolu** → `FileNotFoundException` fırlatır. Mutlak ya da göreli yolu tekrar kontrol edin.  
- **Sürüm uyumsuzluğu** → Maven sürümünün (`25.2`) çalışma zamanı kütüphanesiyle eşleştiğinden emin olun.  
- **Büyük PDF'ler** → bellek kullanımını düşük tutmak için akış kullanmayı veya sayfaları toplu işleyerek işlemeyi düşünün.

## Pratik Uygulamalar
GroupDocs.Viewer çeşitli sistemlere entegre edilebilir:
1. **İçerik Yönetim Sistemleri** – yüklenen PDF'lerden indeksleme için meta verileri otomatik olarak çıkarır.  
2. **Belge Yönetim İş Akışları** – `isPrintingAllowed` bayrağına göre yazdırmaya izin verilip verilmeyeceğine karar verir.  
3. **Web Panoları** – tüm dosyayı yüklemeden sayfa sayısı ve belge türünün canlı önizlemesini gösterir.

## Performans Hususları
- `ViewInfoOptions`'ı sadece meta veriye ihtiyacınız olduğunda kullanın; bilgi zaten önbellekteyse her istek için `getViewInfo` çağrısından kaçının.  
- Bellek kullanımını izleyin, özellikle büyük PDF'lerde, ve `Viewer`'ı hızlıca kapatın (try‑with‑resources bloğu bunu halleder).

## Sonuç
Artık GroupDocs.Viewer for Java kullanarak **extract pdf page count**, belge türünü okuyabilir ve izinleri alabilirsiniz. Farklı render senaryolarına uyacak şekilde diğer `ViewInfoOptions`'ları (ör. `forImageView`) denemekten çekinmeyin.

### Sonraki Adımlar
- `viewer.view` ile sayfaları görüntülere veya HTML'e render etmeyi keşfedin.  
- Meta veri çıkarımını bir veritabanı ile birleştirerek aranabilir belge katalogları oluşturun.

## SSS Bölümü
**S: Ücretsiz deneme ile nasıl başlayabilirim?**  
A: Ücretsiz lisansınızı almanızla ilgili talimatlar için [GroupDocs' Free Trial page](https://releases.groupdocs.com/viewer/java/) adresini ziyaret edin.

**S: GroupDocs.Viewer bulut uygulamalarında kullanılabilir mi?**  
A: Evet, kütüphane çeşitli ortamları destekler ve bulut‑tabanlı çözümlere entegre edilebilir.

**S: PDF render'ı sırasında bir hatayla karşılaşırsam ne yapmalıyım?**  
A: Belgenizin uyumluluğunu kontrol edin veya geliştirilmiş destek için GroupDocs.Viewer'ın en son sürümüne güncelleyin.

## Kaynaklar
- **Dokümantasyon**: [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **API Referansı**: [GroupDocs Viewer API Reference](https://reference.groupdocs.com/viewer/java/)  
- **İndirme**: [GroupDocs Viewer Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Satın Alma**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Ücretsiz Deneme**: [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Geçici Lisans**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Destek**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-04-13  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs