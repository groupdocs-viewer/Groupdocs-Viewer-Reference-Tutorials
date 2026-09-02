---
date: '2026-08-30'
description: DWG'yi PNG'ye dönüştürmeyi, background color'ı Java'da ayarlamayı ve
  GroupDocs.Viewer for Java ile image size'ı özelleştirmeyi öğrenin.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: GroupDocs.Viewer for Java kullanarak DWG'yi PNG'ye dönüştürün ve custom
  image width ile background color ayarlayın. Bu kılavuz, adım adım kurulum, code
  snippets ve troubleshooting tips sunar.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Java'da custom size ve background color ile DWG'yi PNG'ye dönüştürün
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: GroupDocs.Viewer for Java kullanarak DWG'yi PNG'ye custom size & background
  color ile dönüştürme
type: docs
url: /tr/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# DWG'yi Özel Boyut ve Arka Plan Rengi ile PNG'ye Dönüştürme – GroupDocs.Viewer for Java Kullanarak

Bu öğreticide, GroupDocs.Viewer for Java kullanarak, çıktı boyutlarını ve arka plan rengini kontrol ederken **DWG'yi PNG'ye nasıl dönüştüreceğinizi** öğreneceksiniz. Rapor içine CAD çizimlerini gömmek, bir web portalı için küçük resimler oluşturmak ya da toplu render işlemini otomatikleştirmek isteseniz de, aşağıdaki adımlar her PNG dosyasının görsel görünümünü tam olarak kontrol etmenizi sağlar.

## Hızlı Yanıtlar
- **“DWG'yi PNG'ye dönüştürmek” ne anlama geliyor?** Bu, bir DWG CAD dosyasını kod aracılığıyla PNG görüntüsüne dönüştürme sürecidir; vektör detayını raster pikseller olarak korur.  
- **Özel bir genişlik ayarlayabilir miyim?** Evet – ihtiyacınız olan tam piksel genişliğini tanımlamak için `CadOptions.forRenderingByWidth(int width)` metodunu çağırın.  
- **Arka plan rengini nasıl değiştiririm?** Render öncesinde `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` kullanın.  
- **Hangi kütüphane gereklidir?** GroupDocs.Viewer for Java (sürüm 25.2 veya daha yeni).  
- **Lisans gerekli mi?** Geçici ya da tam lisans, değerlendirme sınırlamalarını kaldırır ve sınırsız renderlamayı etkinleştirir.

![Özel Boyut ve Arka Plan Rengi ile PNG Olarak CAD Çizimlerini Render Etme – GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## GroupDocs.Viewer for Java Nedir?
GroupDocs.Viewer for Java, sunucu taraflı bir API olup, CAD dosyaları dahil 150'den fazla dosya formatını görüntülere, PDF'lere veya HTML'e dönüştürür. AutoCAD gibi üçüncü taraf bir yazılım gerektirmeden çalışır; bu da otomatik işlem hatları için idealdir.

## Özel boyut ve arka plan rengi ile DWG'yi PNG'ye nasıl dönüştürürsünüz?
DWG dosyasını bir `Viewer` örneğiyle yükleyin, istenen genişlik ve arka plan için `CadOptions` yapılandırın ve son olarak `viewer.view` metodunu `PngViewOptions` ile çağırın. Bu üç adımlı akış, dosya G/Ç, renderlama ve çıktı adlandırmasını tek, bellek‑verimli bir işlemde yönetir.

Viewer, bir belgeyi yükleyen ve renderlama yapan temel sınıftır.  
CadOptions, görüntü genişliği ve arka plan rengi gibi CAD‑özel ayarları yapılandırır.  
PngViewOptions, renderlanan sayfalar için PNG çıktı formatını ve adlandırma desenini tanımlar.

Artık herhangi bir DWG çizimini belirttiğiniz tam genişlikte bir PNG'ye renderlayabilir ve markanıza ya da UI temanızla eşleşecek herhangi bir katı renk (veya şeffaf) arka planı seçebilirsiniz.

## Neden özel bir arka plan rengi ayarlamalısınız?
Arka plan rengi ayarlamak, renderlanan PNG'nin çevredeki UI öğeleriyle sorunsuz bir şekilde bütünleşmesini, istenmeyen beyaz kenarların önlenmesini ve varsayılan beyaz tuvalde kaybolabilecek çizim detaylarının vurgulanmasını sağlar. GroupDocs.Viewer, özel RGB değerleri dahil olmak üzere herhangi bir `java.awt.Color`'ı destekler ve size piksel‑tam kontrol sunar.

java.awt.Color, arka planların renderlanmasında kullanılan bir renk değerini temsil eder.

## Önkoşullar
- **Java Development Kit (JDK) 8+** – API, Java 8 ve üzerini hedefler.  
- **Maven** – bağımlılık yönetimi için.  
- **IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz herhangi bir editör.  
- **Temel Java dosya işleme bilgisi** – kaynak DWG dosyalarını okuyup PNG çıktıları yazmak için.

## GroupDocs.Viewer for Java Kurulumu
GroupDocs deposunu ve Viewer bağımlılığını Maven `pom.xml` dosyanıza ekleyin:

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

### Lisans edinme
GroupDocs portalından geçici ya da tam bir lisans anahtarı edinin ve `license.lic` dosyasını proje kaynak klasörünüze yerleştirin. Bu, 20 sayfalık değerlendirme sınırlamasını kaldırır ve tam çözünürlüklü renderlamayı etkinleştirir.

### Temel başlatma ve kurulum
DWG dosyalarınızı içeren klasöre işaret eden bir `Viewer` örneği oluşturun:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Özellik 1: Özel görüntü boyutu ve arka plan rengi ile CAD çizimlerini renderlama

### CAD arka plan rengini nasıl değiştirirsiniz
CAD arka plan rengini değiştirmek için renderlamadan önce CadOptions nesnesini yapılandırın. İstenen genişliği `forRenderingByWidth` ile ayarlayın ve yeni arka planı `setBackgroundColor` ile uygulayın. Viewer, belirtilen rengi yansıtan PNG görüntüleri üretir ve tüm çıktı dosyalarında tutarlı bir görsel stil sağlar.

#### Adım‑adım uygulama

##### Gerekli paketleri içe aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Çıktı dizinini ve dosya‑yolu formatını ayarlayın
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Özel render seçenekleriyle viewer'ı başlatın
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

**Parametrelerin açıklaması**  
- `PngViewOptions` – PNG çıktı formatını ve adlandırma desenini tanımlar.  
- `forRenderingByWidth(int width)` – renderlayıcıyı, verilen piksel değerine eşit genişlikte bir görüntü üretmeye zorlar; yükseklik orantılı olarak ölçeklenir.  
- `setBackgroundColor(Color color)` – varsayılan beyaz tuvali seçtiğiniz renk ile değiştirir, oluşturulan varlıklar arasında görsel tutarlılığı artırır.

#### Sorun giderme ipuçları
- Çıktı klasörünün mevcut olduğundan emin olun; yoksa `Files.createDirectories(outputDir)` kullanın.  
- Giriş dosya yolunun doğru olduğunu ve uygulamanın okuma izinlerine sahip olduğunu doğrulayın.  

## Özellik 2: Render seçeneklerinde arka plan rengini ayarlama

### PNG arka plan rengini nasıl ayarlarsınız
PNG arka plan rengini ayarlamak, bir Color örneği oluşturup renderlamadan önce CadOptions'a atamayı içerir. Bu, oluşturulan her PNG'nin belirtilen arka planı kullanmasını, marka yönergelerinize veya UI temanızla eşleşmesini sağlar. Önceden tanımlı sabitleri kullanabilir veya kesin kontrol için özel RGB değerleri tanımlayabilirsiniz.

java.awt.Color, arka planların renderlanmasında kullanılan bir renk değerini temsil eder.

#### Adım‑adım uygulama

##### Gerekli paketleri içe aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Arka plan rengiyle render seçeneklerini yapılandırın
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

**Ana yapılandırma seçenekleri**  
- Farklı boyutlar için `forRenderingByWidth(int width)` ayarlayın; örneğin web küçük resimleri için 800 px veya yüksek çözünürlüklü baskılar için 1920 px.  
- Herhangi bir önceden tanımlı `Color` sabitini (ör. `Color.LIGHT_GRAY`) kullanın veya kesin marka renkleri için `new Color(r, g, b)` ile özel bir örnek oluşturun.

## Pratik uygulamalar

### 1. Mühendislik dokümantasyonu
Özel renderlama, her çizimin şirket stil kılavuzuna uymasını sağlar ve dışa aktarımdan sonra manuel görüntü düzenlemeyi ortadan kaldırır.

### 2. Mimari görselleştirme
Mavi planları, slayt setleri veya müşteri odaklı portallar ile uyumlu bir arka planla sunarak görsel bütünlüğü artırın.

### 3. Üretim prototiplemesi
Aşağı akış araçlarının belirli bir görüntü boyutu ve arka plan beklediği hızlı prototip iş akışları için PNG'ler oluşturun.

### Entegrasyon olasılıkları
Bu renderleme hattını bir belge‑yönetim sistemi (ör. SharePoint) ile eşleştirerek bir DWG dosyası yüklendiğinde otomatik olarak ön izleme görüntüleri oluşturun.

## Performans değerlendirmeleri

### Performansı optimize etme
- **Toplu işleme:** DWG dosyalarının bulunduğu bir dizini döngüye alıp her birini sırasıyla renderlayarak JVM ısınma maliyetlerini amorti edin.  
- **Kaynak yönetimi:** Büyük çizimler (500+ sayfa) için JVM yığınını (`-Xmx2g`) artırın veya bellek yetersizliği hatalarını önlemek için dosyaları daha küçük partilerde işleyin.

### Kaynak kullanım yönergeleri
CPU ve bellek kullanımını VisualVM gibi araçlarla izleyin; `Viewer` örneklerini try‑with‑resources kullanarak hemen serbest bırakın.

### Java bellek yönetimi için en iyi uygulamalar
- Try‑with‑resources (gösterildiği gibi) kullanarak `Viewer`'ı otomatik kapatın.  
- Büyük `Path` nesnelerini hemen kullanım sonrası tutmaktan kaçının.  

## Yaygın sorunlar ve çözümler

| Sorun | Çözüm |
|-------|----------|
| Çıktı klasörü bulunamadı | Klasörü önceden oluşturun veya `Files.createDirectories(outputDirectory);` ekleyin |
| Boş görüntü | `cadOptions.setBackgroundColor`'ın `forRenderingByWidth`'den sonra çağrıldığından emin olun |
| Bellek yetersizliği hataları | `-Xmx` JVM seçeneğini artırın veya dosyaları daha küçük partilerde işleyin |

## Sıkça Sorulan Sorular

**S: DWG dışındaki diğer CAD formatlarını renderlayabilir miyim?**  
C: Evet, GroupDocs.Viewer DXF, DWF ve birkaç ek CAD formatını destekler.

**S: Önceden tanımlı bir sabit yerine özel bir RGB rengi nasıl kullanırım?**  
C: `new Color(123, 45, 67)` ile yeni bir `Color` nesnesi oluşturup `setBackgroundColor`'a geçirin.

**S: Yalnızca belirli bir düzeni veya katmanı renderlamak mümkün mü?**  
C: `viewer.view` çağırmadan önce `CadOptions` aracılığıyla düzen veya katman seçeneklerini belirtebilirsiniz.

**S: Kütüphane şeffaf arka planları destekliyor mu?**  
C: Çıktı formatı destekliyorsa tam şeffaflık için arka plan rengini `new Color(0,0,0,0)` olarak ayarlayın.

**S: Hangi GroupDocs.Viewer sürümü gereklidir?**  
C: Öğreticide sürüm 25.2 kullanılmıştır, ancak daha yeni sürümler aynı API yapısını korur.

**Son Güncelleme:** 2026-08-30  
**Test Edilen:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs

## İlgili Öğreticiler

- [groupdocs viewer dwg – Java'da GroupDocs.Viewer Kullanarak Belirli CAD Çizimlerini Render Etme](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [GroupDocs.Viewer ile Java'da CAD Katmanlarını Render Etme – Tam Kılavuz](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Java'da GroupDocs.Viewer ile PDF'yi HTML'ye Dönüştürme ve Görüntü Kalitesini Optimize Etme](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)