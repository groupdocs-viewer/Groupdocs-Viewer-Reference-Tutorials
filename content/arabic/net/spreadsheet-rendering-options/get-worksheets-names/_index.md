---
"description": "استكشف روعة GroupDocs.Viewer لـ .NET - دمج عرض المستندات بسلاسة في تطبيقاتك. جرّب النسخة التجريبية المجانية الآن!"
"linktitle": "الحصول على أسماء أوراق العمل"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "الحصول على أسماء أوراق العمل"
"url": "/ar/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# الحصول على أسماء أوراق العمل

## مقدمة
أهلاً بكم في عالم GroupDocs.Viewer الرائع لـ .NET! إذا كنت مطوراً أو شغوفاً باستكشاف إمكانيات عرض المستندات الفعّالة في تطبيقات .NET، فأنت على موعد مع تجربة شيّقة. في هذا الدليل الشامل، سنتناول تفاصيل استرجاع أسماء أوراق العمل باستخدام GroupDocs.Viewer. لذا، استعدوا وانطلقوا في هذه الرحلة الشيقة!
## المتطلبات الأساسية
قبل أن نتعمق في سحر البرمجة، دعنا نتأكد من إعداد كل شيء:
1. قم بتثبيت GroupDocs.Viewer لـ .NET: توجه إلى [رابط التحميل](https://releases.groupdocs.com/viewer/net/) للحصول على أحدث إصدار من GroupDocs.Viewer لـ .NET. اتبع تعليمات التثبيت لدمجه بسلاسة في بيئة التطوير الخاصة بك.
2. جهز مستندك: تأكد من أن لديك مستندًا مستهدفًا، على سبيل المثال ملف Excel باسم "file.xlsx"، في دليل المستند المخصص لك.
## استيراد مساحات الأسماء
بعد أن أصبحت المتطلبات الأساسية جاهزة، لنبدأ باستيراد مساحات الأسماء اللازمة. هذا يضمن تعرّف تطبيقك على وظائف GroupDocs.Viewer لـ .NET واستخدامها.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. إعداد دليل المستندات
```csharp
string outputDirectory = "Your Document Directory";
```
استبدل "دليل المستندات الخاص بك" بالمسار إلى الدليل الذي يوجد فيه المستند المستهدف.
## 2. تهيئة العارض
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
في هذه الخطوة، نقوم بإنشاء مثيل لفئة Viewer، مما يوفر المسار إلى ملف Excel الخاص بك.
## 3. تكوين خيارات عرض المعلومات
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
هنا، قمنا بتكوين ViewInfoOptions لتوليد عروض HTML وتعيين خيارات إضافية لعرض جدول البيانات.
## 4. استرجاع معلومات العرض
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
استخدم مثيل العارض لاسترداد معلومات العرض استنادًا إلى الخيارات التي تم تكوينها.
## 5. عرض أسماء أوراق العمل
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
قم بالتنقل بين الصفحات المسترجعة وطباعة اسم كل ورقة عمل في وحدة التحكم.
## خاتمة
تهانينا! لقد نجحت في عملية جلب أسماء أوراق العمل باستخدام GroupDocs.Viewer لـ .NET. هذا يفتح آفاقًا واسعة لتحسين وظائف عرض المستندات في تطبيقاتك.
## الأسئلة الشائعة
### هل يمكنني استخدام GroupDocs.Viewer لـ .NET مع تنسيقات مستندات أخرى؟
بالتأكيد! يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF وMicrosoft Office وغيرها.
### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك استكشاف GroupDocs.Viewer لـ .NET باستخدام [نسخة تجريبية مجانية](https://releases.groupdocs.com/).
### أين يمكنني العثور على الدعم الإضافي؟
توجه إلى [منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) لدعم المجتمع والمناقشات.
### هل يمكنني الحصول على ترخيص مؤقت؟
بالتأكيد! قم بزيارة [هذا الرابط](https://purchase.groupdocs.com/temporary-license/) للحصول على رخصتك المؤقتة.
### هل تتوفر مصادر توثيقية مفصلة؟
بالتأكيد! تحقق من [الوثائق الرسمية](https://tutorials.groupdocs.com/viewer/net/) للحصول على معلومات وإرشادات متعمقة.