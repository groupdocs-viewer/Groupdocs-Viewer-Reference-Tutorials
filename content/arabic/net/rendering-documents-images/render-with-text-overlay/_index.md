---
"description": "قم بعرض المستندات بسلاسة في تطبيقات .NET باستخدام GroupDocs.Viewer، الذي يدعم تنسيقات مختلفة لتحسين تجربة المستخدم."
"linktitle": "العرض مع النص المتراكب للعرض"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "العرض مع النص المتراكب للعرض"
"url": "/ar/net/rendering-documents-images/render-with-text-overlay/"
"weight": 13
type: docs
---
# العرض مع النص المتراكب للعرض

## مقدمة
في مجال تطوير .NET، تُعدّ إدارة وعرض مختلف تنسيقات المستندات بسلاسة أمرًا بالغ الأهمية للعديد من التطبيقات. يُبرز GroupDocs.Viewer لـ .NET كحلٍّ فعّال لعرض المستندات بسهولة داخل تطبيقات .NET. سواءً كانت ملفات PDF، أو مستندات Word، أو جداول بيانات Excel، أو عروض PowerPoint التقديمية، يُبسّط GroupDocs.Viewer العملية، مُقدّمًا مجموعةً من الميزات لتحسين عرض المستندات.
## المتطلبات الأساسية
قبل الخوض في دمج GroupDocs.Viewer لـ .NET في مشاريعك، تأكد من إعداد المتطلبات الأساسية التالية:
### إعداد بيئة .NET
1. تثبيت Visual Studio: إذا لم تقم بذلك بالفعل، فقم بتنزيل Visual Studio وتثبيته من موقع Microsoft على الويب.
   
2. إنشاء مشروع .NET: افتح Visual Studio وقم بإنشاء مشروع .NET جديد أو افتح مشروعًا موجودًا حيث تريد دمج GroupDocs.Viewer.
3. .NET Framework: تأكد من أن مشروعك يستهدف إصدارًا متوافقًا من .NET Framework.
### تثبيت GroupDocs.Viewer
1. تنزيل GroupDocs.Viewer: قم بزيارة [رابط التحميل](https://releases.groupdocs.com/viewer/net/) للحصول على أحدث إصدار من GroupDocs.Viewer لـ .NET.
2. أضف GroupDocs.Viewer إلى مشروعك: استخرج الملفات التي تم تنزيلها وأضف تجميعات GroupDocs.Viewer الضرورية إلى دروس المشروع الخاصة بك.

## استيراد مساحات الأسماء
للاستفادة من وظائف GroupDocs.Viewer في تطبيق .NET الخاص بك، قم باستيراد المساحات المطلوبة:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
تأكد من الاستبدال `"Your Document Directory"` مع المسار الذي تريد تخزين صفحات المستند المُقدمة فيه.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
يحدد هذا السطر تنسيق تسمية الصفحات المعروضة. في هذا المثال، يستخدم عنصرًا نائبًا `{0}` لتمثيل رقم الصفحة.
## الخطوة 3: تهيئة كائن العارض
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // كتلة الكود
}
```
إنشاء `Viewer` الكائن عن طريق تمرير مسار المستند المراد عرضه. في هذه الحالة، `TestFiles.SAMPLE_DOCX` يمثل مسار مستند العينة.
## الخطوة 4: تعيين خيارات العرض
```csharp
PngViewOptions options = new PngViewOptions(pageFilePathFormat);
options.ExtractText = true;
```
جهّز خيارات العرض بناءً على متطلباتك. هنا، `PngViewOptions` يتم استخدامه لعرض الصفحات كصور PNG، و `ExtractText` تم ضبطه على `true` لاستخراج النص من المستند.
## الخطوة 5: عرض المستند
```csharp
viewer.View(options);
```
استدعاء `View` طريقة `Viewer` الكائن، تمرير خيارات العرض لبدء عملية العرض.
## الخطوة 6: عرض رسالة النجاح
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
بعد العرض، اعرض رسالة نجاح تشير إلى اكتمال العملية والموقع الذي يتم فيه تخزين الصفحات المعروضة.

## خاتمة
يتيح دمج GroupDocs.Viewer لـ .NET في مشاريعك آفاقًا واسعة لعرض المستندات بكفاءة. بفضل واجهة برمجة التطبيقات سهلة الاستخدام وميزاتها القوية، أصبح التعامل مع مختلف تنسيقات المستندات سلسًا، مما يُحسّن تجربة المستخدم.
## الأسئلة الشائعة
### هل GroupDocs.Viewer متوافق مع كافة تنسيقات المستندات؟
يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF، ومستندات Microsoft Office، والصور، والمزيد.
### هل يمكنني تخصيص خيارات العرض وفقًا لمتطلبات تطبيقي؟
نعم، يوفر GroupDocs.Viewer خيارات تخصيص واسعة النطاق لتكييف عملية العرض مع احتياجاتك المحددة.
### هل يوفر GroupDocs.Viewer دعمًا متعدد الأنظمة الأساسية؟
تم تصميم GroupDocs.Viewer في المقام الأول لتطبيقات .NET ولكنه يوفر أيضًا الدعم لتطبيقات Java من خلال GroupDocs.Viewer لـ Java.
### هل GroupDocs.Viewer مناسب لمعالجة المستندات على نطاق واسع؟
نعم، تم تحسين GroupDocs.Viewer للتعامل مع كميات كبيرة من المستندات بكفاءة، مما يجعله مثاليًا لتطبيقات مستوى المؤسسة.
### أين يمكنني العثور على المساعدة إذا واجهت مشكلات أثناء التكامل أو الاستخدام؟
يمكنك طلب الدعم من منتدى مجتمع GroupDocs [هنا](https://forum.groupdocs.com/c/viewer/9).