---
"description": "تعرّف على كيفية عرض HTML بهوامش مخصصة في .NET باستخدام GroupDocs.Viewer. حسّن عرض المستندات بسهولة."
"linktitle": "عرض HTML باستخدام الهوامش المحددة من قبل المستخدم"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض HTML باستخدام الهوامش المحددة من قبل المستخدم"
"url": "/ar/net/rendering-web-documents/render-html-margins/"
"weight": 11
---

# عرض HTML باستخدام الهوامش المحددة من قبل المستخدم

## مقدمة
في مجال تطوير .NET، يُعدّ عرض HTML بهوامش مُحددة من قِبل المستخدم جانبًا أساسيًا لإنشاء مستندات جذابة بصريًا. سواءً كان الأمر يتعلق بتعديل هوامش موقع ويب أو تهيئة تخطيطات الطباعة، فإن التحكم الدقيق في الهوامش يُحسّن العرض العام للمحتوى. في هذا البرنامج التعليمي، سنتعمق في استخدام GroupDocs.Viewer لـ .NET لتحقيق هذه الوظيفة بسلاسة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: ثبّت مكتبة GroupDocs.Viewer لـ .NET. يمكنك تنزيلها من [موقع إلكتروني](https://releases.groupdocs.com/viewer/net/).
2. بيئة .NET: احصل على بيئة عمل لتطوير .NET.
3. مستند HTML: قم بإعداد مستند HTML الذي تريد عرضه بهوامش مخصصة.

## استيراد مساحات الأسماء
قبل أن تبدأ، تأكد من استيراد مساحات الأسماء الضرورية:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## الخطوة 1: تعيين دليل الإخراج
قم بتحديد الدليل الذي تريد حفظ الملفات المقدمة فيه:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
تعيين تنسيق مسارات الملفات للصفحات المقدمة:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "html_render_margins_page_{0}.jpg");
```
## الخطوة 3: ضبط الهوامش لعرض JPG
تكوين الهوامش لعرض HTML بتنسيق JPG:
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
وبالمثل، قم بتعديل الهوامش لتحويل HTML إلى تنسيق PNG:
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
لعرض ملفات PDF، اضبط الهوامش وفقًا لذلك:
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
يتيح تخصيص الهوامش عند عرض مستندات HTML في .NET باستخدام GroupDocs.Viewer للمطورين تخصيص عرض المحتوى بدقة. باتباع هذا الدليل، يمكنك بسهولة تعديل الهوامش لصيغ الإخراج JPG أو PNG أو PDF، مما يُحسّن المظهر العام وسهولة قراءة مستنداتك.
## الأسئلة الشائعة
### هل GroupDocs.Viewer لـ .NET متوافق مع تنسيقات HTML المختلفة؟
يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات HTML، مما يضمن التوافق مع مستندات HTML المختلفة.
### هل يمكنني تعديل الهوامش بشكل ديناميكي استنادًا إلى محتوى المستند؟
نعم، يمكنك تعديل الهوامش برمجيًا استنادًا إلى خصائص المستند أو البرامج التعليمية للمستخدم.
### هل هناك أية قيود على تعديلات الهامش؟
يوفر GroupDocs.Viewer المرونة في تعديلات الهامش، مما يسمح بالتخصيص ضمن حدود معقولة.
### هل يدعم GroupDocs.Viewer تنسيقات إخراج أخرى غير JPG و PNG و PDF؟
نعم، يدعم GroupDocs.Viewer العرض بتنسيقات مختلفة، بما في ذلك TIFF وSVG والمزيد.
### كيف يمكنني الحصول على مزيد من المساعدة أو الإبلاغ عن المشكلات المتعلقة بـ GroupDocs.Viewer؟
يمكنك زيارة منتدى GroupDocs.Viewer [هنا](https://forum.groupdocs.com/c/viewer/9) للدعم والمناقشات.