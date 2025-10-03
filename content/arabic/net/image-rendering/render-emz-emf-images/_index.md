---
"description": "تعلّم كيفية عرض صور EMZ وEMF بتنسيقات مختلفة باستخدام GroupDocs.Viewer لـ .NET. دليل تعليمي سهل الاستخدام للمطورين."
"linktitle": "عرض صور EMZ وEMF"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض صور EMZ وEMF"
"url": "/ar/net/image-rendering/render-emz-emf-images/"
"weight": 14
type: docs
---
# عرض صور EMZ وEMF

## مقدمة

GroupDocs.Viewer لـ .NET هي واجهة برمجة تطبيقات فعّالة لعرض المستندات، تُمكّن المطورين من عرض أنواع مختلفة من المستندات، بما في ذلك صور EMZ (ملفات تعريف Windows المُحسّنة) وEMF (ملفات تعريف Windows المُحسّنة)، في تطبيقات .NET. في هذا البرنامج التعليمي، سنستكشف كيفية عرض صور EMZ وEMF بتنسيقات مختلفة مثل HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET.

![عرض صور EMZ وEMF باستخدام GroupDocs.Viewer لـ .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:

1. GroupDocs.Viewer لـ .NET: يمكنك تنزيل المكتبة من [هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: تأكد من أن لديك بيئة تطوير متوافقة تم إعدادها لتطوير .NET.
3. عينات من صور EMZ/EMF: احصل على عينات من صور EMZ وEMF متاحة للرسم.

## استيراد مساحات الأسماء

قبل الغوص في الكود، دعنا نستورد مساحات الأسماء الضرورية:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

الآن، دعنا نقسم كل مثال إلى خطوات متعددة في شكل دليل خطوة بخطوة:

## تحويل صور EMZ/EMF إلى HTML

### الخطوة 1: تعيين دليل الإخراج:
```csharp
string outputDirectory = "Your Document Directory";
```
يستبدل `"Your Document Directory"` مع المسار الذي تريد حفظ ملف HTML المُقدم فيه.

### الخطوة 2: تحديد تنسيق مسار ملف الصفحة:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
سيؤدي هذا إلى تحديد تنسيق مسار الملف لملف HTML المقدم.

### الخطوة 3: العرض إلى HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
يقوم هذا الكود بتهيئة `Viewer` كائن مع صورة EMZ النموذجية ويعرضها بتنسيق HTML باستخدام الخيارات المحددة.

## تحويل صور EMZ/EMF إلى JPG وPNG وPDF

كرر الخطوات التالية لعرض التنسيقات JPG وPNG وPDF:

### الخطوة 1: تحديد تنسيق مسار ملف الصفحة:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
قم بضبط اسم الملف وامتداده وفقًا لتنسيق الإخراج المطلوب (`jpg`، `png`، أو `pdf`).

### الخطوة 2: تقديم إلى التنسيق المناسب:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // ضبط الخيارات وفقًا لتنسيق الإخراج (Jpg، Png، Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
يستبدل `JpgViewOptions` مع `PngViewOptions` أو `PdfViewOptions` بناءً على تنسيق الإخراج المطلوب.

## خاتمة

في الختام، يوفر GroupDocs.Viewer لـ .NET حلاً متكاملاً لعرض صور EMZ وEMF بتنسيقات مختلفة في تطبيقات .NET. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكن للمطورين دمج إمكانيات عرض المستندات بسهولة في تطبيقاتهم.

## الأسئلة الشائعة

### س: هل يمكن لـ GroupDocs.Viewer عرض تنسيقات مستندات أخرى غير صور EMZ وEMF؟
ج: نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات بما في ذلك PDF وDOCX وPPTX وXLSX والمزيد.

### س: هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer لـ .NET؟
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.groupdocs.com/).

### س: هل يوفر GroupDocs.Viewer الدعم للمطورين؟
ج: نعم، توفر GroupDocs الدعم من خلال [المنتدى](https://forum.groupdocs.com/c/viewer/9) حيث يمكن للمطورين طرح الأسئلة وطلب المساعدة.

### س: هل يمكنني شراء ترخيص مؤقت لـ GroupDocs.Viewer لـ .NET؟
ج: نعم، التراخيص المؤقتة متاحة للشراء [هنا](https://purchase.groupdocs.com/temporary-license/).

### س: أين يمكنني العثور على وثائق مفصلة لـ GroupDocs.Viewer لـ .NET؟
ج: يمكنك الرجوع إلى الوثائق [هنا](https://tutorials.groupdocs.com/viewer/net/) للحصول على إرشادات شاملة حول استخدام واجهة برمجة التطبيقات (API).