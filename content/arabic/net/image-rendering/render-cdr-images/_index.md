---
"description": "تعلّم كيفية تحويل صور CDR إلى صيغ HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET. حوّل ملفات CorelDRAW بسهولة مع هذا البرنامج التعليمي."
"linktitle": "عرض صور CDR"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض صور CDR"
"url": "/ar/net/image-rendering/render-cdr-images/"
"weight": 12
---

# عرض صور CDR

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية عرض صور CDR (CorelDRAW) باستخدام GroupDocs.Viewer لـ .NET. CDR هو تنسيق ملف مرتبط بشكل أساسي بـ CorelDRAW، وهو محرر رسومات متجهية. باستخدام GroupDocs.Viewer، يمكنك بسهولة تحويل ملفات CDR إلى صيغ مختلفة مثل HTML وJPG وPNG وPDF.

![عرض صور CDR باستخدام GroupDocs.Viewer لـ .NET](/viewer/image-rendering/render-cdr-images.png)

## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: تأكد من تثبيت GroupDocs.Viewer لـ .NET. يمكنك تنزيله من [هنا](https://releases.groupdocs.com/viewer/net/).
2. دليل المستندات: قم بإعداد الدليل الذي تريد حفظ الصور المرسومة فيه.
3. المعرفة الأساسية بلغة C#: المعرفة بلغة البرمجة C# ضرورية لفهم أمثلة التعليمات البرمجية.
## استيراد مساحات الأسماء
قبل الغوص في أمثلة التعليمات البرمجية، قم باستيراد المساحات الأساسية الضرورية في ملف C# الخاص بك:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
الآن، دعونا نقسم كل مثال إلى خطوات متعددة:
## العرض إلى HTML
1. قم بتحديد دليل الإخراج الذي تريد حفظ ملفات HTML المقدمة فيه:
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
## تقديم إلى JPG
1. تحديد تنسيق مسار الملف لملفات JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. استخدم فئة Viewer لتقديم ملف CDR إلى JPG:
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
2. استخدم فئة Viewer لتقديم ملف CDR إلى PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## تحويل إلى PDF
1. تحديد تنسيق مسار الملف لملف PDF:
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
3. اختياريًا، يمكنك تحديد خيارات العرض أو عرض صفحات محددة عن طريق تمرير معلمات إضافية إلى `viewer.View()` طريقة.
## خاتمة
تحويل صور CDR إلى صيغ مختلفة مثل HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET عملية سهلة وبسيطة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحويل ملفات CDR بكفاءة إلى صيغ مختلفة تناسب احتياجاتك.
## الأسئلة الشائعة
### هل GroupDocs.Viewer لـ .NET متوافق مع كافة إصدارات ملفات CDR؟
يدعم GroupDocs.Viewer لـ .NET عرض ملفات CDR التي تم إنشاؤها بواسطة إصدارات مختلفة من CorelDRAW.
### هل يمكنني تخصيص مخرجات الملفات المقدمة؟
نعم، يوفر GroupDocs.Viewer لـ .NET خيارات مختلفة لتخصيص الإخراج، مثل ضبط جودة الصورة، وتعيين العلامة المائية، وما إلى ذلك.
### هل يتطلب GroupDocs.Viewer لـ .NET أي تبعيات خارجية؟
لا، GroupDocs.Viewer لـ .NET عبارة عن مكتبة مستقلة ولا تتطلب أي تبعيات خارجية لعرض المستندات.
### هل هناك نسخة تجريبية متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من GroupDocs.Viewer لـ .NET من [هنا](https://releases.groupdocs.com/).
### أين يمكنني الحصول على الدعم لـ GroupDocs.Viewer لـ .NET؟
يمكنك الحصول على الدعم من منتدى مجتمع GroupDocs.Viewer [هنا](https://forum.groupdocs.com/c/viewer/9).