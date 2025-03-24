---
title: تقديم ملف PDF بحجم الصفحة الأصلي
linktitle: تقديم ملف PDF بحجم الصفحة الأصلي
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض ملفات PDF بأحجام الصفحة الأصلية باستخدام GroupDocs.Viewer لـ .NET. اتبع دليلنا خطوة بخطوة وقم بدمج هذه الوظيفة بسلاسة.
weight: 17
url: /ar/net/pdf-rendering-options/render-pdf-original-page-size/
---
## مقدمة
في مجال تطوير .NET، يبرز GroupDocs.Viewer كأداة قوية لعرض تنسيقات المستندات المختلفة، بما في ذلك ملفات PDF. أحد المتطلبات الشائعة في معالجة المستندات هو عرض ملفات PDF مع الحفاظ على أحجام صفحاتها الأصلية. يتطلب تحقيق هذه المهمة بسلاسة فهمًا شاملاً لـ GroupDocs.Viewer لـ .NET ووظائفه.
## المتطلبات الأساسية
قبل الغوص في عرض ملفات PDF بأحجام الصفحة الأصلية باستخدام GroupDocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
### 1. قم بتثبيت GroupDocs.Viewer لـ .NET
 ابدأ بتنزيل مكتبة GroupDocs.Viewer من موقع الويب. يمكنك الحصول على المكتبة من المقدمة[رابط التحميل](https://releases.groupdocs.com/viewer/net/). اتبع تعليمات التثبيت المتوفرة في الوثائق لدمجها في مشروع .NET الخاص بك بشكل فعال.
### 2. إعداد بيئة التطوير
تأكد من أن لديك بيئة تطوير تم إعدادها لتطوير .NET. يتضمن ذلك تثبيت IDE متوافق، مثل Visual Studio، وفهم أساسي لبرمجة C#.
### 3. الحصول على وثيقة PDF
ستحتاج إلى نموذج مستند PDF لعرضه باستخدام GroupDocs.Viewer. يمكنك استخدام أي مستند PDF لأغراض الاختبار. إذا لم يكن لديك واحد، يمكنك تنزيل نموذج PDF من مصادر مختلفة عبر الإنترنت.

## استيراد مساحات الأسماء
قبل متابعة عرض ملفات PDF، من الضروري استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. تسمح لك هذه الخطوة بالوصول إلى الفئات والأساليب المطلوبة من مكتبة GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن بعد أن أصبحت لديك المتطلبات الأساسية ومساحات الأسماء الضرورية التي تم استيرادها، دعنا نقسم عملية عرض ملفات PDF بأحجام الصفحة الأصلية باستخدام GroupDocs.Viewer لـ .NET إلى خطوات بسيطة:
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
 تأكد من تحديد الدليل الذي تريد حفظ الصفحات المعروضة فيه. يستبدل`"Your Document Directory"` مع مسار الدليل المطلوب.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
قم بإعداد التنسيق لتسمية ملفات الصفحات المعروضة. في هذا المثال، سيتم حفظ الصفحات كصور PNG مع أسماء الملفات بالتنسيق`"page_1.png"`, `"page_2.png"`، وما إلى ذلك وهلم جرا.
## الخطوة 3: تقديم ملف PDF بحجم الصفحة الأصلي
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 إنشاء مثيل أ`Viewer` كائن مع المسار إلى ملف PDF الخاص بك. ثم قم بإنشاء`PngViewOptions` باستخدام تنسيق مسار ملف الصفحة المحدد. تعيين`RenderOriginalPageSize` الملكية ل`true` للحفاظ على أحجام الصفحة الأصلية أثناء العرض.
## الخطوة 4: عرض موقع المستند المقدم
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
اطبع رسالة تشير إلى نجاح العرض وقم بتوفير الدليل حيث يتم حفظ الصفحات المعروضة.

## خاتمة
يعد عرض ملفات PDF بأحجام الصفحة الأصلية باستخدام GroupDocs.Viewer لـ .NET عملية مباشرة عند اتباع الخطوات الموضحة في هذا البرنامج التعليمي. ومن خلال استيراد مساحات الأسماء الضرورية واتباع الدليل خطوة بخطوة، يمكنك دمج هذه الوظيفة بسلاسة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يستطيع GroupDocs.Viewer عرض تنسيقات المستندات الأخرى إلى جانب PDF؟
نعم، يدعم GroupDocs.Viewer عرض تنسيقات المستندات المختلفة، بما في ذلك Word وExcel وPowerPoint والمزيد.
### هل GroupDocs.Viewer متوافق مع .NET Core؟
نعم، GroupDocs.Viewer متوافق مع كل من بيئات .NET Framework و.NET Core.
### هل يمكنني تخصيص تنسيق الإخراج للصفحات المعروضة؟
نعم، يمكنك تخصيص تنسيق الإخراج عن طريق ضبط الخيارات التي يوفرها GroupDocs.Viewer، مثل تعيين تنسيقات صور مختلفة أو تحديد خيارات العرض المخصصة.
### هل يقدم GroupDocs.Viewer الدعم لعرض المستندات المستندة إلى السحابة؟
نعم، يوفر GroupDocs.Viewer واجهات برمجة التطبيقات لعرض المستندات المستندة إلى السحابة، مما يسمح لك بعرض المستندات مباشرة من موفري التخزين السحابي.
### هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer؟
 نعم، يمكنك استكشاف GroupDocs.Viewer باستخدام نسخة تجريبية مجانية من خلال زيارة الملف المرفق[وصلة](https://releases.groupdocs.com/).