---
title: عرض الأرشيفات على صفحات HTML مفردة أو متعددة
linktitle: عرض الأرشيفات على صفحات HTML مفردة أو متعددة
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية عرض الأرشيفات على صفحات HTML باستخدام GroupDocs.Viewer لـ .NET. قم بدمج إمكانيات عرض المستندات بسهولة في تطبيقات .NET الخاصة بك.
weight: 12
url: /ar/net/rendering-archive-files/render-archives-html/
---
## مقدمة
تعد GroupDocs.Viewer for .NET مكتبة قوية لعرض المستندات تسمح للمطورين بدمج إمكانيات عرض المستندات بسهولة في تطبيقات .NET الخاصة بهم. سواء كنت بحاجة إلى عرض الأرشيفات على صفحات HTML فردية أو متعددة، فسيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1.  GroupDocs.Viewer لـ .NET: تأكد من تثبيت المكتبة في مشروعك. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: تمتع بإعداد بيئة تطوير عمل لتطوير .NET.
3. دليل المستندات: قم بإعداد دليل حيث يتم تخزين المستندات الخاصة بك.
4. الفهم الأساسي لـ C#: تعرف على أساسيات لغة البرمجة C#.

## استيراد مساحات الأسماء
في كود C# الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

اتبع هذه الخطوات لعرض الأرشيفات على صفحات HTML فردية أو متعددة باستخدام GroupDocs.Viewer لـ .NET:
## الخطوة 1: تعيين دليل الإخراج
حدد الدليل الذي تريد حفظ صفحات HTML المعروضة فيه:
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار الملف
حدد تنسيق مسار الملف لصفحات HTML. لعرض صفحة واحدة:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
للعرض متعدد الصفحات:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## الخطوة 3: التقديم إلى صفحة HTML واحدة
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## الخطوة 4: التقديم إلى صفحات HTML متعددة
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // تعيين العناصر لكل صفحة
    viewer.View(options);
}
```
## الخطوة 5: التحقق من الإخراج
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
يعد عرض الأرشيفات إلى صفحات HTML باستخدام GroupDocs.Viewer لـ .NET عملية مباشرة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج إمكانات عرض المستندات بسلاسة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني عرض تنسيقات مستندات أخرى إلى جانب الأرشيف؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات بما في ذلك PDF وDOCX وXLSX وPPTX والمزيد.
### هل GroupDocs.Viewer مناسب لكل من تطبيقات سطح المكتب والويب؟
بالتأكيد، يمكن استخدام GroupDocs.Viewer في كل من تطبيقات سطح المكتب والويب بسلاسة.
### هل يقدم GroupDocs.Viewer خيارات تخصيص لواجهة العارض؟
نعم، يمكنك تخصيص واجهة العارض وفقًا لمتطلباتك.
### هل يمكنني عرض المستندات بشكل غير متزامن مع GroupDocs.Viewer؟
نعم، يوفر GroupDocs.Viewer إمكانات عرض غير متزامنة لتحسين الأداء.
### هل يدعم GroupDocs.Viewer التعليقات التوضيحية للمستندات؟
نعم، يسمح GroupDocs.Viewer للمستخدمين بعرض التعليقات التوضيحية للمستندات وإدارتها بكفاءة.