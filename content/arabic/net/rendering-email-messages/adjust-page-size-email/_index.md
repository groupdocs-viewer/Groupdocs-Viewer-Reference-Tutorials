---
"description": "تعرّف على كيفية ضبط حجم الصفحة عند تحويل رسائل البريد الإلكتروني إلى PDF باستخدام GroupDocs.Viewer لـ .NET. حسّن كفاءة عرض المستندات."
"linktitle": "ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني"
"url": "/ar/net/rendering-email-messages/adjust-page-size-email/"
"weight": 10
---

# ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني

## مقدمة
في مجال تطوير .NET، يوفر GroupDocs.Viewer حلاً شاملاً لعرض صيغ المستندات المختلفة، بما في ذلك رسائل البريد الإلكتروني. يركز هذا البرنامج التعليمي على ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني بتنسيق PDF باستخدام GroupDocs.Viewer لـ .NET. باتباع الخطوات الموضحة في هذا الدليل، ستتعلم كيفية تعديل حجم الصفحة بسلاسة لتلبية متطلباتك الخاصة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. تم تثبيت GroupDocs.Viewer لـ .NET
تأكد من تثبيت GroupDocs.Viewer لـ .NET في بيئة التطوير لديك. يمكنك تنزيله من [هنا](https://releases.groupdocs.com/viewer/net/).
### 2. فهم أساسي لتطوير .NET
تعرف على أساسيات تطوير .NET، بما في ذلك برمجة C# ومعالجة الملفات.
### 3. بيئة التطوير المتكاملة (IDE)
قم بتثبيت IDE مثل Visual Studio لكتابة وتنفيذ كود .NET.

## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم باستيراد المساحات الأساسية اللازمة للاستفادة من وظائف GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## الخطوة 1: تعيين دليل الإخراج
قم بتحديد الدليل الذي سيتم حفظ ملف PDF الناتج فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد مسار الملف
دمج دليل الإخراج مع اسم ملف الإخراج.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## الخطوة 3: تهيئة كائن العارض
قم بإنشاء مثيل لفئة العارض وحدد مسار ملف رسالة البريد الإلكتروني.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## الخطوة 4: تكوين خيارات عرض PDF
قم بإنشاء PdfViewOptions وتعيين مسار ملف الإخراج.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## الخطوة 5: ضبط حجم الصفحة
تعديل خاصية حجم الصفحة في EmailOptions من PdfViewOptions.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## الخطوة 6: عرض المستند
استدعاء طريقة العرض لكائن العارض، وتمرير PdfViewOptions الذي تم تكوينه.
```csharp
viewer.View(options);
```
## الخطوة 7: عرض رسالة النجاح
إعلام المستخدم بنجاح عملية العرض ودليل الإخراج.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
في الختام، يوضح هذا البرنامج التعليمي كيفية ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني بتنسيق PDF باستخدام GroupDocs.Viewer لـ .NET. باتباع هذه التعليمات خطوة بخطوة، يمكنك تعديل أحجام الصفحات بكفاءة لتلبية احتياجاتك المحددة، مما يُحسّن إمكانيات عرض المستندات وإدارتها في تطبيقات .NET.
## الأسئلة الشائعة
### هل GroupDocs.Viewer متوافق مع تنسيقات رسائل البريد الإلكتروني المختلفة؟
يدعم GroupDocs.Viewer عرض تنسيقات رسائل البريد الإلكتروني المختلفة، بما في ذلك MSG وEML.
### هل يمكنني تخصيص حجم الصفحة وفقًا لدروسي التعليمية؟
نعم، يمكنك تعديل حجم الصفحة باستخدام PdfViewOptions في GroupDocs.Viewer، مما يوفر المرونة في عرض المستندات.
### هل يوفر GroupDocs.Viewer الدعم لتنسيقات المستندات الأخرى؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF، وMicrosoft Office، والصور، والمزيد.
### هل GroupDocs.Viewer مناسب لتطبيقات مستوى المؤسسة؟
بالتأكيد، يوفر GroupDocs.Viewer وظائف قوية مناسبة للتطبيقات على نطاق صغير وعلى مستوى المؤسسات، مما يضمن عرض المستندات وإدارتها بكفاءة.
### أين يمكنني الحصول على المساعدة أو الدعم الإضافي لـ GroupDocs.Viewer؟
يمكنك زيارة منتدى GroupDocs.Viewer [هنا](https://forum.groupdocs.com/c/viewer/9) لطلب المساعدة، وطرح الأسئلة، والتفاعل مع المجتمع.