---
"description": "أتقن عرض مستندات MS Project باستخدام GroupDocs.Viewer لـ .NET. عرض الملاحظات، وضبط وحدات الوقت، واستكشاف تنسيقات الإخراج المختلفة بسهولة."
"linktitle": "تقديم الملاحظات وضبط وحدات الوقت (MS Project)"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تقديم الملاحظات وضبط وحدات الوقت (MS Project)"
"url": "/ar/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# تقديم الملاحظات وضبط وحدات الوقت (MS Project)

## مقدمة
GroupDocs.Viewer لـ .NET هي واجهة برمجة تطبيقات فعّالة لعرض المستندات، تُمكّن المطورين من عرض ومعالجة تنسيقات المستندات المختلفة ضمن تطبيقات .NET الخاصة بهم. في هذا البرنامج التعليمي، سنركز على عرض الملاحظات وضبط وحدات الوقت خصيصًا لمستندات MS Project.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: تأكد من تنزيل مكتبة GroupDocs.Viewer لـ .NET وتثبيتها. يمكنك تنزيلها من [هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: قم بإعداد بيئة التطوير المفضلة لديك مع دعم .NET.
3. مستند MS Project: احصل على مستند MS Project نموذجي جاهز للاختبار.
## استيراد مساحات الأسماء
أولاً، دعنا نستورد مساحات الأسماء الضرورية للبدء في عرض مستندات MS Project:
## الخطوة 1: استيراد مساحات الأسماء
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
الآن بعد أن قمنا باستيراد مساحات الأسماء المطلوبة، دعنا نقسم كل مثال إلى خطوات متعددة للحصول على فهم شامل.
## تحويل مستند MS Project إلى HTML
لتحويل مستند MS Project إلى تنسيق HTML مع الملاحظات المضمنة، اتبع الخطوات التالية:
### الخطوة 2: تعيين دليل الإخراج وتنسيق الملف
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### الخطوة 3: تهيئة كائن العارض وتعيين الخيارات
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### الخطوة 4: تحويل المستند إلى HTML
```csharp
viewer.View(options);
```
## تحويل مستند MS Project إلى تنسيقات الصور
يمكنك أيضًا تحويل مستندات MS Project إلى صيغ صور مثل JPG وPNG. إليك الطريقة:
### الخطوة 5: تعيين دليل الإخراج وتنسيق الملف لـ JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### الخطوة 6: تهيئة كائن العارض وتعيين خيارات JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### الخطوة 7: تحويل المستند إلى JPG
```csharp
viewer.View(options);
```
كرر الخطوات المماثلة لعرض الصور بتنسيق PNG وغيره من تنسيقات الصور.
## تحويل مستند MS Project إلى PDF
لتحويل مستند MS Project إلى تنسيق PDF، اتبع الخطوات التالية:
### الخطوة 8: تعيين دليل الإخراج وتنسيق الملف لملف PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### الخطوة 9: تهيئة كائن العارض وتعيين خيارات PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### الخطوة 10: تحويل المستند إلى PDF
```csharp
viewer.View(options);
```

## خاتمة
تهانينا! لقد نجحت في تعلم كيفية عرض مستندات MS Project وضبط وحدات الوقت باستخدام GroupDocs.Viewer لـ .NET. استخدم هذه المعرفة في مشاريعك لتحسين إمكانية عرض المستندات.
## الأسئلة الشائعة
### هل يمكنني تقديم مستندات MS Project إلى تنسيقات أخرى غير HTML والصور وPDF؟
نعم، يدعم GroupDocs.Viewer لـ .NET العرض بتنسيقات مختلفة مثل DOCX وXLSX وPPTX والمزيد.
### هل هناك نسخة تجريبية متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.groupdocs.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ GroupDocs.Viewer لـ .NET؟
يزور [هذا الرابط](https://purchase.groupdocs.com/temporary-license/) للحصول على ترخيص مؤقت.
### أين يمكنني العثور على الوثائق الخاصة بـ GroupDocs.Viewer لـ .NET؟
راجع الوثائق [هنا](https://tutorials.groupdocs.com/viewer/net/).
### أين يمكنني الحصول على الدعم أو طرح الأسئلة المتعلقة بـ GroupDocs.Viewer لـ .NET؟
يمكنك زيارة منتدى الدعم [هنا](https://forum.groupdocs.com/c/viewer/9).