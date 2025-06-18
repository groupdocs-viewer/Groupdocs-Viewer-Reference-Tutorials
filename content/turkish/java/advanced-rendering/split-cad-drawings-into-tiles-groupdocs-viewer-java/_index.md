---
"date": "2025-04-24"
"description": "Java için GroupDocs.Viewer'ı kullanarak büyük CAD çizimlerini parçalara nasıl verimli bir şekilde böleceğinizi öğrenin, böylece uygulamalarınızda performansı ve yönetim kolaylığını artırın."
"title": "Verimli İşleme için GroupDocs.Viewer Java'yı Kullanarak CAD Çizimlerini Döşemelere Bölme"
"url": "/tr/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/"
"weight": 1
---

# GroupDocs.Viewer Java ile CAD Çizimlerini Döşemelere Bölme

## giriiş
Java uygulamanızda büyük CAD çizimlerini yönetmek ve verimli bir şekilde işlemek için mi mücadele ediyorsunuz? Bu kılavuz, bu çizimleri yönetilebilir döşemelere bölmek için GroupDocs.Viewer for Java'nın nasıl kullanılacağını gösterecektir. Çizimi daha küçük bölümlere bölerek performansı ve kullanım kolaylığını önemli ölçüde artırabilirsiniz.

**Ne Öğreneceksiniz:**
- Java için GroupDocs.Viewer'ı kurma ve yapılandırma.
- CAD çizimlerini parçalara bölmenin adım adım süreci.
- Anahtar yapılandırmaları ve optimizasyon teknikleri.
- Pratik uygulamalar ve entegrasyon olanakları.

Öncelikle ortamınızın gerekli ön koşullara sahip olacak şekilde hazır olduğundan emin olalım.

## Ön koşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:

- **Kütüphaneler**: Java için GroupDocs.Viewer (sürüm 25.2 veya üzeri).
- **Çevre Kurulumu**: Çalışan bir Java Geliştirme Kiti (JDK) ve IntelliJ IDEA veya Eclipse gibi entegre bir geliştirme ortamı.
- **Bilgi Önkoşulları**Java programlama konusunda temel bilgi ve Maven derleme aracına aşinalık.

## Java için GroupDocs.Viewer Kurulumu
GroupDocs.Viewer'ı kullanmak için, onu projenize bir bağımlılık olarak ekleyin. Maven kullanıyorsanız:

**Maven Yapılandırması:**
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

### Lisans Edinimi
GroupDocs.Viewer'ın tüm yeteneklerini keşfetmeniz için ücretsiz deneme lisansı sunulmaktadır:
- **Ücretsiz Deneme**: Ziyaret etmek [GroupDocs Ücretsiz Deneme](https://releases.groupdocs.com/viewer/java/) Kütüphaneyi indirip test etmek için.
- **Geçici Lisans**Geçici lisans için başvuruda bulunun [Geçici Lisans Sayfası](https://purchase.groupdocs.com/temporary-license/).
- **Satın almak**: Onların tam lisansını satın alın [Satın Alma Sayfası](https://purchase.groupdocs.com/buy).

### Temel Başlatma ve Kurulum
Java uygulamanızda GroupDocs.Viewer'ı başlatmak için:
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Oluşturma kodunuz buraya gelecek.
        }
    }
}
```
Kurulum tamamlandıktan sonra özelliği uygulamaya geçelim.

## Uygulama Kılavuzu

### Çizimi Parçalara Böl
Bu bölüm, daha verimli işleme ve işleme için bir CAD çiziminin daha küçük parçalara nasıl bölüneceğini gösterir. Her parça orijinal boyutunun dörtte biri olacaktır.

#### Adım 1: Çıktı Dizin Yolunu Tanımlayın
Öncelikle render edilmiş görsellerinizin nereye kaydedileceğini tanımlayarak başlayın:
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
Bu kurulum, yeniden kullanılabilirliği ve netliği garanti altına alarak yolu elde etmek için bir yardımcı yöntem kullanır.

#### Adım 2: Görünüm Seçeneklerini Yapılandırın
Her bölümü ayrı ayrı işlemek için seçenekleri ayarlayın:
```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```
Bu kod parçacığı, tüm sayfaları aynı anda işlemeden PNG formatına dönüştürmeyi yapılandırır.

#### Adım 3: Fayans Boyutlarını Hesaplayın
Her bir fayansın boyutlarını belirleyin:
```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Her bir karo toplam büyüklüğün dörtte biri kadardır.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

#### Adım 4: Döşemeleri Oluşturun ve Kaydedin
Hesaplanan her bir kutucuğu oluşturma seçeneklerine ekleyin ve oluşturun:
```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```
Bu son adım, belirtilen döşemelere göre belgeyi işler ve her birini ayrı bir PNG dosyası olarak kaydeder.

### Sorun Giderme İpuçları
- Projenizin derleme yolunun GroupDocs.Viewer JAR dosyalarını içerdiğinden emin olun.
- Çıktı dizininin uygulamanız tarafından yazılabilir olduğunu doğrulayın.
- Belirli çizim dosyalarındaki sorunları teşhis etmek için işlemede herhangi bir istisna olup olmadığını kontrol edin.

## Pratik Uygulamalar
CAD çizimlerini parçalara bölmek şu durumlarda faydalı olabilir:
1. **Web Haritalama**: Sunucu kaynaklarını aşırı yüklemeden büyük mimari planları web haritalarına verimli bir şekilde yükleme.
2. **Belge Yönetim Sistemleri**: Büyük çizimlerin belirli bölümlerine daha kolay yönetim ve daha hızlı erişim.
3. **Mobil Uygulamalar**:Kullanıcı etkileşimine bağlı olarak çizimin yalnızca gerekli kısımlarının oluşturulmasıyla performansın artırılması.

## Performans Hususları
Uygulamanızın performansını optimize etmek için:
- Detay ve işlem süresi arasında denge sağlamak için döşemeleri stratejik olarak kullanın.
- Özellikle çok büyük çizimlerle uğraşırken bellek kullanımını izleyin.
- Otomatik kaynak temizliği için try-with-resources'ı kullanmak gibi, verimli bellek yönetimi için Java'daki en iyi uygulamaları kullanın.

## Çözüm
Artık CAD çizimlerini GroupDocs.Viewer for Java kullanarak parçalara nasıl böleceğinizi öğrendiniz. Bu yaklaşım yalnızca işleme performansını iyileştirmekle kalmaz, aynı zamanda büyük belge dosyalarıyla uğraşırken uygulamanızın kullanılabilirliğini de artırır.

**Sonraki Adımlar:**
- Belirli kullanım durumlarına göre farklı fayans boyutlarıyla denemeler yapın.
- Belge işleme yeteneklerinizi daha da geliştirmek için GroupDocs.Viewer'ın sunduğu diğer özellikleri keşfedin.

Bu çözümü projenize uygulamaya hazır mısınız? Deneyin ve iyileştirmeleri kendiniz görün!

## SSS Bölümü
1. **GroupDocs.Viewer Java'yı kullanırken karşılaşılan yaygın hatalar nelerdir?**
   - Yaygın sorunlar arasında yanlış dosya yolları, çıktı dizinlerinde yetersiz izinler veya eksik bağımlılıklar yer alır.
2. **Bu yöntemle diğer türdeki belgeleri de parçalara bölebilir miyim?**
   - Örnek CAD çizimlerine odaklanmış olsa da, benzer ilkeler GroupDocs.Viewer tarafından desteklenen diğer belge biçimlerine de uygulanabilir.
3. **Daha büyük dosyaları nasıl daha verimli şekilde yönetebilirim?**
   - Büyük dosya işlemeyi yönetmek için Java'da çoklu iş parçacığı veya eşzamansız işlemeyi kullanmayı düşünün.
4. **Çıktı görüntü kalitesini özelleştirme desteği var mı?**
   - Evet, PNGViewOptions ayarlarını düzenleyerek oluşturulan görsellerin çözünürlüğünü ve kalitesini değiştirebilirsiniz.
5. **Uygulamamın render sırasında belleği dolarsa ne yapmalıyım?**
   - Döşeme boyutlarınızı optimize edin ve Java'nın yığın boyutunu VM seçenekleriyle artırmayı düşünün `-Xmx` daha fazla kullanılabilir bellek için.

## Kaynaklar
- [Belgeleme](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer'ı indirin](https://releases.groupdocs.com/viewer/java/)
- [Lisans Satın Alın](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme](https://releases.groupdocs.com/viewer/java/)
- [Geçici Lisans](https://purchase.groupdocs.com/temporary-license/)
- [Destek Forumu](https://forum.groupdocs.com/c/viewer/9)

Bu kılavuzu takip ederek, GroupDocs.Viewer'ı kullanarak Java uygulamalarınızda verimli belge oluşturmayı uygulamak için iyi bir donanıma sahip olursunuz. İyi kodlamalar!