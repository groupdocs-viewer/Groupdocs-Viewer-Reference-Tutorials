---
"description": "تعرّف على كيفية استبعاد الخطوط من HTML المُعرَّض باستخدام GroupDocs.Viewer لـ .NET. اتبع هذا الدليل خطوة بخطوة لعرض المستندات بسلاسة."
"linktitle": "استبعاد الخطوط من HTML المُقدم"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "استبعاد الخطوط من HTML المُقدم"
"url": "/ar/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
---

# استبعاد الخطوط من HTML المُقدم

## مقدمة
GroupDocs.Viewer لـ .NET هي مكتبة عرض مستندات فعّالة، تُمكّن المطورين من عرض أكثر من 50 تنسيقًا للمستندات في تطبيقات .NET دون الحاجة إلى أي تبعيات خارجية. في هذا البرنامج التعليمي، سنركز على ميزة مُحددة في GroupDocs.Viewer: استبعاد الخطوط من مُخرجات HTML المُعرضة. 
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1. فهم أساسي لتطوير C# و.NET.
2. تم تثبيت GroupDocs.Viewer لـ .NET. يمكنك تنزيله من [هنا](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio أو أي IDE آخر لتطوير C#.

## استيراد مساحات الأسماء
في كود C# الخاص بك، تأكد من تضمين المساحات الأساسية اللازمة:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## الخطوة 1: تحديد دليل الإخراج
قم بإعداد الدليل الذي تريد حفظ ملفات HTML المُقدمة فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
قم بتحديد تنسيق مسارات الملفات الخاصة بالصفحات الفردية للمستند المقدم.
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
## الخطوة 4: تعيين خيارات عرض HTML
قم بتحديد خيارات عرض HTML، بما في ذلك تنسيق الموارد المضمنة والخطوط التي يجب استبعادها.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## الخطوة 5: عرض المستند
قم بتمرير خيارات عرض HTML إلى كائن العارض لعرض المستند.
```csharp
viewer.View(options);
```
## الخطوة 6: إخراج موقع المستند المُقدم
إعلام المستخدم بالموقع الذي يتم حفظ ملفات HTML المقدمة فيه.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام GroupDocs.Viewer لـ .NET لاستبعاد الخطوط من مُخرَجات HTML المُعرَّضة. باتباع الخطوات الموضحة أعلاه، يمكنك تخصيص عملية العرض لتلبية متطلباتك الخاصة، مما يضمن عرضًا مثاليًا للمستندات في تطبيقاتك.
## الأسئلة الشائعة
### هل يمكنني استبعاد خطوط متعددة من HTML المقدم؟
نعم، يمكنك إضافة أسماء خطوط متعددة إلى `FontsToExclude` القائمة في خيارات عرض HTML.
### هل GroupDocs.Viewer متوافق مع كافة أطر عمل .NET؟
نعم، يدعم GroupDocs.Viewer .NET Framework 4.6.1 والإصدارات الأحدث.
### هل يمكنني تقديم المستندات من مواقع التخزين البعيدة؟
نعم، يدعم GroupDocs.Viewer عرض المستندات من التخزين المحلي بالإضافة إلى مواقع التخزين البعيدة والجداول.
### هل يدعم GroupDocs.Viewer التصميم المستجيب لإخراج HTML؟
نعم، يمكنك تمكين العرض المستجيب عن طريق ضبط خيارات عرض HTML وفقًا لذلك.
### هل يتوفر الدعم الفني لـ GroupDocs.Viewer؟
نعم، يمكنك طلب المساعدة والمشاركة في المناقشات على [منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).