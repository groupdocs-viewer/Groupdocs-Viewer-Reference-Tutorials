---
title: تقديم XML SpreadSheetML
linktitle: تقديم XML SpreadSheetML
second_title: GroupDocs.Viewer .NET API
description: استكشف العرض السلس لملفات XML SpreadSheetML بتنسيقات مختلفة باستخدام GroupDocs.Viewer لـ .NET. الاندماج بسهولة في تطبيقاتك.
type: docs
weight: 16
url: /ar/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## مقدمة
مرحبًا بك في عالم GroupDocs.Viewer لـ .NET! في هذا البرنامج التعليمي، سنرشدك خلال عرض ملفات XML SpreadSheetML بسهولة باستخدام GroupDocs.Viewer، وهي مكتبة .NET قوية. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيساعدك هذا الدليل التفصيلي خطوة بخطوة على دمج عرض XML SpreadSheetML في تطبيقاتك بسهولة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
- بيئة تطوير بدعم .NET.
-  تم تثبيت GroupDocs.Viewer لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.groupdocs.com/viewer/net/).
- فهم أساسي للبرمجة C#.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. وهذا يضمن أن لديك حق الوصول إلى الوظائف التي يوفرها GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
حدد المسار إلى دليل المستندات الخاص بك حيث سيتم حفظ الإخراج.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد مسارات ملف الإخراج
قم بإعداد المسارات الكاملة لملفات الإخراج بتنسيق HTML، وJPG، وPNG، وPDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## الخطوة 3: تحديد خيارات التحميل
حدد نوع الملف بشكل صريح كـ Excel 2003 XML SpreadSheetML لعرضه بدقة.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## الخطوة 4: التقديم إلى HTML متعدد الصفحات
استخدم خيارات عرض HTML لعرض ملف XML SpreadSheetML في مستند HTML متعدد الصفحات.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 5: تقديم إلى JPG
قم بعرض ملف XML SpreadSheetML في صورة JPG باستخدام الخيارات المحددة.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 6: تقديم إلى PNG
وبالمثل، قم بتحويل الملف إلى صورة PNG مع الخيارات المحددة.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## الخطوة 7: تقديم إلى PDF
وأخيرًا، قم بتحويل ملف XML SpreadSheetML إلى مستند PDF باستخدام الخيارات المحددة.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية عرض ملفات XML SpreadSheetML باستخدام GroupDocs.Viewer لـ .NET. عزز قدرات عرض المستندات لديك من خلال استكشاف المزيد من الميزات والخيارات التي توفرها هذه المكتبة متعددة الاستخدامات.
## الأسئلة الشائعة
### هل GroupDocs.Viewer متوافق مع تنسيقات الملفات الأخرى؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF وWord وExcel والمزيد.
### هل يمكنني تخصيص مظهر المستندات المقدمة؟
قطعاً! يقدم GroupDocs.Viewer خيارات تخصيص متنوعة، مما يسمح لك بتخصيص الإخراج وفقًا لاحتياجاتك المحددة.
### أين يمكنني العثور على دعم وموارد إضافية؟
 قم بزيارة[منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) لدعم المجتمع واستكشاف[توثيق](https://reference.groupdocs.com/viewer/net/)للحصول على معلومات مفصلة.
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.groupdocs.com/).
### كيف أحصل على ترخيص مؤقت؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.groupdocs.com/temporary-license/).