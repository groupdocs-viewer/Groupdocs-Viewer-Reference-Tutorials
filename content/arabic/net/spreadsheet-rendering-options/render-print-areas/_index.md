---
title: عرض مناطق الطباعة باستخدام GroupDocs.Viewer لـ .NET
linktitle: تقديم مناطق الطباعة
second_title: GroupDocs.Viewer .NET API
description: استكشف GroupDocs.Viewer لـ .NET واعرض مناطق الطباعة بتنسيقات مختلفة للمستندات دون عناء. جرب النسخة التجريبية المجانية الآن! #GroupDocs.Viewer
type: docs
weight: 17
url: /ar/net/spreadsheet-rendering-options/render-print-areas/
---
## مقدمة
مرحبًا بك في هذا الدليل الشامل حول الاستفادة من GroupDocs.Viewer لـ .NET لعرض مناطق الطباعة في مستنداتك. إذا كنت أحد مطوري .NET وتبحث عن حل قوي لعرض المستندات، فأنت في المكان الصحيح. في هذا البرنامج التعليمي، سنرشدك خلال عملية عرض مناطق الطباعة باستخدام GroupDocs.Viewer، مما يضمن تجربة سلسة في تطبيقاتك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية بتطوير C# و.NET.
-  تم تثبيت GroupDocs.Viewer لـ .NET. يمكنك تنزيله[هنا](https://releases.groupdocs.com/viewer/net/).
- مستند نموذجي (على سبيل المثال، "SAMPLE.XLSX") في دليل المستند المحدد.
## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في كود C# الخاص بك للتنفيذ الصحيح:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: إعداد دليل المستندات
ابدأ بتحديد دليل الإخراج لصفحات HTML المقدمة:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
قم بإنشاء تنسيق لمسارات ملف الصفحة، مع دمج دليل الإخراج وعنصر نائب لرقم الصفحة:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: تهيئة GroupDocs.Viewer
قم بإنشاء مثيل لفئة Viewer باستخدام المسار إلى نموذج المستند الخاص بك:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## الخطوة 4: تكوين خيارات عرض HTML
تكوين خيارات عرض HTML، وتحديد تنسيق مسار ملف الصفحة وتمكين الخيارات لعرض مناطق الطباعة:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## الخطوة 5: تقديم الوثيقة
 استدعاء`View` طريقة عرض المستند بالخيارات المحددة:
```csharp
viewer.View(options);
```
## الخطوة 6: عرض رسالة النجاح
اطبع رسالة نجاح، تشير إلى أنه تم عرض المستند المصدر بنجاح:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية استخدام GroupDocs.Viewer لـ .NET لعرض مناطق الطباعة في مستنداتك. تفتح هذه الأداة القوية إمكانيات جديدة لعرض المستندات في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل GroupDocs.Viewer متوافق مع تنسيقات المستندات المختلفة؟
 نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF وDOCX وXLSX والمزيد. الرجوع إلى[توثيق](https://reference.groupdocs.com/viewer/net/) للحصول على قائمة كاملة.
### هل يمكنني تجربة GroupDocs.Viewer قبل إجراء عملية الشراء؟
 قطعاً! يمكنك استكشاف الأداة من خلال الإصدار التجريبي المجاني المتاح[هنا](https://releases.groupdocs.com/).
### أين يمكنني العثور على الدعم أو طلب المساعدة في أي مشكلة؟
 قم بزيارة[منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9)للتواصل مع المجتمع والحصول على المساعدة.
### هل هناك خيار ترخيص مؤقت متاح؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.groupdocs.com/temporary-license/).
### أين يمكنني شراء GroupDocs.Viewer لـ .NET؟
 يمكنك إجراء عملية الشراء الخاصة بك[هنا](https://purchase.groupdocs.com/buy).