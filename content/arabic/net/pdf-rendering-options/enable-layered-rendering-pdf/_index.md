---
"description": "تعرّف على كيفية تفعيل العرض الطبقي في مستندات PDF باستخدام GroupDocs.Viewer لـ .NET. حسّن تجربة عرض المستندات بسهولة."
"linktitle": "تمكين العرض الطبقي في PDF"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تمكين العرض الطبقي في PDF"
"url": "/ar/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
---

# تمكين العرض الطبقي في PDF

## مقدمة
في هذا البرنامج التعليمي، سنتعمق في عملية تفعيل العرض الطبقي في مستندات PDF باستخدام GroupDocs.Viewer لـ .NET. يتيح العرض الطبقي عرضًا وتحريرًا محسّنين للمستندات، مما يوفر للمستخدمين تجربة عرض أكثر تفاعلية.

![تمكين العرض الطبقي في PDF باستخدام GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: تأكد من تثبيت الحزمة أو المكتبة اللازمة لاستخدام GroupDocs.Viewer لـ .NET في مشروعك.
2. Visual Studio: يجب أن يكون Visual Studio مثبتًا على نظامك لتتمكن من ترميز الأمثلة المقدمة وتنفيذها.
3. الفهم الأساسي للغة C#: يفترض هذا البرنامج التعليمي الإلمام بقواعد لغة البرمجة C# ومفاهيمها.

## استيراد مساحات الأسماء
ابدأ باستيراد المساحات المطلوبة إلى مشروعك:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
تأكد من تحديد مسار الدليل الذي تريد حفظ الإخراج المقدم فيه.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
تحدد هذه الخطوة تنسيق مسارات الملفات الخاصة بالصفحات الفردية في الناتج المقدم. `{0}` هو عنصر نائب لرقم الصفحة.
## الخطوة 3: تمكين العرض الطبقي
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
هنا، نقوم بإنشاء `Viewer` الكائن وتحديد مستند PDF المراد معالجته. ثم نقوم بتكوينه `HtmlViewOptions` مع تنسيق مسار ملف الصفحة المحدد. عن طريق ضبط `EnableLayeredRendering` الممتلكات إلى `true` في `PdfOptions`، نقوم بتمكين العرض الطبقي لمستند PDF.
## الخطوة 4: عرض دليل الإخراج
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
وأخيرًا، نقوم بطباعة رسالة تشير إلى نجاح عرض المستند المصدر ونطالب المستخدم بالتحقق من الإخراج في الدليل المحدد.

## خاتمة
يُحسّن تفعيل العرض الطبقي في مستندات PDF باستخدام GroupDocs.Viewer لـ .NET من إمكانية عرض المستندات، مما يوفر للمستخدمين تجربة أكثر ثراءً وتفاعلية. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج هذه الميزة بسلاسة في تطبيقات .NET.
## الأسئلة الشائعة
### ما هو العرض الطبقي في مستندات PDF؟
يتيح العرض الطبقي فصل المكونات المختلفة ومعالجتها داخل مستند PDF، مما يتيح المشاهدة التفاعلية وتجربة مستخدم محسنة.
### هل يمكنني تخصيص دليل الإخراج للمستندات المقدمة؟
نعم، يمكنك تحديد أي مسار دليل للإخراج وفقًا لمتطلباتك.
### هل يدعم GroupDocs.Viewer تنسيقات ملفات أخرى إلى جانب PDF؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات بما في ذلك Word وExcel وPowerPoint والمزيد.
### هل GroupDocs.Viewer متوافق مع .NET Core؟
نعم، GroupDocs.Viewer متوافق مع بيئات .NET Framework و.NET Core.
### أين يمكنني العثور على الدعم أو المساعدة الإضافية؟
يمكنك زيارة منتدى GroupDocs.Viewer لأي استفسارات أو مساعدة بخصوص مكتبة العارض.