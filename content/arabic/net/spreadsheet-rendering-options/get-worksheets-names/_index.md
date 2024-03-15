---
title: الحصول على أسماء أوراق العمل
linktitle: الحصول على أسماء أوراق العمل
second_title: GroupDocs.Viewer .NET API
description: اكتشف سحر GroupDocs.Viewer لـ .NET - قم بدمج عرض المستندات في تطبيقاتك بسلاسة. جرب النسخة التجريبية المجانية الآن!
type: docs
weight: 11
url: /ar/net/spreadsheet-rendering-options/get-worksheets-names/
---
## مقدمة
مرحبًا بك في عالم GroupDocs.Viewer الرائع لـ .NET! إذا كنت مطورًا أو متحمسًا لاستكشاف إمكانيات عرض المستندات القوية ضمن تطبيقات .NET الخاصة بك، فأنت في المكان المناسب. في هذا الدليل الشامل، سوف نتعمق في تعقيدات استرداد أسماء أوراق العمل باستخدام GroupDocs.Viewer. لذا، اربط حزام الأمان ودعنا نبدأ هذه الرحلة المثيرة!
## المتطلبات الأساسية
قبل أن نتعمق في سحر البرمجة، دعونا نتأكد من إعداد كل شيء لديك:
1.  قم بتثبيت GroupDocs.Viewer لـ .NET: توجه إلى[رابط التحميل](https://releases.groupdocs.com/viewer/net/)للحصول على أحدث إصدار من GroupDocs.Viewer لـ .NET. اتبع تعليمات التثبيت لدمجها بسلاسة في بيئة التطوير الخاصة بك.
2. جهّز المستند الخاص بك: تأكد من أن لديك مستندًا مستهدفًا، لنفترض ملف Excel باسم "file.xlsx" في دليل المستندات المخصص لك.
## استيراد مساحات الأسماء
الآن بعد أن أصبحت لديك المتطلبات الأساسية، فلنبدأ الأمور عن طريق استيراد مساحات الأسماء الضرورية. وهذا يضمن أن تطبيقك يتعرف على الوظائف التي يوفرها GroupDocs.Viewer لـ .NET ويمكنه الاستفادة منها.
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
استبدل "دليل المستندات الخاص بك" بالمسار إلى الدليل الذي يوجد به المستند المستهدف.
## 2. تهيئة العارض
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
في هذه الخطوة، نقوم بإنشاء مثيل لفئة Viewer، وتوفير المسار إلى ملف Excel الخاص بك.
## 3. تكوين خيارات عرض المعلومات
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
هنا، نقوم بتكوين ViewInfoOptions لإنشاء عروض HTML وتعيين خيارات إضافية لعرض جدول البيانات.
## 4. استرجاع معلومات العرض
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
استخدم مثيل العارض لاسترداد معلومات العرض بناءً على الخيارات التي تم تكوينها.
## 5. عرض أسماء أوراق العمل
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
قم بالمراجعة عبر الصفحات المستردة واطبع اسم كل ورقة عمل إلى وحدة التحكم.
## خاتمة
تهانينا! لقد نجحت في التنقل عبر عملية جلب أسماء أوراق العمل باستخدام GroupDocs.Viewer لـ .NET. ويفتح هذا عددًا لا يحصى من الإمكانيات لتحسين وظائف عرض المستندات داخل تطبيقاتك.
## الأسئلة الشائعة
### هل يمكنني استخدام GroupDocs.Viewer لـ .NET مع تنسيقات المستندات الأخرى؟
قطعاً! يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF وMicrosoft Office والمزيد.
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك استكشاف GroupDocs.Viewer لـ .NET من خلال موقعنا[تجربة مجانية](https://releases.groupdocs.com/).
### أين يمكنني العثور على دعم إضافي؟
 توجه إلى[منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) لدعم المجتمع والمناقشات.
### هل يمكنني الحصول على ترخيص مؤقت؟
 بالتأكيد! يزور[هذا الرابط](https://purchase.groupdocs.com/temporary-license/) للحصول على ترخيصك المؤقت.
### هل هناك موارد توثيقية مفصلة متاحة؟
 قطعاً! تفحص ال[الوثائق الرسمية](https://reference.groupdocs.com/viewer/net/) للحصول على معلومات وأدلة متعمقة.