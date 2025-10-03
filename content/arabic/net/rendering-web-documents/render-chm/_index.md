---
"description": "تعرّف على كيفية عرض ملفات CHM في .NET باستخدام GroupDocs.Viewer. حوّل CHM إلى صيغ HTML وJPG وPNG وPDF بسهولة."
"linktitle": "عرض ملفات CHM"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض ملفات CHM"
"url": "/ar/net/rendering-web-documents/render-chm/"
"weight": 10
type: docs
---
# عرض ملفات CHM

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية عرض ملفات CHM (تعليمات HTML المُجمّعة) باستخدام GroupDocs.Viewer لـ .NET. GroupDocs.Viewer لـ .NET هي واجهة برمجة تطبيقات فعّالة لعرض المستندات، تُمكّن المطورين من عرض أكثر من 170 نوعًا من المستندات ضمن تطبيقات .NET الخاصة بهم دون الحاجة إلى تثبيت أي برامج خارجية.

## المتطلبات الأساسية

قبل أن نتعمق في تقديم ملفات CHM، تأكد من أن لديك المتطلبات الأساسية التالية:

### تثبيت GroupDocs.Viewer لـ .NET

للبدء، عليك تثبيت GroupDocs.Viewer لـ .NET. يمكنك تنزيل المكتبة من [موقع GroupDocs](https://releases.groupdocs.com/viewer/net/) أو قم بتثبيته عبر مدير الحزم NuGet عن طريق تشغيل الأمر التالي في وحدة التحكم في مدير الحزم:

```bash
Install-Package GroupDocs.Viewer
```

## استيراد مساحات الأسماء

تأكد من استيراد المساحات الأساسية اللازمة إلى مشروعك:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن دعونا نقسم عملية العرض إلى خطوات متعددة:

## الخطوة 1: تحديد دليل الإخراج

قم بتحديد الدليل الذي تريد حفظ الملفات المقدمة فيه:

```csharp
string outputDirectory = "Your Document Directory";
```

## الخطوة 2: العرض إلى HTML

لتحويل ملفات CHM إلى HTML، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // اضبط على "صحيح" لتحويل كل محتوى CHM إلى صفحة واحدة

    viewer.View(options); // تحويل جميع الصفحات
}
```

## الخطوة 3: تقديم إلى JPG

لتحويل ملفات CHM إلى صور JPG، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // تحويل الصفحات 1 و2 و3 فقط
}
```

## الخطوة 4: التقديم إلى PNG

لتحويل ملفات CHM إلى صور PNG، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // تحويل الصفحات 1 و2 و3 فقط
}
```

## الخطوة 5: تقديم إلى PDF

لتحويل ملفات CHM إلى مستند PDF، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // تحويل جميع الصفحات
}
```

## الخطوة 6: التحقق من الناتج

بمجرد اكتمال عملية العرض، تحقق من دليل الإخراج المحدد للملفات المقدمة:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة

عرض ملفات CHM باستخدام GroupDocs.Viewer لـ .NET عملية سهلة وبسيطة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحويل مستندات CHM بكفاءة إلى صيغ مختلفة، مثل HTML والصور (JPG وPNG) وPDF، وذلك ضمن تطبيقات .NET.

## الأسئلة الشائعة

### س1: هل يمكن لـ GroupDocs.Viewer عرض تنسيقات مستندات أخرى غير CHM؟

ج1: نعم، يدعم GroupDocs.Viewer عرض أكثر من 170 تنسيقًا للمستندات بما في ذلك PDF وDOCX وXLSX وPPTX والمزيد.

### س2: هل GroupDocs.Viewer متوافق مع .NET Core؟

ج2: نعم، يدعم GroupDocs.Viewer .NET Core بالإضافة إلى .NET Framework التقليدي.

### س3: هل يمكنني تخصيص خيارات العرض لتنسيقات الإخراج المختلفة؟

ج3: نعم، يوفر GroupDocs.Viewer خيارات مختلفة لتخصيص عملية العرض، مثل تحديد أرقام الصفحات، وتعيين جودة الصورة، وتكوين مسارات الإخراج.

### س4: هل يتطلب GroupDocs.Viewer أي اعتماديات خارجية لعرض المستندات؟

ج4: لا، GroupDocs.Viewer هي مكتبة مستقلة ولا تتطلب أي تبعيات خارجية أو تثبيتات برامج تابعة لجهات خارجية.

### س5: هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer؟

ج5: نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من GroupDocs.Viewer من خلال زيارة [موقع إلكتروني](https://releases.groupdocs.com/).