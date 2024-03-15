---
title: ضبط حجم الصورة وجودتها (JPG)
linktitle: ضبط حجم الصورة وجودتها (JPG)
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية تحسين حجم الصورة وجودتها بتنسيق JPEG باستخدام Groupdocs.Viewer لـ .NET. تعزيز تجربة عرض المستندات الخاصة بك.
type: docs
weight: 11
url: /ar/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## مقدمة
تعد Groupdocs.Viewer for .NET مكتبة قوية تمكن المطورين من دمج وظيفة عرض المستندات بسلاسة في تطبيقات .NET الخاصة بهم. أحد المتطلبات الشائعة في تطبيقات عرض المستندات هو القدرة على ضبط حجم الصور وجودتها، خاصة عند التعامل مع صور JPEG (JPG). في هذا البرنامج التعليمي، سنرشدك خلال عملية ضبط حجم الصورة وجودتها باستخدام Groupdocs.Viewer for .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. الفهم الأساسي للغة البرمجة C#.
2. تم تثبيت Visual Studio على نظامك.
3.  تم تثبيت Groupdocs.Viewer لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى كود C# الخاص بك. توفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب المطلوبة للعمل مع Groupdocs.Viewer.
## الخطوة 1: استيراد مساحات الأسماء
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن، دعونا نقسم رمز المثال المقدم إلى خطوات متعددة لفهم أفضل.
## الخطوة 2: تعيين دليل الإخراج وتنسيق مسار ملف الصفحة
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
في هذه الخطوة، نحدد دليل الإخراج حيث سيتم حفظ الصور المقدمة ونحدد تنسيق مسار الملف لكل صورة صفحة.
## الخطوة 3: تهيئة العارض وتكوين خيارات عرض JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
هنا، نقوم بتهيئة كائن العارض بالمسار إلى المستند المراد عرضه. بعد ذلك، نقوم بإنشاء مثيل لـ JpgViewOptions ونقوم بتعيين العرض والارتفاع المطلوبين لصور JPEG.
## الخطوة 4: تقديم المستند المصدر
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
أخيرًا، نقوم بطباعة رسالة تشير إلى نجاح عرض المستند المصدر والموقع الذي يتم فيه حفظ الصور الناتجة.

## خاتمة
تعلمنا في هذا البرنامج التعليمي كيفية ضبط حجم وجودة صور JPEG باستخدام Groupdocs.Viewer لـ .NET. باتباع الخطوات الموضحة أعلاه، يمكنك بسهولة دمج هذه الوظيفة في تطبيقات .NET الخاصة بك، مما يوفر للمستخدمين تجربة مشاهدة محسنة للصور.
## الأسئلة الشائعة
### هل يمكنني ضبط جودة الصورة أيضًا؟
نعم، يمكنك ضبط جودة الصورة عن طريق تعيين خاصية الجودة في JpgViewOptions.
### ما هي تنسيقات المستندات التي يدعمها Groupdocs.Viewer لـ .NET؟
يدعم Groupdocs.Viewer for .NET نطاقًا واسعًا من تنسيقات المستندات بما في ذلك DOCX وPDF وPPTX وXLSX والمزيد.
### هل يتوافق Groupdocs.Viewer لـ .NET مع .NET Core؟
نعم، يتوافق Groupdocs.Viewer for .NET مع .NET Core بالإضافة إلى .NET Framework التقليدي.
### هل يمكنني تخصيص تنسيق تسمية ملف الإخراج؟
نعم، يمكنك تخصيص تنسيق تسمية ملف الإخراج عن طريق تعديل متغير pageFilePathFormat في التعليمات البرمجية.
### هل يدعم Groupdocs.Viewer لـ .NET التعليقات التوضيحية للمستندات؟
نعم، يوفر Groupdocs.Viewer for .NET دعمًا شاملاً لتعليقات المستند بما في ذلك تمييز النص وتسطيره والتعليق عليه.