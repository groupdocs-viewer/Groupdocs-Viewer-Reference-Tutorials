---
"description": "تعرّف على كيفية عرض مخطط واحد في رسومات CAD باستخدام GroupDocs.Viewer لـ .NET. خطوات سهلة لدمج سلس في تطبيقات .NET."
"linktitle": "عرض تخطيط واحد في رسومات CAD"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض تخطيط واحد في رسومات CAD"
"url": "/ar/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
type: docs
---
# عرض تخطيط واحد في رسومات CAD

## مقدمة
في مجال تطوير .NET، يُعدّ التعامل مع رسومات CAD وعرضها متطلبًا شائعًا. يُبسّط GroupDocs.Viewer لـ .NET هذه المهمة بتوفيره حلاً شاملاً لعرض رسومات CAD ضمن تطبيقات .NET. في هذا البرنامج التعليمي، سنتعمق في عرض مخطط واحد في رسومات CAD باستخدام GroupDocs.Viewer لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- فهم أساسي للغة البرمجة C# وإطار عمل .NET.
- تم تثبيت Visual Studio على نظامك.
- تم تنزيل مكتبة GroupDocs.Viewer لـ .NET وتنزيل الدروس التعليمية في مشروعك. يمكنك تنزيلها من [هنا](https://releases.groupdocs.com/viewer/net/).
- التعرف على تنسيقات ملفات CAD وبنيتها.

## استيراد مساحات الأسماء
أولاً، قم باستيراد المساحات الأساسية اللازمة إلى كود C# الخاص بك للوصول إلى وظائف GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## الخطوة 1: تحديد دليل الإخراج
حدد الدليل الذي تريد حفظ الإخراج المقدم فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
قم بتحديد تنسيق مسار الملف لكل صفحة مُقدمة.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: إنشاء كائن العارض
إنشاء مثيل لفئة Viewer المقدمة بواسطة GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## الخطوة 4: تكوين خيارات عرض HTML
قم بتكوين خيارات لعرض مخرجات HTML باستخدام الموارد المضمنة.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## الخطوة 5: تحديد اسم تخطيط CAD
حدد اسم تخطيط CAD الذي تريد تقديمه.
```csharp
options.CadOptions.LayoutName = "Model";
```
## الخطوة 6: تقديم رسم CAD
استدعاء طريقة العرض لكائن العارض باستخدام الخيارات المحددة.
```csharp
viewer.View(options);
```
## الخطوة 7: عرض رسالة النجاح
إعلام المستخدم بنجاح تقديم المستند المصدر.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
قد يكون عرض رسومات CAD، وخاصةً عند التعامل مع المخططات، مهمةً شاقة. مع ذلك، مع GroupDocs.Viewer لـ .NET، تصبح العملية سلسة وفعالة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك عرض مخطط واحد بسهولة في رسومات CAD ضمن تطبيقات .NET.
## الأسئلة الشائعة
### هل يمكنني عرض تخطيطات متعددة في وقت واحد باستخدام GroupDocs.Viewer لـ .NET؟
نعم، يدعم GroupDocs.Viewer لـ .NET عرض تخطيطات متعددة من رسومات CAD.
### هل GroupDocs.Viewer متوافق مع تنسيقات ملفات CAD المختلفة؟
بالتأكيد، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات ملفات CAD، بما في ذلك DWG وDXF وDGN والمزيد.
### هل يمكنني تخصيص خيارات العرض لرسومات CAD؟
نعم، يوفر GroupDocs.Viewer خيارات واسعة لتخصيص إعدادات العرض وفقًا لمتطلباتك.
### هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك استكشاف ميزات GroupDocs.Viewer من خلال الإصدار التجريبي المجاني المتاح [هنا](https://releases.groupdocs.com/).
### أين يمكنني الحصول على الدعم لـ GroupDocs.Viewer لـ .NET؟
لأي استفسارات أو مساعدة، يمكنك زيارة منتدى GroupDocs.Viewer [هنا](https://forum.groupdocs.com/c/viewer/9).