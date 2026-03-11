---
date: '2026-01-08'
description: GroupDocs.Viewer for Java ile özel boyutlar ve arka plan renkleri kullanarak
  CAD çizimlerini yüksek kaliteli PNG görüntülerine nasıl dönüştüreceğinizi öğrenin.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: GroupDocs.Viewer for Java Kullanarak CAD Çizimlerini Özel Boyut ve Arka Plan
  Rengi ile PNG Olarak Render Etme
type: docs
url: /tr/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# CAD Çizimlerini PNG Olarak Özelleştirilmiş Boyut ve Arka Plan Rengiyle Render Etme – GroupDocs.Viewer for Java Kullanarak

CAD çizimlerinizi belirli boyut ve estetikleri koruyarak yüksek kaliteli görüntülere dönüştürmekte zorlanıyor musunuz? Bu öğreticide **CAD render etme** yöntemini, özelleştirilmiş boyut ve arka plan rengiyle PNG olarak nasıl yapacağınızı göstereceğiz, böylece raporlar, sunumlar veya web ön izlemeleri için tam istediğiniz görünümü elde edebilirsiniz.

## Hızlı Yanıtlar
- **“how to render CAD” ne anlama geliyor?** CAD dosyalarını (ör. DWG) kod kullanarak PNG gibi görüntü formatlarına dönüştürmeyi ifade eder.  
- **Özel bir genişlik ayarlayabilir miyim?** Evet – `CadOptions.forRenderingByWidth(int width)` kullanın.  
- **Arka planı nasıl değiştiririm?** `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` çağırın.  
- **Hangi kütüphane gerekiyor?** GroupDocs.Viewer for Java (sürüm 25.2 veya sonrası).  
- **Lisans gerekli mi?** Geçici veya satın alınmış bir lisans, değerlendirme sınırlamalarını kaldırır.

![GroupDocs.Viewer for Java ile Özelleştirilmiş Boyut ve Arka Plan Rengiyle CAD Çizimlerini PNG Olarak Render Etme](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## CAD Çizimlerini Render Etme – Genel Bakış
Bu bölüm, temel hedefi genişletir: **CAD render etme** çizimlerini boyut ve arka planı kontrol ederek PNG dosyalarına dönüştürmek. Tam kurulum, kod parçacıkları ve pratik ipuçları üzerinden ilerleyeceğiz.

## Öğrenecekleriniz
- Projenizde GroupDocs.Viewer for Java kurulumunu yapmak  
- **DWG'yi PNG'ye dönüştürme** özelleştirilmiş boyutlarla  
- **Arka plan rengini PNG olarak ayarlama** render sırasında şık bir görünüm için  
- Özelleştirilmiş render'ın değer kattığı gerçek dünya senaryoları  

## Ön Koşullar

### Gerekli Kütüphaneler ve Bağımlılıklar
- Java Development Kit (JDK) 8+  
- Maven bağımlılık yönetimi için  

### Ortam Kurulum Gereksinimleri
- IntelliJ IDEA veya Eclipse gibi bir IDE  
- Temel Java bilgisi  

### Bilgi Ön Koşulları
- Java'da dosya işlemleri konusunda aşinalık  

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

### Lisans Edinme
Değerlendirme kısıtlamalarını kaldırmak için geçici veya tam bir lisans edinin.

### Temel Başlatma ve Kurulum
CAD dosyanıza işaret eden bir `Viewer` örneği oluşturun:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Uygulama Kılavuzu

### Özellik 1: Özelleştirilmiş Görüntü Boyutu ve Arka Plan Rengiyle CAD Çizimlerini Render Etme

#### Genel Bakış
Bu özellik, **DWG'yi PNG'ye dönüştürmenizi** sağlar ve görüntü genişliği ile arka plan tonunu belirlemenize imkan tanır.

#### Adım‑Adım Uygulama

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

##### Özelleştirilmiş Render Seçenekleriyle Viewer'ı Başlatın
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
- `forRenderingByWidth(int width)` – özelleştirilmiş görüntü genişliğini ayarlar.  
- `setBackgroundColor(Color color)` – PNG'ye **arka plan rengi render'ı uygular**.

#### Sorun Giderme İpuçları
- Çıktı klasörünün var olduğunu doğrulayın; gerekirse oluşturun.  
- Girdi dosya yolunu ve izinleri iki kez kontrol edin.  

### Özellik 2: Render Seçeneklerinde Arka Plan Rengini Ayarlama

#### Genel Bakış
Burada, görsel tutarlılığı artırmak için **arka plan rengini PNG olarak ayarlamaya** odaklanıyoruz.

#### Adım‑Adım Uygulama

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
Özelleştirilmiş render, mühendislik çizimlerinin kurumsal stil kılavuzlarına uygun olmasını sağlar.

### 2. Mimari Görselleştirme
Sunum slaytlarıyla uyumlu temiz bir arka planla planları sergileyin.

### 3. Üretim Prototipleme
Hızlı prototipleme iş akışları için hassas PNG'ler oluşturun.

### Entegrasyon Olanakları
Bu render hattını belge yönetim sistemleriyle birleştirerek görsel varlık üretimini otomatikleştirin.

## Performans Hususları

### Performansı Optimize Etme
- **Toplu İşleme:** Döngü içinde birden fazla CAD dosyasını render edin.  
- **Kaynak Yönetimi:** Büyük çizimler için JVM yığın boyutunu ayarlayın.

### Kaynak Kullanım Kılavuzları
CPU ve belleği izleyin; `Viewer` örneklerini hızlıca serbest bırakın.

### Java Bellek Yönetimi için En İyi Uygulamalar
- Gösterildiği gibi `Viewer`'ı otomatik kapatmak için try‑with‑resources kullanın.  
- Gerekenden uzun süre büyük `Path` nesnelerini tutmaktan kaçının.

## Yaygın Sorunlar ve Çözümler

| Sorun | Çözüm |
|-------|----------|
| **Çıktı klasörü bulunamadı** | Klasörü önceden oluşturun veya `Files.createDirectories(outputDirectory);` ekleyin. |
| **Boş görüntü** | `cadOptions.setBackgroundColor`'ın `forRenderingByWidth`'den sonra ayarlandığından emin olun. |
| **Bellek yetersizliği hataları** | `-Xmx` JVM seçeneğini artırın veya dosyaları daha küçük partilerde işleyin. |

## Sıkça Sorulan Sorular

**S:** DWG dışındaki diğer CAD formatlarını render edebilir miyim?  
**C:** Evet, GroupDocs.Viewer DXF, DWF ve birkaç diğer CAD dosya tipini destekler.

**S:** Önceden tanımlı bir sabit yerine özel bir RGB rengi nasıl kullanırım?  
**C:** `new Color(123, 45, 67)` gibi yeni bir `Color` örneği oluşturun ve `setBackgroundColor`'a geçirin.

**S:** Yalnızca belirli bir düzeni veya katmanı render etmek mümkün mü?  
**C:** `viewer.view` çağrısından önce `CadOptions` aracılığıyla düzen veya katman seçeneklerini belirtebilirsiniz.

**S:** Kütüphane şeffaf arka planları destekliyor mu?  
**C:** Hedef format şeffaflığı destekliyorsa, tam şeffaflık için arka plan rengini `new Color(0,0,0,0)` olarak ayarlayın.

**S:** Hangi GroupDocs.Viewer sürümü gerekiyor?  
**C:** Öğreticide sürüm 25.2 kullanılmıştır, ancak daha yeni sürümler aynı API'yi korur.

## Sonuç
Artık **CAD render etme** yöntemini kullanarak GroupDocs.Viewer for Java ile özelleştirilmiş boyut ve arka plan renklerine sahip PNG dosyaları oluşturabilirsiniz. Bu teknikleri mühendislik, mimari veya üretim iş akışları için profesyonel görünümlü görsel varlıklar yaratmak amacıyla uygulayın.

### Sonraki Adımlar
- Farklı görüntü genişlikleri ve renklerle denemeler yapın.  
- Render kodunu bir toplu işleme servisine entegre edin.  
- PDF dönüşümü veya çok sayfalı render gibi ek Viewer seçeneklerini keşfedin.

---

**Son Güncelleme:** 2026-01-08  
**Test Edilen:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs