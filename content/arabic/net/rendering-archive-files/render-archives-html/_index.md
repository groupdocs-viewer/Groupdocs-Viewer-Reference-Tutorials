---
"description": "تعرّف على كيفية عرض الأرشيفات على صفحات HTML باستخدام GroupDocs.Viewer لـ .NET. تكامل بسهولة مع إمكانيات عرض المستندات في تطبيقات .NET."
"linktitle": "تحويل الأرشيفات إلى صفحات HTML مفردة أو متعددة"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تحويل الأرشيفات إلى صفحات HTML مفردة أو متعددة"
"url": "/ar/net/rendering-archive-files/render-archives-html/"
"weight": 12
---

# تحويل الأرشيفات إلى صفحات HTML مفردة أو متعددة

## مقدمة
GroupDocs.Viewer لـ .NET هي مكتبة عرض مستندات فعّالة تُمكّن المطورين من دمج إمكانيات عرض المستندات بسهولة في تطبيقات .NET الخاصة بهم. سواءً كنتَ بحاجة إلى عرض الأرشيفات على صفحة HTML واحدة أو صفحات HTML متعددة، سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: تأكد من تثبيت المكتبة في مشروعك. يمكنك تنزيلها من [هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير عمل لتطوير .NET.
3. دليل المستندات: قم بإعداد دليل لتخزين مستنداتك.
4. الفهم الأساسي للغة C#: تعرف على أساسيات لغة البرمجة C#.

## استيراد مساحات الأسماء
في كود C# الخاص بك، تأكد من استيراد المساحات الأساسية اللازمة:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

اتبع الخطوات التالية لعرض الأرشيفات على صفحات HTML مفردة أو متعددة باستخدام GroupDocs.Viewer لـ .NET:
## الخطوة 1: تعيين دليل الإخراج
قم بتحديد الدليل الذي تريد حفظ صفحات HTML المُقدمة فيه:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار الملف
حدد تنسيق مسار الملف لصفحات HTML. لعرض صفحة واحدة:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
للرسم متعدد الصفحات:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## الخطوة 3: عرض إلى صفحة HTML واحدة
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## الخطوة 4: عرض على صفحات HTML متعددة
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // تعيين العناصر لكل صفحة
    viewer.View(options);
}
```
## الخطوة 5: التحقق من الناتج
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
تحويل الأرشيفات إلى صفحات HTML باستخدام GroupDocs.Viewer لـ .NET عملية سهلة وبسيطة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج إمكانيات عرض المستندات بسلاسة في تطبيقات .NET.
## الأسئلة الشائعة
### هل يمكنني تقديم تنسيقات مستندات أخرى بالإضافة إلى الأرشيفات؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات بما في ذلك PDF وDOCX وXLSX وPPTX والمزيد.
### هل GroupDocs.Viewer مناسب لكل من تطبيقات سطح المكتب والويب؟
بالتأكيد، يمكن استخدام GroupDocs.Viewer في تطبيقات سطح المكتب والويب بسلاسة.
### هل يوفر GroupDocs.Viewer خيارات تخصيص لواجهة العارض؟
نعم، يمكنك تخصيص واجهة العارض وفقًا لمتطلباتك.
### هل يمكنني عرض المستندات بشكل غير متزامن باستخدام GroupDocs.Viewer؟
نعم، يوفر GroupDocs.Viewer إمكانيات عرض غير متزامنة لتحسين الأداء.
### هل يدعم GroupDocs.Viewer التعليقات التوضيحية للمستندات؟
نعم، يسمح GroupDocs.Viewer للمستخدمين بعرض تعليقات المستندات وإدارتها بكفاءة.