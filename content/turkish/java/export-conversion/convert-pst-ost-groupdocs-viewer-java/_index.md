---
date: '2026-02-15'
description: GroupDocs.Viewer for Java kullanarak pst dosyasını html ve JPG, PNG,
  PDF gibi diğer formatlara nasıl dönüştüreceğinizi öğrenin. Bu kılavuz, gerekli tüm
  adımları ve yapılandırmaları kapsar.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: GroupDocs.Viewer for Java kullanarak PST'yi HTML, JPG, PNG ve PDF'ye dönüştür
type: docs
url: /tr/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# PST'yi HTML, JPG, PNG, PDF'ye Dönüştürme – GroupDocs.Viewer for Java Kullanarak

Outlook PST/OST dosyalarını **html'ye dönüştürmek** veya JPG, PNG ya da PDF gibi diğer formatlara çevirmek mi istiyorsunuz? Güçlü GroupDocs.Viewer for Java kütüphanesi sayesinde bu görev basit ve verimli bir şekilde gerçekleştirilebilir. Bu öğreticide, e‑posta arşivlerinizi web‑dostu HTML, görüntü dosyaları veya tek bir PDF olarak nasıl render edeceğinizi öğrenecek, böylece e‑postalarınızı kolayca paylaşabilir ve arşivleyebilirsiniz.

![Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Neler Öğreneceksiniz**
- Maven projesinde GroupDocs.Viewer for Java nasıl kurulur.  
- **java convert pst** dosyalarını HTML, JPG, PNG ve PDF'ye dönüştürmek için adım‑adım talimatlar.  
- Optimum performans için yapılandırma ipuçları ve yaygın hatalar.

## Hızlı Yanıtlar
- **PST dönüşümünü hangi kütüphane yapar?** GroupDocs.Viewer for Java.  
- **PST'yi doğrudan PDF'ye dönüştürebilir miyim?** Evet, `PdfViewOptions` kullanarak.  
- **Üretim ortamı için lisans gerekli mi?** Geçerli bir GroupDocs lisansı gerekir.  
- **Hangi Java sürümü destekleniyor?** JDK 8 veya üzeri.  
- **Ekleri manuel olarak çıkarmam gerekir mi?** Hayır, görüntüleyici ekleri otomatik olarak render eder.

## GroupDocs.Viewer for Java ile pst'yi html'ye nasıl dönüştürülür
Aşağıda, ayrıntılı kod örneklerine geçmeden önce dönüşüm sürecinin kısa bir özetini bulacaksınız.

### Neden GroupDocs.Viewer?
- **Yüksek doğrulukta** e‑posta gövdeleri, ekler ve biçimlendirme render'ı.  
- **Birden çok çıktı formatı** (HTML, JPG, PNG, PDF) tek bir API üzerinden.  
- **Harici bağımlılık yok** – her şey Java uygulamanız içinde çalışır.

## Ön Koşullar

- **GroupDocs.Viewer for Java** – sürüm 25.2 ve üzeri.  
- **Java Development Kit (JDK)** – 8 ve üzeri.  
- Bağımlılık yönetimi için Maven.  
- Temel Java bilgisi ve Maven aşinalığı.

## GroupDocs.Viewer for Java Kurulumu

`pom.xml` dosyanıza GroupDocs deposunu ve bağımlılığını ekleyin:

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
- **Ücretsiz deneme** – tüm özellikleri ücretsiz keşfedin.  
- **Geçici lisans** – gerekirse değerlendirme süresini uzatın.  
- **Tam lisans** – üretim dağıtımları için gereklidir.

### Temel Başlatma

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Uygulama Kılavuzu

Aşağıdaki bölümler, PST/OST dosyalarını her desteklenen formata render etmenizi adım adım gösterir.

### PST/OST Belgelerini HTML'ye Render Etme

#### Adım 1: Çıktı Dizinini Oluşturma

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Adım 2: Yükleme Seçeneklerini Yapılandırma

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Adım 3: Viewer'ı Başlatma ve HTML Render Etme

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST Belgelerini JPG'ye Render Etme

#### Adım 1: Çıktı Dizinini Oluşturma

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Adım 2: Yükleme Seçeneklerini Yapılandırma

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Adım 3: Viewer'ı Başlatma ve JPG Render Etme

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST Belgelerini PNG'ye Render Etme

#### Adım 1: Çıktı Dizinini Oluşturma

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Adım 2: Yükleme Seçeneklerini Yapılandırma

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Adım 3: Viewer'ı Başlatma ve PNG Render Etme

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST Belgelerini PDF'ye Render Etme

#### Adım 1: Çıktı Dizinini Oluşturma

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Adım 2: Yükleme Seçeneklerini Yapılandırma

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Adım 3: Viewer'ı Başlatma ve PDF Render Etme

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Pratik Kullanım Alanları

- **E‑posta Arşivleme:** Büyük PST arşivlerini uyumluluk için aranabilir HTML veya PDF'ye dönüştürün.  
- **Belge Yönetim Sistemleri:** Sadece PDF, PNG veya JPG kabul eden sistemlerde dönüştürülmüş dosyaları saklayın.  
- **İşbirliği Platformları:** Dönüştürülmüş e‑postaları Slack veya Teams'te görüntü olarak paylaşın.  
- **Hukuki İnceleme:** Mahkemelere e‑posta delillerinin PDF versiyonlarını sunun.  
- **Yedekleme Stratejileri:** Kritik mesajların hafif PNG veya JPG anlık görüntülerini tutun.

## Performans Düşünceleri

- **Kaynak Yönetimi:** Birden fazla dosya işlenirken `Viewer` örneklerini yeniden kullanarak yükü azaltın.  
- **Bellek Ayarı:** Sunucu kapasitesine göre `loadOptions.setResourceLoadingTimeout` değerini ayarlayın.  
- **Asenkron İşleme:** Dönüşümü arka plan iş parçacıklarına taşıyarak UI yanıt süresini artırın.  

## Sıkça Sorulan Sorular

**S: Aynı kod tabanı ile **convert pst to pdf** nasıl yapılır?**  
C: PDF render bölümünde gösterildiği gibi `PdfViewOptions` kullanın; kodun geri kalanı aynı kalır.

**S: GroupDocs.Viewer şifreli PST dosyalarını işleyebilir mi?**  
C: Evet, render etmeden önce `LoadOptions.setPassword("yourPassword")` ile şifreyi sağlayın.

**S: **java convert pst** PNG vs JPG farkı nedir?**  
C: PNG kayıpsız kalite sunar, ekran görüntüleri için idealdir; JPG ise e‑posta ön izlemeleri için daha küçük dosya boyutu sağlar.

**S: **how to convert pst** dosyalarını toplu olarak nasıl işlerim?**  
C: PST dosyalarının bulunduğu bir klasörü döngüyle gezerek render mantığını çalıştırın; her dosya için aynı `Viewer` yapılandırmasını yeniden kullanın.

## Sonuç

Artık GroupDocs.Viewer for Java kullanarak **convert pst to html**, JPG, PNG ve PDF'ye dönüştürmek için eksiksiz, üretim‑hazır bir kılavuzunuz var. Yukarıdaki adımları izleyerek e‑posta dönüşümünü herhangi bir Java‑tabanlı iş akışına entegre edebilir, erişilebilirliği artırabilir ve uyumluluk gereksinimlerini karşılayabilirsiniz.

---

**Son Güncelleme:** 2026-02-15  
**Test Edilen Versiyon:** GroupDocs.Viewer for Java 25.2  
**Yazar:** GroupDocs  

---