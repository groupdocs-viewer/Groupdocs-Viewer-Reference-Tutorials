---
"description": "تعرّف على كيفية تحديد نوع الملف عند تحميل المستندات باستخدام GroupDocs.Viewer لـ .NET. قدّم تنسيقات مختلفة بدقة في تطبيقات .NET."
"linktitle": "تحديد نوع الملف عند تحميل المستندات"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تحديد نوع الملف عند تحميل المستندات"
"url": "/ar/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# تحديد نوع الملف عند تحميل المستندات

## مقدمة
GroupDocs.Viewer لـ .NET هي واجهة برمجة تطبيقات متعددة الاستخدامات لعرض المستندات، تدعم مجموعة واسعة من تنسيقات الملفات، بما في ذلك DOCX وPDF وPPTX وغيرها. بتحديد نوع الملف عند تحميل المستندات، يمكنك ضمان دقة العرض وتجربة مشاهدة سلسة لمستخدميك.

![تحديد نوع الملف عند تحميل المستندات في GroupDocs.Viewer لـ .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة C# وإطار عمل .NET.
- تم تثبيت Visual Studio على نظامك.
- GroupDocs.Viewer لـ .NET مُثبّت في مشروعك. يمكنك تنزيله من [هنا](https://releases.groupdocs.com/viewer/net/).
##
## استيراد مساحات الأسماء
أولاً، عليك استيراد مساحات الأسماء اللازمة إلى شيفرة C#. تتيح هذه المساحات الوصول إلى الفئات والأساليب اللازمة لعرض المستندات.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: إعداد دليل الإخراج
قم بتحديد الدليل الذي تريد حفظ صفحات المستند المُقدمة فيه.
```csharp
string outputDirectory = "Your Document Directory";
```
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
قم بتحديد تنسيق تسمية ملفات HTML الناتجة لكل صفحة من المستند.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## الخطوة 3: تحديد خيارات التحميل
إنشاء مثيل لـ `LoadOptions` الفئة وتعيين نوع الملف المطلوب.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## الخطوة 4: تحميل المستند وعرضه
استخدم `Viewer` فئة لتحميل المستند وتقديمه بتنسيق HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## الخطوة 5: عرض رسالة النجاح
أبلغ المستخدم بأن المستند تم عرضه بنجاح وحدد موقع ملفات الإخراج.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام GroupDocs.Viewer لـ .NET لتحديد نوع الملف عند تحميل المستندات. باتباع هذه الخطوات البسيطة، يمكنك ضمان دقة عرض تنسيقات المستندات المختلفة في تطبيقات .NET.
## الأسئلة الشائعة
### هل يمكنني عرض مستندات أخرى غير DOCX باستخدام GroupDocs.Viewer لـ .NET؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات الملفات، بما في ذلك PDF وPPTX وXLSX والمزيد.
### هل GroupDocs.Viewer لـ .NET متوافق مع .NET Core؟
نعم، GroupDocs.Viewer لـ .NET متوافق مع كل من .NET Framework و.NET Core.
### هل يمكنني تخصيص ملفات HTML الناتجة عن GroupDocs.Viewer؟
نعم، يمكنك تخصيص مخرجات HTML باستخدام الخيارات المختلفة التي توفرها واجهة برمجة التطبيقات.
### هل يتطلب GroupDocs.Viewer لـ .NET أي تبعيات خارجية؟
لا، GroupDocs.Viewer لـ .NET هي مكتبة مستقلة ولا تتطلب أي تبعيات خارجية.
### هل هناك نسخة تجريبية متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.groupdocs.com/viewer/net/).