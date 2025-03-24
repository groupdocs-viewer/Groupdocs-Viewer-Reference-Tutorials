---
title: تعطيل تحديد النص في PDF
linktitle: تعطيل تحديد النص في PDF
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية تعطيل تحديد النص في PDF باستخدام GroupDocs.Viewer لـ .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 13
url: /ar/net/pdf-rendering-options/disable-text-selection-pdf/
---
## مقدمة
يعد GroupDocs.Viewer for .NET واجهة برمجة تطبيقات قوية لعرض المستندات تسمح للمطورين بدمج إمكانات عرض المستندات في تطبيقات .NET الخاصة بهم دون عناء. إحدى الوظائف الرئيسية التي يوفرها GroupDocs.Viewer هي القدرة على تعطيل تحديد النص في مستندات PDF. تعتبر هذه الميزة مفيدة بشكل خاص في السيناريوهات التي تحتاج فيها إلى منع المستخدمين من نسخ النص من المستندات الحساسة، مما يضمن أمان المستند وسلامته.
## المتطلبات الأساسية
قبل أن نتعمق في الدليل التفصيلي حول كيفية تعطيل تحديد النص في PDF باستخدام GroupDocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
1.  تثبيت GroupDocs.Viewer لـ .NET: تأكد من أنك قمت بتنزيل وتثبيت GroupDocs.Viewer لـ .NET من[رابط التحميل](https://releases.groupdocs.com/viewer/net/).
2. دليل المستندات: قم بإعداد دليل حيث سيتم تخزين المستندات الخاصة بك. ستحتاج إلى تحديد هذا الدليل في مقتطف الشفرة لعرض مستند PDF.

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية للوصول إلى الوظائف التي يوفرها GroupDocs.Viewer لـ .NET. وإليك كيف يمكنك القيام بذلك:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن، دعنا نقسم عملية تعطيل تحديد النص في مستند PDF باستخدام GroupDocs.Viewer لـ .NET إلى خطوات متعددة:
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
 في هذه الخطوة، استبدل`"Your Document Directory"` باستخدام مسار الدليل الذي يوجد به مستند PDF الخاص بك.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
تحدد هذه الخطوة تنسيق مسارات الملفات لصفحات HTML المعروضة. سيتم تحويل كل صفحة من مستند PDF إلى ملف HTML برقم صفحة تسلسلي.
## الخطوة 3: عرض مستند PDF مع تعطيل تحديد النص
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 يستبدل`"Path to Your PDF Document"` مع المسار الفعلي لملف PDF الخاص بك. يقوم مقتطف الكود هذا بتهيئة أ`Viewer` الكائن، ويقوم بتكوين خيارات عرض HTML لتضمين الموارد، ويعطل تحديد النص عن طريق الإعداد`RenderTextAsImage` الملكية ل`true`.
## الخطوة 4: عرض رسالة النجاح
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
بعد عرض مستند PDF، تعرض هذه الخطوة رسالة نجاح مع الدليل الذي تم تخزين صفحات HTML المعروضة فيه.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعطيل تحديد النص في مستندات PDF باستخدام GroupDocs.Viewer لـ .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك دمج هذه الميزة بسلاسة في تطبيقات .NET الخاصة بك، مما يضمن أمان المستندات وتحسين تجربة المستخدم.
## الأسئلة الشائعة
### هل يمكنني تخصيص دليل الإخراج لصفحات HTML المقدمة؟
نعم، يمكنك تحديد أي مسار دليل تريد تخزين صفحات HTML المعروضة فيه.
### هل يتوافق GroupDocs.Viewer for .NET مع إصدارات مختلفة من .NET Framework؟
نعم، يتوافق GroupDocs.Viewer for .NET مع إصدارات مختلفة من .NET Framework، بما في ذلك .NET Core و.NET Framework.
### هل يؤثر تعطيل تحديد النص على الوظائف الأخرى لمستند PDF؟
لا، فتعطيل تحديد النص يمنع المستخدمين فقط من تحديد النص ونسخه من المستند. وظائف أخرى لا تزال سليمة.
### هل يمكنني تمكين تحديد النص مرة أخرى بعد عرض المستند؟
 نعم، يمكنك تمكين تحديد النص بمجرد ضبط الإعداد`RenderTextAsImage` الملكية ل`false` في خيارات عرض HTML.
### هل هناك إصدار تجريبي متاح لـ GroupDocs.Viewer لـ .NET؟
 نعم، يمكنك الوصول إلى الإصدار التجريبي المجاني من GroupDocs.Viewer لـ .NET من[موقع إلكتروني](https://releases.groupdocs.com/).