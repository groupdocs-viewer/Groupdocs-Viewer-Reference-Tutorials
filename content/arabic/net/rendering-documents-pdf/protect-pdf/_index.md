---
title: حماية ملف PDF المقدم بكلمة مرور
linktitle: حماية ملف PDF المقدم بكلمة مرور
second_title: GroupDocs.Viewer .NET API
description: قم بحماية ملفات PDF المقدمة بكلمات مرور بسهولة باستخدام Groupdocs.Viewer لـ .NET. حافظ على مستنداتك آمنة وسرية.
type: docs
weight: 12
url: /ar/net/rendering-documents-pdf/protect-pdf/
---
## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية استخدام Groupdocs.Viewer لـ .NET لحماية ملف PDF المعروض بكلمة مرور. من خلال إضافة إجراءات أمنية، يمكنك التحكم في الوصول إلى مستندات PDF الخاصة بك، مما يضمن السرية والنزاهة.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1.  Groupdocs.Viewer لمكتبة .NET: قم بتنزيل المكتبة وتثبيتها من[موقع إلكتروني](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: تأكد من أن لديك بيئة تطوير عمل معدة لتطوير .NET.

## استيراد مساحات الأسماء
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## الخطوة 1: تحديد دليل الإخراج ومسار الملف
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## الخطوة 2: تهيئة كائن العارض وتعيين خيارات الأمان
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## الخطوة 3: ضبط خيارات عرض PDF
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## الخطوة 4: تقديم المستند مع خيارات الأمان
```csharp
    viewer.View(options);
}
```
## الخطوة 5: التحقق من المستند المقدم
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
باتباع هذه الخطوات، يمكنك حماية ملف PDF المعروض بكلمة مرور باستخدام Groupdocs.Viewer لـ .NET. وهذا يضمن أن تظل مستنداتك آمنة ولا يمكن الوصول إليها إلا للمستخدمين المصرح لهم.

## خاتمة
يعد تأمين مستندات PDF أمرًا ضروريًا للحفاظ على السرية والنزاهة. باستخدام Groupdocs.Viewer for .NET، يمكنك بسهولة حماية ملفات PDF المقدمة بكلمات مرور، والتحكم في الوصول إلى المعلومات الحساسة.

## الأسئلة الشائعة
### هل يمكنني حماية ملفات PDF بمستويات مختلفة من الأذونات؟
نعم، يمكنك تحديد أذونات مختلفة للعرض والطباعة والنسخ والمزيد مع حماية ملفات PDF بكلمات مرور.
### هل Groupdocs.Viewer متوافق مع تنسيقات الملفات المختلفة؟
قطعاً! يدعم Groupdocs.Viewer عرض مجموعة واسعة من تنسيقات الملفات، بما في ذلك DOCX وXLSX وPPTX وPDF والمزيد.
### هل يمكنني دمج Groupdocs.Viewer في تطبيق .NET الموجود لدي؟
بالتأكيد! يوفر Groupdocs.Viewer واجهات برمجة التطبيقات للتكامل السلس في تطبيقات .NET، مما يوفر إمكانات قوية لعرض المستندات.
### هل يقدم Groupdocs.Viewer الدعم لخدمات التخزين السحابية؟
نعم، يدعم Groupdocs.Viewer التكامل مع خدمات التخزين السحابية الشائعة مثل Dropbox وGoogle Drive وAmazon S3، مما يسمح لك بعرض المستندات المخزنة في السحابة.
### هل هناك إصدار تجريبي متاح لـ Groupdocs.Viewer؟
 نعم، يمكنك البدء باستخدام Groupdocs.Viewer عن طريق الوصول إلى الإصدار التجريبي المجاني من[موقع إلكتروني](https://releases.groupdocs.com/).