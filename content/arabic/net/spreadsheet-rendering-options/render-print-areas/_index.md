---
"description": "استكشف GroupDocs.Viewer لـ .NET، واعرض مساحات الطباعة بسهولة بتنسيقات مستندات متنوعة. جرّب النسخة التجريبية المجانية الآن!"
"linktitle": "عرض مناطق الطباعة"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض مناطق الطباعة باستخدام GroupDocs.Viewer لـ .NET"
"url": "/ar/net/spreadsheet-rendering-options/render-print-areas/"
"weight": 17
---

# عرض مناطق الطباعة باستخدام GroupDocs.Viewer لـ .NET

## مقدمة
مرحبًا بكم في هذا الدليل الشامل حول استخدام GroupDocs.Viewer لـ .NET لعرض مساحات الطباعة في مستنداتكم. إذا كنتم مطوري .NET وتبحثون عن حل فعّال لعرض المستندات، فأنتم في المكان المناسب. في هذا البرنامج التعليمي، سنشرح لكم عملية عرض مساحات الطباعة باستخدام GroupDocs.Viewer، لضمان تجربة سلسة في تطبيقاتكم.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- معرفة عملية بتطوير C# و.NET.
- تم تثبيت GroupDocs.Viewer لـ .NET. يمكنك تنزيله [هنا](https://releases.groupdocs.com/viewer/net/).
- مستند نموذجي (على سبيل المثال، "SAMPLE.XLSX") في دليل المستندات المحدد.
## استيراد مساحات الأسماء
تأكد من استيراد المساحات الأساسية اللازمة في كود C# الخاص بك للتنفيذ السليم:
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
إنشاء تنسيق لمسارات ملفات الصفحات، من خلال الجمع بين دليل الإخراج وعنصر نائب لرقم الصفحة:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: تهيئة GroupDocs.Viewer
قم بإنشاء فئة Viewer باستخدام المسار إلى مستند العينة الخاص بك:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## الخطوة 4: تكوين خيارات عرض HTML
قم بتكوين خيارات عرض HTML، وتحديد تنسيق مسار ملف الصفحة وتمكين الخيارات لعرض مناطق الطباعة:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## الخطوة 5: تقديم المستند
استدعاء `View` الطريقة لعرض المستند بالخيارات المحددة:
```csharp
viewer.View(options);
```
## الخطوة 6: عرض رسالة النجاح
اطبع رسالة نجاح تشير إلى أن المستند المصدر تم عرضه بنجاح:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية استخدام GroupDocs.Viewer لـ .NET لعرض مساحات الطباعة في مستنداتك. تتيح لك هذه الأداة الفعّالة إمكانيات جديدة لعرض المستندات في تطبيقات .NET.
## الأسئلة الشائعة
### هل GroupDocs.Viewer متوافق مع تنسيقات المستندات المختلفة؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF وDOCX وXLSX وغيرها. راجع [التوثيق](https://tutorials.groupdocs.com/viewer/net/) للحصول على القائمة الكاملة.
### هل يمكنني تجربة GroupDocs.Viewer قبل إجراء عملية شراء؟
بالتأكيد! يمكنك استكشاف الأداة من خلال نسخة تجريبية مجانية متاحة. [هنا](https://releases.groupdocs.com/).
### أين يمكنني العثور على الدعم أو طلب المساعدة لأية مشاكل؟
قم بزيارة [منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) للتواصل مع المجتمع والحصول على المساعدة.
### هل يتوفر خيار الترخيص المؤقت؟
نعم يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.groupdocs.com/temporary-license/).
### أين يمكنني شراء GroupDocs.Viewer لـ .NET؟
يمكنك إجراء عملية الشراء الخاصة بك [هنا](https://purchase.groupdocs.com/buy).