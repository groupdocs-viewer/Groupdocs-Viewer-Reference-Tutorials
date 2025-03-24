---
title: تمكين عرض الطبقات في PDF
linktitle: تمكين عرض الطبقات في PDF
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية تمكين عرض الطبقات في مستندات PDF باستخدام GroupDocs.Viewer لـ .NET. تعزيز تجربة عرض المستندات دون عناء.
weight: 15
url: /ar/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في عملية تمكين عرض الطبقات في مستندات PDF باستخدام GroupDocs.Viewer لـ .NET. يسمح عرض الطبقات بعرض المستندات ومعالجتها بشكل محسّن، مما يوفر للمستخدمين تجربة مشاهدة أكثر تفاعلية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: تأكد من تثبيت الحزمة أو المكتبة اللازمة لاستخدام GroupDocs.Viewer لـ .NET في مشروعك.
2. Visual Studio: يجب أن يكون Visual Studio مثبتًا على نظامك لترميز الأمثلة المتوفرة وتنفيذها.
3. الفهم الأساسي لـ C#: يفترض هذا البرنامج التعليمي الإلمام بتركيب ومفاهيم لغة البرمجة C#.

## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء المطلوبة إلى مشروعك:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
تأكد من تحديد مسار الدليل حيث تريد حفظ المخرجات المقدمة.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 تقوم هذه الخطوة بتعيين تنسيق مسارات الملفات للصفحات الفردية في المخرجات المعروضة.`{0}` هو عنصر نائب لرقم الصفحة.
## الخطوة 3: تمكين عرض الطبقات
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 هنا نقوم بإنشاء`Viewer` الكائن وحدد مستند PDF المراد معالجته. نقوم بعد ذلك بتكوين`HtmlViewOptions` باستخدام تنسيق مسار ملف الصفحة المحدد. عن طريق الإعداد`EnableLayeredRendering` الملكية ل`true` في`PdfOptions`، نقوم بتمكين عرض الطبقات لمستند PDF.
## الخطوة 4: عرض دليل الإخراج
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
أخيرًا، نطبع رسالة تشير إلى نجاح عرض المستند المصدر ونطلب من المستخدم التحقق من الإخراج في الدليل المحدد.

## خاتمة
يؤدي تمكين عرض الطبقات في مستندات PDF باستخدام GroupDocs.Viewer لـ .NET إلى تحسين إمكانيات عرض المستندات، مما يوفر للمستخدمين تجربة أكثر ثراءً وتفاعلية. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج هذه الميزة بسلاسة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### ما هو عرض الطبقات في مستندات PDF؟
يسمح عرض الطبقات بفصل المكونات المختلفة ومعالجتها داخل مستند PDF، مما يتيح العرض التفاعلي وتجربة المستخدم المحسنة.
### هل يمكنني تخصيص دليل الإخراج للمستندات المقدمة؟
نعم، يمكنك تحديد أي مسار دليل للإخراج وفقًا لمتطلباتك.
### هل يدعم GroupDocs.Viewer تنسيقات الملفات الأخرى إلى جانب PDF؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات بما في ذلك Word وExcel وPowerPoint والمزيد.
### هل GroupDocs.Viewer متوافق مع .NET Core؟
نعم، GroupDocs.Viewer متوافق مع كل من بيئات .NET Framework و.NET Core.
### أين يمكنني العثور على دعم أو مساعدة إضافية؟
يمكنك زيارة منتدى GroupDocs.Viewer لأية استفسارات أو مساعدة بخصوص مكتبة العارض.