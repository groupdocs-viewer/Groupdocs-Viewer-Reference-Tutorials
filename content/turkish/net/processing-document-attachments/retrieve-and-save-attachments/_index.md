---
title: Belge Eklerini Alma ve Kaydetme
linktitle: Belge Eklerini Alma ve Kaydetme
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer'ı kullanarak .NET uygulamaları içindeki belge eklerini verimli bir şekilde yönetin. Ekleri sorunsuz bir şekilde alın ve kaydedin.
type: docs
weight: 12
url: /tr/net/processing-document-attachments/retrieve-and-save-attachments/
---
## giriiş
Dijital çağda, verimli belge yönetimi hem işletmeler hem de bireyler için çok önemlidir. E-postaları yönetmek, sözleşmeleri görüntülemek veya raporlara erişmek olsun, belge görselleştirme için güvenilir bir araca sahip olmak çok önemlidir. GroupDocs.Viewer for .NET, kullanıcıların çeşitli belge formatlarını doğrudan .NET uygulamalarında zahmetsizce görüntülemesine ve bunlarla etkileşime girmesine olanak tanıyan güçlü bir çözüm olarak ortaya çıkıyor.
## Önkoşullar
Belge eklerini almak ve kaydetmek için GroupDocs.Viewer for .NET'i kullanmaya başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. İşletim Ortamı: .NET framework ile kurulmuş bir çalışma ortamı.
2.  Kurulum: .NET kütüphanesi için GroupDocs.Viewer indirildi ve kuruldu. Kütüphaneye adresinden ulaşabilirsiniz.[İndirme: {link](https://releases.groupdocs.com/viewer/net/).
3. Temel Anlama: C# programlama diline aşinalık.
4. Belge Kaynağı: Gösterim amacıyla ekleri olan örnek bir belgeye erişim.

## Ad Alanlarını İçe Aktar
Belge ekini almak ve kaydetmek amacıyla GroupDocs.Viewer for .NET'i kullanmaya başlamak için gerekli ad alanlarını içe aktarın:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
Belgeden alınan ekleri kaydetmek istediğiniz dizini tanımlayın.
## Adım 2: Görüntüleyici Nesnesini Örneklendirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Ekleri içeren belgenin yolunu içeren Viewer nesnesinin örneğini oluşturun.
## 3. Adım: Ekleri Alın
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Belgede bulunan eklerin listesini alın.
## Adım 4: Ekleri Kaydet
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Her eki yineleyin, dosya yolunu tanımlayın ve eki belirtilen dizine kaydedin.
## Adım 5: Başarı Mesajını Görüntüleyin
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Dizin yolu ile birlikte eklerin başarıyla kaydedildiğini gösteren bir başarı mesajı görüntüleyin.

## Çözüm
GroupDocs.Viewer for .NET'i belge işleme iş akışlarınıza dahil etmek, ekleri yönetme sürecini kolaylaştırarak verimlilik ve rahatlık sunar. Kullanıcılar, yukarıda özetlenen adım adım kılavuzu izleyerek, .NET uygulamaları içindeki belge eklerini sorunsuz bir şekilde alıp kaydedebilirler.
## SSS'ler
### .NET için GroupDocs.Viewer çeşitli belge formatlarını işleyebilir mi?
Evet, GroupDocs.Viewer, PDF, Microsoft Office belgeleri, resimler ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne şuradan erişebilirsiniz:[Burada](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET için geçici lisansları nasıl edinebilirim?
 Geçici lisanslar şuradan alınabilir:[bu bağlantı](https://purchase.groupdocs.com/temporary-license/).
### GroupDocs.Viewer for .NET belgelerini nerede bulabilirim?
 Kapsamlı belgeler mevcut[Burada](https://reference.groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET için hangi destek seçenekleri mevcut?
 Topluluk forumundan yardım isteyebilirsiniz[Burada](https://forum.groupdocs.com/c/viewer/9).