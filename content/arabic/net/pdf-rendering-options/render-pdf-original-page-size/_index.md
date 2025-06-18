---
"description": "تعرّف على كيفية عرض ملفات PDF بأحجام الصفحات الأصلية باستخدام GroupDocs.Viewer لـ .NET. اتبع دليلنا خطوة بخطوة لدمج هذه الوظيفة بسلاسة."
"linktitle": "عرض ملف PDF بحجم الصفحة الأصلي"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض ملف PDF بحجم الصفحة الأصلي"
"url": "/ar/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# عرض ملف PDF بحجم الصفحة الأصلي

## مقدمة
في مجال تطوير .NET، يبرز GroupDocs.Viewer كأداة فعّالة لعرض مختلف تنسيقات المستندات، بما في ذلك ملفات PDF. من المتطلبات الشائعة في معالجة المستندات عرض ملفات PDF مع الحفاظ على أحجام صفحاتها الأصلية. يتطلب إنجاز هذه المهمة بسلاسة فهمًا شاملًا لـ GroupDocs.Viewer لـ .NET ووظائفه.

![عرض ملف PDF بحجم الصفحة الأصلي باستخدام GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## المتطلبات الأساسية
قبل الغوص في عرض ملفات PDF بأحجام الصفحات الأصلية باستخدام GroupDocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
### 1. تثبيت GroupDocs.Viewer لـ .NET
ابدأ بتنزيل مكتبة GroupDocs.Viewer من الموقع الإلكتروني. يمكنك الحصول عليها من الرابط المُرفق. [رابط التحميل](https://releases.groupdocs.com/viewer/net/)اتبع تعليمات التثبيت المقدمة في الوثائق لدمجها في مشروع .NET الخاص بك بشكل فعال.
### 2. إعداد بيئة التطوير
تأكد من إعداد بيئة تطوير مناسبة لتطوير .NET. يتضمن ذلك تثبيت بيئة تطوير متكاملة متوافقة، مثل Visual Studio، وفهم أساسي لبرمجة C#.
### 3. الحصول على مستند PDF
ستحتاج إلى نموذج مستند PDF لعرضه باستخدام GroupDocs.Viewer. يمكنك استخدام أي مستند PDF لأغراض الاختبار. إذا لم يكن لديك واحد، يمكنك تنزيل نموذج PDF من مصادر متعددة على الإنترنت.

## استيراد مساحات الأسماء
قبل البدء في معالجة ملفات PDF، من الضروري استيراد مساحات الأسماء اللازمة إلى مشروع C#. تتيح لك هذه الخطوة الوصول إلى الفئات والأساليب المطلوبة من مكتبة GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن بعد أن قمت بوضع المتطلبات الأساسية واستيراد مساحات الأسماء الضرورية، دعنا نقوم بتقسيم عملية عرض ملفات PDF بأحجام الصفحات الأصلية باستخدام GroupDocs.Viewer لـ .NET إلى خطوات بسيطة:
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
تأكد من تحديد الدليل الذي تريد حفظ الصفحات المُقدمة فيه. استبدل `"Your Document Directory"` مع مسار الدليل المطلوب.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
حدّد صيغة تسمية ملفات الصفحات المُقدّمة. في هذا المثال، سيتم حفظ الصفحات كصور PNG بأسماء ملفات بالتنسيق `"page_1.png"`، `"page_2.png"`، وما إلى ذلك.
## الخطوة 3: عرض ملف PDF بحجم الصفحة الأصلي
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
إنشاء مثيل `Viewer` كائن بمسار ملف PDF الخاص بك. ثم أنشئ `PngViewOptions` مع تنسيق مسار ملف الصفحة المحدد. اضبط `RenderOriginalPageSize` الممتلكات إلى `true` للحفاظ على أحجام الصفحات الأصلية أثناء العرض.
## الخطوة 4: عرض موقع المستند المُقدم
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
اطبع رسالة تشير إلى نجاح العرض وتوفير الدليل الذي تم حفظ الصفحات التي تم عرضها فيه.

## خاتمة
يُعد عرض ملفات PDF بأحجام الصفحات الأصلية باستخدام GroupDocs.Viewer لـ .NET عملية سهلة باتباع الخطوات الموضحة في هذا البرنامج التعليمي. باستيراد مساحات الأسماء اللازمة واتباع الدليل خطوة بخطوة، يمكنك دمج هذه الوظيفة بسلاسة في تطبيقات .NET.
## الأسئلة الشائعة
### هل يمكن لـ GroupDocs.Viewer عرض تنسيقات مستندات أخرى بالإضافة إلى PDF؟
نعم، يدعم GroupDocs.Viewer عرض تنسيقات المستندات المختلفة، بما في ذلك Word وExcel وPowerPoint والمزيد.
### هل GroupDocs.Viewer متوافق مع .NET Core؟
نعم، GroupDocs.Viewer متوافق مع بيئات .NET Framework و.NET Core.
### هل يمكنني تخصيص تنسيق إخراج الصفحات المقدمة؟
نعم، يمكنك تخصيص تنسيق الإخراج عن طريق ضبط الخيارات التي يوفرها GroupDocs.Viewer، مثل تعيين تنسيقات صور مختلفة أو تحديد خيارات عرض مخصصة.
### هل يوفر GroupDocs.Viewer الدعم لعرض المستندات المستند إلى السحابة؟
نعم، يوفر GroupDocs.Viewer واجهات برمجة التطبيقات لعرض المستندات المستندة إلى السحابة، مما يسمح لك بعرض المستندات مباشرة من موفري التخزين السحابي.
### هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer؟
نعم، يمكنك استكشاف GroupDocs.Viewer باستخدام نسخة تجريبية مجانية من خلال زيارة الموقع المقدم [وصلة](https://releases.groupdocs.com/).