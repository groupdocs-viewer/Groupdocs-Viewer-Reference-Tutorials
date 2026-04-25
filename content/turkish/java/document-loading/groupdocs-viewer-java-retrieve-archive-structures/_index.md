---
date: '2026-02-05'
description: GroupDocs.Viewer kullanarak viewinfo almayı ve Java arşiv dosyası tipi
  yapılarını elde etmeyi öğrenin. Bu rehber kurulum, kod örnekleri ve gerçek dünya
  kullanım senaryolarını kapsar.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Java'da ViewInfo Nasıl Alınır ve Arşiv Yapıları Nasıl Getirilir
type: docs
url: /tr/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Java'da ViewInfo Nasıl Alınır ve Arşiv Yapıları Nasıl Getirilir

Arşiv dosyalarını etkili bir şekilde yönetmek, yapılarını net bir şekilde anlamayı gerektirir. Bu öğreticide, herhangi bir arşiv için **how to get viewinfo** öğrenecek ve bunun **java archive file type** ile çalışmanıza nasıl yardımcı olduğunu göreceksiniz. GroupDocs.Viewer'ı kurmayı, görünüm bilgilerini çıkarmayı ve klasör hiyerarşilerini özyinelemeli olarak okumayı adım adım göstereceğiz, böylece çözümü gerçek projelere entegre edebilirsiniz.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**Neler Öğreneceksiniz**
- GroupDocs.Viewer for Java'ı kurma ve yapılandırma.  
- Arşivlerden **get viewinfo** yöntemleri.  
- Bir arşiv dosyasının klasör yapısını okuma ve gösterme teknikleri.  
- Java projelerinde GroupDocs.Viewer kullanırken pratik uygulamalar ve performans hususları.

## Hızlı Cevaplar
- **viewinfo** ne sağlar? Dosya türünü, sayfa sayısını ve arşiv klasör listelerini döndürür.  
- **Hangi arşivler desteklenir?** ZIP, RAR, TAR ve diğer yaygın formatlar.  
- **Lisans gerekir mi?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Büyük arşivleri işleyebilir miyim?** Evet – daha sonra gösterildiği gibi akış ve uygun bellek yönetimi kullanın.  
- **Maven gerekli mi?** Maven, GroupDocs.Viewer bağımlılığını yönetmenin önerilen yoludur.

## “how to get viewinfo” nedir?
`getViewInfo`, tam içeriği render etmeden bir belge veya arşiv hakkında meta verileri çıkaran GroupDocs.Viewer API'sinde bir yöntemdir. Arşivler için, iç klasör ağacını gösterir ve hangi bölümlerin render edileceğine ya da daha ileri işleneceğine karar vermenizi sağlar.

## Neden Java Arşiv Dosyası Türü Yapılarını Getirmelisiniz?
Bir **java archive file type** (ör. ZIP, RAR) iç düzenini anlamak şunları sağlar:
- Her şeyi çıkarmadan ihtiyaç duyulan dosyaları hızlıca bulmak.  
- Yalnızca ilgili alt‑klasörleri işleyen otomatik boru hatları oluşturmak.  
- Arşiv gezinmesini içerik‑yönetimi veya veri‑alım sistemlerine entegre etmek.

## Önkoşullar

- **Java Development Kit (JDK):** Versiyon 8 veya üzeri.  
- **Maven:** Bağımlılık yönetimi ve derlemeler için.  
- **Temel Java bilgisi:** OOP kavramlarına aşina olmak faydalıdır ancak zorunlu değildir.

Ayrıca GroupDocs.Viewer kütüphanesine erişiminiz olmalı; bunu aşağıda gösterildiği gibi Maven projenize ekleyebilirsiniz.

## GroupDocs.Viewer for Java Kurulumu

### Maven Yapılandırması

`pom.xml` dosyanıza depo ve bağımlılığı ekleyin.

**Depolar:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Bağımlılıklar:**
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
- **Geçici Lisans:** Kısa vadeli değerlendirme için geçici anahtar isteyin.  
- **Tam Lisans:** Sınırsız üretim kullanımı için ticari lisans satın alın.

Kütüphane sınıf yolunuza (classpath) eklendikten sonra kodlamaya başlayabilirsiniz.

## Uygulama Rehberi

### Arşiv Dosyaları için ViewInfo Nasıl Alınır

Bu bölüm, `getViewInfo` metodunu çağırmak ve klasör hiyerarşisini okumak için tam adımları gösterir.

#### Görüntüleyiciyi Başlatma

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Görünüm Bilgilerini Almak

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Klasör Yapısını Görüntüleme

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Özyinelemeli Klasör Okuma

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

### Özellik 2: Arşiv Klasör Yapısını Getirme

Bu özellik, bir arşiv dosyasının klasör yapısını yazdırmaya odaklanır. İlk özellik ile benzer, ancak özyinelemeli keşfe vurgu yapar.

#### View Info Seçeneklerini Ayarlama

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Özyinelemeli Keşif

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Pratik Uygulamalar

1. **Veri Yönetimi:** Arşiv yapılarını anlayarak büyük veri setlerini hızlıca düzenleyin.  
2. **Otomatik Dosya İşleme:** Arşivlenmiş dosyaları tamamen çıkarmadan toplu işleyin.  
3. **CMS Entegrasyonu:** İçerik‑yönetim sistemlerini anlık arşiv gezinmesi ile geliştirin.

## Performans Hususları

- **Bellek Kullanımını Optimize Et:** Klasörleri bir seferde bir seviye işleyin ve `Viewer` örneğini hemen kapatın.  
- **Güncel Kal:** Performans artışı için en yeni GroupDocs.Viewer sürümünü ve JDK sürümlerini kullanın.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|------|
| `NullPointerException` klasör okurken | `viewInfo.getFolders()` boş dizinler için null döndürür | Döngüye girmeden önce null veya boş liste kontrol edin. |
| Büyük ZIP dosyalarının yavaş işlenmesi | Tüm arşiv bellek içine yüklenir | Yeni GroupDocs sürümlerinde bulunan akış seçeneklerini kullanın. |
| Lisans bulunamadı | Lisans dosyası yolu yanlış | Lisans dosyasını uygulama köküne yerleştirin veya `License.setLicense("path/to/license.json")` ayarlayın. |

## Sıkça Sorulan Sorular

**S: GroupDocs.Viewer nedir?**  
C: HTML, görüntü ve PDF gibi formatlara belge ve arşivleri render eden güçlü bir Java kütüphanesidir.

**S: GroupDocs.Viewer'ı diğer programlama dilleriyle kullanabilir miyim?**  
C: Evet, GroupDocs birden çok platform için SDK'lar sunar, ancak bu öğretici Java uygulamasına odaklanmaktadır.

**S: Büyük arşiv dosyalarını nasıl yönetirim?**  
C: Verimli bellek yönetimi uygulayın ve gerekirse arşivleri bölmeyi düşünün.

**S: GroupDocs.Viewer hangi arşiv türlerini destekler?**  
C: ZIP, RAR, TAR ve diğer birçok formatı destekler.

**S: İşleyebileceğim arşiv boyutu için bir limit var mı?**  
C: Limitler sistem kaynaklarınıza bağlıdır. Pratik limitleri belirlemek için hedef ortamınızda test edin.

**S: “how to get viewinfo” şifre korumalı arşivlerde çalışır mı?**  
C: Evet, `getViewInfo` çağırmadan önce `ArchiveOptions.setPassword("yourPassword")` ile şifreyi sağlayabilirsiniz.

## Sonuç

Bu rehberi izleyerek artık herhangi bir desteklenen arşiv için **how to get viewinfo**'ı ve GroupDocs.Viewer for Java kullanarak klasör hiyerarşisini nasıl dolaşacağınızı biliyorsunuz. Bu teknikler, daha akıllı veri‑işleme boru hatları oluşturmanıza, CMS entegrasyonlarını geliştirmenize ve büyük arşiv dosyası koleksiyonlarını güvenle yönetmenize olanak tanır. Sonraki adımda, arşivden tek tek dosyaları render etmeyi veya diğer Viewer özellikleriyle PDF/HTML'ye dönüştürmeyi keşfedin.

---

**Son Güncelleme:** 2026-02-05  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs  

**Kaynaklar**
- **Dokümantasyon:** [GroupDocs Viewer Java Dokümantasyonu](https://docs.groupdocs.com/viewer/java/)
- **API Referansı:** [GroupDocs API Referansı for Java](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs İndirme Sayfası:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **GroupDocs Satın Al:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Ücretsiz Deneme** ve **Geçici Lisans:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)