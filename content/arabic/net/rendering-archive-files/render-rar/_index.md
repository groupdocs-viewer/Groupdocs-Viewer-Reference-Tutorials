---
"description": "تعرّف على كيفية تحويل أرشيفات RAR إلى صيغ HTML أو JPG أو PNG أو PDF باستخدام GroupDocs.Viewer لـ .NET. استعرض محتويات أرشيفات RAR وشاركها بسهولة."
"linktitle": "عرض أرشيفات RAR"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض أرشيفات RAR"
"url": "/ar/net/rendering-archive-files/render-rar/"
"weight": 13
---

# عرض أرشيفات RAR

## مقدمة
أرشيفات RAR هي تنسيق شائع لضغط وتخزين ملفات ومجلدات متعددة في حاوية واحدة. يُعدّ عرض أرشيفات RAR بتنسيقات مختلفة، مثل HTML وJPG وPNG وPDF، أمرًا أساسيًا لعرض محتوياتها أو مشاركتها. في هذا البرنامج التعليمي، سنستكشف كيفية عرض أرشيفات RAR باستخدام GroupDocs.Viewer لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: قم بتثبيت مكتبة GroupDocs.Viewer لـ .NET من [رابط التحميل](https://releases.groupdocs.com/viewer/net/).
2. أرشيف RAR نموذجي: احصل على أرشيف RAR نموذجي جاهز للعرض.

## استيراد مساحات الأسماء
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: العرض إلى HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## الخطوة 3: تقديم إلى JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## الخطوة 4: التقديم إلى PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## الخطوة 5: تقديم إلى PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## خاتمة
يُسهّل GroupDocs.Viewer لـ .NET عرض أرشيفات RAR بتنسيقات مختلفة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة تحويل أرشيفات RAR إلى تنسيقات HTML أو JPG أو PNG أو PDF، مما يُتيح عرض محتوياتها ومشاركتها بسهولة.
## الأسئلة الشائعة
### هل يمكن لـ GroupDocs.Viewer لـ .NET التعامل مع أرشيفات RAR المشفرة؟
نعم، يدعم GroupDocs.Viewer لـ .NET عرض أرشيفات RAR المشفرة بشرط توفير كلمات المرور اللازمة أثناء عملية العرض.
### هل من الممكن تخصيص مظهر إخراج المستندات المقدمة؟
بالتأكيد! يوفر GroupDocs.Viewer لـ .NET خيارات تخصيص شاملة، مما يسمح للمستخدمين بتخصيص مظهر المستندات المعروضة وفقًا لإرشاداتهم.
### هل يدعم GroupDocs.Viewer لـ .NET عرض تنسيقات أرشيف أخرى غير RAR؟
نعم، يدعم GroupDocs.Viewer لـ .NET عرض تنسيقات الأرشيف المختلفة بما في ذلك ZIP وTAR و7z والمزيد.
### هل يمكنني دمج GroupDocs.Viewer لـ .NET في تطبيق الويب الخاص بي؟
بالتأكيد! يوفر GroupDocs.Viewer لـ .NET واجهات برمجة تطبيقات مناسبة للتكامل مع تطبيقات سطح المكتب والويب.
### هل هناك نسخة تجريبية متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من GroupDocs.Viewer لـ .NET من [موقع إلكتروني](https://releases.groupdocs.com/).