---
title: تقديم أرقام Visio
linktitle: تقديم أرقام Visio
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض أشكال Visio باستخدام GroupDocs.Viewer لـ .NET مع هذا البرنامج الشامل. تعزيز إمكانيات عرض المستندات في تطبيقات .NET الخاصة بك.
weight: 10
url: /ar/net/rendering-visio-documents/render-visio-figures/
---
## مقدمة
في العصر الرقمي الحالي، يلعب عرض المستندات دورًا حاسمًا في التطبيقات المختلفة. سواء أكان ذلك عرض المستندات على موقع ويب أو تحويلها إلى تنسيقات مختلفة، فإن العرض الفعال أمر ضروري. يوفر GroupDocs.Viewer for .NET حلاً قويًا لعرض المستندات ومعالجتها داخل تطبيقات .NET. في هذا البرنامج التعليمي، سوف نتعمق في عرض أشكال Visio باستخدام GroupDocs.Viewer لـ .NET، مع تقسيم العملية إلى خطوات بسيطة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. إعداد البيئة: تأكد من أن لديك بيئة عمل لتطوير .NET.
2.  GroupDocs.Viewer لـ .NET: قم بتنزيل وتثبيت GroupDocs.Viewer لـ .NET من[رابط التحميل](https://releases.groupdocs.com/viewer/net/).
3. الفهم الأساسي لـ C#: تعرف على أساسيات لغة البرمجة C#.
4. نموذج مستند Visio: احصل على نموذج مستند Visio جاهز للعرض.

## استيراد مساحات الأسماء
في مشروع C# الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. التقديم إلى HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- دليل الإخراج: حدد الدليل الذي سيتم حفظ ملف HTML المعروض فيه.
- تنسيق مسار ملف الصفحة: حدد تنسيق المسار لصفحة HTML.
- تهيئة العارض: تهيئة كائن العارض بالمسار إلى مستند Visio.
- خيارات عرض HTML: تكوين الخيارات لعرض HTML.
- خيارات عرض Visio: قم بتعيين الخيارات الخاصة بعرض Visio، مثل عرض الأشكال وعرض الشكل فقط.
## 2. التقديم إلى JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- كما هو الحال مع العرض إلى HTML، قم بتكوين خيارات العرض إلى تنسيق JPG.
## 3. التقديم إلى PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- يتبع تكوين العرض إلى تنسيق PNG نمطًا مشابهًا للعرض JPG.
## 4. التقديم إلى PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- للعرض إلى PDF، قم بتكوين الخيارات الخاصة بتنسيق PDF.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية عرض أشكال Visio باستخدام GroupDocs.Viewer لـ .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك دمج إمكانات عرض المستندات بسلاسة في تطبيقات .NET الخاصة بك، مما يعزز تجربة المستخدم والإنتاجية.
## الأسئلة الشائعة
### هل يمكنني تخصيص خيارات العرض لأشكال Visio؟
نعم، يوفر GroupDocs.Viewer for .NET خيارات شاملة لتخصيص العرض، بما في ذلك عرض الشكل، وعرض الأشكال فقط، والمزيد.
### هل يعتبر GroupDocs.Viewer for .NET مناسبًا لعرض المستندات على نطاق واسع؟
بالتأكيد، تم تحسين GroupDocs.Viewer for .NET للتعامل مع عرض المستندات على نطاق واسع بكفاءة.
### هل يدعم GroupDocs.Viewer تنسيقات المستندات الأخرى بخلاف Visio؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF وMicrosoft Office وAutoCAD والمزيد.
### هل يمكنني دمج GroupDocs.Viewer في تطبيقات الويب؟
نعم، يمكن دمج GroupDocs.Viewer بسلاسة في تطبيقات الويب لعرض المستندات ومعالجتها.
### هل هناك نسخة تجريبية متاحة للاختبار قبل الشراء؟
نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من[موقع إلكتروني](https://releases.groupdocs.com/) لاختبار قدرات GroupDocs.Viewer لـ .NET.