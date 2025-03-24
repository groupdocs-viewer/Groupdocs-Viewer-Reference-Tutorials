---
title: ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني
linktitle: ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني إلى PDF باستخدام GroupDocs.Viewer لـ .NET. تعزيز كفاءة عرض المستندات.
weight: 10
url: /ar/net/rendering-email-messages/adjust-page-size-email/
---
## مقدمة
في مجال تطوير .NET، يوفر GroupDocs.Viewer حلاً شاملاً لعرض تنسيقات المستندات المختلفة، بما في ذلك رسائل البريد الإلكتروني. يركز هذا البرنامج التعليمي على ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني بتنسيق PDF باستخدام GroupDocs.Viewer لـ .NET. باتباع الخطوات الموضحة في هذا الدليل، ستتعلم كيفية التعامل مع حجم الصفحة بسلاسة لتلبية متطلباتك المحددة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. تم تثبيت GroupDocs.Viewer لـ .NET
 تأكد من تثبيت GroupDocs.Viewer for .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).
### 2. الفهم الأساسي لتطوير .NET
تعرف على أساسيات تطوير .NET، بما في ذلك برمجة C# ومعالجة الملفات.
### 3. IDE (بيئة التطوير المتكاملة)
قم بتثبيت IDE مثل Visual Studio لكتابة وتنفيذ تعليمات NET البرمجية.

## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم باستيراد مساحات الأسماء الضرورية للاستفادة من وظائف GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## الخطوة 1: تعيين دليل الإخراج
حدد الدليل الذي سيتم حفظ ملف PDF الناتج فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد مسار الملف
قم بدمج دليل الإخراج مع اسم ملف الإخراج.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## الخطوة 3: تهيئة كائن العارض
قم بإنشاء مثيل لفئة Viewer وحدد مسار ملف رسالة البريد الإلكتروني.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## الخطوة 4: تكوين خيارات عرض PDF
قم بإنشاء مثيل لـ PdfViewOptions وقم بتعيين مسار ملف الإخراج.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## الخطوة 5: ضبط حجم الصفحة
قم بتعديل خاصية حجم الصفحة في EmailOptions لـ PdfViewOptions.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## الخطوة 6: تقديم الوثيقة
استدعاء طريقة العرض لكائن العارض، بتمرير PdfViewOptions الذي تم تكوينه.
```csharp
viewer.View(options);
```
## الخطوة 7: عرض رسالة النجاح
أبلغ المستخدم بالعرض الناجح ودليل الإخراج.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
في الختام، يوضح هذا البرنامج التعليمي كيفية ضبط حجم الصفحة عند عرض رسائل البريد الإلكتروني بتنسيق PDF باستخدام GroupDocs.Viewer لـ .NET. باتباع هذه الإرشادات خطوة بخطوة، يمكنك التعامل بكفاءة مع أحجام الصفحات لتلبية متطلباتك المحددة، وتعزيز عرض المستندات وإمكانيات الإدارة داخل تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يتوافق GroupDocs.Viewer مع تنسيقات رسائل البريد الإلكتروني المختلفة؟
يدعم GroupDocs.Viewer عرض تنسيقات رسائل البريد الإلكتروني المختلفة، بما في ذلك MSG وEML.
### هل يمكنني تخصيص حجم الصفحة وفقًا لتفضيلاتي؟
نعم، يمكنك ضبط حجم الصفحة باستخدام GroupDocs.Viewer's PdfViewOptions، مما يوفر المرونة في عرض المستندات.
### هل يوفر GroupDocs.Viewer الدعم لتنسيقات المستندات الأخرى؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF وMicrosoft Office والصور والمزيد.
### هل GroupDocs.Viewer مناسب للتطبيقات على مستوى المؤسسة؟
بالتأكيد، يوفر GroupDocs.Viewer وظائف قوية مناسبة لكل من التطبيقات الصغيرة الحجم وعلى مستوى المؤسسات، مما يضمن كفاءة عرض المستندات وإدارتها.
### أين يمكنني طلب المساعدة أو الدعم الإضافي بخصوص GroupDocs.Viewer؟
 يمكنك زيارة منتدى GroupDocs.Viewer[هنا](https://forum.groupdocs.com/c/viewer/9) لطلب المساعدة وطرح الأسئلة والتفاعل مع المجتمع.