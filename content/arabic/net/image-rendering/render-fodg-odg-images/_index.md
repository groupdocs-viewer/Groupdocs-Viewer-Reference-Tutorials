---
title: تقديم صور FODG وODG
linktitle: تقديم صور FODG وODG
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض صور FODG وODG إلى HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET. تعزيز التعامل مع المستندات الخاصة بك.
type: docs
weight: 15
url: /ar/net/image-rendering/render-fodg-odg-images/
---
## مقدمة
في عالم تطوير البرمجيات، يعد التعامل الفعال مع تنسيقات المستندات أمرًا بالغ الأهمية. تعد GroupDocs.Viewer for .NET أداة قوية مصممة لتبسيط عملية عرض صور FODG وODG داخل تطبيقات .NET. سيرشدك هذا البرنامج التعليمي عبر الخطوات المطلوبة لعرض هذه الصور بتنسيقات مختلفة، مثل HTML وJPG وPNG وPDF، باستخدام GroupDocs.Viewer لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1.  GroupDocs.Viewer لـ .NET: قم بتنزيل وتثبيت GroupDocs.Viewer لـ .NET من[هنا](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: تأكد من تثبيت .NET Framework على نظامك.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء
قبل البدء بالتنفيذ، قم باستيراد مساحات الأسماء الضرورية:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## الخطوة 1: تعيين دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
 يستبدل`"Your Document Directory"`باستخدام مسار الدليل الذي تريد حفظ الصور المعروضة فيه.
## الخطوة 2: تقديم إلى HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
تعرض هذه الخطوة صورة FODG إلى تنسيق HTML.
## الخطوة 3: تقديم إلى JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
هنا، يتم تقديم صورة FODG إلى تنسيق JPG.
## الخطوة 4: تقديم إلى PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
تقوم هذه الخطوة بتحويل صورة FODG إلى تنسيق PNG.
## الخطوة 5: تقديم إلى PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
وأخيرًا، يتم تحويل صورة FODG إلى تنسيق PDF.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية عرض صور FODG وODG إلى تنسيقات مختلفة باستخدام GroupDocs.Viewer لـ .NET. باتباع هذه الخطوات، يمكنك دمج إمكانات عرض المستندات بسلاسة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يتوافق GroupDocs.Viewer for .NET مع كافة إصدارات .NET Framework؟
يتوافق GroupDocs.Viewer for .NET مع نطاق واسع من إصدارات .NET Framework، بما في ذلك الإصدارات الأحدث.
### هل يمكنني عرض المستندات بشكل غير متزامن مع GroupDocs.Viewer لـ .NET؟
نعم، يوفر GroupDocs.Viewer for .NET إمكانات عرض غير متزامنة لتحسين الأداء.
### هل يدعم GroupDocs.Viewer for .NET عرض المستندات المشفرة؟
نعم، يدعم GroupDocs.Viewer for .NET عرض المستندات المشفرة باستخدام مفاتيح فك التشفير المناسبة.
### هل من الممكن تخصيص إخراج العرض باستخدام GroupDocs.Viewer لـ .NET؟
بالتأكيد، يوفر GroupDocs.Viewer for .NET خيارات تخصيص متنوعة لتخصيص مخرجات العرض وفقًا لمتطلباتك.
### هل يمكنني عرض المستندات من مواقع التخزين البعيدة باستخدام GroupDocs.Viewer لـ .NET؟
نعم، يدعم GroupDocs.Viewer for .NET عرض المستندات من مواقع التخزين المحلية والبعيدة.