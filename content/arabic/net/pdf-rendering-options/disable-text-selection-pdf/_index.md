---
"description": "تعرّف على كيفية تعطيل تحديد النص في ملف PDF باستخدام GroupDocs.Viewer لـ .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس."
"linktitle": "تعطيل تحديد النص في PDF"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تعطيل تحديد النص في PDF"
"url": "/ar/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# تعطيل تحديد النص في PDF

## مقدمة
GroupDocs.Viewer لـ .NET هي واجهة برمجة تطبيقات فعّالة لعرض المستندات، تُمكّن المطورين من دمج إمكانيات عرض المستندات في تطبيقات .NET بسهولة. من أهم وظائف GroupDocs.Viewer إمكانية تعطيل تحديد النص في مستندات PDF. تُعد هذه الميزة مفيدة بشكل خاص في الحالات التي تتطلب منع المستخدمين من نسخ النصوص من المستندات الحساسة، مما يضمن أمان المستندات وسلامتها.

![تعطيل تحديد النص في PDF باستخدام GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## المتطلبات الأساسية
قبل أن نتعمق في الدليل خطوة بخطوة حول كيفية تعطيل تحديد النص في PDF باستخدام GroupDocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
1. تثبيت GroupDocs.Viewer لـ .NET: تأكد من أنك قمت بتنزيل GroupDocs.Viewer لـ .NET وتثبيته من [رابط التحميل](https://releases.groupdocs.com/viewer/net/).
2. دليل المستندات: جهّز دليلًا لتخزين مستنداتك. ستحتاج إلى تحديد هذا الدليل في مقتطف الكود لعرض مستند PDF.

## استيراد مساحات الأسماء
أولاً، عليك استيراد مساحات الأسماء اللازمة للوصول إلى وظائف GroupDocs.Viewer لـ .NET. إليك كيفية القيام بذلك:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن، دعنا نقوم بتقسيم عملية تعطيل تحديد النص في مستند PDF باستخدام GroupDocs.Viewer لـ .NET إلى خطوات متعددة:
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
في هذه الخطوة، استبدل `"Your Document Directory"` مع مسار الدليل الذي يوجد به مستند PDF الخاص بك.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
تُحدد هذه الخطوة تنسيق مسارات صفحات HTML المُعالجة. سيتم تحويل كل صفحة من مستند PDF إلى ملف HTML برقم صفحة متسلسل.
## الخطوة 3: عرض مستند PDF مع تعطيل تحديد النص
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
يستبدل `"Path to Your PDF Document"` مع المسار الفعلي لملف PDF الخاص بك. هذا المقطع من التعليمات البرمجية يُهيئ `Viewer` الكائن، يقوم بتكوين خيارات عرض HTML لتضمين الموارد، ويقوم بتعطيل تحديد النص عن طريق الإعداد `RenderTextAsImage` الممتلكات إلى `true`.
## الخطوة 4: عرض رسالة النجاح
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
بعد عرض مستند PDF، تعرض هذه الخطوة رسالة نجاح بالإضافة إلى الدليل الذي يتم تخزين صفحات HTML المعروضة فيه.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعطيل تحديد النص في مستندات PDF باستخدام GroupDocs.Viewer لـ .NET. باتباع هذا الدليل المفصل، يمكنك دمج هذه الميزة بسلاسة في تطبيقات .NET، مما يضمن أمان المستندات ويحسّن تجربة المستخدم.
## الأسئلة الشائعة
### هل يمكنني تخصيص دليل الإخراج لصفحات HTML المقدمة؟
نعم، يمكنك تحديد أي مسار دليل تريد تخزين صفحات HTML المقدمة فيه.
### هل GroupDocs.Viewer لـ .NET متوافق مع الإصدارات المختلفة من إطار عمل .NET؟
نعم، GroupDocs.Viewer لـ .NET متوافق مع الإصدارات المختلفة لإطار عمل .NET، بما في ذلك .NET Core و.NET Framework.
### هل يؤثر تعطيل تحديد النص على الوظائف الأخرى لمستند PDF؟
لا، تعطيل تحديد النص يمنع المستخدمين فقط من تحديد النص ونسخه من المستند. تبقى الوظائف الأخرى كما هي.
### هل يمكنني تفعيل اختيار النص مرة أخرى بعد عرض المستند؟
نعم، يمكنك تمكين تحديد النص ببساطة عن طريق ضبط `RenderTextAsImage` الممتلكات إلى `false` في خيارات عرض HTML.
### هل هناك نسخة تجريبية متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من GroupDocs.Viewer لـ .NET من [موقع إلكتروني](https://releases.groupdocs.com/).