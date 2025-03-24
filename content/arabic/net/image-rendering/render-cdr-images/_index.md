---
title: تقديم صور CDR
linktitle: تقديم صور CDR
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض صور CDR إلى HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET. قم بتحويل ملفات CorelDRAW بسهولة باستخدام هذا البرنامج التعليمي.
weight: 12
url: /ar/net/image-rendering/render-cdr-images/
---

# تقديم صور CDR

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية عرض صور CDR (CorelDRAW) باستخدام GroupDocs.Viewer لـ .NET. CDR هو تنسيق ملف يرتبط أساسًا بـ CorelDRAW، وهو محرر رسومات متجهة. باستخدام GroupDocs.Viewer، يمكنك بسهولة تحويل ملفات CDR إلى تنسيقات مختلفة مثل HTML وJPG وPNG وPDF.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
1.  GroupDocs.Viewer لـ .NET: تأكد من تثبيت GroupDocs.Viewer لـ .NET. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).
2. دليل المستندات: قم بإعداد الدليل الذي تريد حفظ الصور المعروضة فيه.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# ضروري لفهم أمثلة التعليمات البرمجية.
## استيراد مساحات الأسماء
قبل الغوص في أمثلة التعليمات البرمجية، قم باستيراد مساحات الأسماء الضرورية في ملف C# الخاص بك:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
الآن، دعونا نقسم كل مثال إلى خطوات متعددة:
## التقديم إلى HTML
1. حدد دليل الإخراج الذي تريد حفظ ملفات HTML المقدمة فيه:
```csharp
string outputDirectory = "Your Document Directory";
```
2. حدد تنسيق مسار الملف لملفات HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. استخدم فئة Viewer لعرض ملف CDR إلى HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## التقديم إلى JPG
1. تحديد تنسيق مسار الملف لملفات JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. استخدم فئة Viewer لعرض ملف CDR إلى JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## تقديم إلى PNG
1. تحديد تنسيق مسار الملف لملفات PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. استخدم فئة Viewer لعرض ملف CDR إلى PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## التقديم إلى PDF
1. تحديد تنسيق مسار الملف لـ PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. استخدم فئة Viewer لعرض ملف CDR إلى PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  اختياريًا، يمكنك تحديد خيارات العرض أو عرض صفحات معينة عن طريق تمرير معلمات إضافية إلى ملف`viewer.View()` طريقة.
## خاتمة
يعد عرض صور CDR بتنسيقات مختلفة مثل HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET عملية مباشرة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحويل ملفات CDR بكفاءة إلى تنسيقات مختلفة بناءً على متطلباتك.
## الأسئلة الشائعة
### هل يتوافق GroupDocs.Viewer for .NET مع كافة إصدارات ملفات CDR؟
يدعم GroupDocs.Viewer for .NET عرض ملفات CDR التي تم إنشاؤها بواسطة إصدارات مختلفة من CorelDRAW.
### هل يمكنني تخصيص مخرجات الملفات المقدمة؟
نعم، يوفر GroupDocs.Viewer for .NET خيارات متنوعة لتخصيص المخرجات، مثل ضبط جودة الصورة، وتعيين العلامة المائية، وما إلى ذلك.
### هل يتطلب GroupDocs.Viewer لـ .NET أي تبعيات خارجية؟
لا، GroupDocs.Viewer for .NET عبارة عن مكتبة مستقلة ولا تتطلب أي تبعيات خارجية لعرض المستندات.
### هل هناك إصدار تجريبي متاح لـ GroupDocs.Viewer لـ .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من GroupDocs.Viewer لـ .NET من[هنا](https://releases.groupdocs.com/).
### أين يمكنني الحصول على دعم لـ GroupDocs.Viewer لـ .NET؟
 يمكنك الحصول على الدعم من منتدى مجتمع GroupDocs.Viewer[هنا](https://forum.groupdocs.com/c/viewer/9).