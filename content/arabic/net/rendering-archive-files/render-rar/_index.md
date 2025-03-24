---
title: تقديم أرشيفات RAR
linktitle: تقديم أرشيفات RAR
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض أرشيفات RAR إلى تنسيقات HTML أو JPG أو PNG أو PDF باستخدام GroupDocs.Viewer لـ .NET. عرض ومشاركة محتويات أرشيفات RAR بسهولة.
weight: 13
url: /ar/net/rendering-archive-files/render-rar/
---

# تقديم أرشيفات RAR

## مقدمة
تعد أرشيفات RAR تنسيقًا شائعًا لضغط وتخزين ملفات ومجلدات متعددة في حاوية واحدة. يمكن أن يكون عرض أرشيفات RAR بتنسيقات مختلفة مثل HTML أو JPG أو PNG أو PDF أمرًا ضروريًا لعرض محتويات هذه الأرشيفات أو مشاركتها. في هذا البرنامج التعليمي، سنستكشف كيفية عرض أرشيفات RAR باستخدام GroupDocs.Viewer لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: قم بتثبيت GroupDocs.Viewer لمكتبة .NET من ملف .NET[رابط التحميل](https://releases.groupdocs.com/viewer/net/).
2. نموذج أرشيف RAR: احصل على نموذج أرشيف RAR جاهز للعرض.

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
## الخطوة 2: تقديم إلى HTML
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
## الخطوة 4: تقديم إلى PNG
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
أصبح عرض أرشيفات RAR بتنسيقات مختلفة أمرًا بسيطًا باستخدام GroupDocs.Viewer لـ .NET. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة تحويل أرشيفات RAR إلى تنسيقات HTML أو JPG أو PNG أو PDF، مما يتيح سهولة عرض محتوياتها ومشاركتها.
## الأسئلة الشائعة
### هل يستطيع GroupDocs.Viewer لـ .NET التعامل مع أرشيفات RAR المشفرة؟
نعم، يدعم GroupDocs.Viewer for .NET عرض أرشيفات RAR المشفرة بشرط توفير كلمات المرور الضرورية أثناء عملية العرض.
### هل من الممكن تخصيص مظهر الإخراج للمستندات المقدمة؟
قطعاً! يوفر GroupDocs.Viewer for .NET خيارات تخصيص واسعة النطاق تسمح للمستخدمين بتخصيص مظهر المستندات المقدمة وفقًا لتفضيلاتهم.
### هل يدعم GroupDocs.Viewer for .NET عرض تنسيقات أرشيف أخرى بخلاف RAR؟
نعم، يدعم GroupDocs.Viewer for .NET عرض تنسيقات الأرشيف المختلفة بما في ذلك ZIP وTAR و7z والمزيد.
### هل يمكنني دمج GroupDocs.Viewer لـ .NET في تطبيق الويب الخاص بي؟
بالتأكيد! يوفر GroupDocs.Viewer for .NET واجهات برمجة التطبيقات المناسبة للتكامل في كل من تطبيقات سطح المكتب والويب.
### هل هناك إصدار تجريبي متاح لـ GroupDocs.Viewer لـ .NET؟
 نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من GroupDocs.Viewer لـ .NET من[موقع إلكتروني](https://releases.groupdocs.com/).