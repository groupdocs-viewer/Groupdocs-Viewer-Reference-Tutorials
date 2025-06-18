---
"description": "اكتشف قوة Groupdocs.Viewer لـ .NET في عرض ملفات Numbers بسلاسة. حوّلها إلى HTML وJPG وPNG وPDF بسهولة."
"linktitle": "أرقام العرض"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "أرقام العرض"
"url": "/ar/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# أرقام العرض

## مقدمة
مرحبًا بكم في هذا الدليل التعليمي خطوة بخطوة لعرض ملفات Numbers باستخدام Groupdocs.Viewer لـ .NET. سواءً كنت مطورًا محترفًا أو مبتدئًا، سيرشدك هذا الدليل خلال عملية تحويل مستندات Numbers إلى صيغ مختلفة. يُعد Groupdocs.Viewer لـ .NET أداة فعّالة تتيح لك دمج إمكانيات عرض المستندات بسلاسة في تطبيقات .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- معرفة عملية بتطوير C# و.NET.
- تم تثبيت مكتبة Groupdocs.Viewer لـ .NET. يمكنك تنزيلها. [هنا](https://releases.groupdocs.com/viewer/net/).
- مسار دليل المستند الخاص بك حيث سيتم حفظ ملفات الإخراج.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، تأكد من استيراد المساحات الأساسية اللازمة لاستخدام مكتبة Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: إعداد دليل الإخراج
قبل البدء بالمعالجة، حدد مجلد الإخراج الذي ستُحفظ فيه الملفات المُحوّلة. استبدل "مجلد مستنداتك" بالمسار الفعلي:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: عرض HTML متعدد الصفحات
استخدم الكود التالي لتحويل ملف Numbers إلى HTML متعدد الصفحات:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 3: تقديم إلى JPG
قم بتحويل ملف الأرقام إلى صيغة JPG باستخدام الكود التالي:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 4: التقديم إلى PNG
قم بتحويل ملف الأرقام إلى صيغة PNG باستخدام الكود التالي:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 5: تقديم إلى PDF
وأخيرًا، قم بتحويل ملف الأرقام إلى صيغة PDF باستخدام الكود التالي:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
تهانينا! لقد نجحت في عرض ملفات Numbers بتنسيقات مختلفة باستخدام Groupdocs.Viewer لـ .NET.
## خاتمة
في هذا البرنامج التعليمي، تناولنا أساسيات عرض ملفات Numbers باستخدام Groupdocs.Viewer لـ .NET. توفر هذه المكتبة القوية تكاملاً سلسًا لعرض المستندات وتحويلها في تطبيقات .NET.
## الأسئلة الشائعة
### هل يمكنني استخدام Groupdocs.Viewer لـ .NET مع أنواع المستندات الأخرى؟
نعم، يدعم Groupdocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك Word وExcel وPDF والمزيد.
### هل يتوفر ترخيص مؤقت لأغراض الاختبار؟
نعم يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.groupdocs.com/temporary-license/) للاختبار.
### أين يمكنني العثور على الدعم لـ Groupdocs.Viewer لـ .NET؟
قم بزيارة [منتدى Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) للحصول على المساعدة والمناقشات.
### كيف يمكنني شراء النسخة الكاملة من Groupdocs.Viewer لـ .NET؟
يمكنك شراء النسخة الكاملة [هنا](https://purchase.groupdocs.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك استكشاف النسخة التجريبية المجانية [هنا](https://releases.groupdocs.com/).