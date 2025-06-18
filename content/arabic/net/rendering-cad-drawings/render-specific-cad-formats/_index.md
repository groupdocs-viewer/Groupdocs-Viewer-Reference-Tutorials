---
"description": "تعرف على كيفية عرض تنسيقات CAD المحددة مثل CF2 إلى HTML وJPG وPNG وPDF باستخدام Groupdocs.Viewer لـ .NET."
"linktitle": "تنسيقات CAD الخاصة بالعرض (CF2)"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تنسيقات CAD الخاصة بالعرض (CF2)"
"url": "/ar/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# تنسيقات CAD الخاصة بالعرض (CF2)

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية عرض صيغ CAD محددة باستخدام Groupdocs.Viewer لـ .NET. Groupdocs.Viewer هي واجهة برمجة تطبيقات فعّالة لعرض المستندات، تتيح للمطورين عرض أكثر من 170 نوعًا من المستندات في تطبيقاتهم دون الحاجة إلى تثبيت أي برامج خارجية. سنركز تحديدًا على عرض صيغ CAD، مثل CF2، إلى صيغ إخراج متنوعة مثل HTML وJPG وPNG وPDF.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Visual Studio على نظامك.
- Groupdocs.Viewer لـ .NET SDK. يمكنك تنزيله من [هنا](https://releases.groupdocs.com/viewer/net/).
- المعرفة الأساسية بلغة البرمجة C#.
## استيراد مساحات الأسماء
أولاً، دعنا نستورد مساحات الأسماء الضرورية المطلوبة لعرض تنسيقات CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
الآن، دعونا نقسم كل مثال إلى خطوات متعددة:
## تحويل CF2 إلى HTML
### الخطوة 1: قم بتحديد دليل الإخراج الذي سيتم حفظ HTML المُقدم فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
### الخطوة 2: قم بتحديد تنسيق مسار الملف لإخراج HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### الخطوة 3: قم بتهيئة كائن العارض وتحديد ملف CF2 المدخل.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // تعيين خيارات عرض إضافية إذا لزم الأمر
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## تحويل CF2 إلى JPG
### الخطوة 1: قم بتحديد تنسيق مسار الملف لإخراج JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### الخطوة 2: قم بتهيئة كائن العارض وتحديد ملف CF2 المدخل.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // تعيين خيارات عرض إضافية إذا لزم الأمر
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## تحويل CF2 إلى PNG

### الخطوة 1: قم بتحديد تنسيق مسار الملف لإخراج PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### الخطوة 2: قم بتهيئة كائن العارض وتحديد ملف CF2 المدخل.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // تعيين خيارات عرض إضافية إذا لزم الأمر
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## تحويل CF2 إلى PDF
### الخطوة 1: قم بتحديد تنسيق مسار الملف لإخراج PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### الخطوة 2: قم بتهيئة كائن العارض وتحديد ملف CF2 المدخل.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // تعيين خيارات عرض إضافية إذا لزم الأمر
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية عرض صيغ CAD محددة، مثل CF2، باستخدام Groupdocs.Viewer لـ .NET. باتباع هذا الدليل المفصل، يمكنك بسهولة دمج إمكانيات عرض المستندات في تطبيقات .NET.
## الأسئلة الشائعة
### هل يمكن لـ Groupdocs.Viewer عرض تنسيقات CAD أخرى غير CF2؟
نعم، يدعم Groupdocs.Viewer مجموعة واسعة من تنسيقات CAD، بما في ذلك DWG، وDXF، وDGN، والمزيد.
### هل Groupdocs.Viewer مناسب لعرض المستندات في تطبيقات الويب؟
بالتأكيد، يمكن دمج Groupdocs.Viewer بسلاسة في تطبيقات الويب لعرض المستندات مباشرة في المتصفح.
### هل يتطلب Groupdocs.Viewer أي اعتماديات خارجية للرسم؟
لا، Groupdocs.Viewer عبارة عن واجهة برمجة تطبيقات مستقلة ولا تتطلب أي تبعيات خارجية أو تثبيتات برامج.
### هل يمكنني تخصيص خيارات العرض وفقًا لمتطلباتي؟
نعم، يوفر Groupdocs.Viewer خيارات عرض مختلفة يمكن تخصيصها لتلبية احتياجاتك المحددة.
### هل هناك نسخة تجريبية متاحة لـ Groupdocs.Viewer؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Groupdocs.Viewer من [هنا](https://releases.groupdocs.com/).