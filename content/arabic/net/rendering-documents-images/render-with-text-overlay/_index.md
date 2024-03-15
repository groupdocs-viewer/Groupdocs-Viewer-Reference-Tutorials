---
title: تقديم مع النص المتراكب للعرض
linktitle: تقديم مع النص المتراكب للعرض
second_title: GroupDocs.Viewer .NET API
description: قم بعرض المستندات بسلاسة في تطبيقات .NET باستخدام GroupDocs.Viewer، الذي يدعم التنسيقات المختلفة لتحسين تجربة المستخدم.
type: docs
weight: 13
url: /ar/net/rendering-documents-images/render-with-text-overlay/
---
## مقدمة
في مجال تطوير .NET، تعد إدارة وعرض تنسيقات المستندات المختلفة بسلاسة أمرًا بالغ الأهمية للعديد من التطبيقات. يظهر GroupDocs.Viewer for .NET كحل قوي لعرض المستندات بسهولة داخل تطبيقات .NET الخاصة بك. سواء أكان ذلك ملفات PDF أو مستندات Word أو جداول بيانات Excel أو عروض PowerPoint التقديمية، فإن GroupDocs.Viewer يبسط العملية، ويقدم مجموعة من الميزات لتحسين عرض المستندات.
## المتطلبات الأساسية
قبل الخوض في دمج GroupDocs.Viewer لـ .NET في مشاريعك، تأكد من إعداد المتطلبات الأساسية التالية:
### إعداد بيئة .NET
1. تثبيت Visual Studio: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيل Visual Studio وتثبيته من موقع Microsoft على الويب.
   
2. إنشاء مشروع .NET: افتح Visual Studio وقم بإنشاء مشروع .NET جديد أو افتح مشروعًا موجودًا حيث تريد دمج GroupDocs.Viewer.
3. .NET Framework: تأكد من أن مشروعك يستهدف إصدارًا متوافقًا من .NET Framework.
### تثبيت GroupDocs.Viewer
1.  تنزيل GroupDocs.Viewer: قم بزيارة[رابط التحميل](https://releases.groupdocs.com/viewer/net/) للحصول على أحدث إصدار من GroupDocs.Viewer لـ .NET.
2. أضف GroupDocs.Viewer إلى مشروعك: استخرج الملفات التي تم تنزيلها وأضف مجموعات GroupDocs.Viewer الضرورية إلى مراجع مشروعك.

## استيراد مساحات الأسماء
للاستفادة من وظائف GroupDocs.Viewer في تطبيق .NET الخاص بك، قم باستيراد مساحات الأسماء المطلوبة:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
 تأكد من الاستبدال`"Your Document Directory"` بالمسار الذي تريد تخزين صفحات المستند المعروضة فيه.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
 يحدد هذا السطر تنسيق تسمية الصفحات المعروضة. في هذا المثال، يستخدم عنصرًا نائبًا`{0}` لتمثيل رقم الصفحة.
## الخطوة 3: تهيئة كائن العارض
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // كتلة التعليمات البرمجية
}
```
 إنشاء`Viewer`الكائن عن طريق تمرير مسار المستند المراد عرضه. في هذه الحالة،`TestFiles.SAMPLE_DOCX` يمثل مسار المستند النموذجي.
## الخطوة 4: تعيين خيارات العرض
```csharp
PngViewOptions options = new PngViewOptions(pageFilePathFormat);
options.ExtractText = true;
```
 قم بتكوين خيارات العرض بناءً على متطلباتك. هنا،`PngViewOptions` يستخدم لعرض الصفحات كصور PNG، و`ExtractText` تم ضبطه على`true` لاستخراج النص من الوثيقة.
## الخطوة 5: تقديم الوثيقة
```csharp
viewer.View(options);
```
 استدعاء`View` طريقة`Viewer` الكائن، وتمرير خيارات العرض لبدء عملية العرض.
## الخطوة 6: عرض رسالة النجاح
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
بعد العرض، قم بعرض رسالة نجاح تشير إلى اكتمال العملية والموقع الذي تم تخزين الصفحات المعروضة فيه.

## خاتمة
يؤدي دمج GroupDocs.Viewer لـ .NET في مشروعاتك إلى فتح عالم من الإمكانيات لعرض المستندات بكفاءة. بفضل واجهة برمجة التطبيقات البديهية والميزات القوية، يصبح التعامل مع تنسيقات المستندات المختلفة سلسًا، مما يعزز تجربة المستخدم.
## الأسئلة الشائعة
### هل GroupDocs.Viewer متوافق مع جميع تنسيقات المستندات؟
يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF ومستندات Microsoft Office والصور والمزيد.
### هل يمكنني تخصيص خيارات العرض وفقًا لمتطلبات تطبيقي؟
نعم، يوفر GroupDocs.Viewer خيارات تخصيص واسعة النطاق لتخصيص عملية العرض وفقًا لاحتياجاتك المحددة.
### هل يقدم GroupDocs.Viewer دعمًا عبر الأنظمة الأساسية؟
تم تصميم GroupDocs.Viewer بشكل أساسي لتطبيقات .NET ولكنه يوفر أيضًا دعمًا لتطبيقات Java من خلال GroupDocs.Viewer لـ Java.
### هل GroupDocs.Viewer مناسب لمعالجة المستندات على نطاق واسع؟
نعم، تم تحسين GroupDocs.Viewer للتعامل مع كميات كبيرة من المستندات بكفاءة، مما يجعله مثاليًا للتطبيقات على مستوى المؤسسة.
### أين يمكنني الحصول على المساعدة إذا واجهت مشكلات أثناء التكامل أو الاستخدام؟
 يمكنك طلب الدعم من منتدى مجتمع GroupDocs[هنا](https://forum.groupdocs.com/c/viewer/9).