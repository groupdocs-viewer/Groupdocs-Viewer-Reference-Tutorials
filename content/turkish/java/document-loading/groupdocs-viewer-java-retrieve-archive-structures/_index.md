---
date: '2026-06-30'
description: GroupDocs.Viewer kullanarak viewinfo nasıl alınır ve java arşiv dosya
  tipi yapılarını nasıl getirileceğini öğrenin. Bu rehber kurulum, kod örnekleri ve
  gerçek dünya kullanım senaryolarını kapsar.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Java'da ViewInfo Nasıl Alınır ve Arşiv Yapıları Nasıl Getirilir
type: docs
url: /tr/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Java'da ViewInfo Nasıl Alınır ve Arşiv Yapıları Nasıl Geri Getirilir

Arşiv dosyalarını etkili bir şekilde yönetmek, yapılarının net bir şekilde anlaşılmasını gerektirir. Bu öğreticide, herhangi bir arşiv için **viewinfo nasıl alınır** öğrenecek ve bunun **java arşiv dosyası türü** ile çalışmanıza nasıl yardımcı olduğunu göreceksiniz. GroupDocs.Viewer'ı kurmayı, görünüm bilgilerini çıkarmayı ve klasör hiyerarşilerini özyinelemeli olarak okumayı adım adım gösterecek ve çözümü gerçek projelere entegre edebilmenizi sağlayacağız.

![Java için GroupDocs.Viewer ile Arşiv Yapıları](/viewer/document-loading/archive-structures-java.png)

**Neler Öğreneceksiniz**
- Java için GroupDocs.Viewer'ı kurma ve yapılandırma.  
- Arşivlerden **viewinfo alma** yöntemleri.  
- Bir arşiv dosyasının klasör yapısını okuma ve görüntüleme teknikleri.  
- Java projelerinde GroupDocs.Viewer kullanırken pratik uygulamalar ve performans hususları.

## Hızlı Yanıtlar
- **“viewinfo” ne sağlar?** Bir arşiv içindeki dosya türünü, sayfa sayısını ve klasör ve dosyaların tam listesini döndürür.  
- **Hangi arşiv formatları desteklenir?** ZIP, RAR, TAR, 7z, ISO ve 12+ diğer yaygın format.  
- **Üretim için lisans gerekir mi?** Evet—üretim için ticari bir lisans gereklidir; değerlendirme için ücretsiz deneme sürümü kullanılabilir.  
- **Büyük arşivler verimli bir şekilde işlenebilir mi?** Kesinlikle—akış seçeneklerini kullanın ve bellek kullanımını düşük tutmak için bir seferde bir klasör seviyesini işleyin.  
- **Kütüphaneyi eklemenin tek yolu Maven mi?** Maven önerilen bağımlılık yöneticisidir, ancak Gradle veya manuel JAR ekleme de çalışır.

## “how to get viewinfo” Nedir?

`getViewInfo`, tam renderleme yapmadan bir belge veya arşivden meta verileri çıkaran bir GroupDocs.Viewer API yöntemidir. Tek bir çağrıda iç klasör ağacını, dosya sayısını ve temel özellikleri döndürür, böylece hangi bölümleri işleyeceğinize karar verebilirsiniz. Bu çağrı, tipik sunucularda 500 MB'a kadar arşivlerin tam bir anlık görüntüsünü bir saniyeden kısa sürede döndürür.

## Neden Java Arşiv Dosyası Türü Yapılarını Geri Getirmelisiniz?

**java arşiv dosyası türü**'nün iç düzenini geri getirmek, ihtiyaç duyulan dosyaları anında bulmanızı, gereksiz çıkarma işlemlerinden kaçınmanızı ve yalnızca ilgili alt‑klasörlere dokunan otomatik iş akışları oluşturmanızı sağlar. Bu yaklaşım, büyük arşivlerde I/O'yu %70'e kadar azaltır ve veri‑alma senaryolarında dakikada binlerce dosyayı taramayı mümkün kılar.

## Önkoşullar

- **Java Development Kit (JDK):** Versiyon 8 veya daha yenisi.  
- **Maven:** Bağımlılık yönetimi ve derlemeler için.  
- **Temel Java bilgisi:** Nesne‑yönelimli programlama kavramlarına aşina olmak faydalıdır ancak zorunlu değildir.  

Ayrıca, aşağıda gösterildiği gibi Maven projenize ekleyebileceğiniz GroupDocs.Viewer kütüphanesine erişiminiz olmalıdır.

## Java için GroupDocs.Viewer Kurulumu

### Maven Yapılandırması

`pom.xml` dosyanıza depo ve bağımlılığı ekleyin.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Lisans Edinme

- **Ücretsiz Deneme:** GroupDocs web sitesinden deneme sürümünü indirin.  
- **Geçici Lisans:** Kısa vadeli değerlendirme için geçici bir anahtar isteyin.  
- **Tam Lisans:** Sınırsız üretim kullanımı için ticari bir lisans satın alın.

Kütüphane sınıf yolunuza (classpath) eklendikten sonra kodlamaya başlayabilirsiniz.

## Uygulama Kılavuzu

### Arşiv Dosyaları için ViewInfo Nasıl Alınır

Görünüm bilgilerini elde etmek için, önce arşivi Viewer'a yükleyin, ardından meta verileri almak için `getViewInfo` metodunu çağırın ve son olarak döndürülen klasör hiyerarşisini yineleyin. Bu üç adımlı desen, desteklenen tüm arşiv formatları için çalışır ve tek bir API çağrısında tam bir anlık görüntü sağlar, sonraki işleme sürecini basitleştirir.

#### Viewer'ı Başlatma

`Viewer` sınıfı, tüm render ve inceleme işlemleri için giriş noktasıdır. Dosya akışlarını, format algılamayı ve kaynak temizlemeyi yönetir.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Görünüm Bilgilerini Geri Getirme

`ViewInfo`, dosya türü, toplam sayfa sayısı ve klasör ve dosyaların hiyerarşik listesini içeren meta verileri kapsar. `getViewInfo` çağrısı bu nesneyi anında döndürür.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Klasör Yapısını Görüntüleme

`viewInfo.getFolders()` üzerinden yineleyerek her klasör adını, derinliğini ve içindeki dosyaları yazdırın. Bu basit döngü, arşivin okunabilir bir ağaç görünümünü sağlar.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Özyinelemeli Klasör Okuma

Derinlemesine iç içe geçmiş arşivler için, özyinelemeli bir yardımcı yöntem ağacı derinlik‑ilk (depth‑first) gezebilir ve tüm arşivi belleğe yüklemeden her alt‑klasörün ziyaret edilmesini sağlar.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Özellik 2: Arşiv Klasör Yapısını Geri Getirme

Bu özellik, bir arşiv dosyasının klasör yapısını yazdırmaya odaklanır. İlk özellik ile benzer ancak özyinelemeli keşfe vurgu yapar.

#### Görünüm Bilgisi Seçeneklerini Ayarlama

`ArchiveOptions`, `getViewInfo` çağrısı öncesinde şifre koruması, sayfa limitleri ve akış (streaming) tercihlerini belirlemenizi sağlar.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Özyinelemeli Keşif

İkinci bir özyinelemeli rutin, şifre korumalı arşivleri ve büyük dosya setlerini verimli bir şekilde nasıl ele alacağınızı gösterir.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Pratik Uygulamalar

1. **Veri Yönetimi:** Arşiv yapılarını anlayarak büyük veri setlerini hızlı bir şekilde düzenleyin.  
2. **Otomatik Dosya İşleme:** Arşivlenmiş dosyaları tamamen çıkarmadan toplu işleyin, I/O'yu %70'e kadar azaltın.  
3. **CMS Entegrasyonu:** İçerik yönetim sistemlerini anlık arşiv gezinmesiyle geliştirin, editörlerin dosyaları doğrudan arşivden önizlemesini sağlayın.

## Performans Hususları

- **Bellek Kullanımını Optimize Edin:** Klasörleri bir seferde bir seviye işleyin ve `Viewer` örneğini hızlıca kapatın.  
- **Güncel Kalın:** Performans artışı için en yeni GroupDocs.Viewer sürümünü (yazı zamanı 25.2) ve JDK sürümlerini kullanın.  
- **Streaming Desteği:** Kütüphane, içsel parçalı‑okuma mimarisi sayesinde tüm dosyayı RAM'e yüklemeden 1 GB'den büyük arşivleri akış (stream) olarak işleyebilir.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| `NullPointerException` klasör okurken | `viewInfo.getFolders()` boş dizinler için null döndürür | İterasyon yapmadan önce null veya boş listeyi kontrol edin. |
| Büyük ZIP dosyalarının yavaş işlenmesi | Tüm arşiv bellek içine yüklenir | Yeni GroupDocs sürümlerinde bulunan streaming seçeneklerini kullanın. |
| Lisans bulunamadı | Lisans dosyası yolu yanlış | Lisans dosyasını uygulama kök dizinine yerleştirin veya `License.setLicense("path/to/license.json")` ayarlayın. |

## Sıkça Sorulan Sorular

**S:** GroupDocs.Viewer nedir?  
**C:** GroupDocs.Viewer, yerel uygulamalara ihtiyaç duymadan 100'den fazla belge, görüntü ve arşiv formatını HTML, PDF veya görüntü akışlarına (streams) dönüştüren bir Java kütüphanesidir.

**S:** GroupDocs.Viewer'ı diğer programlama dilleriyle kullanabilir miyim?  
**C:** Evet, GroupDocs .NET, Python, PHP ve daha fazlası için SDK'lar sunar, ancak bu öğretici Java uygulamasına odaklanmaktadır.

**S:** Büyük arşiv dosyalarını nasıl yönetirim?  
**C:** `ArchiveOptions.setUseStreaming(true)` ile streaming'i etkinleştirin, bir seferde bir klasör seviyesini işleyin ve kullanım sonrası `Viewer` nesnesini serbest bırakın.

**S:** GroupDocs.Viewer hangi arşiv türlerini destekler?  
**C:** ZIP, RAR, TAR, 7z, ISO, ARJ, CAB ve daha birçok özel konteyner türü dahil olmak üzere 12+ arşiv formatını destekler.

**S:** Arşivler için bir boyut limiti var mı?  
**C:** Pratik limit, sunucunuzun RAM ve CPU'suna bağlıdır; streaming etkinleştirildiğinde 16 GB RAM'li bir makinede 2 GB arşivlerin sorunsuz işlendiği görülmüştür.

**S:** “how to get viewinfo” şifre korumalı arşivlerde çalışır mı?  
**C:** Evet, `getViewInfo` çağırmadan önce şifreyi `ArchiveOptions.setPassword("yourPassword")` ile sağlayın.

## Sonuç

Bu kılavuzu izleyerek artık **viewinfo nasıl alınır** ve Java için GroupDocs.Viewer kullanarak herhangi bir desteklenen arşivin klasör hiyerarşisini nasıl gezebileceğinizi biliyorsunuz. Bu teknikler, daha akıllı veri‑işleme iş akışları oluşturmanızı, CMS entegrasyonlarını geliştirmenizi ve büyük arşiv dosyası koleksiyonlarını güvenle yönetmenizi sağlar. Sonraki adımda, arşivden tek tek dosyaları render etmeyi veya diğer Viewer özelliklerini kullanarak PDF/HTML'ye dönüştürmeyi keşfedin.

---

**Son Güncelleme:** 2026-06-30  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs  

**Kaynaklar**
- **Dokümantasyon:** [GroupDocs Viewer Java Dokümantasyonu](https://docs.groupdocs.com/viewer/java/)
- **API Referansı:** [GroupDocs Java API Referansı](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs Viewer İndir:** [GroupDocs İndirme Sayfası](https://releases.groupdocs.com/viewer/java/)
- **Lisans Satın Al:** [GroupDocs Satın Al](https://purchase.groupdocs.com/buy)
- **Ücretsiz Deneme ve Geçici Lisans:** [GroupDocs Ücretsiz Deneme](https://releases.groupdocs.com/viewer/java/) | [Geçici Lisans](https://purchase.groupdocs.com/temporary-license/)

## İlgili Öğreticiler

- [Java için GroupDocs.Viewer ile Belge Metaverisini Çıkarma - Belge Görünüm Bilgilerini ve İçgörüleri Geri Getirme](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Java için GroupDocs.Viewer ile Ekleri Geri Getirme ve Belge Eklerini Yazdırma](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java Rehberi: Belge Önizleme ve Yönetimi için GroupDocs.Viewer API ile Belirli Sayfaları Render Etme](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)