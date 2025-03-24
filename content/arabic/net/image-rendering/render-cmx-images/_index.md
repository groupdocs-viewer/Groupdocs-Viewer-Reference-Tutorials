---
title: تقديم صور CMX
linktitle: تقديم صور CMX
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض صور CMX إلى تنسيقات مختلفة بسهولة باستخدام GroupDocs.Viewer لـ .NET. تعزيز إدارة المستندات الخاصة بك.
weight: 13
url: /ar/net/image-rendering/render-cmx-images/
---
## مقدمة
في مجال إدارة المستندات ومعالجتها، يعد عرض الصور من تنسيقات مختلفة مهمة محورية. يعمل GroupDocs.Viewer for .NET على تبسيط هذه العملية من خلال توفير وظائف شاملة لعرض صور CMX في تنسيقات مختلفة مثل HTML وJPG وPNG وPDF. سيرشدك هذا البرنامج التعليمي خلال عملية عرض صور CMX خطوة بخطوة باستخدام GroupDocs.Viewer لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  GroupDocs.Viewer لمكتبة .NET: قم بتنزيل وتثبيت GroupDocs.Viewer لمكتبة .NET من[هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: تمتع ببيئة تطوير عمل تم إعدادها باستخدام .NET Framework.
3. ملف صورة CMX: احصل على ملف صورة CMX الذي ترغب في عرضه.

## استيراد مساحات الأسماء
قبل المتابعة، تأكد من استيراد مساحات الأسماء الضرورية للوصول إلى وظائف GroupDocs.Viewer في تطبيق .NET الخاص بك:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## التقديم إلى HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- تحديد دليل الإخراج: قم بتعيين الدليل الذي تريد تخزين ملفات HTML المقدمة فيه.
- تحديد تنسيق مسار الملف: تحديد تنسيق ملفات HTML الإخراج.
- إنشاء كائن عارض: قم بإنشاء مثيل لفئة العارض باستخدام ملف صورة CMX.
- خيارات عرض HTML: قم بتكوين خيارات عرض HTML، مثل تضمين الموارد.
- تقديم CMX إلى HTML: قم باستدعاء طريقة العرض لكائن العارض لعرض صورة CMX إلى HTML.
## التقديم إلى JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- تحديد دليل الإخراج: قم بتعيين الدليل لتخزين ملفات JPG المقدمة.
- تحديد تنسيق مسار الملف: تحديد تنسيق ملفات JPG الناتجة.
- إنشاء كائن عارض: قم بإنشاء مثيل لفئة العارض باستخدام ملف صورة CMX.
- خيارات عرض JPG: قم بتكوين خيارات عرض JPG.
- تقديم CMX إلى JPG: قم باستدعاء طريقة العرض لكائن العارض لعرض صورة CMX إلى JPG.
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
- تحديد تنسيق مسار الملف: تحديد تنسيق ملفات PNG الناتجة.
- إنشاء كائن عارض: قم بإنشاء مثيل لفئة العارض باستخدام ملف صورة CMX.
- خيارات عرض PNG: تكوين خيارات عرض PNG.
- تقديم CMX إلى PNG: قم باستدعاء طريقة العرض لكائن العارض لعرض صورة CMX إلى PNG.
## التقديم إلى PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- تحديد دليل الإخراج: قم بتعيين الدليل لتخزين ملف PDF المقدم.
- تحديد تنسيق مسار الملف: تحديد تنسيق ملف PDF الناتج.
- إنشاء كائن عارض: قم بإنشاء مثيل لفئة العارض باستخدام ملف صورة CMX.
- خيارات عرض PDF: تكوين خيارات عرض PDF.
- تقديم CMX إلى PDF: قم باستدعاء طريقة العرض لكائن العارض لعرض صورة CMX إلى PDF.

## خاتمة
في الختام، يقدم GroupDocs.Viewer for .NET حلاً قويًا لعرض صور CMX إلى تنسيقات مختلفة بسلاسة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة دمج إمكانات عرض صور CMX في تطبيقات .NET الخاصة بك، مما يعزز كفاءة إدارة المستندات.
## الأسئلة الشائعة
### هل يمكنني عرض صفحات معينة من صورة CMX؟
نعم، يمكنك عرض صفحات معينة عن طريق تحديد رقم الصفحة في خيارات العرض.
### هل يتوافق GroupDocs.Viewer for .NET مع جميع أطر عمل .NET؟
نعم، يتوافق GroupDocs.Viewer for .NET مع أطر عمل .NET المتعددة، بما في ذلك .NET Core و.NET Framework.
### هل يدعم GroupDocs.Viewer عرض صور CMX المشفرة؟
نعم، يدعم GroupDocs.Viewer عرض صور CMX المشفرة باستخدام مفاتيح فك التشفير المناسبة.
### هل يمكنني تخصيص خيارات العرض لتنسيقات الإخراج المختلفة؟
بالتأكيد، يوفر GroupDocs.Viewer خيارات واسعة لتخصيص معلمات العرض بناءً على متطلباتك.
### هل يوجد منتدى مجتمعي لدعم GroupDocs.Viewer؟
 نعم، يمكنك طلب المساعدة والتفاعل مع مجتمع GroupDocs.Viewer في منتدى الدعم[هنا](https://forum.groupdocs.com/c/viewer/9).