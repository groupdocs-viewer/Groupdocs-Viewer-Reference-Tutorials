---
title: تقديم ملفات CHM
linktitle: تقديم ملفات CHM
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض ملفات CHM في .NET باستخدام GroupDocs.Viewer. قم بتحويل CHM إلى تنسيقات HTML وJPG وPNG وPDF دون عناء.
weight: 10
url: /ar/net/rendering-web-documents/render-chm/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية عرض ملفات CHM (تعليمات HTML المترجمة) باستخدام GroupDocs.Viewer لـ .NET. GroupDocs.Viewer for .NET عبارة عن واجهة برمجة تطبيقات قوية لعرض المستندات تسمح للمطورين بعرض أكثر من 170 نوعًا من المستندات داخل تطبيقات .NET الخاصة بهم دون الحاجة إلى أي عمليات تثبيت خارجية للبرامج.

## المتطلبات الأساسية

قبل أن نتعمق في عرض ملفات CHM، تأكد من أن لديك المتطلبات الأساسية التالية:

### تثبيت GroupDocs.Viewer لـ .NET

 للبدء، تحتاج إلى تثبيت GroupDocs.Viewer لـ .NET. يمكنك تحميل المكتبة من[موقع مستندات المجموعة](https://releases.groupdocs.com/viewer/net/) أو قم بتثبيته عبر NuGet Package Manager عن طريق تشغيل الأمر التالي في وحدة تحكم إدارة الحزم:

```bash
Install-Package GroupDocs.Viewer
```

## استيراد مساحات الأسماء

تأكد من استيراد مساحات الأسماء الضرورية إلى مشروعك:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن دعونا نقسم عملية العرض إلى خطوات متعددة:

## الخطوة 1: تحديد دليل الإخراج

حدد الدليل الذي تريد حفظ الملفات المقدمة فيه:

```csharp
string outputDirectory = "Your Document Directory";
```

## الخطوة 2: تقديم إلى HTML

لعرض ملفات CHM إلى HTML، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // اضبط على "صحيح" لتحويل محتوى آلية تبادل المعلومات بالكامل إلى صفحة واحدة

    viewer.View(options); //تحويل كافة الصفحات
}
```

## الخطوة 3: تقديم إلى JPG

لتحويل ملفات CHM إلى صور JPG، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // تحويل الصفحات 1، 2، 3 فقط
}
```

## الخطوة 4: تقديم إلى PNG

لتحويل ملفات CHM إلى صور PNG، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // تحويل الصفحات 1، 2، 3 فقط
}
```

## الخطوة 5: تقديم إلى PDF

لتقديم ملفات CHM إلى مستند PDF، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //تحويل كافة الصفحات
}
```

## الخطوة 6: التحقق من الإخراج

بمجرد اكتمال عملية العرض، تحقق من دليل الإخراج المحدد للملفات المقدمة:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة

يعد عرض ملفات CHM باستخدام GroupDocs.Viewer لـ .NET عملية مباشرة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحويل مستندات آلية تبادل المعلومات (CHM) بكفاءة إلى تنسيقات مختلفة مثل HTML والصور (JPG وPNG) وPDF ضمن تطبيقات .NET الخاصة بك.

## الأسئلة الشائعة

### س1: هل يمكن لـ GroupDocs.Viewer عرض تنسيقات المستندات الأخرى بخلاف آلية تبادل المعلومات؟

ج1: نعم، يدعم GroupDocs.Viewer عرض أكثر من 170 تنسيقًا للمستندات بما في ذلك PDF وDOCX وXLSX وPPTX والمزيد.

### س2: هل GroupDocs.Viewer متوافق مع .NET Core؟

ج2: نعم، يدعم GroupDocs.Viewer .NET Core بالإضافة إلى .NET Framework التقليدي.

### س3: هل يمكنني تخصيص خيارات العرض لتنسيقات الإخراج المختلفة؟

ج3: نعم، يوفر GroupDocs.Viewer خيارات متنوعة لتخصيص عملية العرض، مثل تحديد أرقام الصفحات، وتعيين جودة الصورة، وتكوين مسارات الإخراج.

### س 4: هل يتطلب GroupDocs.Viewer أي تبعيات خارجية لعرض المستندات؟

ج4: لا، GroupDocs.Viewer عبارة عن مكتبة مستقلة ولا تتطلب أي تبعيات خارجية أو عمليات تثبيت برامج تابعة لجهة خارجية.

### س5: هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer؟

 ج5: نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من GroupDocs.Viewer من خلال زيارة[موقع إلكتروني](https://releases.groupdocs.com/).