---
title: تقديم صور EMZ وEMF
linktitle: تقديم صور EMZ وEMF
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض صور EMZ وEMF إلى تنسيقات مختلفة باستخدام GroupDocs.Viewer لـ .NET. برنامج تعليمي سهل المتابعة للمطورين.
type: docs
weight: 14
url: /ar/net/image-rendering/render-emz-emf-images/
---
## مقدمة

GroupDocs.Viewer for .NET عبارة عن واجهة برمجة تطبيقات قوية لعرض المستندات تسمح للمطورين بعرض أنواع مختلفة من المستندات، بما في ذلك صور EMZ (ملف تعريف Windows المحسن) وصور EMF (ملف تعريف محسّن) في تطبيقات .NET الخاصة بهم. في هذا البرنامج التعليمي، سوف نستكشف كيفية عرض صور EMZ وEMF إلى تنسيقات مختلفة مثل HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1.  GroupDocs.Viewer لـ .NET: يمكنك تنزيل المكتبة من[هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: تأكد من أن لديك بيئة تطوير متوافقة تم إعدادها لتطوير .NET.
3. عينة من صور EMZ/EMF: احصل على عينة من صور EMZ وEMF متاحة للعرض.

## استيراد مساحات الأسماء

قبل الغوص في الكود، فلنستورد مساحات الأسماء الضرورية:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

الآن، دعونا نقسم كل مثال إلى خطوات متعددة بتنسيق دليل خطوة بخطوة:

## تقديم صور EMZ/EMF إلى HTML

### الخطوة 1: تعيين دليل الإخراج:
```csharp
string outputDirectory = "Your Document Directory";
```
 يستبدل`"Your Document Directory"`بالمسار الذي تريد حفظ ملف HTML المعروض فيه.

### الخطوة 2: تحديد تنسيق مسار ملف الصفحة:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
سيحدد هذا تنسيق مسار الملف لملف HTML المعروض.

### الخطوة 3: التقديم إلى HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 يقوم هذا الرمز بتهيئة`Viewer` كائن مع نموذج صورة EMZ ويعرضه إلى تنسيق HTML باستخدام الخيارات المحددة.

## عرض صور EMZ/EMF إلى JPG وPNG وPDF

كرر الخطوات التالية للعرض بتنسيقات JPG، وPNG، وPDF:

### الخطوة 1: تحديد تنسيق مسار ملف الصفحة:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
اضبط اسم الملف وامتداده وفقًا لتنسيق الإخراج المطلوب (`jpg`, `png` ، أو`pdf`).

### الخطوة 2: التقديم إلى التنسيق المعني:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // ضبط الخيارات وفقًا لتنسيق الإخراج (Jpg، Png، Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 يستبدل`JpgViewOptions` مع`PngViewOptions` أو`PdfViewOptions` بناء على تنسيق الإخراج المطلوب.

## خاتمة

في الختام، يوفر GroupDocs.Viewer for .NET حلاً سلسًا لعرض صور EMZ وEMF إلى تنسيقات مختلفة في تطبيقات .NET. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكن للمطورين دمج إمكانات عرض المستندات في تطبيقاتهم بسهولة.

## الأسئلة الشائعة

### س: هل يمكن لـ GroupDocs.Viewer عرض تنسيقات المستندات الأخرى بخلاف صور EMZ وEMF؟
ج: نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات بما في ذلك PDF وDOCX وPPTX وXLSX والمزيد.

### س: هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer لـ .NET؟
 ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.groupdocs.com/).

### س: هل يقدم GroupDocs.Viewer الدعم للمطورين؟
 ج: نعم، يوفر GroupDocs الدعم من خلاله[المنتدى](https://forum.groupdocs.com/c/viewer/9) حيث يمكن للمطورين طرح الأسئلة وطلب المساعدة.

### س: هل يمكنني شراء ترخيص مؤقت لـ GroupDocs.Viewer لـ .NET؟
 ج: نعم، التراخيص المؤقتة متاحة للشراء[هنا](https://purchase.groupdocs.com/temporary-license/).

### س: أين يمكنني العثور على الوثائق التفصيلية الخاصة بـ GroupDocs.Viewer لـ .NET؟
 ج: يمكنك الرجوع إلى الوثائق[هنا](https://reference.groupdocs.com/viewer/net/)للحصول على إرشادات شاملة حول استخدام واجهة برمجة التطبيقات.