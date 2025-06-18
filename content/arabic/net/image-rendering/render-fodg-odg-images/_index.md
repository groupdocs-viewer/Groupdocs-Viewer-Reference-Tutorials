---
"description": "تعرّف على كيفية تحويل صور FODG وODG إلى صيغ HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET. حسّن من معالجة مستنداتك."
"linktitle": "تقديم صور FODG وODG"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تقديم صور FODG وODG"
"url": "/ar/net/image-rendering/render-fodg-odg-images/"
"weight": 15
---

# تقديم صور FODG وODG

## مقدمة
في عالم تطوير البرمجيات، يُعدّ التعامل الفعّال مع صيغ المستندات أمرًا بالغ الأهمية. GroupDocs.Viewer for .NET أداة فعّالة مُصمّمة لتبسيط عملية عرض صور FODG وODG ضمن تطبيقات .NET. سيشرح لك هذا البرنامج التعليمي الخطوات اللازمة لعرض هذه الصور بصيغ مُختلفة، مثل HTML وJPG وPNG وPDF، باستخدام GroupDocs.Viewer for .NET.

![عرض صور FODG وODG باستخدام GroupDocs.Viewer لـ .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: قم بتنزيل GroupDocs.Viewer لـ .NET وتثبيته من [هنا](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: تأكد من تثبيت .NET Framework على نظامك.
3. المعرفة الأساسية بلغة C#: ستكون المعرفة بلغة البرمجة C# مفيدة.

## استيراد مساحات الأسماء
قبل البدء بالتنفيذ، قم باستيراد المساحات الأساسية الضرورية:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## الخطوة 1: تعيين دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
يستبدل `"Your Document Directory"` مع مسار الدليل الذي تريد حفظ الصور المقدمة فيه.
## الخطوة 2: العرض إلى HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
تؤدي هذه الخطوة إلى تحويل صورة FODG إلى تنسيق HTML.
## الخطوة 3: تقديم إلى JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
هنا، يتم تقديم صورة FODG بتنسيق JPG.
## الخطوة 4: التقديم إلى PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
تؤدي هذه الخطوة إلى تحويل صورة FODG إلى تنسيق PNG.
## الخطوة 5: تقديم إلى PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
وأخيرًا، يتم تحويل صورة FODG إلى تنسيق PDF.

## خاتمة
في هذا البرنامج التعليمي، استكشفنا كيفية عرض صور FODG وODG بتنسيقات مختلفة باستخدام GroupDocs.Viewer لـ .NET. باتباع هذه الخطوات، يمكنك دمج إمكانيات عرض المستندات بسلاسة في تطبيقات .NET.
## الأسئلة الشائعة
### هل GroupDocs.Viewer لـ .NET متوافق مع كافة إصدارات .NET Framework؟
يعد GroupDocs.Viewer لـ .NET متوافقًا مع مجموعة واسعة من إصدارات .NET Framework، بما في ذلك الإصدارات الأحدث.
### هل يمكنني عرض المستندات بشكل غير متزامن باستخدام GroupDocs.Viewer لـ .NET؟
نعم، يوفر GroupDocs.Viewer لـ .NET إمكانيات عرض غير متزامنة لتحسين الأداء.
### هل يدعم GroupDocs.Viewer لـ .NET عرض المستندات المشفرة؟
نعم، يدعم GroupDocs.Viewer لـ .NET عرض المستندات المشفرة باستخدام مفاتيح فك التشفير المناسبة.
### هل من الممكن تخصيص مخرجات العرض باستخدام GroupDocs.Viewer لـ .NET؟
بالتأكيد، يوفر GroupDocs.Viewer لـ .NET خيارات تخصيص مختلفة لتخصيص مخرجات العرض وفقًا لمتطلباتك.
### هل يمكنني عرض المستندات من مواقع التخزين البعيدة باستخدام GroupDocs.Viewer لـ .NET؟
نعم، يدعم GroupDocs.Viewer لـ .NET عرض المستندات من مواقع التخزين المحلية والبعيدة.