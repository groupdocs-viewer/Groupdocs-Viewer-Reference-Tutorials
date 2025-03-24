---
title: Sayfaları Çevir ve Döndür
linktitle: Sayfaları Çevir ve Döndür
second_title: GroupDocs.Viewer .NET API'si
description: Sorunsuz belge oluşturma, çevirme ve döndürme için Groupdocs.Viewer for .NET'i uygulamalarınıza nasıl entegre edeceğinizi öğrenin.
weight: 12
url: /tr/net/rendering-options/flip-rotate-pages/
---

# Sayfaları Çevir ve Döndür

## giriiş
Bu eğitimde, özellikle sayfaları çevirme ve döndürmeye odaklanarak Groupdocs.Viewer for .NET'in işlevlerini inceleyeceğiz. Groupdocs.Viewer for .NET, .NET uygulamaları içinde çeşitli formatlardaki belgeleri işlemek için tasarlanmış güçlü bir araçtır. İster bir belge yönetim sistemi geliştiriyor olun, ister belge görüntüleme yeteneklerini yazılımınıza entegre etmeye ihtiyaç duyuyor olun, Groupdocs.Viewer for .NET etkili bir çözüm sunar.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
### .NET için Groupdocs.Viewer'ı yükleme
 Groupdocs.Viewer for .NET'i kullanmak için paketi NuGet Paket Yöneticisi aracılığıyla yüklemeniz gerekir. Ayrıntılı kurulum talimatlarını şurada bulabilirsiniz:[dokümantasyon](https://tutorials.groupdocs.com/viewer/net/).

## Ad Alanlarını İçe Aktar
Groupdocs.Viewer for .NET'i etkili bir şekilde kullanmak için projenizde gerekli ad alanlarının içe aktarıldığından emin olun.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Groupdocs.Viewer for .NET'i kullanarak sayfaları çevirme ve döndürme işlemini basit adımlara ayıralım:
## Adım 1: Çıktı Dizinini ve Dosya Yolunu Ayarlayın
Çıktı dosyasının kaydedilmesini istediğiniz dizini tanımlayın ve çıktı dosyası yolunu belirtin.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Adım 2: Görüntüleyici Nesnesini Başlatın
Görüntülemek istediğiniz belgenin yolunu ileterek Viewer sınıfının bir örneğini oluşturun.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## 3. Adım: Görünüm Seçeneklerini Yapılandırın
Çıktı dosyası biçimini ve sayfa döndürme gibi ek ayarları belirlemek gibi görünüm seçeneklerini ayarlayın.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Adım 4: Belgeyi Oluşturun
Viewer nesnesinin View yöntemini çağırın ve görünüm seçeneklerini iletin.
```csharp
viewer.View(viewOptions);
```
## Adım 5: Başarı Mesajını Görüntüleyin
Kullanıcıya belgenin başarıyla oluşturulduğunu bildirin ve doğrulama için çıktı dizinini belirtin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Sonuç olarak, Groupdocs.Viewer for .NET, sayfaları çevirmek ve döndürmek de dahil olmak üzere, belgeleri işlemek için güçlü yetenekler sunar. Bu öğreticide özetlenen adımları izleyerek, bu özellikleri .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir, kullanıcılarınızın belge görüntüleme deneyimlerini geliştirebilirsiniz.
## SSS'ler
### Groupdocs.Viewer for .NET tüm belge formatlarıyla uyumlu mu?
Evet, Groupdocs.Viewer for .NET, DOCX, PDF, PPTX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### Sayfaları çevirmenin ve döndürmenin ötesinde görüntüleme seçeneklerini özelleştirebilir miyim?
Kesinlikle Groupdocs.Viewer for .NET, belgeleri görüntülemek için çeşitli özelleştirme seçenekleri sunarak deneyimi gereksinimlerinize göre uyarlamanıza olanak tanır.
### Groupdocs.Viewer for .NET'in ücretsiz deneme sürümü var mı?
 Evet, Groupdocs.Viewer for .NET'in ücretsiz denemesinden şu adresi ziyaret ederek yararlanabilirsiniz:[İnternet sitesi](https://releases.groupdocs.com/).
### .NET için Groupdocs.Viewer desteğini nasıl alabilirim?
 Yardım isteyebilir ve toplulukla iletişim kurabilirsiniz.[Groupdocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9).
### .NET için Groupdocs.Viewer'a yönelik geçici lisansı nereden alabilirim?
 Groupdocs.Viewer for .NET'e yönelik geçici lisanslar şu adresten edinilebilir:[satın alma sayfası](https://purchase.groupdocs.com/temporary-license/).