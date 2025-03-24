---
title: الوجه وتدوير الصفحات
linktitle: الوجه وتدوير الصفحات
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية دمج Groupdocs.Viewer for .NET في تطبيقاتك لعرض المستندات وقلبها وتدويرها بسلاسة.
weight: 12
url: /ar/net/rendering-options/flip-rotate-pages/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في وظائف Groupdocs.Viewer لـ .NET، مع التركيز بشكل خاص على تقليب الصفحات وتدويرها. يعد Groupdocs.Viewer for .NET أداة قوية مصممة لعرض المستندات بتنسيقات مختلفة داخل تطبيقات .NET. سواء كنت تقوم بتطوير نظام إدارة المستندات أو تحتاج إلى دمج إمكانات عرض المستندات في برنامجك، فإن Groupdocs.Viewer for .NET يوفر حلاً فعالاً.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من إعداد المتطلبات الأساسية التالية:
### تثبيت Groupdocs.Viewer لـ .NET
 لاستخدام Groupdocs.Viewer لـ .NET، تحتاج إلى تثبيت الحزمة عبر NuGet Package Manager. يمكنك العثور على تعليمات التثبيت التفصيلية في[توثيق](https://tutorials.groupdocs.com/viewer/net/).

## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء اللازمة في مشروعك لاستخدام Groupdocs.Viewer لـ .NET بشكل فعال.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

دعنا نقسم عملية قلب الصفحات وتدويرها باستخدام Groupdocs.Viewer لـ .NET إلى خطوات بسيطة:
## الخطوة 1: تعيين دليل الإخراج ومسار الملف
حدد الدليل الذي تريد حفظ ملف الإخراج فيه وحدد مسار ملف الإخراج.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## الخطوة 2: تهيئة كائن العارض
قم بإنشاء مثيل لفئة العارض عن طريق تمرير المسار إلى المستند الذي تريد عرضه.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## الخطوة 3: تكوين خيارات العرض
قم بإعداد خيارات العرض، مثل تحديد تنسيق ملف الإخراج وأي إعدادات إضافية مثل تدوير الصفحة.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## الخطوة 4: تقديم الوثيقة
قم باستدعاء طريقة العرض لكائن العارض وتمرير خيارات العرض.
```csharp
viewer.View(viewOptions);
```
## الخطوة 5: عرض رسالة النجاح
أبلغ المستخدم بأن المستند قد تم تقديمه بنجاح وحدد دليل الإخراج للتحقق منه.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
في الختام، يوفر Groupdocs.Viewer for .NET إمكانات قوية لعرض المستندات، بما في ذلك تقليب الصفحات وتدويرها. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج هذه الميزات بسلاسة في تطبيقات .NET الخاصة بك، مما يعزز تجارب عرض المستندات للمستخدمين.
## الأسئلة الشائعة
### هل يتوافق Groupdocs.Viewer for .NET مع كافة تنسيقات المستندات؟
نعم، يدعم Groupdocs.Viewer for .NET نطاقًا واسعًا من تنسيقات المستندات، بما في ذلك DOCX وPDF وPPTX والمزيد.
### هل يمكنني تخصيص خيارات العرض بما يتجاوز تقليب الصفحات وتدويرها؟
بالتأكيد، يوفر Groupdocs.Viewer for .NET خيارات تخصيص متنوعة لعرض المستندات، مما يسمح لك بتخصيص التجربة وفقًا لمتطلباتك.
### هل تتوفر نسخة تجريبية مجانية من Groupdocs.Viewer لـ .NET؟
 نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Groupdocs.Viewer لـ .NET من خلال زيارة[موقع إلكتروني](https://releases.groupdocs.com/).
### كيف يمكنني الحصول على دعم لـ Groupdocs.Viewer لـ .NET؟
 يمكنك طلب المساعدة والتفاعل مع المجتمع من خلال[منتدى Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### أين يمكنني الحصول على ترخيص مؤقت لـ Groupdocs.Viewer لـ .NET؟
 يمكن الحصول على التراخيص المؤقتة لـ Groupdocs.Viewer لـ .NET من[صفحة الشراء](https://purchase.groupdocs.com/temporary-license/).