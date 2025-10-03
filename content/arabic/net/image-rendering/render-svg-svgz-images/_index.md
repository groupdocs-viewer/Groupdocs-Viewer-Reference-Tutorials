---
"description": "تعرّف على كيفية عرض صور SVG وSVGZ باستخدام GroupDocs.Viewer لـ .NET. حوّل الرسومات المتجهة إلى HTML وJPG وPNG وPDF بسهولة."
"linktitle": "عرض صور SVG وSVGZ"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض صور SVG وSVGZ"
"url": "/ar/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# عرض صور SVG وSVGZ

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية عرض صور SVG وSVGZ باستخدام GroupDocs.Viewer لـ .NET. GroupDocs.Viewer لـ .NET هي واجهة برمجة تطبيقات فعّالة لعرض المستندات، تُمكّن المطورين من عرض تنسيقات مستندات متنوعة في تطبيقات .NET الخاصة بهم. يُعدّ SVG وSVGZ تنسيقات صور شائعة الاستخدام في الرسومات المتجهة، وباستخدام GroupDocs.Viewer لـ .NET، يمكنك عرضها بسهولة بتنسيقات إخراج مختلفة مثل HTML وJPG وPNG وPDF.

![عرض صور SVG وSVGZ باستخدام GroupDocs.Viewer لـ .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من تثبيت المتطلبات الأساسية التالية وإعدادها:
1. GroupDocs.Viewer لـ .NET: قم بتنزيل GroupDocs.Viewer لـ .NET وتثبيته من [هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: تأكد من أن لديك بيئة تطوير عمل لتطوير .NET، مثل Visual Studio.
3. ملف SVGZ نموذجي: احصل على ملف SVGZ نموذجي جاهز للاختبار.

## استيراد مساحات الأسماء
قبل أن نتعمق في الكود، دعنا نستورد مساحات الأسماء الضرورية:
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

## الخطوة 2: تحويل SVGZ إلى JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## الخطوة 3: تحويل SVGZ إلى PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## الخطوة 4: تحويل SVGZ إلى PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية عرض صور SVG وSVGZ باستخدام GroupDocs.Viewer لـ .NET. بخطوات بسيطة، يمكنك تحويل صور SVGZ إلى صيغ إخراج متنوعة مثل HTML وJPG وPNG وPDF، مما يجعلها سهلة الوصول والعرض في بيئات مختلفة.
## الأسئلة الشائعة
### هل يمكن لـ GroupDocs.Viewer عرض تنسيقات صور أخرى؟
نعم، يدعم GroupDocs.Viewer عرض تنسيقات الصور المختلفة بما في ذلك PNG، JPEG، BMP، TIFF، GIF، والمزيد.
### هل GroupDocs.Viewer متوافق مع .NET Core؟
نعم، GroupDocs.Viewer متوافق مع كل من .NET Framework و.NET Core.
### هل يمكنني تخصيص خيارات العرض؟
نعم، يوفر GroupDocs.Viewer خيارات عرض شاملة تسمح لك بتخصيص الناتج وفقًا لمتطلباتك.
### هل يتطلب GroupDocs.Viewer أي تبعيات لجهات خارجية؟
لا، GroupDocs.Viewer عبارة عن واجهة برمجة تطبيقات مستقلة ولا تتطلب أي تبعيات تابعة لجهات خارجية لعرض المستندات.
### هل هناك نسخة تجريبية متاحة للاختبار؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من GroupDocs.Viewer من [هنا](https://releases.groupdocs.com/) لتقييم مميزاته قبل الشراء.