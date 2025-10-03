---
"description": "تعرّف على كيفية تعديل حجم الصورة الناتجة لرسومات CAD باستخدام GroupDocs.Viewer لـ .NET. حسّن الرؤية وسهولة الاستخدام بسهولة."
"linktitle": "ضبط حجم الصورة الناتجة لرسومات CAD"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "ضبط حجم الصورة الناتجة لرسومات CAD"
"url": "/ar/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
type: docs
---
# ضبط حجم الصورة الناتجة لرسومات CAD

## مقدمة
غالبًا ما تتطلب رسومات CAD تعديلات محددة لعرضها وعرضها بشكل مثالي. يوفر GroupDocs.Viewer لـ .NET مجموعة أدوات فعّالة لإدارة وتخصيص مخرجات رسومات CAD. في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة خلال عملية ضبط حجم الصورة الناتجة لرسومات CAD.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: قم بتنزيل GroupDocs.Viewer لـ .NET وتثبيته من [هنا](https://releases.groupdocs.com/viewer/net/).
2. دليل المستندات: قم بإعداد الدليل الذي يوجد فيه مستندك.
3. الفهم الأساسي: تعرف على المفاهيم الأساسية لبرمجة .NET.

## استيراد مساحات الأسماء
أولاً، تأكد من استيراد مساحات الأسماء الضرورية للوصول إلى وظائف GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: تعيين دليل الإخراج
قم بتحديد الدليل الذي تريد تخزين الصور الناتجة من رسومات CAD فيه:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
حدّد تنسيق مسارات ملفات الصفحات. سيُستخدم هذا التنسيق لتسمية الصفحات وحفظها كملفات HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: ضبط حجم الصورة
داخل كتلة الاستخدام لكائن العارض، اضبط حجم الصورة لرسومات CAD عن طريق تعيين الخيارات المناسبة:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## الخطوة 4: عرض دليل الإخراج
بعد تقديم المستند، اعرض رسالة تشير إلى التقديم الناجح وحدد موقع دليل الإخراج:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
يُعدّ تعديل حجم الصورة الناتجة لرسومات CAD أمرًا بالغ الأهمية لتحسين وضوحها وسهولة استخدامها. مع GroupDocs.Viewer لـ .NET، تُصبح هذه العملية مُبسّطة وفعّالة، مما يسمح لك بتخصيص الناتج وفقًا لاحتياجاتك الخاصة.
## الأسئلة الشائعة
### هل يمكنني تعديل حجم الصورة الناتجة لأنواع أخرى من المستندات بالإضافة إلى رسومات CAD؟
نعم، يدعم GroupDocs.Viewer لـ .NET أنواعًا مختلفة من المستندات، ويمكنك ضبط حجم الصورة الناتجة لمعظم تنسيقات المستندات.
### هل GroupDocs.Viewer لـ .NET متوافق مع الإصدارات المختلفة من إطار عمل .NET؟
نعم، GroupDocs.Viewer لـ .NET متوافق مع إصدارات متعددة من إطار عمل .NET، مما يضمن المرونة وسهولة الاستخدام عبر بيئات مختلفة.
### هل هناك أي خيارات ترخيص متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك استكشاف خيارات الترخيص المختلفة، بما في ذلك التراخيص المؤقتة والتراخيص التجارية، لتناسب احتياجاتك.
### هل يمكنني تخصيص تنسيق إخراج المستندات المقدمة؟
بالتأكيد، يوفر GroupDocs.Viewer لـ .NET خيارات تخصيص مختلفة، مما يسمح لك بتخصيص تنسيق الإخراج وفقًا لدروسك التعليمية.
### أين يمكنني العثور على الدعم أو المساعدة الإضافية مع GroupDocs.Viewer لـ .NET؟
يمكنك زيارة منتدى GroupDocs.Viewer [هنا](https://forum.groupdocs.com/c/viewer/9) للحصول على الدعم وطرح الأسئلة والتفاعل مع المجتمع.