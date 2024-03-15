---
title: تقديم تنسيقات CAD محددة (CF2)
linktitle: تقديم تنسيقات CAD محددة (CF2)
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض تنسيقات CAD محددة مثل CF2 إلى HTML وJPG وPNG وPDF باستخدام Groupdocs.Viewer لـ .NET.
type: docs
weight: 12
url: /ar/net/rendering-cad-drawings/render-specific-cad-formats/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية عرض تنسيقات CAD محددة باستخدام Groupdocs.Viewer لـ .NET. Groupdocs.Viewer عبارة عن واجهة برمجة تطبيقات قوية لعارض المستندات تتيح للمطورين عرض أكثر من 170 نوعًا من المستندات في تطبيقاتهم دون الحاجة إلى أي عمليات تثبيت خارجية للبرامج. على وجه التحديد، سنركز على تقديم تنسيقات CAD مثل CF2 إلى تنسيقات إخراج مختلفة مثل HTML وJPG وPNG وPDF.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Visual Studio على نظامك.
-  Groupdocs.Viewer لـ .NET SDK. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).
- المعرفة الأساسية بلغة البرمجة C#.
## استيراد مساحات الأسماء
أولاً، لنستورد مساحات الأسماء الضرورية المطلوبة لعرض تنسيقات CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
الآن، دعونا نقسم كل مثال إلى خطوات متعددة:
## تقديم CF2 إلى HTML
### الخطوة 1: تحديد دليل الإخراج حيث سيتم حفظ HTML المعروض.
```csharp
string outputDirectory = "Your Document Directory";
```
### الخطوة 2: تحديد تنسيق مسار الملف لمخرجات HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### الخطوة 3: تهيئة كائن العارض وتحديد ملف الإدخال CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // قم بتعيين خيارات العرض الإضافية إذا لزم الأمر
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## تقديم CF2 إلى JPG
### الخطوة 1: تحديد تنسيق مسار الملف لمخرجات JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### الخطوة 2: تهيئة كائن العارض وتحديد ملف الإدخال CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // قم بتعيين خيارات العرض الإضافية إذا لزم الأمر
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## تقديم CF2 إلى PNG

### الخطوة 1: تحديد تنسيق مسار الملف لمخرجات PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### الخطوة 2: تهيئة كائن العارض وتحديد ملف الإدخال CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // قم بتعيين خيارات العرض الإضافية إذا لزم الأمر
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## تقديم CF2 إلى PDF
### الخطوة 1: تحديد تنسيق مسار الملف لمخرجات PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### الخطوة 2: تهيئة كائن العارض وتحديد ملف الإدخال CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // قم بتعيين خيارات العرض الإضافية إذا لزم الأمر
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية عرض تنسيقات CAD محددة مثل CF2 باستخدام Groupdocs.Viewer لـ .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك بسهولة دمج إمكانيات عرض المستندات في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يمكن لـ Groupdocs.Viewer عرض تنسيقات CAD أخرى بخلاف CF2؟
نعم، يدعم Groupdocs.Viewer مجموعة واسعة من تنسيقات CAD، بما في ذلك DWG وDXF وDGN والمزيد.
### هل Groupdocs.Viewer مناسب لعرض المستندات في تطبيقات الويب؟
بالتأكيد، يمكن دمج Groupdocs.Viewer بسلاسة في تطبيقات الويب لعرض المستندات مباشرة في المتصفح.
### هل يتطلب Groupdocs.Viewer أي تبعيات خارجية للعرض؟
لا، Groupdocs.Viewer عبارة عن واجهة برمجة تطبيقات مستقلة ولا تتطلب أي تبعيات خارجية أو عمليات تثبيت للبرامج.
### هل يمكنني تخصيص خيارات العرض وفقًا لمتطلباتي؟
نعم، يوفر Groupdocs.Viewer خيارات عرض متنوعة يمكن تخصيصها لتلبية احتياجاتك الخاصة.
### هل هناك إصدار تجريبي متاح لـ Groupdocs.Viewer؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Groupdocs.Viewer من[هنا](https://releases.groupdocs.com/).