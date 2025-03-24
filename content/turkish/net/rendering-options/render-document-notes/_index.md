---
title: Belgeyi Notlarla Oluştur
linktitle: Belgeyi Notlarla Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak not içeren belgeleri nasıl oluşturacağınızı öğrenin. .NET uygulamalarınızla kusursuz entegrasyon için adım adım eğitim.
weight: 14
url: /tr/net/rendering-options/render-document-notes/
---
## giriiş
Belge işleme ve görüntüleme alanında GroupDocs.Viewer for .NET, kesintisiz entegrasyon ve güçlü işlevler sunan sağlam bir çözüm olarak duruyor. Bu eğitimin amacı, GroupDocs.Viewer for .NET'i kullanarak notlar içeren belgeleri oluşturma sürecinde size rehberlik etmektir. İster tecrübeli bir geliştirici olun ister sadece .NET dünyasına dalın, bu adım adım kılavuz belge oluşturmanın inceliklerini kolaylıkla aşmanıza yardımcı olacaktır.
## Önkoşullar
Öğreticiye başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
### 1. .NET için GroupDocs.Viewer'ın kurulumu
 Öncelikle ve en önemlisi, geliştirme ortamınızda GroupDocs.Viewer for .NET'in kurulu olması gerekir. Gerekli dosyaları sağlanan dosyalardan indirebilirsiniz.[İndirme: {link](https://releases.groupdocs.com/viewer/net/) ve kurulum talimatlarını takip edin.
### 2. .NET Framework'ün Temel Bilgisi
Bu eğitimde özetlenen kavramları anlamak ve adımları uygulamak için .NET çerçevesine ilişkin temel bir anlayış gereklidir. .NET'te yeniyseniz, çevrimiçi kaynaklar veya eğitimler aracılığıyla temellerini öğrenmeyi düşünün.
### 3. C# Programlama Diline aşinalık
GroupDocs.Viewer for .NET, C# ortamında çalıştığından, C# programlama diline aşina olmak çok önemlidir. C# sözdizimi, veri türleri ve nesne yönelimli programlama ilkeleri hakkında yeterli bilgiye sahip olduğunuzdan emin olun.
### 4. Notlu Belge Dosyaları
GroupDocs.Viewer for .NET'i kullanarak oluşturmayı planladığınız notları içeren belge dosyalarınız olduğundan emin olun. Desteklenen formatlar arasında PDF, DOCX, PPTX vb. yer alır ancak bunlarla sınırlı değildir.

## Ad Alanlarını İçe Aktar
Artık önkoşulları yerine getirdiğinize göre, belge oluşturma işlemini başlatmak için gerekli ad alanlarını içe aktarmaya devam edelim.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
System.IO ad alanı, işleme işlemi sırasında dosya yollarını yönetmek için kullanılacak dosyalardan ve akışlardan okuma ve bunlara yazma için sınıflar sağlar.

Şimdi, notlarla birlikte belgeleri oluşturma sürecini bir dizi adım adım talimatlara ayıralım.
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
İşlenen belge dosyalarının kaydedilmesini istediğiniz dizini belirtin. Bu dizine yazmak için uygun izinlere sahip olduğunuzdan emin olun.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
İşlenen belgenin ayrı sayfaları için dosya yolu formatını tanımlayın. Bu format, sayfaların çıkış dizininde nasıl adlandırılacağını ve organize edileceğini belirleyecektir.
## 3. Adım: Görüntüleyici Nesnesini Başlatın
```csharp
using (Viewer viewer = new Viewer(TestFiles.PPTX_WITH_NOTES))
```
 Notları içeren belge dosyasının yolunu sağlayarak bir Viewer nesnesini başlatın. Yer değiştirmek`TestFiles.PPTX_WITH_NOTES` belge dosyanızın gerçek yolu ile.
## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.RenderNotes = true;
```
 Belgeyi oluşturmak için HTML görünüm seçeneklerini yapılandırın. Ayarlayarak notların oluşturulmasını etkinleştirin`RenderNotes` mülkiyet`true`.
## Adım 5: Belgeyi Oluşturun
```csharp
viewer.View(options);
```
 Çağır`View` Yapılandırılmış HTML görünüm seçeneklerini ileten Viewer nesnesinin yöntemi. Bu, notların bulunduğu belge için oluşturma sürecini başlatacaktır.
## Adım 6: Çıkış Dizinini Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Başarılı işlemeyi belirten bir mesaj görüntüleyin ve işlenmiş belge dosyalarının bulunduğu çıktı dizininin yolunu belirtin.

## Çözüm
Sonuç olarak, GroupDocs.Viewer for .NET'i kullanarak notları içeren belgeleri oluşturmak, yalnızca birkaç satır kodla gerçekleştirilebilecek basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek ve GroupDocs.Viewer'ın güçlü özelliklerinden yararlanarak belge görüntüleme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET tüm belge formatlarıyla uyumlu mu?
GroupDocs.Viewer for .NET, PDF, DOCX, PPTX, XLSX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler. Desteklenen formatların tam listesi için belgelere bakın.
### Oluşturma seçeneklerini belirli gereksinimlere uyacak şekilde özelleştirebilir miyim?
Evet, GroupDocs.Viewer for .NET, belgeleri işlemek için kapsamlı özelleştirme seçenekleri sunarak çıktıyı ihtiyaçlarınıza göre uyarlamanıza olanak tanır.
### GroupDocs.Viewer for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, sağlanan ücretsiz GroupDocs.Viewer for .NET denemesinden yararlanabilirsiniz.[bağlantı](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET için teknik desteği veya yardımı nerede bulabilirim?
 Teknik destek ve yardım için GroupDocs.Viewer forumunu ziyaret edebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9).
### GroupDocs.Viewer for .NET için geçici bir lisans alabilir miyim?
 Evet, sağlanan bağlantıdan GroupDocs.Viewer for .NET için geçici bir lisans alabilirsiniz.[bağlantı](https://purchase.groupdocs.com/temporary-license/).