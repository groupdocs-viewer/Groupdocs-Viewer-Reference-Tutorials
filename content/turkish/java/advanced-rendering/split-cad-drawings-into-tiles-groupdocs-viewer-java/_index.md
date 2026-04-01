---
date: '2026-04-01'
description: GroupDocs Viewer for Java kullanarak CAD çizimlerini parçalara bölmeyi
  öğrenin, render performansını artırın ve büyük dosya işlemlerini basitleştirin.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: GroupDocs Viewer ile CAD Çizimlerini Parçalara Bölme
type: docs
url: /tr/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# CAD Çizimlerini GroupDocs Viewer ile Parçalara Ayırma

Eğer **how to split CAD** dosyalarını daha küçük, daha yönetilebilir parçalara ayırmayı merak ediyorsanız, doğru yerdesiniz. Bu öğreticide, **GroupDocs Viewer for Java** kullanarak büyük CAD çizimlerini parçalara (tiles) ayırmak için gereken adımları adım adım göstereceğiz. Sonunda, render hızını artıran, bellek tüketimini azaltan ve çizimleri web veya mobil uygulamalarda görüntülemeyi kolaylaştıran hazır bir çözüm elde edeceksiniz.

![GroupDocs.Viewer for Java ile CAD Çizimlerini Bölme](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Hızlı Yanıtlar
- **“splitting CAD” ne sağlar?** Büyük bir çizimi daha hızlı yüklenen ve daha az bellek tüketen daha küçük görüntülere (tiles) böler.  
- **Hangi format parçalar için kullanılır?** Varsayılan olarak PNG dosyaları üretilir, ancak diğer formatlar Viewer seçenekleriyle desteklenir.  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ücretli lisans gereklidir.  
- **Parça boyutunu değiştirebilir miyim?** Evet – ihtiyacınıza göre `tileWidth` ve `tileHeight` hesaplamalarını ayarlayın.  
- **Bu yaklaşım çoklu iş parçacığı güvenli mi?** Her bir parçayı kendi `Viewer` örneğinde try‑with‑resources ile render etmek, eşzamanlı yürütme için güvenlidir.

## “how to split CAD” nedir?
Splitting CAD, tek bir, genellikle çok büyük bir CAD çizimini birden fazla dikdörtgen bölüme (tiles) ayırmak anlamına gelir. Her bir parça bağımsız olarak render edilir, bu da kullanıcıya gerçekten ihtiyaç duyduğu bölümleri yüklemenizi sağlar—web haritaları, belge portalları ve mobil görüntüleyiciler için mükemmeldir.

## Neden GroupDocs Viewer for Java Kullanmalı?
GroupDocs Viewer, DWG, DXF ve DWF dahil olmak üzere 100'den fazla dosya formatı için kutudan çıktığı gibi destek sağlar. Tile API'si, tam koordinatları belirtmenize olanak tanır, böylece tüm dosyayı işlemeye gerek kalmadan sadece ilgilendiğiniz alanı render edebilirsiniz. Bu, CPU döngülerini tasarruf eder, bant genişliğini azaltır ve daha akıcı bir kullanıcı deneyimi sunar.

## Önkoşullar
- **Libraries**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Herhangi bir güncel Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse veya başka bir Java‑uyumlu IDE.  
- **Build Tool**: Maven (bağımlılık eklendiği sürece diğer yapı araçları da çalışır).  

## GroupDocs.Viewer for Java Kurulumu
GroupDocs deposunu ve bağımlılığı `pom.xml` dosyanıza ekleyin:

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
GroupDocs.Viewer değerlendirme için ücretsiz bir deneme lisansı sunar:

- **Ücretsiz Deneme**: Kütüphaneyi indirmek için [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) adresini ziyaret edin.  
- **Geçici Lisans**: [Temporary License Page](https://purchase.groupdocs.com/temporary-license/) üzerinden başvurun.  
- **Tam Lisans**: [Purchase Page](https://purchase.groupdocs.com/buy) üzerinden bir üretim lisansı satın alın.

### Temel Başlatma
Kütüphanenin doğru yüklendiğini doğrulamak için basit bir `Viewer` örneği oluşturun:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## CAD Çizimlerini Parçalara Ayırmak İçin Adım Adım Kılavuz

### Adım 1: Çıktı Dizini Tanımlama
Her bir parçayı ayrı bir PNG dosyası olarak saklayacağız. Bir yardımcı yöntem kullanmak, yol mantığını temiz ve yeniden kullanılabilir tutar.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Adım 2: Görünüm Seçeneklerini Yapılandırma
Render formatını PNG olarak ayarlayın ve görüntüleyiciye her sayfayı önceden yüklememesini söyleyin (bu bellek tasarrufu sağlar).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Adım 3: Parça Boyutlarını Hesaplama
İlk olarak çizimin orijinal genişlik ve yüksekliğini alıyoruz, ardından dört eşit bölgeye ayırıyoruz.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Adım 4: Parçaları Render Et ve Kaydet
Hesaplanan parçaları render seçeneklerine ekleyin ve `Viewer`'ın PNG dosyalarını oluşturmasına izin verin.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Sorun Giderme İpuçları
- **Build path** – GroupDocs JAR dosyalarının sınıf yolunda (classpath) olduğundan emin olun.  
- **Permissions** – Çıktı klasörünün Java işlemi tarafından yazılabilir olması gerekir.  
- **Exceptions** – `ViewerException` görürseniz, DWG dosyasının bozuk olmadığını ve doğru lisansın uygulandığını iki kez kontrol edin.

## CAD Parçalarını Bölmenin Yaygın Kullanım Senaryoları
1. **Web Mapping** – Kullanıcı kaydırma/zoom yaptıkça sadece kat planının görünen kısmını yükleyin.  
2. **Document Management** – Daha hızlı ön izleme oluşturmak için her parçayı ayrı ayrı saklayın.  
3. **Mobile Viewing** – Mevcut ekran için gereken parçaları indirerek bant genişliğini azaltın.

## Performans Düşünceleri
- **Tile Size** – Daha büyük parçalar daha az dosya demektir ancak daha yavaş render olur; UI ihtiyaçlarınıza göre bir denge bulun.  
- **Memory Monitoring** – Çok büyük çizimleri işlerken yığın kullanımını izlemek için Java’nın profil araçlarını (ör. VisualVM) kullanın.  
- **Resource Cleanup** – Yukarıda gösterilen try‑with‑resources deseni, yerel kaynakları otomatik olarak serbest bırakır.

## Sıkça Sorulan Sorular

**Q: Aynı yaklaşımı kullanarak diğer dosya türlerini (PDF, görüntüler) parçalara ayırabilir miyim?**  
A: Evet. GroupDocs Viewer birçok formatı destekler; sadece ilgili seçenek sınıfını (ör. `PdfViewOptions`) kullanmanız yeterlidir.

**Q: Çıktı görüntü kalitesini nasıl değiştiririm?**  
A: `viewOptions.setResolution(int dpi)` ayarlayarak veya `PngOptions` nesnesinde sıkıştırma ayarlarını belirleyerek.

**Q: Uygulamam çok büyük DWG dosyalarında bellek yetersizliği yaşıyor—ne yapabilirim?**  
A: Parça boyutlarını küçültün, JVM yığın boyutunu (`-Xmx`) artırın veya parçaları ayrı `Viewer` örneklerinde sıralı olarak render edin.

**Q: Parçaları eşzamanlı olarak render etmek mümkün mü?**  
A: Kesinlikle. Her bir parça render çağrısını bir `CompletableFuture` içine alabilir veya iş yükünü paralelleştirmek için bir executor servisi kullanabilirsiniz.

**Q: Her parça için ayrı bir lisansa ihtiyacım var mı?**  
A: Hayır. Tek bir geçerli GroupDocs Viewer lisansı, uygulamanızdaki tüm render işlemlerini kapsar.

## Kaynaklar
- [Dokümantasyon](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer İndir](https://releases.groupdocs.com/viewer/java/)
- [Lisans Satın Al](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme](https://releases.groupdocs.com/viewer/java/)
- [Geçici Lisans](https://purchase.groupdocs.com/temporary-license/)
- [Destek Forumu](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-04-01  
**Test Edilen:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs  

---