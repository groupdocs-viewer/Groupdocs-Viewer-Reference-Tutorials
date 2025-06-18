---
"description": "تعرف على كيفية دمج Groupdocs.Viewer لـ .NET في تطبيقاتك لعرض المستندات وقلبها وتدويرها بسلاسة."
"linktitle": "قلب وتدوير الصفحات"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "قلب وتدوير الصفحات"
"url": "/ar/net/rendering-options/flip-rotate-pages/"
"weight": 12
---

# قلب وتدوير الصفحات

## مقدمة
في هذا البرنامج التعليمي، سنتعمق في وظائف Groupdocs.Viewer لـ .NET، مع التركيز تحديدًا على قلب الصفحات وتدويرها. يُعد Groupdocs.Viewer لـ .NET أداة فعّالة مصممة لعرض المستندات بتنسيقات مختلفة داخل تطبيقات .NET. سواء كنت تُطوّر نظام إدارة مستندات أو تحتاج إلى دمج إمكانيات عرض المستندات في برنامجك، فإن Groupdocs.Viewer لـ .NET يُوفر حلاً فعّالاً.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من إعداد المتطلبات الأساسية التالية:
### تثبيت Groupdocs.Viewer لـ .NET
لاستخدام Groupdocs.Viewer لـ .NET، يجب تثبيت الحزمة عبر مدير حزم NuGet. يمكنك العثور على تعليمات التثبيت المفصلة في [التوثيق](https://tutorials.groupdocs.com/viewer/net/).

## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في مشروعك لاستخدام Groupdocs.Viewer لـ .NET بشكل فعال.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

دعنا نقسم عملية قلب وتدوير الصفحات باستخدام Groupdocs.Viewer لـ .NET إلى خطوات بسيطة:
## الخطوة 1: تعيين دليل الإخراج ومسار الملف
قم بتحديد الدليل الذي تريد حفظ ملف الإخراج فيه وحدد مسار ملف الإخراج.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## الخطوة 2: تهيئة كائن العارض
قم بإنشاء مثيل لفئة Viewer عن طريق تمرير المسار إلى المستند الذي تريد عرضه.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## الخطوة 3: تكوين خيارات العرض
قم بإعداد خيارات العرض، مثل تحديد تنسيق ملف الإخراج وأي إعدادات إضافية مثل تدوير الصفحة.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## الخطوة 4: عرض المستند
استدعاء طريقة العرض لكائن العارض ومرر خيارات العرض.
```csharp
viewer.View(viewOptions);
```
## الخطوة 5: عرض رسالة النجاح
أبلغ المستخدم بأن المستند تم عرضه بنجاح وحدد دليل الإخراج للتحقق منه.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
في الختام، يوفر Groupdocs.Viewer لـ .NET إمكانيات فعّالة لعرض المستندات، بما في ذلك قلب الصفحات وتدويرها. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج هذه الميزات بسلاسة في تطبيقات .NET، مما يُحسّن تجربة عرض المستندات للمستخدمين.
## الأسئلة الشائعة
### هل Groupdocs.Viewer لـ .NET متوافق مع كافة تنسيقات المستندات؟
نعم، يدعم Groupdocs.Viewer لـ .NET مجموعة واسعة من تنسيقات المستندات، بما في ذلك DOCX، وPDF، وPPTX، والمزيد.
### هل يمكنني تخصيص خيارات العرض بخلاف تقليب الصفحات وتدويرها؟
بالتأكيد، يوفر Groupdocs.Viewer لـ .NET خيارات تخصيص مختلفة لعرض المستندات، مما يسمح لك بتخصيص التجربة وفقًا لمتطلباتك.
### هل هناك نسخة تجريبية مجانية متاحة لـ Groupdocs.Viewer لـ .NET؟
نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Groupdocs.Viewer لـ .NET من خلال زيارة [موقع إلكتروني](https://releases.groupdocs.com/).
### كيف يمكنني الحصول على الدعم لـ Groupdocs.Viewer لـ .NET؟
يمكنك طلب المساعدة والتفاعل مع المجتمع من خلال [منتدى Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### أين يمكنني الحصول على ترخيص مؤقت لـ Groupdocs.Viewer لـ .NET؟
يمكن الحصول على التراخيص المؤقتة لـ Groupdocs.Viewer لـ .NET من [صفحة الشراء](https://purchase.groupdocs.com/temporary-license/).