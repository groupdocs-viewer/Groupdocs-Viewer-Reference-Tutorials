---
"description": "تعرّف على كيفية تحسين حجم وجودة الصور بتنسيق JPEG باستخدام Groupdocs.Viewer لـ .NET. حسّن تجربة عرض مستنداتك."
"linktitle": "ضبط حجم الصورة وجودتها (JPG)"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "ضبط حجم الصورة وجودتها (JPG)"
"url": "/ar/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# ضبط حجم الصورة وجودتها (JPG)

## مقدمة
Groupdocs.Viewer لـ .NET مكتبة فعّالة تُمكّن المطورين من دمج وظيفة عرض المستندات بسلاسة في تطبيقات .NET. من المتطلبات الشائعة في تطبيقات عرض المستندات إمكانية تعديل حجم وجودة الصور، خاصةً عند التعامل مع صور JPEG (JPG). في هذا البرنامج التعليمي، سنشرح لك عملية تعديل حجم وجودة الصور باستخدام Groupdocs.Viewer لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. فهم أساسي للغة البرمجة C#.
2. تم تثبيت Visual Studio على نظامك.
3. تم تثبيت مكتبة Groupdocs.Viewer لـ .NET. يمكنك تنزيلها من [هنا](https://releases.groupdocs.com/viewer/net/).

## استيراد مساحات الأسماء
أولاً، عليك استيراد مساحات الأسماء اللازمة إلى شيفرة C#. تتيح لك هذه المساحات الوصول إلى الفئات والأساليب اللازمة للعمل مع Groupdocs.Viewer.
## الخطوة 1: استيراد مساحات الأسماء
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن، دعنا نقسم الكود المثال المقدم إلى خطوات متعددة لفهم أفضل.
## الخطوة 2: تعيين تنسيق دليل الإخراج ومسار ملف الصفحة
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
في هذه الخطوة، نحدد دليل الإخراج الذي سيتم حفظ الصور المقدمة فيه ونحدد تنسيق مسار الملف لكل صورة صفحة.
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
هنا، نُهيئ كائن العارض بمسار المستند المراد عرضه. ثم نُنشئ مثيلًا لـ JpgViewOptions ونحدد العرض والارتفاع المطلوبين لصور JPEG.
## الخطوة 4: عرض مستند المصدر
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
وأخيرًا، نقوم بطباعة رسالة تشير إلى نجاح عرض المستند المصدر والموقع الذي تم حفظ الصور الناتجة فيه.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية ضبط حجم وجودة صور JPEG باستخدام Groupdocs.Viewer لـ .NET. باتباع الخطوات الموضحة أعلاه، يمكنك بسهولة دمج هذه الوظيفة في تطبيقات .NET، مما يوفر للمستخدمين تجربة عرض صور مُحسّنة.
## الأسئلة الشائعة
### هل يمكنني تعديل جودة الصورة أيضًا؟
نعم، يمكنك ضبط جودة الصورة عن طريق تعيين خاصية الجودة في JpgViewOptions.
### ما هي تنسيقات المستندات التي يدعمها Groupdocs.Viewer لـ .NET؟
يدعم Groupdocs.Viewer لـ .NET مجموعة واسعة من تنسيقات المستندات بما في ذلك DOCX وPDF وPPTX وXLSX والمزيد.
### هل Groupdocs.Viewer لـ .NET متوافق مع .NET Core؟
نعم، Groupdocs.Viewer لـ .NET متوافق مع .NET Core بالإضافة إلى .NET Framework التقليدي.
### هل يمكنني تخصيص تنسيق تسمية ملف الإخراج؟
نعم، يمكنك تخصيص تنسيق تسمية ملف الإخراج عن طريق تعديل المتغير pageFilePathFormat في الكود.
### هل يدعم Groupdocs.Viewer لـ .NET التعليقات التوضيحية للمستندات؟
نعم، يوفر Groupdocs.Viewer لـ .NET دعمًا شاملاً لتعليقات المستندات بما في ذلك تمييز النص وتسطيره والتعليق عليه.