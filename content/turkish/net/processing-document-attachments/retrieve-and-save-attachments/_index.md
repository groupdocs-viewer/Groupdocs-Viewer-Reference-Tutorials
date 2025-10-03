---
"description": "GroupDocs.Viewer'ı kullanarak .NET uygulamaları içindeki belge eklerini verimli bir şekilde yönetin. Ekleri zahmetsizce alın ve kaydedin."
"linktitle": "Belge Eklerini Al ve Kaydet"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Belge Eklerini Al ve Kaydet"
"url": "/tr/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
type: docs
---
# Belge Eklerini Al ve Kaydet

## giriiş
Dijital çağda, verimli belge işleme, işletmeler ve bireyler için hayati önem taşır. İster e-postaları yönetmek, ister sözleşmeleri görüntülemek veya raporlara erişmek olsun, belge görselleştirme için güvenilir bir araca sahip olmak esastır. .NET için GroupDocs.Viewer, kullanıcıların çeşitli belge biçimlerini doğrudan .NET uygulamaları içinde zahmetsizce görüntülemelerini ve bunlarla etkileşim kurmalarını sağlayan sağlam bir çözüm olarak ortaya çıkar.

![GroupDocs.Viewer .NET ile Belge Eklerini Alın ve Kaydedin](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## Ön koşullar
.NET için GroupDocs.Viewer'ı belge eklerini almak ve kaydetmek için kullanmaya başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. İşletim Ortamı: .NET framework ile kurulmuş bir çalışma ortamı.
2. Kurulum: GroupDocs.Viewer for .NET kütüphanesi indirildi ve kuruldu. Kütüphaneye şuradan erişebilirsiniz: [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).
3. Temel Anlayış: C# programlama diline aşinalık.
4. Belge Kaynağı: Gösterim amaçlı ekli örnek belgeye erişim.

## Ad Alanlarını İçe Aktar
Belge eklerini alma ve kaydetme amacıyla .NET için GroupDocs.Viewer'ı kullanmaya başlamak için gerekli ad alanlarını içe aktarın:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Adım 1: Çıktı Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
Belgeden alınan eklerin kaydedileceği dizini tanımlayın.
## Adım 2: Görüntüleyici Nesnesini Örneklendirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Ekleri içeren belgenin yolunu içeren Viewer nesnesini örneklendirin.
## Adım 3: Ekleri Alın
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Belgede bulunan eklerin listesini alın.
## Adım 4: Ekleri Kaydedin
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Her eki inceleyin, dosya yolunu tanımlayın ve eki belirtilen dizine kaydedin.
## Adım 5: Başarı Mesajını Göster
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Eklerin başarıyla kaydedildiğini belirten bir başarı mesajı ve dizin yolunu görüntüleyin.

## Çözüm
GroupDocs.Viewer for .NET'i belge işleme iş akışlarınıza dahil etmek, ekleri yönetme sürecini kolaylaştırır, verimlilik ve kolaylık sunar. Yukarıda özetlenen adım adım kılavuzu izleyerek, kullanıcılar .NET uygulamaları içinde belge eklerini sorunsuz bir şekilde alabilir ve kaydedebilir.
## SSS
### GroupDocs.Viewer for .NET çeşitli belge biçimlerini işleyebilir mi?
Evet, GroupDocs.Viewer PDF, Microsoft Office belgeleri, resimler ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### GroupDocs.Viewer for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, ücretsiz denemeye şu adresten erişebilirsiniz: [Burada](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET için geçici lisansları nasıl alabilirim?
Geçici lisanslar şuradan alınabilir: [bu bağlantı](https://purchase.groupdocs.com/temporary-license/).
### GroupDocs.Viewer for .NET için dokümanları nerede bulabilirim?
Kapsamlı dokümantasyon mevcuttur [Burada](https://tutorials.groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET için hangi destek seçenekleri mevcuttur?
Topluluk forumundan yardım isteyebilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9).