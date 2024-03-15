---
title: تقديم تخطيط واحد في رسومات CAD
linktitle: تقديم تخطيط واحد في رسومات CAD
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض تخطيط فردي في رسومات CAD باستخدام GroupDocs.Viewer لـ .NET. خطوات سهلة للتكامل السلس في تطبيقات .NET الخاصة بك.
type: docs
weight: 14
url: /ar/net/rendering-cad-drawings/render-single-layout-cad/
---
## مقدمة
في مجال تطوير .NET، يعد التعامل مع رسومات CAD وعرضها مطلبًا شائعًا. يعمل GroupDocs.Viewer for .NET على تبسيط هذه المهمة من خلال توفير حل شامل لعرض رسومات CAD داخل تطبيقات .NET. في هذا البرنامج التعليمي، سوف نتعمق في تقديم تخطيط واحد في رسومات CAD باستخدام GroupDocs.Viewer لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- الفهم الأساسي للغة البرمجة C# وإطار عمل .NET.
- تم تثبيت Visual Studio على نظامك.
-  تم تنزيل GroupDocs.Viewer لمكتبة .NET والإشارة إليها في مشروعك. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).
- الإلمام بتنسيقات ملفات CAD وبنيتها.

## استيراد مساحات الأسماء
أولاً، قم باستيراد مساحات الأسماء الضرورية إلى كود C# الخاص بك للوصول إلى وظائف GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## الخطوة 1: تحديد دليل الإخراج
حدد الدليل الذي تريد حفظ المخرجات المقدمة فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
حدد تنسيق مسار الملف لكل صفحة معروضة.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: إنشاء كائن العارض
قم بإنشاء مثيل لفئة Viewer التي يوفرها GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## الخطوة 4: تكوين خيارات عرض HTML
قم بتكوين الخيارات لعرض مخرجات HTML مع الموارد المضمنة.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## الخطوة 5: حدد اسم تخطيط CAD
حدد اسم تخطيط CAD الذي تريد عرضه.
```csharp
options.CadOptions.LayoutName = "Model";
```
## الخطوة 6: تقديم رسم CAD
قم باستدعاء طريقة العرض لكائن العارض بالخيارات المحددة.
```csharp
viewer.View(options);
```
## الخطوة 7: عرض رسالة النجاح
أبلغ المستخدم عن العرض الناجح للمستند المصدر.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
قد يكون تقديم رسومات CAD، خاصة عند التعامل مع التخطيطات، مهمة شاقة. ومع ذلك، مع GroupDocs.Viewer لـ .NET، تصبح العملية سلسة وفعالة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة تقديم تخطيط واحد في رسومات CAD داخل تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني عرض تخطيطات متعددة في وقت واحد باستخدام GroupDocs.Viewer لـ .NET؟
نعم، يدعم GroupDocs.Viewer for .NET عرض تخطيطات متعددة من رسومات CAD.
### هل يتوافق GroupDocs.Viewer مع تنسيقات ملفات CAD المختلفة؟
بالتأكيد، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات ملفات CAD، بما في ذلك DWG وDXF وDGN والمزيد.
### هل يمكنني تخصيص خيارات العرض لرسومات CAD؟
نعم، يوفر GroupDocs.Viewer خيارات شاملة لتخصيص إعدادات العرض وفقًا لمتطلباتك.
### هل تتوفر نسخة تجريبية مجانية من GroupDocs.Viewer لـ .NET؟
 نعم، يمكنك استكشاف ميزات GroupDocs.Viewer من خلال النسخة التجريبية المجانية المتاحة[هنا](https://releases.groupdocs.com/).
### أين يمكنني الحصول على دعم لـ GroupDocs.Viewer لـ .NET؟
 لأية استفسارات أو مساعدة، يمكنك زيارة منتدى GroupDocs.Viewer[هنا](https://forum.groupdocs.com/c/viewer/9).