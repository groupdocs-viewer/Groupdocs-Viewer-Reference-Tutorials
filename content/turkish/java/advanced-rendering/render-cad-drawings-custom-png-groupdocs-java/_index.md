---
date: '2026-03-16'
description: GroupDocs.Viewer for Java kullanarak özel boyut ve arka plan rengiyle
  DWG'yi PNG'ye nasıl dönüştüreceğinizi öğrenin.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: GroupDocs.Viewer for Java Kullanarak DWG'yi Özel Boyut ve Arka Plan Rengiyle
  PNG'ye Nasıl Dönüştürürsünüz
type: docs
url: /tr/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

ed With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

Translate labels but keep dates and version.

**Last Updated:** -> "**Son Güncelleme:**"

**Tested With:** -> "**Test Edilen Versiyon:**"

**Author:** -> "**Yazar:**"

Now produce final markdown with translations.

Make sure to keep code block placeholders unchanged.

Let's craft final output.# DWG'yi PNG'ye Özel Boyut ve Arka Plan Rengiyle Dönüştürme: GroupDocs.Viewer for Java Kullanarak

Eğer **convert DWG to PNG** yaparken görüntü boyutları ve arka plan stilini tam kontrol etmek istiyorsanız doğru yerdesiniz. Bu öğreticide CAD dosyalarını PNG olarak render etme, genişliği özelleştirme ve arka plan rengini değiştirme adımlarını göstereceğiz, böylece çıktı raporunuz, sunumunuz veya web‑önizleme gereksinimlerinizle eşleşir.

## Hızlı Yanıtlar
- **convert DWG to PNG** ne anlama geliyor? Bu, bir DWG CAD dosyasını kod kullanarak PNG görüntüsüne dönüştürme işlemidir.  
- **Özel bir genişlik ayarlayabilir miyim?** Evet – `CadOptions.forRenderingByWidth(int width)` kullanın.  
- **Arka plan rengini nasıl değiştiririm?** `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` çağırın.  
- **Hangi kütüphane gereklidir?** GroupDocs.Viewer for Java (version 25.2 veya sonrası).  
- **Lisans gerekiyor mu?** Geçici veya satın alınmış bir lisans değerlendirme sınırlamalarını kaldırır.

![CAD Çizimlerini Özel Boyut ve Arka Plan Rengiyle PNG Olarak Render Etme – GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## DWG'yi PNG'ye Dönüştürme – Genel Bakış
Bu bölümde ana hedefi genişletiyoruz: **how to convert DWG to PNG** boyut ve arka planı kontrol ederken. Tam kurulumu, ihtiyacınız olan kesin kodu ve yaygın hatalardan kaçınmak için pratik ipuçlarını göreceksiniz.

## Öğrenecekleriniz
- Maven projesinde GroupDocs.Viewer for Java kurulumunu yapmak  
- **Convert DWG to PNG** özel boyutlarla  
- **Change CAD background color** render sırasında pürüzsüz bir görünüm için  
- Özel renderlamanın değer kattığı gerçek dünya senaryoları  

## Ön Koşullar

### Gerekli Kütüphaneler ve Bağımlılıklar
- Java Development Kit (JDK) 8+  
- Maven bağımlılık yönetimi için  

### Ortam Kurulum Gereksinimleri
- IntelliJ IDEA veya Eclipse gibi IDE  
- Temel Java bilgisi  

### Bilgi Ön Koşulları
- Java'da dosya işlemlerine aşinalık  

## GroupDocs.Viewer for Java Kurulumu
GroupDocs deposunu ve bağımlılığını Maven `pom.xml` dosyanıza ekleyin:

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
Değerlendirme kısıtlamalarını kaldırmak için geçici veya tam lisans edinin.

### Temel Başlatma ve Kurulum
`Viewer` örneğini oluşturun ve CAD dosyanıza işaret edin:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Özellik 1: Özel Görüntü Boyutu ve Arka Plan Rengiyle CAD Çizimlerini Render Etme

### CAD Arka Plan Rengini Nasıl Değiştirilir
Bu özellik, **convert DWG to PNG** yaparken özel bir genişlik belirlemenizi ve yeni bir arka plan tonunu uygulamanızı sağlar.

#### Adım Adım Uygulama

##### Gerekli Paketleri İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Çıktı Dizini ve Dosya Yolu Formatını Ayarlayın
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Özel Render Seçenekleriyle Viewer'ı Başlatın
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Parametre Açıklamaları**  
- `PngViewOptions` – çıktı formatını ve adlandırmayı tanımlar.  
- `forRenderingByWidth(int width)` – özel görüntü genişliğini ayarlar.  
- `setBackgroundColor(Color color)` – **set PNG background color** görsel tutarlılığı artırmak için PNG arka plan rengini ayarlar.

#### Sorun Giderme İpuçları
- Çıktı klasörünün mevcut olduğunu doğrulayın; gerekirse oluşturun.  
- Girdi dosya yolunu ve izinleri iki kez kontrol edin.  

## Özellik 2: Render Seçeneklerinde Arka Plan Rengini Ayarlama

### PNG Arka Plan Rengini Nasıl Ayarlarsınız
Burada, **set background color PNG** seçeneğine odaklanıyoruz, böylece her renderlanan görüntü marka paletinize uyar.

#### Adım Adım Uygulama

##### Gerekli Paketleri İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Arka Plan Rengiyle Render Seçeneklerini Yapılandırın
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Ana Yapılandırma Seçenekleri**  
- Farklı boyutlar için `forRenderingByWidth(int width)` ayarlayın.  
- Özel arka planlar için herhangi bir `Color` sabiti veya `new Color(r,g,b)` kullanın.  

## Pratik Uygulamalar

### 1. Mühendislik Dokümantasyonu
Özel renderlama, mühendislik çizimlerinin kurumsal stil kılavuzlarına uymasını sağlar.

### 2. Mimari Görselleştirme
Sunum slaytlarıyla uyumlu temiz bir arka planla planları sunun.

### 3. Üretim Prototipleme
Hızlı prototipleme iş akışları için kesin PNG'ler oluşturun.

### Entegrasyon Olanakları
Bu renderleme hattını belge yönetim sistemleriyle birleştirerek görsel varlık üretimini otomatikleştirin.

## Performans Düşünceleri

### Performansı Optimize Etme
- **Batch Processing:** Döngü içinde birden fazla CAD dosyasını render edin.  
- **Resource Management:** Büyük çizimler için JVM yığın boyutunu ayarlayın.

### Kaynak Kullanım Rehberi
CPU ve belleği izleyin; `Viewer` örneklerini hemen serbest bırakın.

### Java Bellek Yönetimi için En İyi Uygulamalar
- Gösterildiği gibi `Viewer`'ı otomatik kapatmak için try‑with‑resources kullanın.  
- Gereğinden uzun süre büyük `Path` nesnelerini tutmaktan kaçının.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Output folder not found** | Create the directory beforehand or add `Files.createDirectories(outputDirectory);` |
| **Blank image** | Ensure `cadOptions.setBackgroundColor` is set after `forRenderingByWidth`. |
| **Out‑of‑memory errors** | Increase `-Xmx` JVM option or process files in smaller batches. |

## Sıkça Sorulan Sorular

**Q: DWG dışında başka CAD formatlarını render edebilir miyim?**  
**A:** Evet, GroupDocs.Viewer DXF, DWF ve birkaç diğer CAD dosya türünü destekler.

**Q: Önceden tanımlı bir sabit yerine özel bir RGB rengi nasıl kullanılır?**  
**A:** `new Color(123, 45, 67)` gibi yeni bir `Color` örneği oluşturun ve `setBackgroundColor` metoduna geçirin.

**Q: Sadece belirli bir layout veya katmanı render etmek mümkün mü?**  
**A:** `viewer.view` çağrısından önce `CadOptions` aracılığıyla layout veya katman seçeneklerini belirtebilirsiniz.

**Q: Kütüphane şeffaf arka planları destekliyor mu?**  
**A:** Hedef format şeffaflığı destekliyorsa, tam şeffaflık için arka plan rengini `new Color(0,0,0,0)` olarak ayarlayın.

**Q: Hangi GroupDocs.Viewer sürümü gereklidir?**  
**A:** Öğreticide version 25.2 kullanılmıştır, ancak daha yeni sürümler aynı API'yi korur.

---

**Son Güncelleme:** 2026-03-16  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs