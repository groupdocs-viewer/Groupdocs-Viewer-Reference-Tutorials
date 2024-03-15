---
title: ضبط حجم صورة الإخراج لرسومات CAD
linktitle: ضبط حجم صورة الإخراج لرسومات CAD
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية ضبط حجم الصورة الناتجة لرسومات CAD باستخدام GroupDocs.Viewer لـ .NET. تعزيز الرؤية وسهولة الاستخدام دون عناء.
type: docs
weight: 15
url: /ar/net/rendering-cad-drawings/adjust-output-image-size-cad/
---
## مقدمة
غالبًا ما تتطلب رسومات CAD تعديلات محددة للعرض والعرض الأمثل. يوفر GroupDocs.Viewer for .NET مجموعة أدوات قوية لإدارة مخرجات رسومات CAD وتخصيصها. في هذا البرنامج التعليمي، سنرشدك خلال عملية ضبط حجم الصورة الناتجة لرسومات CAD خطوة بخطوة.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
1.  GroupDocs.Viewer لـ .NET: قم بتنزيل وتثبيت GroupDocs.Viewer لـ .NET من[هنا](https://releases.groupdocs.com/viewer/net/).
2. دليل المستندات: قم بإعداد الدليل الذي يوجد به المستند الخاص بك.
3. الفهم الأساسي: تعرف على المفاهيم الأساسية لبرمجة .NET.

## استيراد مساحات الأسماء
أولاً، تأكد من استيراد مساحات الأسماء الضرورية للوصول إلى وظائف GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: تعيين دليل الإخراج
حدد الدليل الذي تريد تخزين الصور الناتجة لرسومات CAD فيه:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
قم بتعيين التنسيق لمسارات ملفات الصفحة. سيتم استخدام هذا التنسيق لتسمية الصفحات الفردية وحفظها كملفات HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: ضبط حجم الصورة
داخل كتلة الاستخدام لكائن العارض، اضبط حجم الصورة لرسومات CAD عن طريق تعيين الخيارات المناسبة:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## الخطوة 4: عرض دليل الإخراج
بعد عرض المستند، قم بعرض رسالة تشير إلى نجاح العرض وتوفير موقع دليل الإخراج:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
يعد ضبط حجم الصورة الناتجة لرسومات CAD أمرًا ضروريًا لتحسين رؤيتها وسهولة استخدامها. باستخدام GroupDocs.Viewer for .NET، تصبح هذه العملية مبسطة وفعالة، مما يسمح لك بتخصيص الإخراج وفقًا لمتطلباتك المحددة.
## الأسئلة الشائعة
### هل يمكنني ضبط حجم الصورة الناتجة لأنواع أخرى من المستندات إلى جانب رسومات CAD؟
نعم، يدعم GroupDocs.Viewer for .NET أنواع المستندات المختلفة، ويمكنك ضبط حجم الصورة الناتجة لمعظم تنسيقات المستندات.
### هل يتوافق GroupDocs.Viewer لـ .NET مع الإصدارات المختلفة من .NET Framework؟
نعم، يتوافق GroupDocs.Viewer for .NET مع إصدارات متعددة من إطار عمل .NET، مما يضمن المرونة وسهولة الاستخدام عبر بيئات مختلفة.
### هل هناك أي خيارات ترخيص متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك استكشاف خيارات الترخيص المختلفة، بما في ذلك التراخيص المؤقتة والتراخيص التجارية، بما يناسب احتياجاتك.
### هل يمكنني تخصيص تنسيق الإخراج للمستندات المقدمة؟
بالتأكيد، يوفر GroupDocs.Viewer for .NET خيارات تخصيص متنوعة، مما يسمح لك بتخصيص تنسيق الإخراج وفقًا لتفضيلاتك.
### أين يمكنني العثور على دعم أو مساعدة إضافية فيما يتعلق بـ GroupDocs.Viewer لـ .NET؟
 يمكنك زيارة منتدى GroupDocs.Viewer[هنا](https://forum.groupdocs.com/c/viewer/9) للحصول على الدعم وطرح الأسئلة والتفاعل مع المجتمع.