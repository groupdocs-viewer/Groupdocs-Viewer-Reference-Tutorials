---
title: حدد نوع الملف عند تحميل المستندات
linktitle: حدد نوع الملف عند تحميل المستندات
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية تحديد نوع الملف عند تحميل المستندات باستخدام GroupDocs.Viewer لـ .NET. عرض التنسيقات المختلفة بدقة في تطبيقات .NET الخاصة بك.
weight: 10
url: /ar/net/advanced-loading/specify-file-type/
---

# حدد نوع الملف عند تحميل المستندات

## مقدمة
GroupDocs.Viewer for .NET عبارة عن واجهة برمجة تطبيقات متعددة الاستخدامات لعرض المستندات تدعم نطاقًا واسعًا من تنسيقات الملفات، بما في ذلك DOCX وPDF وPPTX والمزيد. من خلال تحديد نوع الملف عند تحميل المستندات، يمكنك ضمان عرض دقيق وتجربة عرض سلسة للمستخدمين.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بـ C# و.NET Framework.
- تم تثبيت Visual Studio على نظامك.
- تم تثبيت GroupDocs.Viewer لـ .NET في مشروعك. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).
##
## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى كود C# الخاص بك. توفر مساحات الأسماء هذه الوصول إلى الفئات والأساليب المطلوبة لعرض المستند.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: إعداد دليل الإخراج
حدد الدليل الذي تريد حفظ صفحات المستند المعروضة فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
حدد التنسيق لتسمية ملفات HTML الناتجة لكل صفحة من المستند.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: تحديد خيارات التحميل
 إنشاء مثيل لـ`LoadOptions` فئة وتعيين نوع الملف المطلوب.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## الخطوة 4: تحميل المستند وتقديمه
 استخدم ال`Viewer` فئة لتحميل المستند وتقديمه إلى تنسيق HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## الخطوة 5: عرض رسالة النجاح
أبلغ المستخدم بأن المستند قد تم تقديمه بنجاح وحدد موقع ملفات الإخراج.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام GroupDocs.Viewer لـ .NET لتحديد نوع الملف عند تحميل المستندات. باتباع هذه الخطوات البسيطة، يمكنك ضمان العرض الدقيق لتنسيقات المستندات المختلفة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني عرض مستندات بخلاف DOCX باستخدام GroupDocs.Viewer لـ .NET؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات الملفات، بما في ذلك PDF وPPTX وXLSX والمزيد.
### هل يتوافق GroupDocs.Viewer لـ .NET مع .NET Core؟
نعم، إن GroupDocs.Viewer for .NET متوافق مع كل من .NET Framework و.NET Core.
### هل يمكنني تخصيص ملفات HTML الناتجة عن GroupDocs.Viewer؟
نعم، يمكنك تخصيص مخرجات HTML باستخدام الخيارات المتنوعة التي توفرها واجهة برمجة التطبيقات (API).
### هل يتطلب GroupDocs.Viewer لـ .NET أي تبعيات خارجية؟
لا، GroupDocs.Viewer for .NET عبارة عن مكتبة مستقلة ولا تتطلب أي تبعيات خارجية.
### هل هناك إصدار تجريبي متاح لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.groupdocs.com/viewer/net/).