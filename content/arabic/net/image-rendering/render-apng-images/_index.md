---
"description": "تعرّف على كيفية عرض صور APNG بتنسيقات مختلفة باستخدام Groupdocs.Viewer لـ .NET. دليل خطوة بخطوة مع أمثلة برمجية."
"linktitle": "عرض صور APNG"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض صور APNG"
"url": "/ar/net/image-rendering/render-apng-images/"
"weight": 11
type: docs
---
# عرض صور APNG

## مقدمة
Groupdocs.Viewer لـ .NET أداة فعّالة تُمكّن المطورين من عرض صيغ مستندات متنوعة بسلاسة في تطبيقات .NET. من بين ميزاتها العديدة، تُوفّر وظائف فعّالة لعرض صور APNG (رسومات الشبكة المحمولة المتحركة)، ما يُمكّن المطورين من عرض صور APNG بصيغ مختلفة مثل HTML وJPG وPNG وPDF.

![عرض صور APNG باستخدام GroupDocs.Viewer لـ .NET](/viewer/image-rendering/render-apng-images.png)

في هذا البرنامج التعليمي، سنستكشف كيفية استخدام Groupdocs.Viewer لـ .NET لعرض صور APNG خطوة بخطوة. باتباع هذه التعليمات، ستتمكن من دمج إمكانيات عرض صور APNG في تطبيقات .NET بسهولة.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

1. تثبيت Groupdocs.Viewer لـ .NET: تأكد من تثبيت Groupdocs.Viewer لـ .NET في بيئة التطوير لديك. يمكنك تنزيل الملفات اللازمة من [رابط التحميل الرسمي](https://releases.groupdocs.com/viewer/net/).

2. المعرفة الأساسية بتطوير .NET: تعرف على مفاهيم تطوير .NET، بما في ذلك برمجة C# ومعالجة التبعيات داخل مشاريعك.

3. صورة نموذجية بتنسيق APNG: جهّز ملف صورة نموذجية بتنسيق APNG لأغراض الاختبار. يمكنك استخدام أي ملف صورة APNG متاح، أو إنشاء ملف جديد لتجربة عملية العرض.

الآن، دعنا ننتقل إلى الدليل خطوة بخطوة لعرض صور APNG باستخدام Groupdocs.Viewer لـ .NET.

## استيراد مساحات الأسماء الضرورية

قبل البدء بعرض صور APNG، نحتاج إلى استيراد مساحات الأسماء المطلوبة إلى شيفرة C#. تتيح هذه المساحات الوصول إلى الفئات والأساليب اللازمة للتفاعل مع وظائف Groupdocs.Viewer.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## الخطوة 1: تهيئة دليل الإخراج

أولاً، علينا تحديد المجلد الذي ستُخزَّن فيه المخرجات المُقدَّمة. سنُنشئ متغيرًا نصيًا يحمل مسار مجلد المخرجات.

```csharp
string outputDirectory = "Your Document Directory";
```

يستبدل `"Your Document Directory"` مع المسار الفعلي الذي تريد حفظ الملفات المقدمة فيه.

## الخطوة 2: تحويل صورة APNG إلى HTML

لتقديم صورة APNG إلى تنسيق HTML، سنستخدم `Viewer` الفئة من Groupdocs.Viewer وتحديد خيارات الإخراج وفقًا لذلك.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "apng_result.html");

using (Viewer viewer = new Viewer("Path_to_your_APNG_file"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

    viewer.View(options);
}
```

يستبدل `"Path_to_your_APNG_file"` مع المسار الفعلي لملف صورة APNG الخاص بك.

## الخطوة 3: تحويل صورة APNG إلى JPG

وبنفس الطريقة، يمكننا تحويل صورة APNG إلى تنسيق JPG عن طريق تكوين الخيارات المناسبة.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "apng_result_{0}.jpg");

using (Viewer viewer = new Viewer("Path_to_your_APNG_file"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options);
}
```

## الخطوة 4: تحويل صورة APNG إلى PNG

تتبع عملية تحويل صورة APNG إلى تنسيق PNG نفس النمط، مع ضبط الخيارات وفقًا لذلك.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "apng_result_{0}.png");

using (Viewer viewer = new Viewer("Path_to_your_APNG_file"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options);
}
```

## الخطوة 5: تحويل صورة APNG إلى PDF

أخيرًا، يمكننا تقديم صورة APNG إلى تنسيق PDF باستخدام Groupdocs.Viewer.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "apng_result.pdf");

using (Viewer viewer = new Viewer("Path_to_your_APNG_file"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية عرض صور APNG بتنسيقات مختلفة باستخدام Groupdocs.Viewer لـ .NET. باتباع هذا الدليل المفصل ودمج الشفرة البرمجية المرفقة في تطبيق .NET، يمكنك دمج إمكانيات عرض صور APNG بسلاسة، مما يُحسّن تجربة المستخدمين المرئية.

## الأسئلة الشائعة

### س1: هل يمكن لـ Groupdocs.Viewer عرض تنسيقات صور أخرى غير APNG؟

ج1: نعم، يدعم Groupdocs.Viewer عرض تنسيقات الصور المختلفة، بما في ذلك PNG، وJPG، وBMP، وTIFF، وGIF، وغيرها.

### س2: هل Groupdocs.Viewer متوافق مع تطبيقات .NET Core؟

ج2: نعم، يوفر Groupdocs.Viewer التوافق مع تطبيقات .NET Framework و.NET Core، مما يوفر المرونة للمطورين.

### س3: هل يتطلب Groupdocs.Viewer أي تبعيات إضافية لعرض المستندات؟

A3: يأتي Groupdocs.Viewer مزودًا بكل التبعيات الضرورية المضمنة، مما يزيل الحاجة إلى تثبيتات أو تكوينات إضافية.

### س4: هل يمكنني تخصيص خيارات العرض لتحسين الأداء أو الجودة المرئية؟

ج4: نعم، يوفر Groupdocs.Viewer خيارات تخصيص واسعة النطاق، مما يسمح للمطورين بتخصيص عملية العرض وفقًا لمتطلباتهم المحددة.

### س5: هل الدعم الفني متاح لمستخدمي Groupdocs.Viewer؟

ج٥: نعم، تقدم Groupdocs دعمًا فنيًا متخصصًا لمنتجاتها، بما في ذلك Groupdocs.Viewer. يمكنك الوصول إلى الدعم من خلال [المنتدى الرسمي](https://forum.groupdocs.com/c/viewer/9) أو اتصل بفريق الدعم مباشرة.