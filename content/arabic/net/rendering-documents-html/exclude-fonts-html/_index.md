---
title: استبعاد الخطوط من HTML المقدم
linktitle: استبعاد الخطوط من HTML المقدم
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية استبعاد الخطوط من HTML المعروض باستخدام GroupDocs.Viewer لـ .NET. اتبع هذا الدليل المفصّل خطوة بخطوة لعرض المستندات بسلاسة.
type: docs
weight: 10
url: /ar/net/rendering-documents-html/exclude-fonts-html/
---
## مقدمة
تعد GroupDocs.Viewer for .NET مكتبة قوية لعرض المستندات تسمح للمطورين بعرض أكثر من 50 تنسيقًا للمستندات في تطبيقات .NET الخاصة بهم دون الحاجة إلى تبعيات خارجية. في هذا البرنامج التعليمي، سنركز على ميزة معينة في GroupDocs.Viewer: وهي استبعاد الخطوط من مخرجات HTML المعروضة. 
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1. الفهم الأساسي لتطوير C# و.NET.
2.  تم تثبيت GroupDocs.Viewer لـ .NET. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio أو أي بيئة تطوير متكاملة أخرى لتطوير C#.

## استيراد مساحات الأسماء
في كود C# الخاص بك، تأكد من تضمين مساحات الأسماء الضرورية:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## الخطوة 1: تحديد دليل الإخراج
قم بإعداد الدليل الذي تريد حفظ ملفات HTML المقدمة فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
حدد تنسيق مسارات الملفات للصفحات الفردية للمستند الذي تم عرضه.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: تهيئة كائن العارض
قم بإنشاء كائن العارض باستخدام المستند الذي تريد عرضه.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // الكود الخاص بك يذهب هنا
}
```
## الخطوة 4: قم بتعيين خيارات عرض HTML
حدد خيارات عرض HTML، بما في ذلك تنسيق الموارد المضمنة والخطوط المراد استبعادها.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## الخطوة 5: تقديم الوثيقة
قم بتمرير خيارات عرض HTML إلى كائن العارض لعرض المستند.
```csharp
viewer.View(options);
```
## الخطوة 6: إخراج موقع المستند المعروض
أبلغ المستخدم بالموقع الذي يتم فيه حفظ ملفات HTML المقدمة.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام GroupDocs.Viewer لـ .NET لاستبعاد الخطوط من مخرجات HTML المعروضة. باتباع الخطوات الموضحة أعلاه، يمكنك تخصيص عملية العرض لتلبية متطلباتك المحددة، مما يضمن العرض الأمثل للمستندات في تطبيقاتك.
## الأسئلة الشائعة
### هل يمكنني استبعاد خطوط متعددة من HTML المعروض؟
 نعم، يمكنك إضافة أسماء خطوط متعددة إلى ملف`FontsToExclude` القائمة في خيارات عرض HTML.
### هل يتوافق GroupDocs.Viewer مع جميع أطر عمل .NET؟
نعم، يدعم GroupDocs.Viewer .NET Framework 4.6.1 والإصدارات الأحدث.
### هل يمكنني تقديم المستندات من مواقع التخزين البعيدة؟
نعم، يدعم GroupDocs.Viewer عرض المستندات من وحدة التخزين المحلية بالإضافة إلى مواقع وتدفقات التخزين البعيدة.
### هل يدعم GroupDocs.Viewer التصميم سريع الاستجابة لمخرجات HTML؟
نعم، يمكنك تمكين العرض سريع الاستجابة عن طريق ضبط خيارات عرض HTML وفقًا لذلك.
### هل يتوفر الدعم الفني لـ GroupDocs.Viewer؟
 نعم، يمكنك طلب المساعدة والمشاركة في المناقشات حول[منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).