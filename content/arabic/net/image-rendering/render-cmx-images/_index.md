---
"description": "تعلّم كيفية عرض صور CMX بسهولة بتنسيقات مختلفة باستخدام GroupDocs.Viewer لـ .NET. حسّن إدارة مستنداتك."
"linktitle": "تقديم صور CMX"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تقديم صور CMX"
"url": "/ar/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# تقديم صور CMX

## مقدمة
في مجال إدارة المستندات ومعالجتها، يُعدّ عرض الصور من صيغ مختلفة أمرًا بالغ الأهمية. يُبسّط GroupDocs.Viewer لـ .NET هذه العملية بتوفير وظائف شاملة لعرض صور CMX بصيغ مختلفة مثل HTML وJPG وPNG وPDF. سيرشدك هذا البرنامج التعليمي خطوة بخطوة خلال عملية عرض صور CMX باستخدام GroupDocs.Viewer لـ .NET.

![عرض صور CMX باستخدام GroupDocs.Viewer لـ .NET](/viewer/image-rendering/render-cmx-images.png)

## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لمكتبة .NET: قم بتنزيل وتثبيت مكتبة GroupDocs.Viewer لمكتبة .NET من [هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير عمل باستخدام إطار عمل .NET.
3. ملف صورة CMX: احصل على ملف صورة CMX الذي ترغب في تقديمه.

## استيراد مساحات الأسماء
قبل المتابعة، تأكد من استيراد المساحات الأساسية اللازمة للوصول إلى وظائف GroupDocs.Viewer في تطبيق .NET الخاص بك:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## العرض إلى HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- تحديد دليل الإخراج: قم بتعيين الدليل الذي تريد تخزين ملفات HTML المُقدمة فيه.
- تحديد تنسيق مسار الملف: قم بتحديد تنسيق ملفات HTML الناتجة.
- إنشاء كائن العارض: إنشاء مثيل لفئة العارض باستخدام ملف صورة CMX.
- خيارات عرض HTML: تكوين خيارات عرض HTML، مثل تضمين الموارد.
- تقديم CMX إلى HTML: استدعاء طريقة العرض الخاصة بكائن العارض لتقديم صورة CMX إلى HTML.
## تقديم إلى JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- تحديد دليل الإخراج: قم بتعيين الدليل لتخزين ملفات JPG المقدمة.
- تحديد تنسيق مسار الملف: قم بتحديد تنسيق ملفات JPG الناتجة.
- إنشاء كائن العارض: إنشاء مثيل لفئة العارض باستخدام ملف صورة CMX.
- خيارات عرض JPG: تكوين خيارات عرض JPG.
- تحويل CMX إلى JPG: استدعاء طريقة العرض الخاصة بكائن العارض لتحويل صورة CMX إلى JPG.
## تقديم إلى PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- تحديد دليل الإخراج: قم بتعيين الدليل لتخزين ملفات PNG المقدمة.
- تحديد تنسيق مسار الملف: قم بتحديد تنسيق ملفات PNG الناتجة.
- إنشاء كائن العارض: إنشاء مثيل لفئة العارض باستخدام ملف صورة CMX.
- خيارات عرض PNG: تكوين خيارات عرض PNG.
- تقديم CMX إلى PNG: استدعاء طريقة العرض الخاصة بكائن العارض لتقديم صورة CMX إلى PNG.
## تحويل إلى PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- تحديد دليل الإخراج: قم بتعيين الدليل لتخزين ملف PDF المُقدم.
- تحديد تنسيق مسار الملف: قم بتحديد تنسيق ملف PDF الناتج.
- إنشاء كائن العارض: إنشاء مثيل لفئة العارض باستخدام ملف صورة CMX.
- خيارات عرض PDF: تكوين خيارات عرض PDF.
- تقديم CMX إلى PDF: استدعاء طريقة العرض الخاصة بكائن العارض لتقديم صورة CMX إلى PDF.

## خاتمة
في الختام، يُقدم GroupDocs.Viewer لـ .NET حلاً فعّالاً لعرض صور CMX بتنسيقات مُختلفة بسلاسة. باتباع الخطوات المُوضحة في هذا البرنامج التعليمي، يُمكنك دمج إمكانيات عرض صور CMX بسهولة في تطبيقات .NET، مما يُحسّن كفاءة إدارة المستندات.
## الأسئلة الشائعة
### هل يمكنني عرض صفحات محددة من صورة CMX؟
نعم، يمكنك عرض صفحات محددة عن طريق تحديد رقم الصفحة في خيارات العرض.
### هل GroupDocs.Viewer لـ .NET متوافق مع كافة أطر عمل .NET؟
نعم، GroupDocs.Viewer لـ .NET متوافق مع العديد من أطر عمل .NET، بما في ذلك .NET Core و.NET Framework.
### هل يدعم GroupDocs.Viewer عرض صور CMX المشفرة؟
نعم، يدعم GroupDocs.Viewer عرض صور CMX المشفرة باستخدام مفاتيح فك التشفير المناسبة.
### هل يمكنني تخصيص خيارات العرض لتنسيقات الإخراج المختلفة؟
بالتأكيد، يوفر GroupDocs.Viewer خيارات واسعة لتخصيص معلمات العرض استنادًا إلى متطلباتك.
### هل يوجد منتدى مجتمعي لدعم GroupDocs.Viewer؟
نعم، يمكنك طلب المساعدة والتفاعل مع مجتمع GroupDocs.Viewer على منتدى الدعم [هنا](https://forum.groupdocs.com/c/viewer/9).