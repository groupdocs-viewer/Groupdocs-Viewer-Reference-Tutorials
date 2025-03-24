---
title: أرقام التقديم
linktitle: أرقام التقديم
second_title: GroupDocs.Viewer .NET API
description: اكتشف قوة Groupdocs.Viewer لـ .NET في عرض ملفات Numbers بسلاسة. قم بالتحويل إلى HTML وJPG وPNG وPDF بسهولة.
weight: 15
url: /ar/net/spreadsheet-rendering-options/rendering-numbers/
---

# أرقام التقديم

## مقدمة
مرحبًا بك في هذا البرنامج التعليمي خطوة بخطوة حول عرض ملفات Numbers باستخدام Groupdocs.Viewer لـ .NET. سواء كنت مطورًا متمرسًا أو مبتدئًا، سيرشدك هذا الدليل خلال عملية تحويل مستندات Numbers إلى تنسيقات مختلفة. يعد Groupdocs.Viewer for .NET أداة قوية تسمح لك بدمج إمكانيات عرض المستندات في تطبيقات .NET الخاصة بك بسلاسة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية بتطوير C# و.NET.
-  تم تثبيت Groupdocs.Viewer لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.groupdocs.com/viewer/net/).
- مسار دليل المستند الخاص بك حيث سيتم حفظ ملفات الإخراج.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، تأكد من استيراد مساحات الأسماء اللازمة لاستخدام مكتبة Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: إعداد دليل الإخراج
قبل البدء في العرض، حدد دليل الإخراج حيث سيتم حفظ الملفات المحولة. استبدل "دليل المستندات الخاص بك" بالمسار الفعلي:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: التقديم إلى HTML متعدد الصفحات
استخدم التعليمة البرمجية التالية لتحويل ملف Numbers إلى ملف HTML متعدد الصفحات:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 3: تقديم إلى JPG
قم بتحويل ملف Numbers إلى تنسيق JPG بالكود التالي:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 4: تقديم إلى PNG
قم بتحويل ملف Numbers إلى تنسيق PNG باستخدام الكود التالي:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 5: تقديم إلى PDF
وأخيرًا، قم بتحويل ملف Numbers إلى تنسيق PDF باستخدام الكود التالي:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
تهانينا! لقد نجحت في تحويل ملفات Numbers إلى تنسيقات مختلفة باستخدام Groupdocs.Viewer لـ .NET.
## خاتمة
في هذا البرنامج التعليمي، تناولنا أساسيات عرض ملفات Numbers باستخدام Groupdocs.Viewer لـ .NET. توفر هذه المكتبة القوية تكاملاً سلسًا لعرض المستندات وتحويلها في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني استخدام Groupdocs.Viewer لـ .NET مع أنواع المستندات الأخرى؟
نعم، يدعم Groupdocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك Word وExcel وPDF والمزيد.
### هل الترخيص المؤقت متاح لأغراض الاختبار؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.groupdocs.com/temporary-license/) للاختبار.
### أين يمكنني العثور على دعم لـ Groupdocs.Viewer لـ .NET؟
 قم بزيارة[مستندات المجموعة.منتدى المشاهد](https://forum.groupdocs.com/c/viewer/9) للمساعدة والمناقشات.
### كيف يمكنني شراء الإصدار الكامل من Groupdocs.Viewer لـ .NET؟
 يمكنك شراء النسخة الكاملة[هنا](https://purchase.groupdocs.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.groupdocs.com/).