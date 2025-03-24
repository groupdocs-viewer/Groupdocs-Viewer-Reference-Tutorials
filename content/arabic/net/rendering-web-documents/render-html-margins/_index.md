---
title: تقديم HTML مع هوامش محددة من قبل المستخدم
linktitle: تقديم HTML مع هوامش محددة من قبل المستخدم
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض HTML بهوامش مخصصة في .NET باستخدام GroupDocs.Viewer. تعزيز عرض المستندات دون عناء.
weight: 11
url: /ar/net/rendering-web-documents/render-html-margins/
---

# تقديم HTML مع هوامش محددة من قبل المستخدم

## مقدمة
في مجال تطوير .NET، يعد عرض HTML بهوامش محددة من قبل المستخدم جانبًا مهمًا لإنشاء مستندات جذابة بصريًا. سواء أكان الأمر يتعلق بضبط الهوامش لموقع ويب أو تكوين تخطيطات الطباعة، فإن التحكم الدقيق في الهوامش يعزز العرض العام للمحتوى. في هذا البرنامج التعليمي، سوف نتعمق في استخدام GroupDocs.Viewer لـ .NET لتحقيق هذه الوظيفة بسلاسة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1.  GroupDocs.Viewer لـ .NET: قم بتثبيت GroupDocs.Viewer لمكتبة .NET. يمكنك تنزيله من[موقع إلكتروني](https://releases.groupdocs.com/viewer/net/).
2. بيئة .NET: تمتع ببيئة عمل لتطوير .NET.
3. مستند HTML: قم بإعداد مستند HTML الذي تريد عرضه بهوامش مخصصة.

## استيراد مساحات الأسماء
قبل البدء، تأكد من استيراد مساحات الأسماء الضرورية:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## الخطوة 1: تعيين دليل الإخراج
حدد الدليل الذي تريد حفظ الملفات المقدمة فيه:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
قم بتعيين تنسيق مسارات الملفات للصفحات المعروضة:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "html_render_margins_page_{0}.jpg");
```
## الخطوة 3: ضبط الهوامش لعرض JPG
تكوين الهوامش لعرض تنسيق HTML إلى JPG:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## الخطوة 4: ضبط الهوامش لعرض PNG
وبالمثل، اضبط الهوامش لعرض تنسيق HTML إلى PNG:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## الخطوة 5: ضبط الهوامش لعرض PDF
لعرض PDF، قم بتعيين الهوامش وفقًا لذلك:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```

## خاتمة
يتيح تخصيص الهوامش عند عرض مستندات HTML في .NET باستخدام GroupDocs.Viewer للمطورين تخصيص عرض المحتوى بدقة. باتباع هذا البرنامج التعليمي، يمكنك ضبط الهوامش بسهولة لتنسيقات إخراج JPG أو PNG أو PDF، مما يعزز المظهر المرئي وسهولة قراءة مستنداتك.
## الأسئلة الشائعة
### هل يتوافق GroupDocs.Viewer for .NET مع تنسيقات HTML المختلفة؟
يدعم GroupDocs.Viewer نطاقًا واسعًا من تنسيقات HTML، مما يضمن التوافق مع مستندات HTML المتنوعة.
### هل يمكنني ضبط الهوامش ديناميكيًا بناءً على محتوى المستند؟
نعم، يمكنك ضبط الهوامش برمجيًا استنادًا إلى خصائص المستند أو تفضيلات المستخدم.
### هل هناك أي قيود على تعديلات الهامش؟
يوفر GroupDocs.Viewer المرونة في تعديلات الهامش، مما يسمح بالتخصيص ضمن حدود معقولة.
### هل يدعم GroupDocs.Viewer تنسيقات الإخراج الأخرى بخلاف JPG وPNG وPDF؟
نعم، يدعم GroupDocs.Viewer العرض بتنسيقات مختلفة، بما في ذلك TIFF وSVG والمزيد.
### كيف يمكنني طلب المزيد من المساعدة أو الإبلاغ عن المشكلات المتعلقة بـ GroupDocs.Viewer؟
 يمكنك زيارة منتدى GroupDocs.Viewer[هنا](https://forum.groupdocs.com/c/viewer/9) للدعم والمناقشات.