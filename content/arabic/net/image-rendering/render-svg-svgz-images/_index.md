---
title: عرض صور SVG وSVGZ
linktitle: عرض صور SVG وSVGZ
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض صور SVG وSVGZ باستخدام GroupDocs.Viewer لـ .NET. قم بتحويل الرسومات المتجهة إلى HTML وJPG وPNG وPDF بسهولة.
weight: 16
url: /ar/net/image-rendering/render-svg-svgz-images/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية عرض صور SVG وSVGZ باستخدام GroupDocs.Viewer لـ .NET. يعد GroupDocs.Viewer for .NET واجهة برمجة تطبيقات قوية لعرض المستندات والتي تمكن المطورين من عرض تنسيقات المستندات المختلفة في تطبيقات .NET الخاصة بهم. يعد SVG وSVGZ من تنسيقات الصور الشائعة المستخدمة للرسومات المتجهة، ومع GroupDocs.Viewer لـ .NET، يمكنك بسهولة تحويلها إلى تنسيقات إخراج مختلفة مثل HTML وJPG وPNG وPDF.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من تثبيت المتطلبات الأساسية التالية وإعدادها:
1.  GroupDocs.Viewer لـ .NET: قم بتنزيل وتثبيت GroupDocs.Viewer لـ .NET من[هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: تأكد من أن لديك بيئة تطوير عمل لتطوير .NET، مثل Visual Studio.
3. نموذج ملف SVGZ: احصل على نموذج ملف SVGZ جاهز للاختبار.

## استيراد مساحات الأسماء
قبل أن نتعمق في الكود، فلنستورد مساحات الأسماء الضرورية:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## الخطوة 1: تحويل SVGZ إلى HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## الخطوة 2: تقديم SVGZ إلى JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## الخطوة 3: تقديم SVGZ إلى PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## الخطوة 4: تقديم SVGZ إلى PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية عرض صور SVG وSVGZ باستخدام GroupDocs.Viewer لـ .NET. من خلال بضع خطوات بسيطة، يمكنك تحويل صور SVGZ إلى تنسيقات إخراج مختلفة مثل HTML، وJPG، وPNG، وPDF، مما يجعلها قابلة للوصول والعرض في بيئات مختلفة.
## الأسئلة الشائعة
### هل يمكن لـ GroupDocs.Viewer عرض تنسيقات صور أخرى؟
نعم، يدعم GroupDocs.Viewer عرض تنسيقات الصور المختلفة بما في ذلك PNG وJPEG وBMP وTIFF وGIF والمزيد.
### هل GroupDocs.Viewer متوافق مع .NET Core؟
نعم، GroupDocs.Viewer متوافق مع كل من .NET Framework و.NET Core.
### هل يمكنني تخصيص خيارات العرض؟
نعم، يوفر GroupDocs.Viewer خيارات عرض شاملة تسمح لك بتخصيص المخرجات وفقًا لمتطلباتك.
### هل يتطلب GroupDocs.Viewer أي تبعيات لجهة خارجية؟
لا، GroupDocs.Viewer عبارة عن واجهة برمجة تطبيقات مستقلة ولا تتطلب أي تبعيات لجهة خارجية لعرض المستندات.
### هل هناك نسخة تجريبية متاحة للاختبار؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من GroupDocs.Viewer من[هنا](https://releases.groupdocs.com/) لتقييم ميزاته قبل إجراء عملية الشراء.