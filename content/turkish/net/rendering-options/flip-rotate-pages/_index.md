---
"description": "Sorunsuz belge oluşturma, çevirme ve döndürme için Groupdocs.Viewer for .NET'i uygulamalarınıza nasıl entegre edeceğinizi öğrenin."
"linktitle": "Sayfaları Çevirin ve Döndürün"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Sayfaları Çevirin ve Döndürün"
"url": "/tr/net/rendering-options/flip-rotate-pages/"
"weight": 12
---

# Sayfaları Çevirin ve Döndürün

## giriiş
Bu eğitimde, .NET için Groupdocs.Viewer'ın işlevlerini, özellikle sayfaları çevirme ve döndürmeye odaklanarak inceleyeceğiz. .NET için Groupdocs.Viewer, .NET uygulamaları içinde çeşitli biçimlerdeki belgeleri işlemek için tasarlanmış güçlü bir araçtır. Bir belge yönetim sistemi geliştiriyor veya belge görüntüleme yeteneklerini yazılımınıza entegre etmeniz gerekiyorsa, .NET için Groupdocs.Viewer etkili bir çözüm sunar.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
### .NET için Groupdocs.Viewer'ı yükleme
Groupdocs.Viewer for .NET'i kullanmak için paketi NuGet Paket Yöneticisi aracılığıyla yüklemeniz gerekir. Ayrıntılı yükleme talimatlarını şu adreste bulabilirsiniz: [belgeleme](https://tutorials.groupdocs.com/viewer/net/).

## Ad Alanlarını İçe Aktar
Groupdocs.Viewer for .NET'i etkili bir şekilde kullanabilmek için projenize gerekli ad alanlarının aktarıldığından emin olun.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Groupdocs.Viewer for .NET kullanarak sayfaları çevirme ve döndürme sürecini basit adımlara bölelim:
## Adım 1: Çıktı Dizini ve Dosya Yolunu Ayarlayın
Çıktı dosyasının kaydedilmesini istediğiniz dizini tanımlayın ve çıktı dosyası yolunu belirtin.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Adım 2: Görüntüleyici Nesnesini Başlat
Görüntülemek istediğiniz belgenin yolunu ileterek Viewer sınıfının bir örneğini oluşturun.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Adım 3: Görünüm Seçeneklerini Yapılandırın
Çıkış dosyası biçimini ve sayfa döndürme gibi ek ayarları belirleme gibi görünüm seçeneklerini ayarlayın.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Adım 4: Belgeyi Oluşturun
Viewer nesnesinin View metodunu çağırın ve view seçeneklerini geçirin.
```csharp
viewer.View(viewOptions);
```
## Adım 5: Başarı Mesajını Göster
Kullanıcıya belgenin başarıyla işlendiğini bildirin ve doğrulama için çıktı dizinini belirtin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Sonuç olarak, .NET için Groupdocs.Viewer, sayfaları çevirme ve döndürme dahil olmak üzere belgeleri işlemek için güçlü yetenekler sunar. Bu eğitimde özetlenen adımları izleyerek, bu özellikleri .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir ve kullanıcılarınız için belge görüntüleme deneyimlerini geliştirebilirsiniz.
## SSS
### Groupdocs.Viewer for .NET tüm belge formatlarıyla uyumlu mudur?
Evet, Groupdocs.Viewer for .NET, DOCX, PDF, PPTX ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### Sayfaları çevirme ve döndürmenin ötesinde görüntüleme seçeneklerini özelleştirebilir miyim?
Kesinlikle, Groupdocs.Viewer for .NET belgeleri görüntülemek için çeşitli özelleştirme seçenekleri sunarak deneyiminizi ihtiyaçlarınıza göre uyarlamanıza olanak tanır.
### Groupdocs.Viewer for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, Groupdocs.Viewer for .NET'in ücretsiz deneme sürümünden yararlanmak için şu adresi ziyaret edebilirsiniz: [web sitesi](https://releases.groupdocs.com/).
### Groupdocs.Viewer for .NET desteğini nasıl alabilirim?
Topluluk aracılığıyla yardım arayabilir ve toplulukla etkileşime girebilirsiniz. [Groupdocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9).
### Groupdocs.Viewer for .NET için geçici lisansı nereden alabilirim?
Groupdocs.Viewer for .NET için geçici lisanslar şuradan edinilebilir: [satın alma sayfası](https://purchase.groupdocs.com/temporary-license/).